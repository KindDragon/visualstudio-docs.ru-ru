---
title: Директива параметра T4 | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: 1d590387-1d9d-40a5-a72c-65fae7a8bdf3
caps.latest.revision: 5
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 7c1849cbccc1a903716ba94d02f47a339d6ce426
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2019
ms.locfileid: "72658561"
---
# <a name="t4-parameter-directive"></a>Директива Parameter T4
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

В [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] текстовом шаблоне директива `parameter` объявляет свойства в коде шаблона, которые инициализируются из значений, переданных из внешнего контекста. Эти значения можно задать при написании кода, вызывающего преобразование текста.

## <a name="using-the-parameter-directive"></a>Использование директивы Parameter

```
<#@ parameter type="Full.TypeName" name="ParameterName" #>
```

 Директива `parameter` объявляет свойства в коде шаблона, которые инициализируются из значений, переданных из внешнего контекста. Эти значения можно задать при написании кода, вызывающего преобразование текста. Значения могут передаваться либо в `Session` словаре, либо в <xref:System.Runtime.Remoting.Messaging.CallContext>.

 Можно объявлять параметры любого типа, поддерживающего удаленное взаимодействие. То есть тип должен быть объявлен с <xref:System.SerializableAttribute> или должен быть производным от <xref:System.MarshalByRefObject>. Это позволяет передавать значения параметров в домен приложения, в котором обрабатывается шаблон.

 Например, можно написать текстовый шаблон со следующим содержимым:

```
<#@ template language="C#" #>

<#@ parameter type="System.Int32" name="TimesToRepeat" #>

<# for (int i = 0; i < TimesToRepeat; i++) { #>
Line <#= i #>
<# } #>

```

## <a name="passing-parameter-values-to-a-template"></a>Передача значений параметров в шаблон
 При написании расширения [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], например команды меню или обработчика событий, можно обработать шаблон с помощью службы текстовых шаблонов:

```csharp
// Get a service provider – how you do this depends on the context:
IServiceProvider serviceProvider = dte; // or dslDiagram.Store, for example
// Get the text template service:
ITextTemplating t4 = serviceProvider.GetService(typeof(STextTemplating)) as ITextTemplating;
ITextTemplatingSessionHost host = t4 as ITextTemplatingSessionHost;
// Create a Session in which to pass parameters:
host.Session = host.CreateSession();
// Add parameter values to the Session:
session["TimesToRepeat"] = 5;
// Process a text template:
string result = t4.ProcessTemplate("MyTemplateFile.t4",
  System.IO.File.ReadAllText("MyTemplateFile.t4"));

```

## <a name="passing-values-in-the-call-context"></a>Передача значений в контексте вызова
 Можно также передавать значения в виде логических данных в <xref:System.Runtime.Remoting.Messaging.CallContext>.

 В следующем примере значения передаются с помощью обоих методов:

```csharp
ITextTemplating t4 = this.Store.GetService(typeof(STextTemplating)) as ITextTemplating;
ITextTemplatingSessionHost host = t4 as ITextTemplatingSessionHost;
host.Session = host.CreateSession();
// Pass a value in Session:
host.Session["p1"] = 32;
// Pass another value in CallContext:
System.Runtime.Remoting.Messaging.CallContext.LogicalSetData("p2", "test");

// Process a small template inline:
string result = t4.ProcessTemplate("",
   "<#@parameter type=\"System.Int32\" name=\"p1\"#>"
 + "<#@parameter type=\"System.String\" name=\"p2\"#>"
 + "Test <#=p1#> <#=p2#>");

// Result value is:
//     Test 32 test

```

## <a name="passing-values-to-a-run-time-preprocessed-text-template"></a>Передача значений в шаблон текста времени выполнения (предварительно обработанный)
 Обычно не требуется использовать директиву `<#@parameter#>` с текстовыми шаблонами времени выполнения (предварительно обработанными). Вместо этого можно определить дополнительный конструктор или устанавливаемое свойство для созданного кода, через который вы передаете значения параметров. Дополнительные сведения см. [в разделе Создание текста во время выполнения с помощью текстовых шаблонов T4](../modeling/run-time-text-generation-with-t4-text-templates.md).

 Однако если вы хотите использовать `<#@parameter>` в шаблоне времени выполнения, можно передать ему значения с помощью словаря сеанса. Например, предположим, что вы создали файл как предварительно обработанный шаблон с именем `PreTextTemplate1`. Вы можете вызвать шаблон в программе, используя следующий код.

```csharp
PreTextTemplate1 t = new PreTextTemplate1();
t.Session = new Microsoft.VisualStudio.TextTemplating.TextTemplatingSession();
t.Session["TimesToRepeat"] = 5;
// Add other parameter values to t.Session here.
t.Initialize(); // Must call this to transfer values.
string resultText = t.TransformText();

```

## <a name="obtaining-arguments-from-texttemplateexe"></a>Получение аргументов из Тексттемплате. exe

> [!IMPORTANT]
> Директива `parameter` не извлекает значения, заданные в параметре `–a` служебной программы `TextTransform.exe`. Чтобы получить эти значения, задайте `hostSpecific="true"` в директиве `template` и используйте `this.Host.ResolveParameterValue("","","argName")`.
