---
title: Идентификаторы GUID и идентификаторы команд Visual Studio | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- commands
- id
- command placement
- visual studio command
- guid
ms.assetid: 2ea4bee2-0259-4675-8e65-2023b312b516
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f7670eacc875bf7c5437d9bb92cc1932753093bd
ms.sourcegitcommit: 40bd5b27f247a07c2e2514acb293b23d6ce03c29
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73186623"
---
# <a name="guids-and-ids-of-visual-studio-commands"></a>Идентификаторы GUID и идентификаторы команд Visual Studio
Идентификаторы GUID и ИДЕНТИФИКАТОРы команд, включенных в интегрированную среду разработки (IDE) Visual Studio, определяются в vsct-файлах, которые устанавливаются в составе пакета SDK для Visual Studio. Дополнительные сведения см. в разделе [команды, меню и группы, определяемые интегрированной средой разработки](../../extensibility/internals/ide-defined-commands-menus-and-groups.md).

 Дополнительные сведения о работе с объектами IDE, которые определены в *vsct* -файлах, см. в разделе [Расширение меню и команд](../../extensibility/extending-menus-and-commands.md).

## <a name="find-a-command-definition"></a>Поиск определения команды
 Так как Visual Studio определяет более 1000 команд, нецелесообразно перечислить их здесь. Вместо этого выполните следующие действия, чтобы определить определение команды.

### <a name="to-locate-a-command-definition"></a>Определение местоположения определения команды

1. В Visual Studio откройте следующие файлы в *< пути установки пакета SDK для Visual studio\>\висуалстудиоинтегратион\коммон\инк\\* папку: *шаредкмддеф. vsct*, *шеллкмддеф. vsct*, *всдбгкмдусед. vsct*, *Венусмену. vsct*.

    Большинство команд Visual Studio определены в *шаредкмддеф. vsct* и *шеллкмддеф. vsct*. *Всдбгкмдусед. vsct* определяет команды, относящиеся к отладчику, а *венусмену. vsct* определяет команды, характерные для веб-разработки.

2. Если команда является пунктом меню, обратите внимание на точный текст пункта меню. Если команда является кнопкой на панели инструментов, обратите внимание на текст подсказки, который появляется при его приостановке.

3. Нажмите клавиши **Ctrl**+**F** , чтобы открыть диалоговое окно **найти** .

4. В поле **найти** введите текст, записанный на шаге 2.

5. Убедитесь, что **все открытые документы** отображаются в поле **Искать в** .

6. Нажимайте кнопку **Найти далее** , пока текст не будет выбран в разделе `<Strings>` [элемента кнопки](../../extensibility/button-element.md).

    Элемент `<Button>`, в котором отображается команда, — это определение команды.

   После обнаружения определения команды можно разместить копию команды в другом меню или на панели инструментов, создав [элемент CommandPlacement](../../extensibility/commandplacement-element.md) , который имеет те же `guid` и `id` значения, что и команда. Дополнительные сведения см. в разделе [Создание многократно используемых групп кнопок](../../extensibility/creating-reusable-groups-of-buttons.md).

### <a name="special-cases"></a>Особые случаи
 В следующих случаях текст или текст подсказки в меню может не совпадать с тем, что находится в определении команды.

- Пункты меню, которые содержат подчеркнутый символ, например команду « **Печать** » в меню « **файл** », в которой знак « *P* » подчеркнут.

     Символы, предшествующие символу амперсанда (&) в именах пунктов меню, отображаются подчеркнутыми. Однако *VSCT* -файлы записываются в формате XML, который использует символ амперсанда (&) для обозначения специальных символов и требует, чтобы отображаемый амперсанд был написан как *&amp;amp;* . Поэтому в *vsct* -файле команда **печати** отображается как *&amp;amp; Печать*.

- Команды с динамическим текстом, такие как **сохранение** \<текущего имени файла\>и динамически создаваемые элементы меню, такие как элементы в списке **последние файлы** .

     Нет надежного способа поиска по динамическому тексту. Вместо этого найдите группу, в которой размещена нужная команда, [идентификаторы GUID и идентификаторы меню Visual Studio](../../extensibility/internals/guids-and-ids-of-visual-studio-menus.md) , а также идентификаторы [GUID и идентификаторы панелей инструментов Visual Studio](../../extensibility/internals/guids-and-ids-of-visual-studio-toolbars.md), а также найдите идентификатор этой группы. Если в определении команды нет группы в качестве [родительского элемента](../../extensibility/parent-element.md), выполните поиск по запросу *шаредкмдплаце. vsct* и *Шеллкмдплаце. vsct* (или *всдбгкмдплаце. vsct* для команд отладчика) для элемента `<CommandPlacement>`, который задает родительский элемент кнопки. *Шаредкмдплаце. vsct*, *шеллкмдплаце. vsct*и *всдбгкмдплаце. vsct* находятся в *\<пути установки пакета SDK для Visual Studio\>\висуалстудиоинтегратион\коммон\инк\\* папке.

## <a name="see-also"></a>См. также

- [Файлы таблицы команд Visual Studio (. vsct)](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
- [Справочник по XML-схеме VSCT](../../extensibility/vsct-xml-schema-reference.md)
