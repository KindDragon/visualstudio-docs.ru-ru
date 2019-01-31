---
title: Новые возможности Visual Studio 2017
titleSuffix: ''
description: Сведения о новых возможностях Visual Studio 2017.
ms.date: 12/18/2018
f1_keywords:
- VS.StartPage.WhatsNew
helpviewer_keywords:
- Visual Studio, what's new
- what's new [Visual Studio]
ms.assetid: 7307e180-ba28-4774-8a43-cbb980085a71
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.workload:
- multiple
monikerRange: '>= vs-2017'
ms.openlocfilehash: 3dd6a4d1dc8c17773a509576ad489a7ba3d752ce
ms.sourcegitcommit: 447f2174bdecdd471d8a8e11c19554977db620a0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2019
ms.locfileid: "55090125"
---
# <a name="whats-new-in-visual-studio-2017"></a>Новые возможности Visual Studio 2017

**Обновлено для [выпуска 15.9](/visualstudio/releasenotes/vs2017-relnotes?context=visualstudio/default&contextView=vs-2017)**

Хотите обновить предыдущую версию Visual Studio? Вот что Visual Studio 2017 может предложить вам: Visual Studio 2017 обеспечивает беспрецедентную производительность для любого устройства, приложения или платформы. Используйте Visual Studio 2017 для разработки приложений для Android, iOS, Windows, Linux, а также веб-приложений и облачных приложений. Быстро пишите код, выполняйте отладку и диагностику с легкостью, часто тестируйте и уверенно создавайте выпуски решений. Visual Studio можно расширить и настроить, создав собственные расширения. Система управления версиями в этом выпуске делает разработку гибкой, а совместную работу — эффективной.

>[!div class="button"]
>[Скачать Visual Studio 2012](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

Ниже приведен общий обзор изменений, внесенных с момента выпуска предыдущей версии — Visual Studio 2015:

* **[Пересмотренные основы](#redefined-fundamentals)**. Новые возможности настройки позволяют сократить время установки и выполнять установку любого компонента в любое время.
* **[Быстродействие и производительность](#performance-and-productivity)**. Мы уделили внимание новым и современным возможностям по разработке мобильных, облачных и классических приложений. Теперь Visual Studio запускается и реагирует быстрее, а также использует меньше памяти.
* **[Разработка облачных приложений с помощью Azure](#cloud-app-development-with-azure)**. Встроенный набор инструментов Azure позволяет без проблем создавать ориентированные на облако приложения на базе Microsoft Azure. Visual Studio упрощает настройку, сборку, отладку, упаковку и развертывание приложений и служб в Azure.
* **[Разработка приложений для Windows](#windows-app-development)**. Используйте шаблоны универсальной платформы Windows в Visual Studio 2017, чтобы разработать единый проект для всех устройств под управлением Windows 10 &ndash; персональных компьютеров, планшетов, телефонов, игровых консолей Xbox, очков HoloLens, Surface Hub и многих других.
* **[Разработка мобильных приложений](#mobile-app-development)**. Совершенствуйте проекты и получайте результаты быстрее с Xamarin, который объединяет многоплатформенные требования к мобильности, используя одноядерную базу кода и набор навыков.
* **[Кроссплатформенная разработка](#cross-platform-development)**. Без проблем доставляйте программное обеспечение для любой целевой платформы. Распространяйте процессы DevOps на SQL Server с помощью средств работы с данными Redgate и безопасно автоматизируйте развертывания баз данных в Visual Studio. Или используйте .NET Core для создания приложений и библиотек, которые в неизменном виде выполняются в операционных системах Windows, Linux и macOS.
* **[Разработка игр](#games-development)**. Средства Visual Studio для Unity (VSTU) позволяют использовать Visual Studio для создания сценариев игр и редакторов на языке C#, а затем использовать его мощный отладчик для поиска и исправления ошибок.
* **[Разработка для сценариев ИИ](#ai-development)**. Благодаря инструментам Visual Studio Tools for AI вы получаете эффективные средства для оптимизации инновационных разработок в сфере искусственного интеллекта на основе среды Visual Studio. Решения для создания, тестирования и развертывания ИИ и глубинного обучения легко интегрируются с машинным обучением Azure и предоставляют широкие возможности для экспериментов.

> [!NOTE]
> Полный список новых возможностей и функций Visual Studio 2017 см. в [этой](/visualstudio/releasenotes/vs2017-relnotes?context=visualstudio/default&contextView=vs-2017) статье. Ознакомиться с будущими возможностями вы можете в статье [Предварительные заметки о выпуске](/visualstudio/releasenotes/vs2017-preview-relnotes?context=visualstudio/default&contextView=vs-2017).

Здесь приведены более подробные сведения о некоторых самых важных усовершенствованиях и новых функциях в Visual Studio 2017.

## <a name="redefined-fundamentals"></a>Пересмотренные основы

### <a name="a-new-setup-experience"></a>Новые возможности установки

Visual Studio упрощает и ускоряет установку необходимых вам компонентов в любое время. Удаление тоже происходит без ошибок.

Самое важное изменение, которое вы заметите при установке Visual Studio, — это новый интерфейс установки. На вкладке **Рабочие нагрузки** вы увидите сгруппированные параметры установки для представления общей инфраструктуры, языков и платформ. Этот интерфейс охватывает все — от разработки классических приложений .NET до разработки приложений C++ для устройств с Windows, Linux и iOS.

Выбирайте нужные вам рабочие нагрузки и при необходимости изменяйте их.

 ![Диалоговое окно установки Visual Studio 2017](../install/media/install-visual-studio-enterprise.png)

У вас также есть параметры для тонкой настройки установки:

* Хотите выбрать собственные компоненты вместо рабочих нагрузок? Откройте вкладку **Отдельные компоненты** в установщике.
* Хотите установить языковые пакеты, не изменяя параметр "Язык Windows"? Откройте вкладку **Языковые пакеты** в установщике.
* **Новая возможность в версии 15.7**. Хотите изменить расположение, в которое будет устанавливаться Visual Studio? Откройте вкладку **Параметры установки** в установщике.

Дополнительные сведения о новых возможностях установки, включая пошаговые инструкции по их реализации, см. в статье [Установка Visual Studio](../install/install-visual-studio.md).

### <a name="a-focus-on-accessibility"></a>Специальные возможности

В **версии 15.3** мы внесли более 1700 целевых исправлений, которые улучшают совместимость Visual Studio и вспомогательных технологий, используемых нашими клиентами. Эта версия содержит множество сценариев, которые лучше совмещаются с средством чтения с экрана, темами с высокой контрастностью и другими специальными возможностями по сравнению со сценариями предыдущих версий. Мы также значительно улучшили отладчик, редактор и оболочку.

Дополнительные сведения см. в записи блога [Accessibility improvements in Visual Studio 2017 version 15.3](https://blogs.msdn.microsoft.com/visualstudio/2017/08/14/accessibility-improvements-in-visual-studio-2017-version-15-3/) (Улучшения специальных возможностей в Visual Studio 2017 версии 15.3).

## <a name="performance-and-productivity"></a>Быстродействие и производительность

### <a name="sign-in-across-multiple-accounts"></a>Вход для нескольких учетных записей

В Visual Studio представлена новая служба идентификации, которая позволяет совместно использовать учетные записи пользователей в Team Explorer, инструментах Azure, публикациях для Microsoft Store и т. д.

Вы также можете дольше оставаться в системе. Не требуется выполнять вход через каждые 12 часов. Дополнительные сведения см. в записи блога [Fewer Visual Studio Sign-in Prompts](https://blogs.msdn.microsoft.com/visualstudio/2016/08/15/fewer-visual-studio-sign-in-prompts/) (Сокращение количества запросов на вход в Visual Studio).

### <a name="start-visual-studio-faster"></a>Быстрый запуск Visual Studio

Новый центр производительности Visual Studio поможет вам в оптимизации времени запуска интегрированной среды разработки (IDE). Здесь указываются все расширения и окна инструментов, которые снижают скорость запуска IDE. Его можно использовать для повышения производительности запуска, определив запуск расширения или необходимость открытия окон инструментов во время запуска.

### <a name="faster-on-demand-loading-of-extensions"></a>Ускоренная загрузка расширений по требованию

Visual Studio перемещает свои расширения, а также работает со сторонними расширениями, поэтому они загружаются по требованию, а не во время запуска интегрированной среды разработки. Хотите узнать, какие расширения влияют на скорость запуска, загрузки решений и ввода данных? Эту информацию можно найти, выбрав **Справка** > **Управление производительностью Visual Studio**.

  ![Диалоговое окно "Параметры" в Visual Studio 2017](media/vs2017ide-manage-vs-perf.png)

#### <a name="manage-your-extensions-with-roaming-extensions-manager"></a>Управление расширениями с помощью диспетчера перемещаемых расширений

При входе в Visual Studio настройка каждой среды разработки с использованием избранных расширений стала проще. Новый диспетчер перемещаемых расширений отслеживает все ваши избранные расширения, создавая синхронизируемый список в облаке.

Чтобы просмотреть список расширений в Visual Studio, выберите **Инструменты** > **Расширения и обновления**, а затем — **Диспетчер перемещаемых расширений**.

![Visual Studio 2017: диалоговое окно "Расширения и обновления"](media/vs2017ide-extensions-and-updates.png)

Диспетчер перемещаемых расширений отслеживает все установленные расширения, но вы можете выбрать те, которые нужно добавить в список перемещаемых.

![Visual Studio 2017: диалоговое окно "Расширения и обновления"](media/vs2017ide-RoamingExtensionManager.png)

При использовании диспетчера перемещаемых расширений вы заметите в списке три типа значков.

* ![Значок перемещаемого расширения](media/vs2017ide-roamedicon.png) **_Перемещено_**. Расширение включено в список перемещаемых, но еще не установлено на этом компьютере.
  (Такие расширения можно установить с помощью кнопки **Скачать**.)
* ![Значок перемещаемого и установленного расширения](media/vs2017ide-roamedinstalledicon.png) **_Перемещено и установлено_**: Все расширения из списка перемещаемых, установленные в среде разработки.
  (Если вы решите, что перемещать расширение не нужно, его можно удалить с помощью кнопки **Остановить перемещение**.)
* ![Значок установленного расширения](media/vs2017ide-installedicon.png) **_Установлено_**: Все расширения установлены в среде, но не включены в список перемещаемых.
  (Расширения можно добавить в список перемещаемых с помощью кнопки **Начать перемещение**.)

Любое расширение, скачанное после того, как вы выполнили вход в систему, будет добавлено в список перемещаемых как **перемещаемое и установленное**. Это расширение включается в ваш список перемещения, а значит, будет доступно на любом компьютере.

### <a name="experience-live-unit-testing"></a>Возможности Live Unit Testing

В Visual Studio Enterprise 2017 функция Live Unit Testing предоставляет результаты динамического модульного тестирования и отображает результаты покрытия кода в редакторе в процессе кодирования. Она работает в проектах C# и Visual Basic для .NET Framework и .NET Core и поддерживает три платформы тестирования — MSTest, xUnit и NUnit.

![Live Unit Testing](media/lut-codewindow.png)

Дополнительные сведения см. в статье [Знакомство с Live Unit Testing](../test/live-unit-testing-intro.md). Список новых возможностей, добавленных в каждом выпуске Visual Studio Enterprise 2017, см. в статье [Новые возможности в Live Unit Testing](../test/live-unit-testing-whats-new.md).

### <a name="set-up-a-cicd-pipeline"></a>Настройка конвейера непрерывной интеграции и доставки

#### <a name="automated-testing"></a>Автоматическое тестирование

Автоматическое тестирование является ключевой частью любого конвейера DevOps. Оно позволяет согласованно и стабильно тестировать и выпускать решения в более короткие сроки. Потоки CI/CD (непрерывной интеграции и непрерывной доставки) могут помочь повысить эффективность процесса.

Дополнительные сведения об автоматических тестах см. в записи блога [CI/CD pipeline for automated tests in DevOps](https://blogs.msdn.microsoft.com/visualstudioalmrangers/2017/04/20/set-up-a-cicd-pipeline-to-run-automated-tests-efficiently/) (Конвейер CI/CD для автоматических тестов в DevOps).

Дополнительные сведения о новых возможностях расширения DevLabs [Инструменты непрерывной поставки для Visual Studio](https://marketplace.visualstudio.com/items?itemName=VSIDEDevOpsMSFT.ContinuousDeliveryToolsforVisualStudio) см. в записи блога [Уверенная фиксация: качество кода во время фиксации](https://blogs.msdn.microsoft.com/visualstudio/2017/08/21/committing-with-confidence-commit-time-code-quality-information-updated/).

### <a name="visual-studio-ide-enhancements"></a>Усовершенствования интегрированной среды разработки Visual Studio

#### <a name="multi-caret-editing"></a>Редактирование в нескольких точках вставки

**Новая возможность в версии 15.8**: редактировать файл в нескольких местах одновременно теперь очень просто. Сначала создайте точки вставки и выделения в нескольких местах в файле. Затем используйте функцию нескольких точек вставки, чтобы внести одинаковые изменения в несколько мест одновременно.

Дополнительные сведения см. в разделе [Выбор нескольких точек вставки](finding-and-replacing-text.md#multi-caret-selection) на странице [Поиск и замена текста](finding-and-replacing-text.md).

#### <a name="keep-keybinding-profiles-consistent"></a>Согласованность профилей настраиваемых сочетаний клавиш

**Новая возможность в версии 15.8**: обеспечить согласованность сочетаний клавиш в разных средствах можно с помощью двух новых профилей клавиатуры: Visual Studio Code и ReSharper (Visual Studio). Вы найдете эти схемы в разделе **Сервис** > **Параметры** > **Общие** > **Клавиатура** и в верхнем раскрывающемся меню.

  ![Новые профили настраиваемых сочетаний клавиш для Visual Studio Code и ReSharper](media/vs-keyboard-mappings-code-resharper.png)

#### <a name="use-new-refactorings"></a>Использование нового рефакторинга

Рефакторинг — это процесс усовершенствования кода после его написания. Под рефакторингом понимается оптимизация внутренней структуры кода без изменения его поведения. Мы регулярно добавляем новые возможности рефакторинга, включая следующие:

* Добавление параметра (из CallSite)
* Создание переопределений
* Добавление именованного аргумента
* Добавление проверки значений NULL для параметра
* Добавление разделителей между цифрами в литералы
* Изменение основания для числовых литералов (например, шестнадцатеричное на двоичное)
* Преобразование if-to-switch
* Удаление неиспользуемой переменной

Дополнительные сведения см. в разделе [Распространенные быстрые действия](common-quick-actions.md).

#### <a name="interact-with-git"></a>Взаимодействие с Git

Если вы работаете с проектом в Visual Studio, вы можете настроить код, а также быстро зафиксировать и опубликовать его в службе Git. Вы также можете управлять репозиториями Git, используя пункты меню в правом нижнем углу IDE.

![Visual Studio 2017 взаимодействует с диалоговым окном Git](media/vsIDE-GitInteraction.png)

#### <a name="experience-improved-navigation-controls"></a>Улучшенные возможности перехода

Мы обновили возможности навигации, чтобы помочь вам максимально быстро попасть из точки А в точку В с наименьшими препятствиями.

* **Новая возможность в версии 15.4**: **Перейти к определению** (**CTRL**+**щелок мышью** или **F12**) &ndash; С помощью мыши стало проще переходить к определениям членов. Для этого нужно щелкнуть член, удерживая нажатой клавишу **CTRL**. Если нажать и удерживать клавишу **CTRL**, а затем навести указатель на символ кода, он будет подчеркнут и превратится в ссылку. Дополнительные сведения см. в статье [Функции "Перейти к определению" и "Показать определение"](go-to-and-peek-definition.md).

* **Перейти к реализации** (**CTRL**+**F12**) &ndash; Переходите от любого базового типа или члена к его различным реализациям.

* **Перейти ко всем** (**CTRL**+**T** или **CTRL**+**,**) &ndash; Переходите напрямую к любому объявлению файла, типа, члена или символа. Вы можете отфильтровать список результатов или использовать синтаксис запроса (например, "f searchTerm" для файлов, "t searchTerm" для типов и т. д.).

  ![Улучшенная функция "Перейти ко всем"](media/vs2017ide-navigation-go-to.png)

* **Найти все ссылки** (**SHIFT**+**F12**) &ndash; Используя раскраску синтаксиса, вы можете сгруппировать результаты команды "Найти все ссылки" с помощью сочетания проекта, определения и пути. Вы также можете "заблокировать" результаты, чтобы продолжить поиск других ссылок без потери первоначальных результатов.

  ![Новый инструмент "Найти все ссылки"](media/vs2017ide-find-all-references.png)

* **Визуализатор структуры** &ndash; Пунктирные серые вертикальные линии (направляющие отступа) выполняют функцию ориентиров в коде, чтобы предоставить контекст в кадре представления. Возможно, они вам знакомы из Productivity Power Tools. Вы можете их использовать в любое время для визуализации и определения блока кода, в котором вы находитесь, без необходимости прокрутки. Если навести указатель мыши на строку, отображается подсказка, показывающая начало блока и его родительские элементы. Эта возможность доступна для всех языков поддерживаемых грамматиками TextMate, а также языков C#, Visual Basic и XAML.

  ![Визуализатор структуры Visual Studio 2017](media/vsIDE-StructureVisualizer.png)

Дополнительные сведения о новых функциях производительности см. в статье блога о [производительности в Visual Studio 2017](https://blogs.msdn.microsoft.com/visualstudio/2016/11/28/productivity-in-visual-studio-2017-rc/), опубликованной Марком Уилсоном-Томасом (Mark Wilson-Thomas).

### <a name="visual-c"></a>Visual C++

Вы увидите некоторые улучшения в Visual Studio, а именно — распространение основных рекомендаций C++ в Visual Studio, обновление компилятора с помощью добавления расширенной поддержки функций C++11 и C++, а также добавление и обновление функциональных возможностей библиотек C++. Мы также повысили производительность интегрированной среды разработки C++, рабочих нагрузок установки и т. д.

Мы устранили более 250 ошибок и заявленных проблем в компиляторе и других инструментах. Информация о многих из этих ошибок поступила к нам от клиентов через [сообщество разработчиков для C++](https://developercommunity.visualstudio.com/spaces/62/index.html "сообщество разработчиков для C++").

Дополнительные сведения см. в статье [Новые возможности Visual C++ в Visual Studio 2017](/cpp/top/what-s-new-for-visual-cpp-in-visual-studio).

### <a name="debugging-and-diagnostics"></a>Отладка и диагностика

#### <a name="run-to-click"></a>Выполнение до щелкнутого

Теперь вы можете выполнить более простой переход в процессе отладки. Нет необходимости настраивать точки останова, чтобы остановиться на нужной строке. При остановке в отладчике просто щелкните значок рядом со строкой кода. Выполнение кода остановится на выбранной строке, когда в следующий раз дойдет до нее.

![Отладка Visual Studio 2017 — выполнение до щелчка](media/vs2017ide-RunToClick.png)

#### <a name="the-new-exception-helper"></a>Новый помощник по исправлению ошибок

Новый помощник по исправлению ошибок поможет мгновенно просмотреть сведения об исключении. Данные представлены кратко и содержательно. Вы также можете получить быстрый доступ к внутренним исключениям. При диагностике исключения NullReferenceException вы сможете быстро увидеть, какой параметр имел значение NULL, прямо в помощнике по исправлению ошибок.

![Новое диалоговое окно помощника по исправлению ошибок в Visual Studio](media/vs2017ide-ExceptionHelper.png)

Дополнительные сведения см. в публикации [Use the new Exception Helper in Visual Studio](https://blogs.msdn.microsoft.com/devops/2016/03/31/using-the-new-exception-helper-in-visual-studio-15-preview/) (Использование нового помощника по исправлению ошибок в Visual Studio).

#### <a name="snapshots-and-intellitrace-step-back"></a>Моментальные снимки и возможность возврата на шаг назад в IntelliTrace

**Новая возможность в версии 15.5**: Функция возврата на шаг назад в IntelliTrace автоматически создает моментальный снимок вашего приложения для каждого события точки останова и шага отладчика. Используя записанные моментальные снимки, вы можете возвращаться к этим точкам останова и шагам, просматривая предыдущее состояние приложения. Возможность возврата на шаг назад в IntelliTrace позволяет сэкономить время в тех случаях, когда вам нужно просмотреть предыдущее состояние приложения, но не требуется перезапускать отладку или воссоздавать необходимое состояние приложения.

Для просмотра моментальных снимков и перехода между ними используйте кнопки **На шаг назад** и **На шаг вперед** на панели инструментов **Отладка**. С помощью этих кнопок можно перейти к событиям, которые отображаются на вкладке **События** в окне **Средства диагностики**. При переходе на шаг назад или вперед к событию автоматически активируется отладка с ведением журнала для выбранного события.

![Диалоговое окно нового помощника по исправлению ошибок в Visual Studio](../debugger/media/intellitrace-step-back-icons-description.png  "Кнопки \"На шаг назад\" и \"На шаг вперед\"")

Дополнительные сведения см. на странице [Просмотр моментальных снимков с использованием возврата на шаг назад в IntelliTrace](../debugger/view-historical-application-state.md).

### <a name="containerization"></a>Контейнеризация

Применение контейнеров позволяет повысить плотность и снизить стоимость развертывания приложений, одновременно с этим повышая производительность и гибкость возможностей DevOps.

#### <a name="docker-container-tooling"></a>Инструменты работы с контейнерами Docker

**Новая возможность в версии 15.5**:

* Visual Studio включает инструменты для контейнеров Docker, которые поддерживают многоэтапные файлы Dockerfile, позволяющие упростить создание оптимизированных образов контейнеров.
* По умолчанию Visual Studio будет автоматически извлекать, собирать и запускать необходимые образы контейнеров в фоновом режиме при открытии проекта, который поддерживает Docker. Это поведение можно отключить с помощью параметра **Автоматически запускать контейнеры в фоновом режиме** в Visual Studio.

## <a name="cloud-app-development-with-azure"></a>Разработка облачных приложений с помощью Azure

### <a name="azure-functions-tools"></a>Средства функций Azure

В рамках рабочей нагрузки "Разработка для Azure" мы включили средства, упрощающие разработку функций Azure с помощью предварительно скомпилированных библиотек классов C#. Теперь вы можете создавать, запускать проекты и выполнять их отладку на локальном компьютере разработчика, а затем публиковать их из Visual Studio непосредственно в Azure.

Дополнительные сведения см. на странице [Средства функций Azure для Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-develop-vs).

### <a name="debug-live-aspnet-apps-using-snappoints-and-logpoints-in-live-azure-applications"></a>Отладка работающих приложений ASP.NET с использованием точек прикрепления и точек ведения журнала в работающих приложениях Azure

**Новая возможность в версии 15.5**: Средство Snapshot Debugger создает моментальный снимок рабочих приложений при выполнении интересующего вас кода. Чтобы указать отладчику на необходимость создать моментальный снимок, следует установить точки прикрепления и точки ведения в коде. Отладчик позволяет увидеть источник ошибки, не затрагивая трафик рабочего приложения. Средство Snapshot Debugger позволяет значительно сократить затраты времени на устранение проблем, возникающих в рабочих средах.

Коллекция моментальных снимков доступна для следующих веб-приложений, выполняющихся в службе приложений Azure App:

* Приложения ASP.NET, выполняющиеся на платформе .NET Framework 4.6.1 или более поздней версии.
* Приложения ASP.NET Core, выполняющиеся на платформе .NET Core 2.0 или более поздней версии под управлением Windows.

Дополнительные сведения см. в разделе [Отладка работающих приложений ASP.NET с использованием точек прикрепления и точек ведения журнала](../debugger/debug-live-azure-applications.md).

## <a name="windows-app-development"></a>Разработка приложений для Windows

### <a name="universal-windows-platform"></a>Универсальная платформа Windows 

Универсальная платформа Windows (UWP) — это платформа приложений для Windows 10. Вы можете разрабатывать приложения для универсальной платформы Windows с одним набором API, одним пакетом приложений и одним хранилищем для всех устройств под управлением Windows 10 &ndash; персональных компьютеров, планшетов, телефонов, игровых консолей Xbox, очков HoloLens, Surface Hub и многих других. Универсальная платформа Windows поддерживает различные размеры экранов и широкий спектр моделей взаимодействия, включая сенсорный ввод, мышь и клавиатуру, игровой контроллер или перо. В основе приложений UWP лежит представление о том, что пользователи хотят использовать возможности мобильного интерфейса на всех устройствах, выбирая наиболее удобное и производительное устройство в зависимости от стоящих перед ними задач.

 ![Универсальная платформа Windows ](../cross-platform/media/uwp_coreextensions.png)

Выберите предпочтительный язык разработки (&mdash;C#, Visual Basic, C++ или JavaScript&mdash;), чтобы создать приложение универсальной платформы Windows для устройств Windows 10. В Visual Studio 2017 представлены шаблоны приложений для универсальной платформы Windows для каждого языка, благодаря которым вы сможете создавать единый проект для всех устройств. После завершения работы вы можете создать пакет приложений и загрузить его из Visual Studio в интернет-магазин Microsoft Store, где он будет доступен покупателям с любыми устройствами под управлением Windows 10.

**Новая возможность в версии 15.5**: Версия 15.5 среды Visual Studio 2017 обеспечивает наилучшую поддержку пакета SDK Windows 10 Fall Creators Update (10.0.16299.0). В Windows 10 Fall Creators Update также реализовано множество улучшений для разработчиков приложений для универсальной платформы Windows. Ниже приведены некоторые из основных изменений: 

* **Поддержка .NET Standard 2.0**<br/>Помимо оптимизированного развертывания приложений, в обновлении Windows 10 Fall Creators Update впервые в Windows 10 реализована поддержка .NET Standard 2.0. Фактически [.NET Standard](https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/) — это эталонная реализация библиотеки базовых классов, которые могут реализовываться на любой платформе .NET. Основная цель .NET Standard — максимально упростить разработчикам совместное использование кода на любой выбранной для работы платформе .NET.
* **Сочетание лучших возможностей универсальной платформы Windows и Win32**<br/>Чтобы улучшить платформу Windows 10 и максимально упростить работу с ней для разработчиков любых приложений .NET, в том числе для универсальной платформы Windows, Windows Presentation Foundation, Windows Forms или Xamarin, мы представляем [мост для классических приложений](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-root). Благодаря новому типу проекта, "Пакет приложений", в Visual Studio 2017 версии 15.5 вы можете создавать пакеты приложений Windows для проектов Windows Presentation Foundation или Windows Forms так же, как и для проектов для универсальной платформы Windows. После упаковки приложения вы получаете все преимущества его развертывания в Windows 10 и возможность распространять его через магазин Microsoft Store (пользовательские приложения) или через магазин Microsoft Store для бизнеса и для образовательных учреждений. Поскольку упакованные приложения получают доступ ко всей области API универсальной платформы Windows и к API Win32 для классических приложений, теперь вы можете постепенно модернизировать свои приложения Windows Presentation Foundation и Windows, используя возможности API универсальной платформы Windows и Windows 10. Более того, вы можете включить в приложения для универсальной платформы Windows компоненты Win32, благодаря чему получите доступ к возможностям Win32 в классическом приложении.

Дополнительные сведения об универсальной платформе Windows см. на странице [Разработка приложений для универсальной платформы Windows (UWP)](../cross-platform/develop-apps-for-the-universal-windows-platform-uwp.md).

## <a name="mobile-app-development"></a>Разработка мобильных приложений

### <a name="xamarin"></a>Xamarin

В рамках рабочей нагрузки "Разработка мобильных приложения на .NET" разработчики, знакомые с C#, .NET и Visual Studio, могут доставлять собственные приложения Android, iOS и Windows с помощью Xamarin. Разработчики могут рассчитывать на такие же возможности и производительность при работе с Xamarin для мобильных приложений, включая удаленную отладку на устройствах Android, iOS и Windows, без необходимости изучать нативные языки, например Objective-C или Java. &mdash;

Дополнительные сведения см. на странице [Visual Studio и Xamarin](/xamarin/).

### <a name="entitlements-editor"></a>Редактор объемов обслуживания

**Новые возможности версии 15.3**: для выполнения задач разработки для iOS мы добавили автономный редактор объемов обслуживания. Он имеет понятный пользовательский интерфейс с простой функциональностью. Чтобы запустить его, дважды щелкните файл *entitlements.plist*.

![Редактор назначения для Xamarin](media/xamarin-entitlements-editor.png)

### <a name="visual-studio-tools-for-xamarin"></a>Инструменты Visual Studio для Xamarin

**Новая возможность в версии 15.4**: Xamarin Live позволяет разработчикам непрерывно развертывать, тестировать и отлаживать свои приложения прямо на устройствах iOS и Android. Скачав Xamarin Live Player из &mdash;App Store или Google Play&mdash;, можно связать устройство с Visual Studio и кардинально изменить подход к созданию мобильных приложений. Эта функциональность сейчас включена в Visual Studio, и ее можно включить, перейдя в меню **Сервис** > **Параметры** > **Xamarin** > **Другие** > **Включить Xamarin Live Player**.

![Анимация режимов сопряжения, развертывания и динамического редактирования Xamarin Live Player](media/xamarinliveplayer.gif)

### <a name="support-for-google-android-emulator"></a>Поддержка Google Android Emulator

**Новая возможность в версии 15.8**: при использовании Hyper-V вы теперь можете использовать Google Android Emulator параллельно с другими технологиями на базе Hyper-V, включая виртуальные машины Hyper-V, инструменты для работы с Docker, эмулятор HoloLens и многое другое. (Для этой функции требуется обновление Windows от 10 апреля 2018 г. или более позднее.)

![Эмулятор Google Android с технологиями Hyper-V](media/xamarin-hyperv-android-emulator.png)

#### <a name="xamarinandroid-designer-split-view-editor"></a>Редактор Xamarin.Android Designer с разделенным экраном

Еще одна **новая возможность в версии 15.8**: мы внесли значительные улучшения в среду разработки Xamarin.Android. Главное нововведение — добавлен новый редактор с разделенным экраном, позволяющий одновременно создавать, редактировать и просматривать макеты.

![Редактор Xamarin.Android Designer с разделенным экраном](media/android-designer-split-view.png)

Дополнительные сведения см. в статье [Аппаратное ускорение эмулятора](/xamarin/android/get-started/installation/android-emulator/hardware-acceleration?tabs=vswin)

### <a name="visual-studio-app-center"></a>Центр приложений Visual Studio

**Новая возможность в версии 15.5**: центр приложений Visual Studio &mdash;теперь доступен для всех приложений Android, iOS, macOS и Windows&mdash; и предлагает все возможности, необходимые для управления жизненным циклом приложений, включая автоматическую сборку, тестирование на реальных устройствах в облаке, распространение версий для бета-тестирования и магазинов приложений, а также мониторинг реального использования приложений на основе сведений о сбоях и аналитических данных. Приложения, написанные на Objective-C, Swift, Java, C#, Xamarin и React Native, поддерживаются всеми компонентами.

  ![Тестовая среда центра приложений Visual Studio](media/app-center-test-env.png)

Дополнительные сведения см. в записи блога [Знакомство с Центром приложений: сборка, тестирование, распространение и мониторинг приложений в облаке](https://blogs.msdn.microsoft.com/vsappcenter/introducing-visual-studio-app-center/).

## <a name="cross-platform-development"></a>Кроссплатформенная разработка

### <a name="redgate-data-tools"></a>Средства для работы с данными Redgate

Чтобы расширить возможности DevOps для разработки баз данных SQL Server, в Visual Studio были добавлены средства для работы с данными Redgate.

В составе Visual Studio 2017 Enterprise:

* [Redgate ReadyRoll Core](http://www.red-gate.com/products/sql-development/readyroll/entrypage/microsoft-and-readyroll?utm_source=microsoft&utm_medium=link&utm_campaign=readyroll&utm_term=docs-newinvs) помогает разрабатывать скрипты переноса, управлять изменениями в базах данных с помощью системы управления версиями, а также автоматизировать безопасное развертывание изменений базы данных SQL Server вместе с изменениями приложений.
* [Redgate SQL Prompt Core](http://www.red-gate.com/products/sql-development/sql-prompt/entrypage/microsoft-and-sql-prompt?utm_source=microsoft&utm_medium=link&utm_campaign=sqlprompt&utm_term=docs-newinvs) помогает писать запросы SQL быстрее и точнее с помощью интеллектуального завершения кода. SQL Prompt автоматически завершает объекты и ключевые слова базы данных и системы и предлагает варианты при вводе текста. Код становится чище и содержит меньше ошибок, так как вам не нужно запоминать имя или псевдоним каждого столбца.

В составе всех выпусков Visual Studio 2017:

* [Redgate SQL Search](http://www.red-gate.com/products/sql-development/sql-search/?utm_source=microsoft&utm_medium=link&utm_campaign=sqlsearch&utm_term=docs-newinvs) повышает продуктивность работы, позволяя быстро находить фрагменты и объекты SQL в нескольких базах данных.

Дополнительные сведения см. в статье блога [Средства работы с данными Redgate в Visual Studio 2017](https://blogs.msdn.microsoft.com/visualstudio/2017/03/07/redgate-data-tools-in-visual-studio-2017/).

### <a name="net-core"></a>.NET Core

.NET Core — это универсальная, модульная, кроссплатформенная и открытая версия платформы .NET Standard, которая содержит множество тех же API, что и .NET Framework.

Платформа .NET Core состоит из нескольких компонентов, включая управляемые компиляторы, среду выполнения, библиотеки базовых классов и многочисленные модели приложений, такие как ASP.NET Core. Она поддерживает три основные операционные системы: Windows, Linux и macOS. .NET Core можно использовать при работе с устройствами, облаком, а также в сценариях внедрения и Интернета вещей.

А теперь она включает поддержку Docker.

**Новые возможности версии 15.3**: Visual Studio 2017 версии 15.3 поддерживает разработку .NET Core 2.0. Для использования .NET Core 2.0 необходимо отдельно скачать и установить пакет SDK для .NET Core 2.0.

Дополнительные сведения см. в [руководстве по .NET Core](/dotnet/core/index).

## <a name="games-development"></a>Разработка игр

### <a name="visual-studio-tools-for-unity"></a>Набор средств Visual Studio для Unity

В рамках рабочей нагрузки "Разработка игр для Unity" мы включили средства для разработки кроссплатформенных приложений для создания двумерных и трехмерных игр и интерактивного содержимого. Создайте одну игру и опубликуйте ее на 21 платформе, включая все мобильные платформы, WebGL, настольные системы (Mac, ПК и Linux), Интернет или приставки, с помощью Visual Studio 2017 и Unity 5.6.

Дополнительные сведения см. на странице сведений об [инструментах Visual Studio для Unity](../cross-platform/visual-studio-tools-for-unity.md).

## <a name="ai-development"></a>Разработка для сценариев ИИ

### <a name="visual-studio-tools-for-ai"></a>Инструменты Visual Studio для сценариев ИИ

**Новая возможность в версии 15.5**: Эффективные возможности Visual Studio позволяют ускорить инновации в области ИИ. Используйте встроенные функции редактора кода, такие как выделение синтаксических конструкций, IntelliSense и автоматическое форматирование текста. Вы можете тестировать приложение для глубинного обучения в локальной среде в интерактивном режиме, применяя пошаговую отладку локальных переменных и моделей.

  ![Интегрированная среда разработки для глубинного обучения](../ai/media/about/ide.png)

Дополнительные сведения см. на странице [Инструменты Visual Studio для сценариев ИИ](../ai/about-ai-tools.md).

## <a name="whats-next"></a>Дальнейшие действия

Мы часто добавляем в Visual Studio 2017 новые функции, облегчающие разработку. Ниже перечислены некоторые из наиболее важных обновлений, входящих в экспериментальную предварительную версию:

* **[Live Share](https://visualstudio.microsoft.com/services/live-share/)**  — это новое средство, которое позволяет предоставить базу кода и соответствующий контекст коллеге и обеспечить двунаправленное взаимодействие непосредственно из среды Visual Studio. Благодаря Live Share коллега может легко и безопасно просматривать, изменять и отлаживать проект, предоставленный вами для общего доступа.<br><br>Дополнительные сведения см. в разделе [Часто задаваемые вопросы по Live Share](/visualstudio/liveshare/faq).<br><br>
* **[IntelliCode](https://visualstudio.microsoft.com/services/intellicode/)**  — это новая функция, которая расширяет возможности разработки программного обеспечения и использует ИИ, чтобы предоставлять более контекстно зависимые завершения кода, помогать разработчикам придерживаться шаблонов и стилей, принятых в их команде, находить неочевидные проблемы с кодом и концентрировать проверки кода на действительно важных областях. <br><br>Дополнительные сведения см. в разделе [Часто задаваемые вопросы по IntelliCode](/visualstudio/intellicode/faq).

Хотите ознакомиться с другими будущими возможностями для Visual Studio 2017? См. страницу [Стратегия развития Visual Studio](/visualstudio/productinfo/vs2018-roadmap).

## <a name="contact-us"></a>Обратная связь

 Зачем отправлять отзыв группе Visual Studio? Потому что мы серьезно относимся к отзывам клиентов. Они влияют на многие наши действия.

Если вы хотите внести предложение по улучшению Visual Studio или узнать о вариантах поддержки для продукта, см. страницу [Обращайтесь к нам](talk-to-us.md).

### <a name="report-a-problem"></a>Сообщите о проблеме

 Иногда для передачи всех последствий возникшей проблемы простого сообщения недостаточно. В случае зависания, сбоя или других проблем с производительностью вы можете предоставить нам шаги для воспроизведения и вспомогательные файлы (например, снимки экрана и файлы дампа трассировки и кучи) с помощью средства **Сообщить о проблеме**. Дополнительные сведения об использовании этого средства см. на странице [Как сообщить о проблеме](how-to-report-a-problem-with-visual-studio-2017.md).

## <a name="see-also"></a>См. также

* [Заметки о выпуске Visual Studio 2017](/visualstudio/releasenotes/vs2017-relnotes?context=visualstudio/default&contextView=vs-2017)
* [Новые возможности Visual C++](/cpp/top/what-s-new-for-visual-cpp-in-visual-studio)
* [Новые возможности C#](/dotnet/csharp/whats-new)
* [What's New for Team Foundation Server](/tfs/server/whats-new?view=vsts) (Новые возможности Team Foundation Server)
* [Новые возможности Visual Studio для Mac](https://visualstudio.microsoft.com/vs/visual-studio-mac/)
* [Новые возможности Visual Studio 2019](whats-new-visual-studio-2019.md)