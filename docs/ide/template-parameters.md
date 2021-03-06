---
title: Параметры шаблонов проектов и элементов
ms.date: 01/02/2018
ms.topic: reference
helpviewer_keywords:
- Visual Studio templates, parameters
- template parameters [Visual Studio]
- project templates, parameters
- item templates, parameters
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.openlocfilehash: 582c87eee2586eab12f70e2d27341987e7cb7e2a
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/01/2020
ms.locfileid: "75585890"
---
# <a name="template-parameters"></a>Параметры шаблона

Вы можете заменить значения в шаблоне при создании его экземпляра. Чтобы настроить эту функцию, используйте *параметры шаблона*. Они позволяют заменить такие значения, как имена классов и пространства имен в шаблоне. Эти параметры заменяет мастер шаблонов, запускающийся в фоновом режиме, когда пользователь добавляет новый элемент или проект.

## <a name="declare-and-enable-template-parameters"></a>Объявление и включение параметров шаблона

Параметры шаблона объявляются в формате $*параметр*$. Пример:

- $safeprojectname$

- $guid1$

- $guid5$

### <a name="enable-parameter-substitution-in-templates"></a>Включение подстановки параметров в шаблонах

1. В *VSTEMPLATE*-файле шаблона найдите элемент `ProjectItem`, соответствующий элементу, для которого требуется включить замену параметров.

1. Задайте атрибуту `ReplaceParameters` элемента `ProjectItem` значение `true`.

1. В файле кода для элемента проекта укажите соответствующие параметры. Например, следующий параметр указывает, что безопасное имя проекта используется для пространства имен в файле:

    ```csharp
    namespace $safeprojectname$
    ```

## <a name="reserved-template-parameters"></a>Зарезервированные параметры шаблона

В таблице ниже перечислены параметры зарезервированного шаблона, которые могут использоваться любым шаблоном:

|Параметр|Описание|
|---------------|-----------------|
|clrversion|Текущая версия среды CLR.|
|ext_*|Добавьте префикс `ext_` к любому параметру, чтобы сослаться на переменные родительского шаблона. Например, `ext_safeprojectname`.|
|guid[1–10]|GUID, используемый для замены GUID проекта в файле проекта. Можно указать до 10 уникальных GUID (например, `guid1`).|
|itemname|Имя файла, в котором используется параметр.|
|machinename|Имя текущего компьютера (например, Computer01).|
|projectname|Имя, указанное пользователем при создании проекта.|
|registeredorganization|Значение раздела реестра из HKLM\Software\Microsoft\Windows NT\CurrentVersion\RegisteredOrganization.|
|rootnamespace|Корневое пространство имен для текущего проекта. Этот параметр применяется только к шаблонам элементов.|
|safeitemname|Аналогично параметру `itemname`, но с удалением всех небезопасных символов и пробелов, которые заменяются символом подчеркивания.|
|safeitemrootname|Эквивалентно `safeitemname`.|
|safeprojectname|Имя, указанное пользователем при создании проекта, но с удаленными небезопасными символами и пробелами.|
|time|Текущее время в формате ДД/ММ/ГГГГ 00:00:00.|
|specifiedSolutionName|Имя решения. Если установлен флажок "create solution directory" (Создать каталог решения), `specifiedSolutionName` имеет имя решения. Если флажок "create solution directory" (Создать каталог решения) не установлен, `specifiedSolutionName` пусто.|
|userdomain|Домен текущего пользователя.|
|Имя пользователя|Имя текущего пользователя.|
|webnamespace|Имя текущего веб-сайта. Этот параметр используется в шаблоне веб-формы, чтобы гарантировать уникальные имена классов. Если веб-сайт находится в корневом каталоге веб-сервера, этот параметр шаблона разрешается в корневой каталог веб-сервера.|
|год|Текущий год в формате ГГГГ.|

> [!NOTE]
> Параметры шаблонов зависят от регистра символов.

## <a name="custom-template-parameters"></a>Настраиваемые параметры шаблона

Вы можете указать собственные параметры шаблона и значения в дополнение к зарезервированным параметрам шаблона по умолчанию, которые используются во время замены параметров. Дополнительные сведения см. в разделе [Элемент CustomParameters (шаблоны Visual Studio)](../extensibility/customparameters-element-visual-studio-templates.md).

## <a name="example-use-the-project-name-for-a-file-name"></a>Пример. Использование имени проекта в качестве имени файла

Можно указать переменные имена файлов для элементов проекта с помощью параметра в атрибуте `TargetFileName`.

В следующем примере указывается, что имя исполняемого файла использует имя проекта, заданное `$projectname$`.

```xml
<TemplateContent>
    <ProjectItem
        ReplaceParameters="true"
        TargetFileName="$projectname$.exe">
            File1.exe
    </ProjectItem>
      ...
</TemplateContent>
```

## <a name="example-use-the-safe-project-name-for-the-namespace-name"></a>Пример. Использование безопасного имени проекта в качестве имени пространства имен

Чтобы использовать безопасное имя проекта для пространства имен в файле класса C#, используйте следующий синтаксис:

```csharp
namespace $safeprojectname$
{
    public class Class1
    {
        public Class1()
        { }
    }
}
```

В *VSTEMPLATE*-файл для шаблона проекта включите атрибут `ReplaceParameters="true"` при ссылке на файл:

```xml
<TemplateContent>
    <ProjectItem ReplaceParameters="true">
        Class1.cs
    </ProjectItem>
    ...
</TemplateContent>
```

## <a name="see-also"></a>См. также

- [Практическое руководство. замена параметров в шаблоне](how-to-substitute-parameters-in-a-template.md)
- [Настройка шаблонов](../ide/customizing-project-and-item-templates.md)
- [Практическое руководство. Создание шаблонов проектов](../ide/how-to-create-project-templates.md)
- [Справочник по схемам шаблонов](../extensibility/visual-studio-template-schema-reference.md)
