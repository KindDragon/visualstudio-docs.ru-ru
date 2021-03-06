---
title: Укажите версию .NET Framework для отладки | Документация Майкрософт
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- .NET Framework, specifying version for debugging
- debugging [Visual Studio], specifying .NET Framework version
ms.assetid: 7a4893ba-4620-4774-893f-378d4ca28893
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 1f6107d6396c6228be1d511e81003fbe7faf06c9
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72732640"
---
# <a name="specify-an-older-net-framework-version-for-debugging-c-visual-basic-f"></a>Укажите более раннюю версию .NET Framework для отладки (C#, Visual Basic, F#)

Отладчик Visual Studio поддерживает отладку старых версий платформы Microsoft .NET Framework, а также текущей версии. При запуске приложения из Visual Studio отладчик всегда может найти правильную версию .NET Framework для отлаживаемого приложения. Однако если приложение уже запущено и вы начинаете отладку с помощью команды **attach to**, отладчик не всегда может определить старую версию .NET Framework. В этом случае появится сообщение об ошибке следующего содержания:

``` cmd
The debugger has made an incorrect assumption about the .NET Framework version your application is going to use.
```

В редких случаях, когда возникает эта ошибка, можно задать раздел реестра, указывающий отладчику, какую версию следует использовать.

### <a name="to-specify-a-net-framework-version-for-debugging"></a>Указание версии платформы .NET Framework для отладки

1. Перейдите в каталог "Windows\Microsoft.NET\Framework" и посмотрите, какие версии платформы .NET Framework установлены на компьютере. Номера версий выглядят примерно так:

    `V1.1.4322`

    Определите правильный номер версии и запомните или запишите его.

2. Запустите **Редактор реестра** (regedit).

3. В **редакторе реестра** откройте папку HKEY_LOCAL_MACHINE.

4. Перейдите в HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\10.0\AD7Metrics\Engine\\{449EC4CC-30D2-4032-9256-EE18EB41B62B}

    Если раздел не существует, щелкните правой кнопкой мыши HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\10.0\AD7Metrics\Engine и выберите команду **Создать раздел**. Назовите новый ключ `{449EC4CC-30D2-4032-9256-EE18EB41B62B}`.

5. После перехода к {449EC4CC-30D2-4032-9256-EE18EB41B62B}, найдите в столбце **Имя** ключ "CLRVersionForDebugging".

   1. Если раздел не существует, щелкните правой кнопкой мыши {449EC4CC-30D2-4032-9256-EE18EB41B62B} и выберите команду **Создать строковый параметр**. Затем щелкните правой кнопкой мыши новое строковое значение, выберите команду **Переименовать**и введите `CLRVersionForDebugging`.

6. Дважды щелкните **CLRVersionForDebugging**.

7. В поле **Изменение строки** введите номер версии платформы .NET Framework в поле **Значение**. Например, "V1.1.4322".

8. Нажмите кнопку **ОК**.

9. Закройте **Редактор реестра**.

     Если при запуске отладки по-прежнему возникает сообщение об ошибке, проверьте, что в реестре введен правильный номер версии. Также убедитесь, что используется версия .NET Framework, поддерживаемая Visual Studio. Отладчик совместим с текущей версией платформы .NET Framework и предыдущими версиями, но может не обладать прямой совместимостью с будущими версиями.

## <a name="see-also"></a>См. также
- [Параметры отладчика и подготовка](../debugger/debugger-settings-and-preparation.md)