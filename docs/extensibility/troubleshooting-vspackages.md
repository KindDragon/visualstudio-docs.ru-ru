---
title: Устранение неполадок пакетов VSPackage | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, troubleshooting
- debugging, VSPackages
ms.assetid: 274673e7-72e7-476f-a263-3411b5b874be
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a231d8d02ce7432188053293684d09c7243dfd5e
ms.sourcegitcommit: 260d093d2287ba791f28bdc7103493beabf80b2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77506400"
---
# <a name="troubleshooting-vspackages"></a>Устранение неполадок, связанных с пакетами VSPackage
Ниже приведены распространенные проблемы, которые могут возникнуть при работе с VSPackage, и советы по устранению проблем.

### <a name="to-troubleshoot-a-vspackage-that-keeps-visual-studio-from-starting"></a>Устранение неполадок в VSPackage, сохраняющем запуск Visual Studio

- Запуск [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] в защищенном режиме.

   Чтобы запустить [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] в защищенном режиме, в командной строке введите **devenv. exe/SafeMode**.

   Во время этого процесса пакеты VSPackage не загружаются, за исключением пакетов VSPackage, которые входят в состав [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].

### <a name="to-troubleshoot-a-vspackage-that-does-not-load"></a>Устранение неполадок с пакетом VSPackage, который не загружается

1. Убедитесь, что вы используете корень реестра, в котором пакет VSPackage зарегистрирован для запуска, обычно экспериментальный корень реестра.

    Дополнительные сведения см. [в статье экспериментальный экземпляр](../extensibility/the-experimental-instance.md).

2. Если пакет VSPackage предназначен для запуска в экспериментальном корне реестра, убедитесь, что вы используете экспериментальную версию [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].

    Чтобы запустить экспериментальную версию, введите в командном окне следующую команду: **devenv/рутсуффикс exp**.

3. Проверьте записи реестра VSPackage.

    Дополнительные сведения см. в разделе [Регистрация пакетов VSPackage](registering-and-unregistering-vspackages.md) и Управление пакетами [VSPackage](../extensibility/managing-vspackages.md).

4. Откройте окно **вывода** экземпляра [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], который не может загрузить VSPackage. Сведения о том, почему пакет VSPackage не удается загрузить, может отображаться в этом окне.

   > [!NOTE]
   > Если вы запускаете экспериментальную версию [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] из [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] интегрированной среды разработки (IDE), проверьте окно **вывода** обеих версий.

5. Проверьте журнал действий.

    Дополнительные сведения см. в разделе [инструкции. Использование журнала действий](../extensibility/how-to-use-the-activity-log.md).

6. Для получения дополнительных сведений об исключениях, создаваемых интегрированной средой разработки, щелкните **исключения** в меню **Отладка** , чтобы включить исключения. В диалоговом окне **исключения** выберите типы исключений, сведения о которых требуется получить.

### <a name="to-troubleshoot-a-vspackage-that-does-not-register"></a>Устранение неполадок в пакете VSPackage, который не зарегистрирован

1. Убедитесь, что сборка VSPackage находится в надежном расположении. RegPkg не может зарегистрировать сборки в расположении, не являющемся доверенным или частично доверенном, например в общей сетевой папке в конфигурации безопасности .NET по умолчанию. Хотя предупреждение появляется каждый раз, когда пользователь создает проект в ненадежном расположении, флажок "больше не показывать это сообщение" может препятствовать возникновению этого предупреждения.

### <a name="to-troubleshoot-a-command-that-is-not-visible-or-that-generates-an-error-when-you-click-a-command"></a>Устранение неполадок с командой, которая не отображается или вызывает ошибку при нажатии команды

1. Объедините новые или измененные команды меню и те, которые уже находятся в интегрированной среде разработки, введя следующую команду в [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] командной строке: **devenv/Рутсуффикс exp/Setup**.

2. Убедитесь, что [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] может найти файл UI. dll для VSPackage.

   1. Найдите идентификатор CLSID пакета VSPackage в разделе Packages реестра:

        Хклм\софтваре\микрософт\висуал Studio\\ *\<версии >* \паккажес

   2. Убедитесь, что путь, указанный в подразделе Сателлитедлл, указан правильно.

### <a name="to-troubleshoot-a-vspackage-that-behaves-unexpectedly"></a>Устранение неполадок в пакетах VSPackage, которые неожиданно заменяются

1. Задайте точки останова в коде.

     Хорошей отправной точкой для отладки является конструктор и метод инициализации. Можно также задать точки останова в области, которую требуется вычислить, например команде меню. Чтобы включить точки останова, необходимо запустить в отладчике.

    1. В меню **Проект** выберите **Свойства**.

    2. В диалоговом окне **страницы свойств** перейдите на вкладку **Отладка** .

    3. В поле **аргументы командной строки** введите корневой суффикс среды разработки, для которой предназначен пакет VSPackage. Например, чтобы выбрать экспериментальную сборку, введите: **/Рутсуффикс exp**.

    4. В меню **Отладка** выберите команду **начать отладку** или нажмите клавишу F5.

        > [!NOTE]
        > При отладке проекта создайте или загрузите существующий экземпляр проекта прямо сейчас.

2. Используйте журнал действий.

     Трассировка поведения VSPackage путем записи сведений в журнал действий в ключевых точках. Этот метод особенно полезен при запуске пакета VSPackage в розничной среде. Дополнительные сведения см. в разделе [инструкции. Использование журнала действий](../extensibility/how-to-use-the-activity-log.md).

3. Используйте открытые символы.

     Чтобы улучшить удобочитаемость во время отладки, можно присоединить символы к отладчику.

    1. В меню **Сервис/параметры** перейдите в диалоговое окно **Отладка/символы** .

    2. Добавьте следующее **расположение файла символов (. pdb)** :

         `https://msdl.microsoft.com/download/symbols`

    3. Чтобы повысить производительность, укажите папку кэша символов, например:

        ```
        C:\symbols
        ```

### <a name="to-troubleshoot-a-missing-vspackage-or-one-of-its-dependencies"></a>Устранение неполадок с отсутствующим пакетом VSPackage или одной из его зависимостей

1. Для управляемого кода убедитесь, что пути ссылок верны.

   1. В меню **Проект** выберите **Свойства**.

   2. Перейдите на вкладку **ссылки** в диалоговом окне **страницы свойств** и убедитесь, что все пути указаны правильно. Кроме того, можно использовать **Обозреватель объектов** для поиска объектов, на которые имеются ссылки.

        Для управляемого кода можно использовать [Fuslogvw. exe (средство просмотра журнала привязки сборок)](/dotnet/framework/tools/fuslogvw-exe-assembly-binding-log-viewer) для просмотра сведений о неудачных загрузках сборок.

2. Для неуправляемого кода найдите CLSID пакета VSPackage в узле реестра [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] CLSID:

    Хклм\софтваре\микрософт\висуал Studio\\ *\<версии >* \клсид

   Убедитесь, что запись InprocServer32 имеет правильный путь к библиотеке DLL VSPackage.

## <a name="see-also"></a>См. также:
- [Пакеты VSPackage](../extensibility/internals/vspackages.md)