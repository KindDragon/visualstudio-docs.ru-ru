---
title: Приступая к программированию надстроек VSTO
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VST.ProjectItem.Outlook
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application-level add-ins [Office development in Visual Studio], getting started
- add-ins [Office development in Visual Studio], getting started
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 39cf3e8d59a2ced26f878da979fa87fc663b5bab
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2019
ms.locfileid: "71253592"
---
# <a name="get-started-programming-vsto-add-ins"></a>Приступая к программированию надстроек VSTO
  Надстройки VSTO можно использовать для автоматизации приложений Microsoft Office, расширения функциональных возможностей приложения и настройки пользовательского интерфейса приложения. Сведения о сравнении надстроек VSTO с другими типами решений Office, которые можно создать с помощью Visual Studio, см. в статье [Разработка решений Office &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md).

 [!INCLUDE[appliesto_allapp](../vsto/includes/appliesto-allapp-md.md)]

## <a name="create-vsto-add-in-projects"></a>Создание проектов надстроек VSTO
 Создание проектов надстроек VSTO с помощью одного из шаблонов проектов надстроек VSTO в диалоговом окне " **Создание проекта** ". Эти шаблоны включают в себя необходимые ссылки на сборки и файлы проекта. Visual Studio предоставляет шаблоны проектов надстроек VSTO для большинства приложений Office.

 Дополнительные сведения о создании проекта надстройки VSTO см. в разделе [как Создание проектов Office в Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md). Дополнительные сведения о шаблонах проектов см. в разделе [Общие сведения о шаблонах проектов Office](../vsto/office-project-templates-overview.md).

## <a name="develop-vsto-add-in-projects"></a>Разработка проектов надстроек VSTO
 При создании проекта надстройки VSTO Visual Studio автоматически создает файл кода *ThisAddIn. vb* (in [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)]) или *ThisAddIn.CS* (in C#). Этот файл содержит `ThisAddIn` класс, предоставляющий основу для надстройки VSTO. Члены этого класса можно использовать для выполнения кода при загрузке или выгрузке надстройки VSTO, при доступе к объектной модели ведущего приложения, а также при расширении функциональных возможностей приложения. Дополнительные сведения см. в разделе [программирование VSTO Add-ins](../vsto/programming-vsto-add-ins.md).

## <a name="automate-applications-by-using-the-object-models"></a>Автоматизация приложений с помощью объектных моделей
 Объектные модели приложений Microsoft Office предоставляют множество типов, которые можно использовать в надстройке VSTO. Эти типы можно использовать для автоматизации приложения. Например, можно программным образом создавать и отправлять сообщение электронной почты в Outlook или можно открыть документ и добавить контент в Word. Дополнительные сведения о том, как получить доступ к объектной модели ведущего приложения в коде, см. в разделе [программирование VSTO-надстроек](../vsto/programming-vsto-add-ins.md).

 Дополнительные сведения об объектных моделях конкретных приложений Microsoft Office см. в следующих статьях:

- [Общие сведения об объектной модели Excel](../vsto/excel-object-model-overview.md)

- [Общие сведения об объектной модели Word](../vsto/word-object-model-overview.md)

- [Общие сведения об объектной модели Outlook](../vsto/outlook-object-model-overview.md)

- [Решения InfoPath](../vsto/infopath-solutions.md)

- [Решения PowerPoint](../vsto/powerpoint-solutions.md)

- [Решения проекта](../vsto/project-solutions.md)

- [Общие сведения об объектной модели Visio](../vsto/visio-object-model-overview.md)

## <a name="customize-the-user-interface-of-applications"></a>Настройка пользовательского интерфейса приложений
 Существует несколько различных способов настройки пользовательского интерфейса ведущего приложения с помощью надстройки VSTO.

- Для Excel и Word в документы можно добавлять управляемые элементы управления. Дополнительные сведения см. [в разделе Расширение документов Word и книг Excel в надстройках VSTO во время выполнения](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).

- Можно настроить ленту, если ее поддерживает приложение. Дополнительные сведения см. в статье [Общие сведения о ленте](../vsto/ribbon-overview.md).

- Можно создать настраиваемую область задач, если ее поддерживает приложение. Дополнительные сведения см. в разделе [настраиваемые области задач](../vsto/custom-task-panes.md).

- Для Outlook можно создать пользовательскую область формы. Дополнительные сведения см. в разделе [Создание областей формы Outlook](../vsto/creating-outlook-form-regions.md).

- Для всех приложений Microsoft Office формы Windows Forms можно отображать в надстройке VSTO.

  Дополнительные сведения о настройке пользовательского интерфейса Microsoft Office приложений см. в разделе [Настройка пользовательского интерфейса Office](../vsto/office-ui-customization.md).

## <a name="next-steps"></a>Следующие шаги
 Дополнительные сведения о создании надстроек VSTO см. в следующих пошаговых руководствах.

- [Пошаговое руководство: Создание первой надстройки VSTO для Excel](../vsto/walkthrough-creating-your-first-vsto-add-in-for-excel.md)

- [Пошаговое руководство: Создание первой надстройки VSTO для Outlook](../vsto/walkthrough-creating-your-first-vsto-add-in-for-outlook.md)

- [Пошаговое руководство: Создание первой надстройки VSTO для PowerPoint](../vsto/walkthrough-creating-your-first-vsto-add-in-for-powerpoint.md)

- [Пошаговое руководство: Создание первой надстройки VSTO для проекта](../vsto/walkthrough-creating-your-first-vsto-add-in-for-project.md)

- [Пошаговое руководство: Создание первой надстройки VSTO для Word](../vsto/walkthrough-creating-your-first-vsto-add-in-for-word.md)

  В этих пошаговых руководствах рассматриваются средства разработки решений на базе Office в Visual Studio и модель программирования для надстроек VSTO.

  Список разделов, в которых описаны некоторые распространенные задачи в проектах Office, см. в разделе [Общие задачи в программировании Office](../vsto/common-tasks-in-office-programming.md).

## <a name="see-also"></a>См. также
- [Практическое руководство. Создание проектов Office в Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)
- [Начало работы &#40;с разработкой Office в Visual Studio&#41;](../vsto/getting-started-office-development-in-visual-studio.md)
- [Написание кода в решениях Office](../vsto/writing-code-in-office-solutions.md)
- [Архитектура надстроек VSTO](../vsto/architecture-of-vsto-add-ins.md)
- [Программирование надстроек VSTO](../vsto/programming-vsto-add-ins.md)
