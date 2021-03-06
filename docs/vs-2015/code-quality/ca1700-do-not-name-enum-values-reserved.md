---
title: 'CA1700: не наименование значений &#39;перечислений зарезервировано&#39; | Документация Майкрософт'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1700
- DoNotNameEnumValuesReserved
helpviewer_keywords:
- DoNotNameEnumValuesReserved
- CA1700
ms.assetid: 7a7e01c3-ae7d-4c82-a646-91b58864a749
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 9b5ddeb77a255bcfab121746cd8748c6fcb1f113
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2019
ms.locfileid: "72669308"
---
# <a name="ca1700-do-not-name-enum-values-39reserved39"></a>CA1700: не зарезервированные значения &#39;Enum&#39;
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotNameEnumValuesReserved|
|CheckId|CA1700|
|Категория|Microsoft. Naming|
|Критическое изменение|Критическое|

## <a name="cause"></a>Причина
 Имя члена перечисления содержит слово "reserved".

## <a name="rule-description"></a>Описание правила
 В данном правиле предполагается, что член перечисления, имя которого содержит слово "reserved", не используется в настоящее время, а является местозаполнителем, который будет в дальнейшем переименован или удален. Переименование или удаление элемента — это критическое изменение. Не следует рассчитывать, что пользователи должны пропускать член только потому, что его имя содержит "reserved", и не может полагаться на то, что пользователи могут читать или придерживаться документации. Более того, поскольку зарезервированные элементы отображаются в обозревателях объектов и интеллектуальных интегрированных средах разработки, они могут вызвать путаницу с тем, какие элементы на самом деле используются.

 Вместо использования зарезервированного элемента добавьте новый элемент в перечисление в следующей версии. В большинстве случаев Добавление нового элемента не является критическим изменением при условии, что добавление не приводит к изменению значений исходных элементов.

 В ограниченном числе случаев Добавление элемента является критическим изменением, даже если исходные элементы сохраняют исходные значения. В основном новый элемент не может быть возвращен из существующих путей кода без нарушения вызывающих объектов, использующих инструкцию `switch` (`Select` в [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) для возвращаемого значения, охватывающего список всех членов и вызывающего исключение в случае по умолчанию. Дополнительная проблема заключается в том, что клиентский код может не справиться с изменением поведения методов отражения, таких как <xref:System.Enum.IsDefined%2A?displayProperty=fullName>. Соответственно, если новый элемент должен возвращаться из существующих методов или известно, что несовместимость приложения происходит из-за неправильного использования отражения, единственным неразрывным решением будет:

1. Добавьте новое перечисление, которое содержит исходный и новый элементы.

2. Пометьте исходное перечисление атрибутом <xref:System.ObsoleteAttribute?displayProperty=fullName>.

   Выполните ту же процедуру для всех видимых извне типов или членов, которые предоставляют исходное перечисление.

## <a name="how-to-fix-violations"></a>Устранение нарушений
 Чтобы устранить нарушение этого правила, удалите или переименуйте член.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений
 Можно отключить вывод предупреждений из этого правила для элемента, который в настоящее время используется, или для библиотек, которые уже были отгружены.

## <a name="related-rules"></a>Связанные правила
 [CA2217: не следует помечать перечисления атрибутом FlagsAttribute](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

 [CA1712: не добавляйте имя типа перед перечисляемыми значениями](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)

 [CA1028: хранилище перечислений должно иметь тип Int32](../code-quality/ca1028-enum-storage-should-be-int32.md)

 [CA1008: перечисляемые типы должны иметь нулевое значение](../code-quality/ca1008-enums-should-have-zero-value.md)

 [CA1027: следует помечать перечисления атрибутом FlagsAttribute](../code-quality/ca1027-mark-enums-with-flagsattribute.md)
