---
title: Объекты, добавленные в конструктор, используют другое подключение к данным
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 332ed2f3-3377-4d51-8e3b-fdb98231978e
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 9a3a2e00ccdee20fd374c52235ba648f89a0faa1
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/01/2020
ms.locfileid: "75586163"
---
# <a name="the-objects-you-are-adding-to-the-designer-use-a-different-data-connection-than-the-designer"></a>Объекты, добавляемые в конструктор, используют другое соединение с данными, чем конструктор

Подключение к данным, используемое для добавляемого в конструктор объекта, отличается от подключения, используемого конструктором в настоящий момент. Вы хотите заменить подключение, используемое конструктором?

При добавлении элементов в **Реляционный конструктор объектов** (**Реляционный конструктор**объектов) все элементы используют одно общее подключение к данным. (Область конструктора представляет <xref:System.Data.Linq.DataContext>, которая использует одно соединение для всех объектов на поверхности.) Если добавить в конструктор объект, использующий подключение к данным, которое отличается от подключения к данным, используемым в данный момент конструктором, отображается это сообщение. Для устранения этой ошибки можно выбрать поддержку существующего подключения. Если вы делаете это выбор, то выбранный объект не будет добавлен. В противном случае можно выбрать добавление объекта и переустановить соединение <xref:System.Data.Linq.DataContext> на новое соединение.

## <a name="connection-options"></a>Параметры подключения

- Чтобы заменить существующее соединение подключением, используемым выбранным объектом, нажмите кнопку **Да**.

   Выбранный объект добавляется в **Реляционный конструктор**объектов, а параметр *DataContext. Connection* устанавливается в новое соединение.

   > [!NOTE]
   > При нажатии кнопки **Да**все классы сущностей в **конструкторе O/R** сопоставляются с новым соединением.

- Чтобы продолжить использовать существующее подключение и отменить добавление выбранного объекта, нажмите кнопку **нет**.

   Действие отменяется. *DataContext.Connection* остается установленным на существующее подключение.

## <a name="see-also"></a>См. также:

- [Средства LINQ to SQL в Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
