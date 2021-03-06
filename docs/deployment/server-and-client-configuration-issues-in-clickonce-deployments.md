---
title: Проблемы с конфигурацией сервера или клиента в развертываниях ClickOnce
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- deploying applications, ClickOnce
- troubleshooting ClickOnce deployments
- ClickOnce deployment, troubleshooting
- Windows applications, ClickOnce deployments
ms.assetid: 929e5fcc-dd56-409c-bb57-00bd9549b20b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b1d2512c14c0630d2268adfa465e092555150943
ms.sourcegitcommit: bf2e9d4ff38bf5b62b8af3da1e6a183beb899809
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2020
ms.locfileid: "77557867"
---
# <a name="server-and-client-configuration-issues-in-clickonce-deployments"></a>Вопросы настройки сервера и клиента в развертываниях ClickOnce
Если в Windows Server используется службы IIS (IIS) и развертывание содержит тип файла, который не распознается Windows, например файл Microsoft Word, IIS отклоняет передачу этого файла, и развертывание не будет выполняться.

 Кроме того, некоторые веб-серверы и программное обеспечение веб-приложений, например [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)], содержат список файлов и типов файлов, которые невозможно загрузить. Например, [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] предотвращает скачивание всех файлов *Web. config* . Эти файлы могут содержать конфиденциальные сведения, такие как имена пользователей и пароли.

 Хотя это ограничение не должно вызывать проблем при загрузке основных [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] файлов, таких как манифесты и сборки, это ограничение может препятствовать загрузке файлов данных, входящих в состав приложения [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]. В [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]можно устранить эту ошибку, удалив обработчик, который запрещает скачивание таких файлов из диспетчера конфигурации IIS. Дополнительные сведения см. в документации по серверу IIS.

 Некоторые веб-серверы могут блокировать файлы с расширениями, такими как *DLL*, *config*и *MDF*. Приложения на основе Windows обычно включают файлы с некоторыми из этих расширений. Если пользователь пытается запустить приложение [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)], которое обращается к заблокированному файлу на веб-сервере, возникает ошибка. Вместо того чтобы разблокирование всех расширений файлов, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] публикует каждый файл приложения с расширением *deploy* по умолчанию. Поэтому администратору нужно только настроить веб-сервер для разблокировки следующих трех расширений файлов:

- *.application*

- *.manifest*

- *.deploy*

  Однако можно отключить этот параметр, сняв флажок **использовать расширение файла ". deploy"** в [диалоговом окне "Параметры публикации](/previous-versions/visualstudio/visual-studio-2010/7z83t16a(v=vs.100))". в этом случае необходимо настроить веб-сервер для разблокировки всех расширений файлов, используемых в приложении.

  Если вы используете службы IIS, на которых не установлен .NET Framework, или если вы используете другой веб-сервер (например, Apache), потребуется настроить *. manifest*, *. Application*и *. deploy*.

## <a name="clickonce-and-secure-sockets-layer-ssl"></a>ClickOnce и SSL (SSL)
 Приложение [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] будет работать по протоколу SSL, за исключением случаев, когда Internet Explorer выдает запрос о SSL-сертификате. Запрос может быть вызван при возникновении ошибки в сертификате, например в случае, если имена сайтов не совпадают или истек срок действия сертификата. Чтобы [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] работать через SSL-подключение, убедитесь, что сертификат обновлен и данные сертификата соответствуют данным сайта.

## <a name="clickonce-and-proxy-authentication"></a>Проверка подлинности ClickOnce и прокси
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] обеспечивает поддержку встроенной проверки подлинности прокси Windows, начиная с .NET Framework 3,5. Никакие специальные директивы Machine. config не требуются. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] не обеспечивает поддержку других протоколов проверки подлинности, таких как Basic или Digest.

 Чтобы включить эту функцию, можно также применить исправление к .NET Framework 2,0. Дополнительные сведения см. в разделе [исправление: сообщение об ошибке при попытке установить приложение ClickOnce, созданное в .NET Framework 2,0 на клиентский компьютер, настроенный для использования прокси-сервера: "требуется проверка подлинности прокси"](https://support.microsoft.com/help/917952/fix-error-message-when-you-try-to-install-a-clickonce-application-that).

 Дополнительные сведения см. в разделе [\<defaultProxy > Element (параметры сети)](/dotnet/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings).

## <a name="clickonce-and-web-browser-compatibility"></a>Совместимость ClickOnce и веб-браузера
 В настоящее время [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] установки будут запускаться только в том случае, если URL-адрес манифеста развертывания открыт с помощью Internet Explorer. Развертывание, URL-адрес которого запускается из другого приложения, например Microsoft Office Outlook, запустится успешно, только если Internet Explorer установлен в качестве веб-браузера по умолчанию.

> [!NOTE]
> Mozilla Firefox поддерживается, если поставщик развертывания не является пустым или установлено расширение Microsoft .NET Framework Assistant. Это расширение упаковывается с .NET Framework 3,5 с пакетом обновления 1 (SP1). Для поддержки XBAP подключаемый модуль НПВПФ активируется при необходимости.

## <a name="activate-clickonce-applications-through-browser-scripting"></a>Активация приложений ClickOnce с помощью сценариев браузера
 Если вы разработали пользовательскую веб-страницу, запускающую [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] приложение с помощью активных сценариев, может оказаться, что приложение не запустится на некоторых компьютерах. Internet Explorer содержит параметр, который называется **автоматическим запросом на загрузку файлов**, что влияет на это поведение. Этот параметр доступен на вкладке **Безопасность** в меню **Параметры** , которое влияет на это поведение. Он называется **автоматическим запросом на загрузку файлов**и отображается под категорией **загрузки** . Свойство по умолчанию включено **для** веб-страниц интрасети и по умолчанию **отключено** для веб-страниц Интернета. Если этот параметр имеет значение **Disable**, любая попытка программно активировать [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] приложение (например, путем назначения его URL-адреса свойству `document.location`) будет заблокирована. В этом случае пользователи могут запускать приложения только через загрузку, инициированную пользователем, например, щелкнув гиперссылку в качестве URL-адреса приложения.

## <a name="additional-server-configuration-issues"></a>Дополнительные проблемы с конфигурацией сервера

##### <a name="administrator-permissions-required"></a>Требуются разрешения администратора
 При публикации с помощью протокола HTTP необходимо иметь разрешения администратора на целевом сервере. Для IIS требуется этот уровень разрешений. Если публикация выполняется не по протоколу HTTP, то требуется только разрешение на запись в целевой путь.

##### <a name="server-authentication-issues"></a>Проблемы проверки подлинности сервера
 При публикации на удаленном сервере с отключенным параметром "анонимный доступ" вы получите следующее предупреждение:

```
"The files could not be downloaded from http://<remoteserver>/<myapplication>/.  The remote server returned an error: (401) Unauthorized."
```

> [!NOTE]
> Проверку подлинности NTLM (запрос NT-ответ) можно выполнить, если на сайте запрашиваются учетные данные, отличные от учетных данных по умолчанию, а в диалоговом окне Безопасность нажмите кнопку **ОК** при появлении запроса на сохранение предоставленных учетных данных для будущих сеансов. Однако это решение не будет работать для обычной проверки подлинности.

## <a name="use-third-party-web-servers"></a>Использование веб-серверов сторонних производителей
 При развертывании [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] приложения с веб-сервера, отличного от IIS, может возникнуть проблема, если сервер возвращает неверный тип содержимого для ключевых [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] файлов, таких как манифест развертывания и манифест приложения. Чтобы устранить эту проблему, ознакомьтесь с документацией по веб-серверу, посвященной добавлению новых типов содержимого на сервер, и убедитесь в наличии всех сопоставлений расширений имен файлов, перечисленных в следующей таблице.

|Расширение имени файла|Тип контента|
|-------------------------|------------------|
|`.application`|`application/x-ms-application`|
|`.manifest`|`application/x-ms-manifest`|
|`.deploy`|`application/octet-stream`|
|`.msu`|`application/octet-stream`|
|`.msp`|`application/octet-stream`|

## <a name="clickonce-and-mapped-drives"></a>ClickOnce и подключенные диски
 Если для публикации приложения ClickOnce используется Visual Studio, то в качестве расположения установки нельзя указывать подключенный диск. Однако можно изменить приложение ClickOnce для установки с подключенного диска с помощью генератора и редактора манифеста (Mage. exe и MageUI. exe). Дополнительные сведения см. в разделе [Mage.exe (средство редактирования и Manifest Generation)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool) и [MageUI.exe (средство создания и редактирования манифестов, графический клиент)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client).

## <a name="ftp-protocol-not-supported-for-installing-applications"></a>Протокол FTP не поддерживается для установки приложений
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] поддерживает установку приложений с любого веб-сервера HTTP 1,1 или с файлового сервера. FTP, протокол FTP, не поддерживается для установки приложений. Можно использовать FTP только для публикации приложений. Эти различия обобщены в следующей таблице.

| Тип URL-адреса | Описание |
|----------| - |
| ftp:// | Вы можете опубликовать [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] приложение с помощью этого протокола. |
| http:// | Вы можете установить [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]ное приложение с помощью этого протокола. |
| https:// | Вы можете установить [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]ное приложение с помощью этого протокола. |
| file:// | Вы можете установить [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]ное приложение с помощью этого протокола. |

## <a name="windows-xp-sp2-windows-firewall"></a>Windows XP SP2: брандмауэр Windows
 По умолчанию Windows XP с пакетом обновления 2 (SP2) включает брандмауэр Windows. Если приложение разрабатывается на компьютере с установленной системой Windows XP, вы по-прежнему можете публиковать и запускать [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] приложения с локального сервера, на котором работают службы IIS. Однако доступ к серверу IIS с другого компьютера невозможен, если не открыт брандмауэр Windows. Инструкции по управлению брандмауэром Windows см. в справке Windows.

## <a name="windows-server-enable-frontpage-server-extensions"></a>Windows Server: включение серверных расширений FrontPage
 Серверные расширения FrontPage от корпорации Майкрософт необходимы для публикации приложений на веб-сервере Windows, использующем протокол HTTP.

 По умолчанию в Windows Server не установлены серверные расширения FrontPage. Если вы хотите использовать [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] для публикации на веб-сервере Windows Server, использующем HTTP с серверными расширениями FrontPage, сначала необходимо установить расширения сервера FrontPage. Установку можно выполнить с помощью средства администрирования сервера в Windows Server.

## <a name="windows-server-locked-down-content-types"></a>Windows Server: заблокированные типы содержимого
 Службы IIS на [!INCLUDE[WinXPSvr](../debugger/includes/winxpsvr_md.md)] заблокируют все типы файлов, кроме определенных известных типов содержимого (например, *htm*, *HTML*, *txt*и т. д.). Чтобы включить развертывание [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] приложений с помощью этого сервера, необходимо изменить параметры IIS, чтобы разрешить загрузку файлов типа *. Application*, *. manifest*и других пользовательских типов файлов, используемых приложением.

 При развертывании с помощью сервера IIS запустите *файл inetmgr. exe* и добавьте новые типы файлов для веб-страницы по умолчанию:

- Для расширений *. Application* и *. manifest* тип MIME должен быть "Application/x-MS-Application". Для других типов файлов тип MIME должен быть "Application/октет-Stream".

- Если вы создаете тип MIME с расширением "<em>" и типом MIME "Application/октет-Stream", он разрешит скачивать файлы незаблокированного типа файла. (Однако невозможно скачать Заблокированные типы файлов, такие как *. aspx</em> и *. asmx* .)

  Конкретные инструкции по настройке типов MIME в Windows Server см. в разделе [Добавление типа MIME к веб-сайту или приложению](/iis/configuration/system.webserver/staticcontent/mimemap#how-to-add-a-mime-type-to-a-web-site-or-application).

## <a name="content-type-mappings"></a>Сопоставления типов содержимого
 При публикации по протоколу HTTP тип содержимого (также известный как тип MIME) для файла *приложения* должен быть "Application/x-MS-Application". Если на сервере установлено .NET Framework 2,0, это будет установлено автоматически. Если этот параметр не установлен, необходимо создать ассоциацию типа MIME для [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] виртуального корневого каталога приложения (или всего сервера).

 При развертывании с помощью сервера IIS выполните команду <em>inetmgr.</em> exe и добавить новый тип содержимого application/x-MS-Application для расширения *приложения* .

## <a name="http-compression-issues"></a>Проблемы с сжатием HTTP
 С помощью [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]можно выполнять загрузку, использующую сжатие HTTP, технологию веб-сервера, использующую алгоритм GZIP для сжатия потока данных перед отправкой потока клиенту. Клиент — в данном случае [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]— распаковывает поток перед чтением файлов.

 При использовании IIS можно легко включить сжатие HTTP. Однако при включении сжатия HTTP оно включается только для определенных типов файлов — а именно, HTML и текстовых файлов. Чтобы включить сжатие для сборок (*DLL*), XML (*XML*), манифестов развертывания ( *. Application*) и манифестов приложений ( *. manifest*), необходимо добавить эти типы файлов в список типов для сжатия IIS. Пока вы не добавите типы файлов в развертывание, будут сжиматься только текстовые и HTML-файлы.

 Подробные инструкции для IIS см. [в разделе Указание дополнительных типов документов для СЖАТИЯ HTTP](https://support.microsoft.com/help/234497).

## <a name="see-also"></a>См. также:
- [Устранение неполадок развертываний ClickOnce](../deployment/troubleshooting-clickonce-deployments.md)
- [Выбор стратегии развертывания ClickOnce](../deployment/choosing-a-clickonce-deployment-strategy.md)
- [Обязательные требования к развертыванию приложений](../deployment/application-deployment-prerequisites.md)