---
title: Свойства геометрических фигур
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.dsltools.dsldesigner.geometryshape
helpviewer_keywords:
- Domain-Specific Language, geometry shape
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c00fdf25b29c8a122347cf5261dfcbcb07d9415d
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72747458"
---
# <a name="properties-of-geometry-shapes"></a>Свойства геометрических фигур
Геометрические фигуры можно использовать для указания способа отображения экземпляров доменных классов на предметно-ориентированном языке. Дополнительные сведения см. [в разделе Определение доменного языка](../modeling/how-to-define-a-domain-specific-language.md). Дополнительные сведения об использовании этих свойств см. [в разделе Настройка и расширение предметно-](../modeling/customizing-and-extending-a-domain-specific-language.md)ориентированного языка.

 Геометрические фигуры имеют свойства, перечисленные в следующей таблице.

|свойство;|Описание|Значение по умолчанию|
|-|-|-|
|Цвет заливки|Цвет заливки этой фигуры.|Белый|
|Режим градиента заливки|Режим градиента заливки этой фигуры (горизонтальный, вертикальный, прямой диагональный, обратный по диагонали или нет).|Горизонтально|
|Объект|Геометрия этой фигуры (прямоугольник, Скругленный прямоугольник, эллипс или окружность).|Прямоугольник|
|Имеет точки соединения по умолчанию|Если `True`, фигура будет использовать верхнюю, нижнюю, левую и правую точки соединения в созданном конструкторе.|False|
|Цвет контура|Цвет контура этой фигуры.|Черный|
|Стиль штриха в контуре|Стиль штриха контура этой фигуры (сплошная, Штрихпунктирная, точка, Дашдот, Дашдотдот или пользовательская).|Сплошная|
|Толщина контура|Толщина контура этой фигуры.|0,03125|
|Цвет текста|Цвет, используемый для декораторов текста, связанных с этой фигурой.|Черный|
|Модификатор доступа|Модификатор доступа класса (открытый или внутренний).|Public|
|Настраиваемые атрибуты|Используется для добавления атрибутов в класс исходного кода, создаваемого для этой фигуры.|\<none>|
|Создает двойное производное|Если `True`, будет сформирован как базовый класс, так и разделяемый класс (для поддержки настройки с помощью переопределений). Дополнительные сведения см. [в разделе Переопределение и расширение созданных классов](../modeling/overriding-and-extending-the-generated-classes.md).|False|
|Имеет настраиваемый конструктор|Если `True`, в исходном коде будет предоставлен пользовательский конструктор. Дополнительные сведения см. [в разделе Переопределение и расширение созданных классов](../modeling/overriding-and-extending-the-generated-classes.md).|False|
|Модификатор наследования|Описывает тип наследования класса исходного кода, созданного из фигуры (`none`, `abstract` или `sealed`).|Нет|
|Базовая геометрическая фигура|Базовый класс этой фигуры.|(нет)|
|Название|Имя этой фигуры.|Текущее имя|
|Пространство имен|Пространство имен, связанное с этой фигурой.|Текущее пространство имен|
|Тип подсказки|Как определена подсказка (фиксированная, переменная или нет). Если параметр является фиксированным, то в качестве подсказки используется значение свойства `Fixed Tooltip Text`. Если переменная, то подсказка определяется в пользовательском коде.|Отсутствуют|
|Примечания|Неформальные примечания, связанные с этим элементом.|\<none>|
|Начальная высота|Начальная высота этой фигуры в дюймах.|1|
|Начальная ширина|Начальная ширина этой фигуры в дюймах.|1,5|
|Предоставленный цвет заливки как свойство<br /><br /> Предоставленный режим градиента заливки<br /><br /> Раскрытие цвета контура как свойства<br /><br /> Раскрытие стиля штриха в качестве свойства<br /><br /> Доступная толщина контура в качестве свойства<br /><br /> Отображение цвета текста|Если `True`, пользователь может задать указанное свойство фигуры. Чтобы установить это, щелкните правой кнопкой мыши определение фигуры и выберите пункт **добавить предоставленный**.|False|
|Описание|Описание, используемое для документирования созданного конструктора.|\<none>|
|Отображаемое имя|Имя, которое будет отображаться в созданном конструкторе для этой фигуры.|\<none>|
|Исправлен текст подсказки|Текст, используемый для фиксированной подсказки.|\<none>|
|Ключевое слово Help|Ключевое слово, используемое для индексации справки F1 для этой фигуры.|\<none>|

## <a name="see-also"></a>См. также

- [Глоссарий средств предметно-ориентированных языков](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)