---
title: Расширение схем зависимостей
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams, creating extensions
- layer models
author: JoshuaPartlow
ms.author: joshuapa
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 305c562c7600dc6955ce0307db92f4e257fc1c21
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/01/2020
ms.locfileid: "75596649"
---
# <a name="extend-dependency-diagrams"></a>Расширение схем зависимостей

Можно написать код для создания и обновления схем зависимостей, а также для проверки структуры кода программы на соответствие диаграммам зависимостей в Visual Studio. Вы можете добавить команды, которые отображаются в контекстном меню схем, настроить жесты перетаскивания, а также получить доступ к модели слоев из текстовых шаблонов. Вы можете упаковать эти расширения в расширение Visual Studio Integration Extension (VSIX) и предоставить их другим пользователям Visual Studio.

## <a name="requirements"></a>Требования

На компьютере, где планируется разрабатывать расширения слоев, должны быть установлены следующие компоненты:

- Visual Studio

- [Пакет SDK для Visual Studio](../extensibility/visual-studio-sdk.md)

- Пакет SDK моделирования для Visual Studio

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

На компьютере, на котором нужно запустить расширения слоев, должен быть установлен подходящий выпуск Visual Studio. Чтобы узнать, какие выпуски поддерживаются на схемах зависимостей в Visual Studio, см. раздел [Поддержка архитектуры и средств моделирования в выпуске](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

## <a name="see-also"></a>См. также:

- [Схемы зависимостей: справочные материалы](../modeling/layer-diagrams-reference.md)
- [Схемы зависимостей: рекомендации](../modeling/layer-diagrams-guidelines.md)
- [Создание схем зависимостей на основе кода](../modeling/create-layer-diagrams-from-your-code.md)
- [Проверка кода по схемам зависимостей](../modeling/validate-code-with-layer-diagrams.md)
