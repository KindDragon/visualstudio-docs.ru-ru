---
title: Пошаговое руководство. Развертывание приложения ClickOnce вручную | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Mage.exe, manual ClickOnce deployments
- MageUI.exe, manual ClickOnce deployments
- deploying applications [ClickOnce], manual ClickOnce deployments
- ClickOnce deployment, manually
- ClickOnce deployment, SDK tools
- manual ClickOnce deployments
- manifests [ClickOnce]
ms.assetid: ccee6551-a1b9-4ca2-8845-9c1cf4ac2560
caps.latest.revision: 51
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: cba55c9f4a8f7436b97099b6b548b916ea6e5ecb
ms.sourcegitcommit: c150d0be93b6f7ccbe9625b41a437541502560f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/10/2020
ms.locfileid: "75844943"
---
# <a name="walkthrough-manually-deploying-a-clickonce-application"></a>Разбор примера: развертывание вручную приложения ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Если вы не можете использовать Visual Studio для развертывания приложения [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] или вам необходимо использовать расширенные функции развертывания, такие как развертывание доверенных приложений, следует использовать программу командной строки Mage. exe для создания манифестов [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]. В этом пошаговом руководстве описывается создание [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] развертывания с помощью версии командной строки (Mage. exe) или графической версии (MageUI. exe) Инструмент создания и изменения манифестов.  
  
## <a name="prerequisites"></a>Prerequisites  
 В этом пошаговом руководстве есть некоторые предварительные требования и параметры, которые необходимо выбрать перед созданием развертывания.  
  
- Установите Mage. exe и MageUI. exe.  
  
     Mage. exe и MageUI. exe являются частью [!INCLUDE[winsdklong](../includes/winsdklong-md.md)]. Необходимо либо установить [!INCLUDE[winsdkshort](../includes/winsdkshort-md.md)], либо версию [!INCLUDE[winsdkshort](../includes/winsdkshort-md.md)], которая входит в состав Visual Studio. Дополнительные сведения см. в разделе [Windows SDK](https://msdn.microsoft.com/windowsserver/bb980924.aspx) на сайте MSDN.  
  
- Предоставьте приложение для развертывания.  
  
     В этом пошаговом руководстве предполагается, что у вас есть приложение Windows, готовое к развертыванию. Это приложение будет называться Апптодеплой.  
  
- Определите, как будет распространяться развертывание.  
  
     Варианты распространения включают в себя: Web, файловый ресурс или компакт-диск. Для получения дополнительной информации см. [ClickOnce Security and Deployment](../deployment/clickonce-security-and-deployment.md).  
  
- Определите, требуется ли для приложения повышенный уровень доверия.  
  
     Если приложению требуется полное доверие, например полный доступ к системе пользователя, можно использовать параметр `-TrustLevel` программы Mage. exe, чтобы задать это значение. Если вы хотите определить пользовательский набор разрешений для приложения, можно скопировать раздел разрешений для Интернета или интрасети из другого манифеста, изменить его в соответствии с вашими потребностями и добавить его в манифест приложения с помощью текстового редактора или MageUI. exe. Для получения дополнительной информации см. [Trusted Application Deployment Overview](../deployment/trusted-application-deployment-overview.md).  
  
- Получите сертификат Authenticode.  
  
     Необходимо подписать развертывание с помощью сертификата Authenticode. Тестовый сертификат можно создать с помощью Visual Studio, MageUI. exe или MakeCert. exe и средств Pvk2Pfx. exe. также можно получить сертификат от центра сертификации (ЦС). Если вы решили использовать развертывание доверенных приложений, необходимо также выполнить однократную установку сертификата на все клиентские компьютеры. Для получения дополнительной информации см. [Trusted Application Deployment Overview](../deployment/trusted-application-deployment-overview.md).  
  
    > [!NOTE]
    > Вы также можете подписать развертывание с помощью сертификата CNG, который можно получить из центра сертификации.  
  
- Убедитесь, что приложение не имеет манифеста с данными контроля учетных записей.  
  
     Необходимо определить, содержит ли приложение манифест со сведениями о контроле учетных записей (UAC), например элемент `<dependentAssembly>`. Чтобы изучить манифест приложения, можно использовать служебную программу Windows Sysinternals [Программа Sigcheck](https://technet.microsoft.com/sysinternals/bb897441.aspx) .  
  
     Если приложение содержит манифест с данными контроля учетных записей, его необходимо перестроить без сведений о контроле учетных записей. Для C# проекта в Visual Studio откройте свойства проекта и перейдите на вкладку приложение. В раскрывающемся списке **Манифест** выберите **создать приложение без манифеста**. Для проекта Visual Basic в Visual Studio откройте свойства проекта, перейдите на вкладку приложение и щелкните **Просмотр параметров UAC**. В открытом файле манифеста удалите все элементы в одном элементе `<asmv1:assembly>`.  
  
- Определите, требуются ли приложению необходимые условия на клиентском компьютере.  
  
     [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] приложения, развернутые из Visual Studio, могут включать загрузчик установки необходимых компонентов (Setup. exe) с развертыванием. В этом пошаговом руководстве создаются два манифеста, необходимые для развертывания [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]. Вы можете создать предварительный загрузчик с помощью [задачи GenerateBootstrapper](../msbuild/generatebootstrapper-task.md).  
  
### <a name="to-deploy-an-application-with-the-mageexe-command-line-tool"></a>Развертывание приложения с помощью программы командной строки Mage. exe  
  
1. Создайте каталог, в котором будут храниться файлы развертывания [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)].  
  
2. В только что созданном каталоге развертывания создайте подкаталог версии. Если приложение развертывается в первый раз, присвойте имя подкаталогу версии **1.0.0.0**.  
  
    > [!NOTE]
    > Версия развертывания может отличаться от версии приложения.  
  
3. Скопируйте все файлы приложения в подкаталог версии, включая исполняемые файлы, сборки, ресурсы и файлы данных. При необходимости можно создать дополнительные подкаталоги, содержащие дополнительные файлы.  
  
4. Откройте командную строку [!INCLUDE[winsdkshort](../includes/winsdkshort-md.md)] или Visual Studio и перейдите в подкаталог версии.  
  
5. Создайте манифест приложения с помощью вызова Mage. exe. Следующая инструкция создает манифест приложения для кода, компилируемого для запуска на процессоре Intel x86.  
  
    ```  
    mage -New Application -Processor x86 -ToFile AppToDeploy.exe.manifest -name "My App" -Version 1.0.0.0 -FromDirectory .   
    ```  
  
    > [!NOTE]
    > Не забудьте включить точку (.) после параметра `-FromDirectory`, который указывает текущий каталог. Если точка не включена, необходимо указать путь к файлам приложения.  
  
6. Подпишите манифест приложения с помощью сертификата Authenticode. Замените *MyCert. pfx* на путь к файлу сертификата. Замените *passwd* паролем для файла сертификата.  
  
    ```  
    mage -Sign AppToDeploy.exe.manifest -CertFile mycert.pfx -Password passwd  
    ```  
  
     Чтобы подписать манифест приложения с помощью сертификата CNG, используйте следующую программу. Замените *кнгцерт. pfx* на путь к файлу сертификата.  
  
    ```  
    mage -Sign AppToDeploy.exe.manifest -CertFile cngCert.pfx  
    ```  
  
7. Перейдите в корневую папку каталога развертывания.  
  
8. Создайте манифест развертывания с помощью вызова Mage. exe. По умолчанию программа Mage. exe помечает развертывание [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] как установленное приложение, чтобы его можно было запускать как в сети, так и в автономном режиме. Чтобы приложение было доступно только в том случае, если пользователь подключен к сети, используйте параметр `-Install` со значением `false`. Если используется значение по умолчанию и пользователи будут устанавливать приложение с веб-сайта или из общей папки, убедитесь, что параметр `-ProviderUrl` указывает расположение манифеста приложения на веб-сервере или в общей папке.  
  
    ```  
    mage -New Deployment -Processor x86 -Install true -Publisher "My Co." -ProviderUrl "\\myServer\myShare\AppToDeploy.application" -AppManifest 1.0.0.0\AppToDeploy.exe.manifest -ToFile AppToDeploy.application  
    ```  
  
9. Подпишите манифест развертывания с помощью сертификата Authenticode или CNG.  
  
    ```  
    mage -Sign AppToDeploy.application -CertFile mycert.pfx -Password passwd  
    ```  
  
     или  
  
    ```  
    mage -Sign AppToDeploy.exe.manifest -CertFile cngCert.pfx  
    ```  
  
10. Скопируйте все файлы из каталога развертывания в целевое расположение развертывания или носитель. Это может быть папка на веб-сайте, на узле FTP, в общей папке или компакт-диске.  
  
11. Предоставьте пользователям URL-адрес, UNC или физический носитель, необходимые для установки приложения. Если вы предоставляете URL-адрес или UNC, необходимо предоставить пользователям полный путь к манифесту развертывания. Например, если Апптодеплой развернут в http://webserver01/ в каталоге Апптодеплой, полный путь URL-адреса будет http://webserver01/AppToDeploy/AppToDeploy.application.  
  
### <a name="to-deploy-an-application-with-the-mageuiexe-graphical-tool"></a>Развертывание приложения с помощью графического средства MageUI. exe  
  
1. Создайте каталог, в котором будут храниться файлы развертывания [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)].  
  
2. В только что созданном каталоге развертывания создайте подкаталог версии. Если приложение развертывается в первый раз, присвойте имя подкаталогу версии **1.0.0.0**.  
  
    > [!NOTE]
    > Версия развертывания, скорее всего, отличается от версии приложения.  
  
3. Скопируйте все файлы приложения в подкаталог версии, включая исполняемые файлы, сборки, ресурсы и файлы данных. При необходимости можно создать дополнительные подкаталоги, содержащие дополнительные файлы.  
  
4. Запустите графическое средство MageUI. exe.  
  
    ```  
    MageUI.exe  
    ```  
  
5. Создайте новый манифест приложения, выбрав в меню **файл**, **создать**, **манифест приложения** .  
  
6. На вкладке **имя** по умолчанию введите имя и номер версии этого развертывания. Также укажите **процессор** , для которого создается приложение, например x86.  
  
7. Перейдите на вкладку **файлы** и нажмите кнопку с многоточием ( **...** ) рядом с текстовым полем **каталог приложения** . Откроется диалоговое окно Выбор папки.  
  
8. Выберите подкаталог версии, содержащий файлы приложения, а затем нажмите кнопку **ОК**.  
  
9. Если развертывание выполняется из службы IIS (IIS), установите флажок **при заполнении добавить расширение. deploy в любой файл, в котором он отсутствует** .  
  
10. Нажмите кнопку **заполнить** , чтобы добавить все файлы приложения в список файлов. Если приложение содержит более одного исполняемого файла, пометьте основной исполняемый файл для этого развертывания в качестве запускаемого приложения, выбрав **пункт точка входа** в раскрывающемся списке **Тип файла** . (Если приложение содержит только один исполняемый файл, программа MageUI. exe пометит его для вас.)  
  
11. Перейдите на вкладку **требуемые разрешения** и выберите уровень доверия, который приложение должно утверждать. Значение по умолчанию — **FullTrust**, которое подходит для большинства приложений.  
  
12. Выберите **файл**, **Сохранить как** в меню. Откроется диалоговое окно Параметры подписи с предложением подписать манифест приложения.  
  
13. Если у вас есть сертификат, хранящийся в качестве файла в файловой системе, используйте параметр **подписать с помощью файла сертификата** и выберите сертификат из файловой системы с помощью кнопки с многоточием ( **...** ). Затем введите пароль сертификата.  
  
     \- или -  
  
     Если сертификат хранится в хранилище сертификатов, доступном с компьютера, выберите параметр **подписать с сохраненным сертификатом** и выберите сертификат из предоставленного списка.  
  
14. Нажмите кнопку **ОК** , чтобы подписать манифест приложения. Откроется диалоговое окно Сохранить как.  
  
15. В диалоговом окне Сохранить как укажите каталог версий и нажмите кнопку **сохранить**.  
  
16. В меню выберите **файл**, **создать**, **манифест развертывания** , чтобы создать манифест развертывания.  
  
17. На вкладке **имя** укажите имя и номер версии для этого развертывания (в этом примере —**1.0.0.0** ). Также укажите **процессор** , для которого создается приложение, например x86.  
  
18. Перейдите на вкладку **Описание** и укажите значения для параметров **Издатель** и **продукт**. (**Продукт** — это имя, присваиваемое приложению в меню Пуск Windows при установке приложения на клиентском компьютере для использования в автономном режиме.)  
  
19. Перейдите на вкладку **Параметры развертывания** и в текстовом поле **начальное расположение** укажите расположение манифеста приложения на веб-сервере или в общей папке. Например, \\\Мисервер\мишаре\апптодеплой.аппликатион.  
  
20. Если вы добавили расширение Deploy на предыдущем шаге, также выберите **использовать расширение имени файла** .  
  
21. Перейдите на вкладку **Параметры обновления** и укажите частоту обновления этого приложения. Если приложение использует <xref:System.Deployment.Application.UpdateCheckInfo> для проверки наличия обновлений, снимите флажок **это приложение должно проверять наличие обновлений** .  
  
22. Перейдите на вкладку **ссылка на приложение** и нажмите кнопку **Выбрать манифест** . Откроется диалоговое окно Открыть.  
  
23. Выберите созданный ранее манифест приложения и нажмите кнопку **Открыть**.  
  
24. Выберите **файл**, **Сохранить как** в меню. Откроется диалоговое окно Параметры подписи с предложением подписать манифест развертывания.  
  
25. Если у вас есть сертификат, хранящийся в качестве файла в файловой системе, используйте параметр **подписать с помощью файла сертификата** и выберите сертификат из файловой системы с помощью кнопки с многоточием ( **...** ). Затем введите пароль сертификата.  
  
     \- или -  
  
     Если сертификат хранится в хранилище сертификатов, доступном с компьютера, выберите параметр **подписать с сохраненным сертификатом** и выберите сертификат из предоставленного списка.  
  
26. Нажмите кнопку **ОК** , чтобы подписать манифест развертывания. Откроется диалоговое окно Сохранить как.  
  
27. В диалоговом окне **Сохранить как** перейдите на один из каталогов в корневую папку развертывания и нажмите кнопку **сохранить**.  
  
28. Скопируйте все файлы из каталога развертывания в целевое расположение развертывания или носитель. Это может быть папка на веб-сайте, на узле FTP, в общей папке или компакт-диске.  
  
29. Предоставьте пользователям URL-адрес, UNC или физический носитель, необходимые для установки приложения. Если вы предоставляете URL-адрес или UNC, необходимо предоставить пользователям полный путь к манифесту развертывания. Например, если Апптодеплой развернут в http://webserver01/ в каталоге Апптодеплой, полный путь URL-адреса будет http://webserver01/AppToDeploy/AppToDeploy.application.  
  
## <a name="next-steps"></a>Дальнейшие действия  
 Если необходимо развернуть новую версию приложения, создайте новый каталог с именем после новой версии, например 1.0.0.1, и скопируйте новые файлы приложения в новый каталог. Далее необходимо выполнить описанные выше действия, чтобы создать и подписать новый манифест приложения, а также обновить и подписать манифест развертывания. Не забудьте указать ту же самую более позднюю версию в вызовах программы Mage. exe `-New` и `–Update`, так как [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] только обновляет более высокие версии, при этом наиболее значимое самое левое целое число. Если вы использовали MageUI. exe, можно обновить манифест развертывания, открыв его, выбрав вкладку **ссылка на приложение** , нажав кнопку **Выбрать манифест** , а затем выбрав обновленный манифест приложения.  
  
## <a name="see-also"></a>См. также раздел  
 [Mage.exe (средство создания и редактирования манифеста)](https://msdn.microsoft.com/library/77dfe576-2962-407e-af13-82255df725a1)   
 [MageUI.exe (средство создания и редактирования манифестов, графический клиент)](https://msdn.microsoft.com/library/f9e130a6-8117-49c4-839c-c988f641dc14)   
 [Публикация приложений ClickOnce](../deployment/publishing-clickonce-applications.md)   
   [манифеста развертывания ClickOnce](../deployment/clickonce-deployment-manifest.md)  
 [Манифест приложения ClickOnce](../deployment/clickonce-application-manifest.md)
