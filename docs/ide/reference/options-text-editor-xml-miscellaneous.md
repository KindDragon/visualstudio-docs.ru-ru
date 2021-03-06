---
title: "\"Параметры\", \"Текстовый редактор\", XML, \"Прочее\""
ms.date: 10/29/2018
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.XML.Miscellaneous
ms.assetid: b6538cbe-badd-4313-a1fb-39e906736bbe
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.openlocfilehash: dd468945b1ab9ac83b219b9c8c396f017065e2be
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/01/2020
ms.locfileid: "75568130"
---
# <a name="options-text-editor-xml-miscellaneous"></a>"Параметры", "Текстовый редактор", XML, "Прочее"

Используйте страницу параметров **Прочее**, чтобы изменить параметры автозаполнения и схемы для редактора XML. Чтобы получить доступ к прочим параметрам XML, выберите **Сервис** > **Параметры** > **Текстовый редактор** > **XML**, а затем выберите **Прочее**.

## <a name="auto-insert"></a>Автоматическая вставка

**Закрывающие теги**

Текстовый редактор добавляет закрывающие теги при создании элементов XML. Если выбран открывающий тег, редактор вставляет соответствующий закрывающий тег, включая соответствующий префикс пространства имен. Это флажок установлен по умолчанию.

**Кавычки атрибутов**

При вводе XML-атрибутов редактор вставляет символы `="` и `"` и устанавливает знак вставки ( **^** ) в кавычках. Это флажок установлен по умолчанию.

**Объявления пространств имен**

Редактор автоматически вставляет декларации пространств имен там, где они необходимы. Это флажок установлен по умолчанию.

**Прочая разметка (комментарии, CDATA)**

Комментарии, CDATA, DOCTYPE, инструкции по обработке и другие элементы разметки завершаются автоматически. Это флажок установлен по умолчанию.

## <a name="network"></a>Сеть

**Автоматически загружать определения DTD и схемы**

Схемы и определения DTD загружаются автоматически с адресов HTTP. В этой возможности используется System.Net в режиме автоматического определения прокси-сервера. Это флажок установлен по умолчанию.

## <a name="outlining"></a>Структуризация

**Переходить в режим структурирования после открытия файлов**

Включает возможность структурирования при открытии файла. Это флажок установлен по умолчанию.

## <a name="caching"></a>Кэширование

**Схемы**

Определяет местоположение кэша схемы. Кнопка **обзора** открывает текущее расположение кэша схем в новом окне. Расположение по умолчанию — *%VsInstallDir%\xml\Schemas*.

## <a name="see-also"></a>См. также

- [Параметры XML — форматирование](options-text-editor-xml-formatting.md)
- [Средства XML в Visual Studio](../../xml-tools/xml-tools-in-visual-studio.md)
