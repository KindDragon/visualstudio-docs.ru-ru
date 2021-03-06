---
title: 'CA2202: не удалять объекты несколько раз | Документация Майкрософт'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2202
- Do not dispose objects multiple times
- DoNotDisposeObjectsMultipleTimes
helpviewer_keywords:
- CA2202
ms.assetid: fa85349a-cf1e-42c8-a86b-eacae1f8bd96
caps.latest.revision: 22
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: e0be715d8aea84fac53ea2a796e71850b961730c
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2019
ms.locfileid: "72667404"
---
# <a name="ca2202-do-not-dispose-objects-multiple-times"></a>CA2202: не удаляйте объекты несколько раз
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|донотдиспосеобжектсмултиплетимес|
|CheckId|CA2202|
|Категория|Microsoft. Usage|
|Критическое изменение|Не критическое|

## <a name="cause"></a>Причина
 Реализация метода содержит пути кода, которые могут вызвать <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> или эквивалент Dispose, например метод Close () для некоторых типов, для одного и того же объекта.

## <a name="rule-description"></a>Описание правила
 Правильно реализованный метод <xref:System.IDisposable.Dispose%2A> можно вызывать несколько раз без возникновения исключения. Однако это не гарантируется, и во избежание создания <xref:System.ObjectDisposedException?displayProperty=fullName> не следует вызывать <xref:System.IDisposable.Dispose%2A> более одного раза для объекта.

## <a name="related-rules"></a>Связанные правила
 [CA2000: удалите объекты до того, как будет потеряна область действия](../code-quality/ca2000-dispose-objects-before-losing-scope.md)

## <a name="how-to-fix-violations"></a>Устранение нарушений
 Чтобы устранить нарушение этого правила, измените реализацию так, чтобы независимо от пути кода <xref:System.IDisposable.Dispose%2A> вызывается только один раз для объекта.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений
 Для этого правила отключать вывод предупреждений не следует. Даже если <xref:System.IDisposable.Dispose%2A> для объекта известно, что они безопасно вызываемы несколько раз, реализация может измениться в будущем.

## <a name="example"></a>Пример
 Вложенные инструкции `using` (`Using` в Visual Basic) могут привести к нарушениям предупреждения CA2202. Если ресурс IDisposable вложенной внутренней `using` содержит ресурс внешней инструкции `using`, метод `Dispose` вложенного ресурса освобождает автономный ресурс. При возникновении такой ситуации метод `Dispose` внешней инструкции `using` пытается освободить свой ресурс во второй раз.

 В следующем примере объект <xref:System.IO.Stream>, созданный во внешнем операторе using, освобождается в конце внутреннего оператора using в методе Dispose объекта <xref:System.IO.StreamWriter>, который содержит объект `stream`. В конце внешней инструкции `using` объект `stream` освобождается второй раз. Второй выпуск является нарушением CA2202.

```
using (Stream stream = new FileStream("file.txt", FileMode.OpenOrCreate))
{
    using (StreamWriter writer = new StreamWriter(stream))
    {
        // Use the writer object...
    }
}
```

## <a name="example"></a>Пример
 Чтобы устранить эту проблему, используйте блок `try` / `finally`, а не внешний оператор `using`. В блоке `finally` убедитесь, что ресурс `stream` не имеет значение null.

```
Stream stream = null;
try
{
    stream = new FileStream("file.txt", FileMode.OpenOrCreate);
    using (StreamWriter writer = new StreamWriter(stream))
    {
        stream = null;
        // Use the writer object...
    }
}
finally
{
    if(stream != null)
        stream.Dispose();
}
```

## <a name="see-also"></a>См. также раздел
 [шаблон удаления](https://msdn.microsoft.com/library/31a6c13b-d6a2-492b-9a9f-e5238c983bcb) <xref:System.IDisposable?displayProperty=fullName>
