---
title: предупреждения удобства обслуживания
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.maintainabilityrules
helpviewer_keywords:
- warnings, maintainability
- managed code analysis warnings, maintainability warnings
- maintainability warnings
ms.assetid: 537e70ca-a88c-49df-bfc7-0ee63bbe4f16
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5dad282bfc1c539216b55e41d77d7743808311d6
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/01/2020
ms.locfileid: "75587372"
---
# <a name="maintainability-warnings"></a>Предупреждения, связанные с удобством обслуживания

Предупреждения об обслуживании поддерживают обслуживание библиотек и приложений.

## <a name="in-this-section"></a>В данном разделе

| Правило | Описание |
|-----------|-----------------------------------|
| [CA1500: имена переменных не должны совпадать с именами полей](../code-quality/ca1500.md) | Метод экземпляра объявляет параметр или локальную переменную, имя которой соответствует полю экземпляра объявляющего типа, что приводит к ошибкам. |
| [CA1501: избегайте излишнего наследования](../code-quality/ca1501.md) | Тип расположен глубже четырех уровней в иерархии наследования. Глубокие иерархии вложенных типов трудно отслеживать, понимать и поддерживать. |
| [CA1502: избегайте чрезмерной сложности](../code-quality/ca1502.md) | Это правило измеряет число линейно независимых путей в методе, которое определяется числом и сложностью условных ветвей. |
| [CA1504: проверьте имена полей, которые могут ввести в заблуждение](../code-quality/ca1504.md) | Имя поля экземпляра начинается с "s_", либо имя статического поля (общий в [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) начинается с "m_". |
| [CA1505: избегайте кода, неудобного для поддержки](../code-quality/ca1505.md) | Тип или метод имеет низкий индекс обслуживаемости. Низкий индекс удобства поддержки означает, что тип или метод, вероятно, трудно поддерживать, поэтому их следует переработать. |
| [CA1506: избегайте чрезмерного соединения классов](../code-quality/ca1506.md) | Данное правило измеряет взаимозависимость классов путем подсчета количества уникальных ссылок на типы, содержащихся в типе или методе. |
| [CA1507: используйте NameOf вместо строки](../code-quality/ca1507.md) | Строковый литерал используется в качестве аргумента, где можно использовать `nameof` выражение. |

## <a name="see-also"></a>См. также:

- [Измерение сложности и удобства поддержки управляемого кода](../code-quality/code-metrics-values.md)
