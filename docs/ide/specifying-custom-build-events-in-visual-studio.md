---
title: Указание пользовательских событий сборки
ms.date: 11/04/2016
ms.technology: vs-ide-compile
ms.topic: conceptual
helpviewer_keywords:
- build events, customizing
ms.assetid: 69e935a5-e208-4bcd-865c-3e5f9b047ca8
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fda60ffb97ecb44bd4a881cb42e4d9199cc958b8
ms.sourcegitcommit: f3f668ecaf11b4c2738ebc91923c6b5e38e74670
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2020
ms.locfileid: "76115340"
---
# <a name="specify-custom-build-events-in-visual-studio"></a>Указание настраиваемых событий сборки в Visual Studio

Указав пользовательское событие сборки, вы можете автоматически запустить команды перед тем, как сборка запустится или после того, как она завершится. Например, можно запустить *BAT*-файл до запуска сборки или скопировать новые файлы в папку после выполнения сборки. События сборки запускаются, только если сборка успешно достигает этих точек в процессе сборки.

Конкретные сведения об используемом языке программирования см. в следующих разделах.

- Visual Basic — [Практическое руководство. Указание событий сборки (Visual Basic)](../ide/how-to-specify-build-events-visual-basic.md).

- C#и F# — [Практическое руководство. Указание событий сборки (C#)](../ide/how-to-specify-build-events-csharp.md).

- Visual C++ — [Указание событий сборки](/cpp/build/specifying-build-events).

## <a name="syntax"></a>Синтаксис

События сборки следуют тому же синтаксису, что и команды DOS, но для упрощения процесса создания событий сборки можно использовать макросы. Список доступных макросов см. в разделе [Диалоговое окно "Командная строка события перед сборкой" или "Командная строка события после сборки"](../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md).

Для улучшения результатов воспользуйтесь советами по форматированию:

- Добавьте оператор `call` перед всеми событиями сборки, запускающими *BAT*-файлы.

   Пример: `call C:\MyFile.bat`

   Пример: `call C:\MyFile.bat call C:\MyFile2.bat`

- Заключите пути к файлам в кавычки.

   Пример (для [!INCLUDE[win8](../debugger/includes/win8_md.md)]): "%ProgramFiles(x86)%\Microsoft SDKs\Windows\v8.0A\Bin\NETFX 4.0 Tools\gacutil.exe" -if "$(TargetPath)"

- Разделите несколько команд с помощью разрывов строк.

- При необходимости включите подстановочные знаки.

   Пример: `for %I in (*.txt *.doc *.html) do copy %I c:\`*mydirectory*`\`

  > [!NOTE]
  > Команда `%I` в коде выше должна быть `%%I` в пакетных скриптах.

## <a name="see-also"></a>См. также

- [Компиляция и сборка](../ide/compiling-and-building-in-visual-studio.md)
- [Диалоговое окно "Командная строка события перед сборкой" или "Командная строка события после сборки"](../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md)
- [Специальные знаки в MSBuild](../msbuild/msbuild-special-characters.md)
- [Пошаговое руководство: сборка приложения](../ide/walkthrough-building-an-application.md)
