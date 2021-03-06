---
title: Настроить ссылку на службу - диалоговое окно
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- msvse_wcf.dlg.ConfigureServiceReference
helpviewer_keywords:
- WCF services, Configure Service Reference dialog box
- service references [Visual Studio], configuring behavior
- Configure Service Reference dialog box
ms.assetid: 25e4c36b-2db6-4e71-9010-b7068255d09d
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: f5bae3acb6f687c8c787e2d4121999d1133b0f1f
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/01/2020
ms.locfileid: "75586930"
---
# <a name="configure-service-reference-dialog-box"></a>Настроить ссылку на службу - диалоговое окно

Диалоговое окно **Настройка ссылки на службу** позволяет настроить поведение служб Windows Communication Foundation (WCF).

Чтобы перейти в окно **Настроить ссылку на службу**, щелкните ссылку на службу в **обозревателе решений** правой кнопкой мыши и выберите пункт **Настроить ссылку на службу**. Кроме того, к этому окну можно перейти, нажав кнопку **Дополнительно** в диалоговом окне **Добавление ссылки на службу**.

## <a name="task-list"></a>Список задач

- Чтобы изменить адрес размещения службы WCF, введите новый адрес в поле **Адрес**.

- Чтобы изменить уровень доступа для классов в клиенте WCF, выберите ключевое слово уровня доступа в списке **Уровень доступа для созданных классов**.

- Чтобы вызывать методы службы WCF асинхронно, установите флажок **Создать асинхронные операции**.

- Чтобы создать типы контрактов сообщений в клиенте WCF, установите флажок **Всегда создавать контракты сообщений**.

- Чтобы указать типы коллекций списка или словаря для клиента WCF, выберите нужные типы в списках **Тип коллекции** и **Тип коллекции для словаря**.

- Чтобы отключить совместное использование типов, снимите флажок **Повторно использовать типы в сборках, на которые есть ссылки**. Чтобы включить совместное использование типов для набора сборок, на которые имеются ссылки, установите флажок **Повторно использовать типы в сборках, на которые есть ссылки**, выберите **Повторно использовать типы в сборках, на которые есть ссылки**, а затем выберите нужные сборки в списке **Сборки, на которые заданы ссылки**.

## <a name="uielement-list"></a>Список элементов пользовательского интерфейса

**Адрес**

Обновляет веб-адрес, по которому ссылка на службу ищет службу. Например, во время разработки служба может размещаться на сервере разработки, а затем переноситься на рабочий сервер, что требует изменения адреса.

> [!NOTE]
> Элемент "Адрес" недоступен, если диалоговое окно **Настроить ссылку на службу** открыто из диалогового окна **Добавление ссылки на службу**.

**Уровень доступа для созданных классов**

Определяет уровень доступа кода для классов клиента WCF.

> [!NOTE]
> Для проектов веб-сайтов для этого параметра всегда задано значение `Public`, которое нельзя изменить. Дополнительные сведения см. в разделе [Устранение неполадок ссылок на службы](../data-tools/troubleshooting-service-references.md).

**Создать асинхронные операции**

Определяет, вызываются ли методы службы WCF синхронно (по умолчанию) или асинхронно.

**Создать операции на основе задач**

При написании асинхронного кода этот параметр позволяет использовать преимущества библиотеки параллельных задач (TPL), которая появилась в .NET 4. См. раздел [Библиотека параллельных задач (TPL)](/dotnet/standard/parallel-programming/task-parallel-library-tpl).

**Всегда создавать контракты сообщений**

Определяет, создаются ли типы контрактов сообщений для клиента WCF. Дополнительные сведения о контрактах сообщений см. в разделе [Использование контрактов сообщений](/dotnet/framework/wcf/feature-details/using-message-contracts).

**Тип коллекции**

Указывает тип коллекции списка для клиента WCF. Тип по умолчанию —<xref:System.Array>.

**Тип коллекции для словаря**

Указывает тип коллекции словаря для клиента WCF. Тип по умолчанию —<xref:System.Collections.Generic.Dictionary%602>.

**Повторно использовать типы в сборках, на которые есть ссылки**

Определяет, пытается ли клиент WCF повторно использовать то, что уже существует в упоминаемых сборках, вместо создания новых типов при добавлении или обновлении службы. Этот параметр выбран по умолчанию.

**Повторно использовать типы во всех сборках, на которые имеется ссылка**

Если этот флажок установлен, все типы в **списке сборок, на которые имеются ссылки** , будут использоваться повторно по возможности. По умолчанию этот параметр выбран.

**Повторно использовать типы в указанных сборках, на которые есть ссылки**

Если этот флажок установлен, повторно используются только выбранные типы в **списке сборок, на которые имеются ссылки** .

**Сборки, на которые заданы ссылки**

Содержит список сборок, на которые имеются ссылки, для проекта или веб-сайта. При выборе **повторного использования типов в указанных сборках, на которые имеются ссылки**, можно выбрать или очистить отдельные сборки.

**Добавление веб-ссылки**

Откроется диалоговое окно **Добавление веб-ссылки**.

> [!NOTE]
> Этот параметр следует использовать только для проектов, предназначенных для .NET Framework версии 2,0.
>
> [!NOTE]
> Кнопка **Добавить веб-ссылку** доступна только в том случае, если диалоговое окно **Настройка ссылки на службу** отображается из **диалогового окна Добавление ссылки на службу**.

## <a name="see-also"></a>См. также:

- [Практическое руководство. Добавление ссылки на веб-службу](how-to-add-update-or-remove-a-wcf-data-service-reference.md)
- [Службы Windows Communication Foundation и службы данных WCF](../data-tools/configure-service-reference-dialog-box.md)
