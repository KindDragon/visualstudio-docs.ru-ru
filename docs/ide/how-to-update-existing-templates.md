---
title: Обновление существующих шаблонов элементов проекта
ms.date: 01/02/2018
ms.topic: conceptual
helpviewer_keywords:
- item templates, updating
- Visual Studio templates, updating
- project templates, updating
- updating templates [Visual Studio]
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.openlocfilehash: 44f99646330d3c8a75bd94310bc0adf9073f9d49
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/01/2020
ms.locfileid: "75591363"
---
# <a name="how-to-update-existing-templates"></a>Практическое руководство. Обновление существующих шаблонов

После создания шаблона и сжатия файлов в *ZIP*-файл может потребоваться изменить шаблон. Это можно сделать путем изменения файлов шаблона вручную или путем экспорта нового шаблона из проекта, основанного на шаблоне.

## <a name="use-the-export-template-wizard"></a>Использование мастера экспорта шаблонов

Visual Studio предоставляет мастер **экспорта шаблонов**, который можно использовать для обновления существующего шаблона.

1. Выберите **Файл** > **Создать** > **Проект** в строке меню.

1. Выберите шаблон, который требуется обновить, и продолжайте процедуру создания проекта.

1. Измените проект в Visual Studio. Например, измените тип выходных данных или добавьте новый файл в проект.

1. В меню **Проект** выберите команду **Экспорт шаблона**.

    Открывается **мастер экспорта шаблонов**.

1. Следуйте указаниям мастера, чтобы экспортировать шаблон в виде *ZIP*-файла.

1. Поместите *ZIP*-файл в следующий каталог: *%USERPROFILE%\Documents\Visual Studio \<версия\>\Templates\ProjectTemplates*, чтобы сделать его доступным для выбора. Вам потребуется выполнить этот шаг, если вы не выбрали параметр **Автоматически импортировать шаблон в Visual Studio** в **мастере экспорта шаблонов**.

1. Удалите старый *ZIP*-файл шаблона.

## <a name="manually-update-an-existing-template"></a>Обновление существующего шаблона вручную

Вы можете обновить существующий шаблон без помощи **мастера экспорта шаблонов**, изменив файлы в сжатом *ZIP*-файле.

### <a name="to-manually-update-an-existing-template"></a>Порядок обновления существующего шаблона вручную

1. Найдите *ZIP*-файл, содержащий шаблон. Шаблоны проектов пользователя находятся в каталоге *%USERPROFILE%\Documents\Visual Studio \<версия\>\Templates\ProjectTemplates*.

1. Извлеките содержимое *ZIP*-файла.

1. Измените или удалите текущие файлы шаблона или добавьте в него новые файлы.

1. Откройте, измените и сохраните *VSTEMPLATE*-файл с кодом XML для обработки обновленного поведения или новых файлов.

    Дополнительные сведения о схеме *VSTEMPLATE* см. в разделе [Справочник по схеме шаблонов Visual Studio (расширяемость)](../extensibility/visual-studio-template-schema-reference.md). Дополнительные сведения о том, что именно можно параметризовать в исходных файлах, см. в разделе [Параметры шаблона](../ide/template-parameters.md).

1. Выберите файлы в шаблоне, а в контекстном меню выберите пункты **Отправить** > **Сжатая ZIP-папка**.

    Выбранные файлы будут сжаты в *ZIP*-файл.

1. Поместите новый *ZIP*-файл в тот же каталог, где находится старый *ZIP*-файл.

1. Удалите извлеченные файлы шаблона и *ZIP*-файл старого шаблона.

## <a name="see-also"></a>См. также

- [Настройка шаблонов](../ide/customizing-project-and-item-templates.md)
- [Создание шаблонов проектов и элементов](../ide/creating-project-and-item-templates.md)
- [Справочник по схеме шаблонов Visual Studio](../extensibility/visual-studio-template-schema-reference.md)
- [Параметры шаблона](../ide/template-parameters.md)
