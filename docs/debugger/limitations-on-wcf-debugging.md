---
title: Ограничения на отладку WCF | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging, WCF
- WCF, debugging limitations
ms.assetid: 8e0333c4-1ddc-4abe-8f1c-d19bf6a2a07a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c70195cdc0a6a03395744c63f556ce8c2970aa30
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72731508"
---
# <a name="limitations-on-wcf-debugging"></a>Ограничения на отладку WCF
Существуют три способа, позволяющих начать отладку службы WCF:

- Отладка клиентского процесса, который вызывает службу. Отладчик выполняет шаг с заходом в службу. Служба и используемое клиентское приложение не обязательно должны находиться в одном и том же решении.

- Отладка клиентского процесса, который отправляет запрос службе. Служба должна быть частью решения.

- Использование диалогового окна **Присоединение к процессу** для присоединения текущей работающей службы. Отладка начинается внутри службы.

  В этом разделе описаны ограничения на применение данных сценариев.

## <a name="limitations-on-stepping-into-a-service"></a>Ограничения на выполнение шага с заходом в службу
 Чтобы выполнить шаг с заходом в службу из отлаживаемого клиентского приложения, необходимо соблюдать следующие условия.

- Для вызова службы клиент должен использовать синхронный клиентский объект.

- Операция контракта не может быть односторонней.

- Если сервер асинхронный, то при выполнении кода внутри службы невозможно просмотреть полный стек вызовов.

- В файле app.config или Web.config должна быть включена отладка с помощью показанного ниже кода.

    ```xml
    <system.web>
      <compilation debug="true" />
    </system.web>
    ```

     Этот код требуется добавить только один раз. Его можно добавить, внеся изменения в файл .config или выполнив присоединение к службе с помощью диалогового окна **Присоединение к процессу**. При использовании диалогового окна **Присоединение к процессу** код отладки добавляется к файлу .config автоматически. После этого можно выполнить отладку и выполнить шаг с заходом в службу, не изменяя файл .config.

## <a name="limitations-on-stepping-out-of-a-service"></a>Ограничения на выполнение шага с выходом из службы
 В отношении выхода из пошагового выполнения службы и возвращения к клиенту действуют те же ограничения, что и для шага с заходом в службу. Кроме того, отладчик должен быть присоединен к клиенту. Если во время отладки клиента производится шаг с заходом в службу, отладчик остается присоединенным к службе. Это справедливо как в случае запуска клиента с помощью команды **Начать отладку**, так и в случае присоединения к клиенту с помощью диалогового окна **Присоединение к процессу**. Если отладка начинается путем присоединения к службе, отладчик больше не будет присоединен к клиенту. В таком случае при необходимости выхода из пошагового выполнения службы и возвращения к клиенту необходимо сначала присоединиться к клиенту вручную, используя диалоговое окно **Присоединение к процессу**.

## <a name="limitations-on-automatic-attach-to-a-service"></a>Ограничения на автоматическое присоединение к службе
 Автоматическое присоединение к службе имеет следующие ограничения:

- Служба должна быть частью решения [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], для которого выполняется отладка.

- Служба должна быть размещена. Служба может быть частью проекта веб-сайта (файловая система или HTTP), проекта веб-приложения (файловая система или HTTP) или проекта библиотеки служб WCF. Проекты библиотеки служб WCF могут быть либо библиотеками служб, либо библиотеками служб рабочих процессов.

- Обращение к службе должно производиться из клиента WCF.

- В файле app.config или Web.config должна быть включена отладка с помощью показанного ниже кода.

  ```xml
  <system.web>
    <compilation debug="true" />
  <system.web>
  ```

## <a name="self-hosting"></a>Резидентное размещение
 *Резидентная служба* является службой WCF, которая не запускается внутри IIS, узла службы WCF или сервера разработки [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]. Дополнительные сведения об отладке автономной службы см. [в разделе как выполнять отладку автономной службы WCF](../debugger/how-to-debug-a-self-hosted-wcf-service.md).

## <a name="self-hosting"></a>Резидентное размещение
 Чтобы включить отладку приложений [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] версии 3.0 или 3.5, следует установить [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] версии 3.0 или 3.5 до установки [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)]. Если [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] установлен до установки [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] версии 3.0 или 3.5, при попытке отладки приложения [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 3.0 или 3.5 возникает ошибка. Сообщение об ошибке: "Не удалось автоматически выполнить шаг на сервере". Чтобы устранить эту проблему, используйте **Панель управления** Windows  > **программы и компоненты** для восстановления установки [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)].

## <a name="see-also"></a>См. также
- [Отладка служб WCF](../debugger/debugging-wcf-services.md)
- [Практическое руководство. Отладка резидентной службы WCF](../debugger/how-to-debug-a-self-hosted-wcf-service.md)
