---
title: Учебник. Отладка кода C#
description: Сведения о запуске отладчика Visual Studio, пошаговой отладке кода и просмотру данных.
ms.custom: debug-experiment, seodec18, get-started
ms.date: 01/31/2020
ms.technology: vs-ide-debug
ms.topic: tutorial
dev_langs:
- CSharp
helpviewer_keywords:
- debugger
ms.assetid: 62734c0d-a75a-4576-8f73-0e97c19280e1
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6ede47c9daf37011195d66c746498cdfc809d24b
ms.sourcegitcommit: b2fc9ac7d73c847508f6ed082bed026476bb3955
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2020
ms.locfileid: "77027255"
---
# <a name="tutorial-learn-to-debug-c-code-using-visual-studio"></a>Учебник. Сведения об отладке кода C# с помощью Visual Studio

В этом пошаговом руководстве рассматриваются возможности отладчика Visual Studio. Более полное описание функций отладчика см. в статье c [Знакомство с отладчиком Visual Studio](../../debugger/debugger-feature-tour.md). *Отладка приложения* обычно означает запуск и выполнение приложения с подключенным отладчиком. При этом в отладчике доступно множество способов наблюдения за выполнением кода. Вы можете пошагово перемещаться по коду и просматривать значения, хранящиеся в переменных, задавать контрольные значения для переменных, чтобы отслеживать изменение значений, изучать путь выполнения кода, просматривать выполнение ветви кода и т. д. Если вы не знакомы с процессом отладки, перед выполнением задач в этой статье рекомендуется прочесть документ об [отладке для начинающих](../../debugger/debugging-absolute-beginners.md).

Несмотря на то, что демонстрационное приложение написано на C#, большинство функций применимы к C++, Visual Basic, F#, Python, JavaScript и другим языкам, поддерживаемым Visual Studio (F# не поддерживает возможность "Изменить и продолжить"). F# и JavaScript не поддерживают окно **Видимые**). На снимках экрана представлены примеры на C#.

В этом руководстве рассмотрены следующие задачи:

> [!div class="checklist"]
> * Запуск отладчика и попадание в точки останова.
> * Использование команд для пошагового выполнения кода в отладчике.
> * Проверка переменных в подсказках к данным и окнах отладчика.
> * Просмотр стека вызовов

## <a name="prerequisites"></a>Предварительные требования

::: moniker range=">=vs-2019"

У вас должна быть установлена среда Visual Studio 2019 и рабочая нагрузка **Кроссплатформенная разработка .NET Core**.

::: moniker-end
::: moniker range="vs-2017"

У вас должна быть установлена среда Visual Studio 2017 и рабочая нагрузка **Кроссплатформенная разработка .NET Core**.

::: moniker-end

::: moniker range="vs-2017"

Установите Visual Studio бесплатно со страницы [скачиваемых материалов Visual Studio](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download), если еще не сделали этого.

::: moniker-end

::: moniker range="vs-2019"

Установите Visual Studio бесплатно со страницы [скачиваемых материалов Visual Studio](https://visualstudio.microsoft.com/downloads), если еще не сделали этого.

::: moniker-end

Если вам нужно установить рабочую нагрузку, но вы уже используете Visual Studio, выберите пункт **Средства** > **Получить средства и компоненты...** , после чего запустится Visual Studio Installer. Запускается Visual Studio Installer. Выберите рабочую нагрузку **Кроссплатформенная разработка .NET Core** и затем элемент **Изменить**.

## <a name="create-a-project"></a>Создание проекта

Сначала вы создадите проект консольного приложения .NET Core. Для этого типа проекта уже имеются все нужные файлы шаблонов, что избавляет вас от лишней работы.

::: moniker range="vs-2017"

1. Откройте Visual Studio 2017.

2. В верхней строке меню последовательно выберите **Файл** > **Создать** > **Проект**.

3. В левой области диалогового окна **Новый проект** разверните узел **C#** и выберите **.NET Core**. На средней панели выберите **Консольное приложение (.NET Core)** . Назовите проект *get-started-debugging*.

     Если шаблона проекта **Console App (.NET Core)** (Консольное приложение (.NET Core)) нет, выберите ссылку **Открыть Visual Studio Installer** в левой области диалогового окна **Новый проект**.

     Запускается Visual Studio Installer. Выберите рабочую нагрузку **Кроссплатформенная разработка .NET Core** и затем элемент **Изменить**.

::: moniker-end

::: moniker range="vs-2019"

1. Запустите Visual Studio 2019.

   Если окно запуска не открыто, выберите **Файл** > **Окно запуска**.

1. На начальном экране выберите **Создать проект**.

1. В поле поиска окна **Создание проекта** введите *консоль*. Затем выберите **C#** в списке языков и **Windows** в списке платформ. 

   Применив фильтры языка и платформы, выберите шаблон **Консольное приложение (.NET Core)** и нажмите кнопку **Далее**.

   ![Выбор шаблона C# для консольного приложения (.NET Core)](../csharp/media/vs-2019/get-started-create-console-project.png)

   > [!NOTE]
   > Если шаблон **Консольное приложение (.NET Core)** отсутствует, его можно установить из окна **Создание проекта**. В сообщении **Не нашли то, что искали?** выберите ссылку **Установка других средств и компонентов**. После этого в Visual Studio Installer выберите рабочую нагрузку **Кроссплатформенная разработка .NET Core**.

1. В поле **Имя проекта** окна **Настроить новый проект** введите *GetStartedDebugging*. Затем нажмите **Создать**.

   Новый проект открывается в Visual Studio.
   
::: moniker-end

## <a name="create-the-application"></a>Создание приложения

1. Откройте файл *Program.cs* и замените все его содержимое по умолчанию следующим кодом:

    ```csharp
    using System;
    class ArrayExample
    {
        static void Main()
        {
            char[] letters = { 'f', 'r', 'e', 'd', ' ', 's', 'm', 'i', 't', 'h'};
            string name = "";
            int[] a = new int[10];
            for (int i = 0; i < letters.Length; i++)
            {
                name += letters[i];
                a[i] = i + 1;
                SendMessage(name, a[i]);
            }
            Console.ReadKey();
        }
        static void SendMessage(string name, int msg)
        {
            Console.WriteLine("Hello, " + name + "! Count to " + msg);
        }
    }
    ```

## <a name="start-the-debugger"></a>Запуск отладчика

1. Нажмите клавишу **F5** (**Отладка > Начать отладку**) или кнопку **Начать отладку**![Начать отладку](../../debugger/media/dbg-tour-start-debugging.png "Начало отладки") на панели инструментов отладки.

     При нажатии клавиши **F5** происходит запуск приложения с присоединенным отладчиком. Но пока мы не сделали ничего особенного, чтобы проанализировать код. Поэтому приложение будет просто загружено, и вы увидите выходные данные консоли.

    ```cmd
    Hello, f! Count to 1
    Hello, fr! Count to 2
    Hello, fre! Count to 3
    Hello, fred! Count to 4
    Hello, fred ! Count to 5
    Hello, fred s! Count to 6
    Hello, fred sm! Count to 7
    Hello, fred smi! Count to 8
    Hello, fred smit! Count to 9
    Hello, fred smith! Count to 10
    ```

     В этом руководстве мы более подробно рассмотрим приложение с отладчиком и познакомимся с возможностями отладчика.

2. Остановите отладчик, нажав красную кнопку остановки ![Остановить отладку](../../debugger/media/dbg-tour-stop-debugging.png "Остановить отладку") (**SHIFT** + **F5**).

3. В окне консоли нажмите клавишу, чтобы закрыть его.

## <a name="set-a-breakpoint-and-start-the-debugger"></a>Установка точки останова и запуск отладчика

1. В цикле `for` функции `Main` установите точку останова, щелкнув левое поле следующей строки кода:

    `name += letters[i];`

    В месте установки точки останова появится красный круг ![Точка останова](../../debugger/media/dbg-breakpoint.png "Точка останова").

    Точки останова — это один из самых простых и важных компонентов надежной отладки. Точка останова указывает, где Visual Studio следует приостановить выполнение кода, чтобы вы могли проверить значения переменных или поведение памяти либо выполнение ветви кода.

2. Нажмите клавишу **F5** или кнопку **Начать отладку**![Начать отладку](../../debugger/media/dbg-tour-start-debugging.png "Начало отладки"). Запустится приложение и отладчик перейдет к строке кода, где задана точка останова.

    ![Установка точки останова и попадание в нее](../csharp/media/get-started-set-breakpoint.png)

    Желтая стрелка представляет оператор, на котором приостановлен отладчик. В этой же точке приостанавливается выполнение приложения (этот оператор пока не выполнен).

     Если приложение еще не запущено, клавиша **F5** запускает отладчик и останавливается в первой точке останова. В противном случае **F5** продолжает выполнение приложения до следующей точки останова.

    Точки останова полезны, если вам известны строка или раздел кода, которые вы хотите подробно изучить. Дополнительные сведения о различных типах точек останова, которые можно задать, например об условных точках останова, см. в разделе [Использование точек останова](../../debugger/using-breakpoints.md).

## <a name="navigate-code-in-the-debugger-using-step-commands"></a>Переход по коду в отладчике с помощью пошаговых команд

Здесь мы используем в основном сочетания клавиш, так как они позволяют быстро выполнять приложение в отладчике (эквивалентные команды, например команды меню, отображаются в круглых скобках).

1. Во время приостановки в цикле `for` в методе `Main` дважды нажмите клавишу **F11** (или выберите **Отладка > Шаг с заходом**), чтобы перейти в вызов метода `SendMessage`.

     После двойного нажатия клавиши **F11** вы должны находиться на следующей строке кода:

     `SendMessage(name, a[i]);`

1. Еще раз нажмите клавишу **F11**, чтобы выполнить шаг с заходом в метод `SendMessage`.

     Желтый указатель перемещается в метод `SendMessage`.

     ![Использование клавиши F11 для перехода в код](../csharp/media/get-started-f11.png "Шаг с заходом (F10)")

     F11 — это команда **Шаг с заходом**, которая выполняет приложение с переходом к следующему оператору. Клавишу F11 удобно использовать для более детальной проверки потока выполнения. (Мы также покажем другие варианты более быстрого перемещения по коду.) По умолчанию отладчик пропускает непользовательский код (дополнительные сведения см. в статье об [отладке в режиме "Только мой код"](../../debugger/just-my-code.md)).

     Предположим, что вы закончили изучать метод `SendMessage` и хотите выйти из него, но остаться в отладчике. Это можно сделать с помощью команды **Шаг с выходом**.

1. Нажмите сочетание клавиш **SHIFT** + **F11** (или **Отладка > Шаг с выходом**).

     Эта команда возобновляет выполнение приложения (и работу отладчика) до возврата данных текущим методом или текущей функции.

     Вы должны вернуться в цикл `for` в методе `Main`, приостановленный на вызове метода `SendMessage`.

1. Нажмите клавишу **F11** несколько раз, пока не вернетесь к вызову метода `SendMessage`.

1. Во время приостановки на вызове метода один раз нажмите клавишу **F10** (или выберите **Отладка > Шаг с обходом**).

     ![Использование клавиши F10 для обхода кода](../csharp/media/get-started-step-over.png "Шаг с обходом (F10)")

     Обратите внимание, что в этот раз отладчик не заходит в метод `SendMessage`. Клавиша **F10** перемещает отладчик без захода в функции или методы в коде приложения (код продолжает выполняться). Нажав клавишу **F10** (а не **F11**) в вызове метода `SendMessage`, мы пропускаем код реализации для `SendMessage` (пока это нас не интересует). Дополнительные сведения о различных способах перемещения по коду см. в разделе [Навигация по коду в отладчике](../../debugger/navigating-through-code-with-the-debugger.md).

## <a name="navigate-code-using-run-to-click"></a>Переход по коду с помощью команды "Выполнение до щелкнутого"

1. Нажмите клавишу **F5**, чтобы снова перейти к точке останова.

1. В редакторе кода прокрутите вниз и наведите указатель мыши на метод `Console.WriteLine` в методе `SendMessage`, чтобы в левой части появилась зеленая кнопка **Выполнение до щелкнутого**![](../../debugger/media/dbg-tour-run-to-click.png "RunToClick"). В подсказке для кнопки выводится "Выполнить до этого места".

     ![Использование функции выполнения до щелкнутого](../csharp/media/get-started-run-to-click.png "Выполнение до щелкнутого")

   > [!NOTE]
   > Кнопка **Выполнение до щелкнутого** впервые появилась в [!include[vs_dev15](../../misc/includes/vs_dev15_md.md)]. (Если кнопка с зеленой стрелкой отсутствует, воспользуйтесь клавишей **F11**, чтобы переместить отладчик в нужное место.)

2. Нажмите кнопку **Выполнение до щелкнутого**![Выполнение до щелкнутого](../../debugger/media/dbg-tour-run-to-click.png "RunToClick").

    Отладчик перемещается к методу `Console.WriteLine`.

    Использование этой кнопки аналогично установке временной точки останова. Функция **Выполнение до щелкнутого** удобна для быстрой работы в видимой области кода приложения (можно щелкнуть в любом открытом файле).

## <a name="restart-your-app-quickly"></a>Быстрый перезапуск приложения

Нажмите кнопку **Перезапустить** ![Перезапустить приложение](../../debugger/media/dbg-tour-restart.png "RestartApp") на панели инструментов отладки (**CTRL** + **SHIFT** + **F5**).

Кнопка **Перезапустить** позволяет сэкономить время, затрачиваемое на остановку приложения и перезапуск отладчика. Отладчик приостанавливается в первой точке останова, достигнутой при выполнении кода.

Отладчик еще раз останавливается в точке останова, ранее заданной вами в цикле `for`.

## <a name="inspect-variables-with-data-tips"></a>Проверка переменных с помощью подсказок по данным

Функции, позволяющие проверять переменные, являются самыми полезными возможностями отладчика. Реализовывать эту задачу можно разными способами. Часто при попытке выполнить отладку проблемы пользователь старается выяснить, хранятся ли в переменных значения, которые требуются ему в определенное время.

1. При приостановке на операторе `name += letters[i]` наведите указатель мыши на переменную `letters` и увидите ее значение по умолчанию, а именно значение первого элемента в массиве — `char[10]`.

1. Разверните переменную `letters`, чтобы просмотреть ее свойства, включая все элементы, которые она содержит.

1. Затем наведите указатель мыши на переменную `name`, чтобы просмотреть ее текущее значение — пустую строку.

1. Несколько раз нажмите клавишу **F5** (или выберите **Отладка** > **Продолжить**), чтобы выполнить несколько итераций по циклу `for`, каждый раз снова приостанавливая выполнение в точке останова и наводя указатель мыши на переменную `name`, чтобы просмотреть ее значение.

     ![Просмотр подсказок по данным](../csharp/media/get-started-data-tip.gif "Просмотр подсказок по данным")

     Значение переменной изменяется при каждой итерации цикла `for` — `f`, затем `fr`, `fre` и т. д.

     Часто при отладке требуется быстро проверить значения свойств в переменных, чтобы убедиться, что в них хранятся ожидаемые значения. Советы по данным — отличный способ это сделать.

## <a name="inspect-variables-with-the-autos-and-locals-windows"></a>Проверка переменных с помощью окон "Видимые" и "Локальные"

1. Взгляните на окно **Видимые** в нижней части редактора кода.

    Если оно закрыто, откройте его во время приостановки в отладчике, выбрав **Отладка** > **Окна** > **Видимые**.

    В окне **Видимые** отображаются переменные и их текущие значения. В окне **Видимые** отображаются все переменные, используемые в текущей или предыдущей строке (сведения о зависящем от языка поведении см. в соответствующей документации).

1. Затем посмотрите на окно **Локальные** на вкладке рядом с окном **Видимые**.

1. Разверните переменную `letters`, чтобы отобразить элементы, которые она содержит.

     ![Проверка переменных в окне локальных переменных](../csharp/media/get-started-locals-window.png "Окно локальных значений")

    В окне **Локальные** показаны переменные, которые находятся в текущей [области](https://www.wikipedia.org/wiki/Scope_(computer_science)), то есть текущем контексте выполнения.

## <a name="set-a-watch"></a>Установка контрольного значения

1. В основном окне редактора кода щелкните правой кнопкой мыши переменную `name` и выберите команду **Добавить контрольное значение**.

    В нижней части редактора кода откроется окно **Контрольное значение**. В окне **Контрольное значение** можно указать переменную (или выражение), которую необходимо отслеживать.

    Теперь у вас есть контрольное значение, заданное для переменной `name`, и по мере перемещения по отладчику вы можете наблюдать за изменением его значения. В отличие от других окон переменных, в окне **Контрольное значение** всегда отображаются просматриваемые вами переменные (они выделяются серым цветом, когда находятся вне области действия).

## <a name="examine-the-call-stack"></a>Просмотр стека вызовов

1. Во время приостановки в цикле `for` щелкните окно **Стек вызовов**, которое по умолчанию открыто в нижней правой области.

    Если оно закрыто, откройте его во время приостановки в отладчике, выбрав **Отладка** > **Окна** > **Стек вызовов**.

2. Несколько раз нажмите клавишу **F11**, пока отладчик не приостановится в методе `SendMessage`. Взгляните на окно **Стек вызовов**.

    ![Изучение стека вызовов](../csharp/media/get-started-call-stack.png "ExamineCallStack")

    В окне **Стек вызовов** показан порядок вызова методов и функций. В верхней строке приведена текущая функция (в данном приложении метод `SendMessage`). Во второй строке показано, что функция `SendMessage` была вызвана из метода `Main` и т. д.

   > [!NOTE]
   > Окно **Стек вызовов** аналогично перспективе "Отладка" в некоторых интегрированных средах разработки, например Eclipse.

    Стек вызовов хорошо подходит для изучения и анализа потока выполнения приложения.

    Дважды щелкните строку кода, чтобы просмотреть исходный код. При этом также изменится текущая область, проверяемая отладчиком. Это действие не перемещает отладчик.

    Для выполнения других задач можно воспользоваться контекстными меню из окна **Стек вызовов**. Например, можно вставлять точки останова в указанные функции, перемещать отладчик с помощью функции **Выполнение до текущей позиции** и изучать исходный код. Дополнительные сведения см. в разделе [Практическое руководство. просмотреть стек вызовов](../../debugger/how-to-use-the-call-stack-window.md).

## <a name="change-the-execution-flow"></a>Изменение потока выполнения

1. Дважды нажмите клавишу **F11**, чтобы запустить метод `Console.WriteLine`.

1. Приостановив отладчик в вызове метода `SendMessage`, с помощью мыши захватите желтую стрелку (указатель выполнения) в левой части и переместите ее вверх на одну строку — обратно в `Console.WriteLine`.

1. Нажмите клавишу **F11**.

    Отладчик повторно выполнит метод `Console.WriteLine` (вы увидите это в выходных данных окна консоли).

    Изменяя поток выполнения, можно решать множество задач, например тестировать различные пути выполнения кода или повторно выполнять код без перезапуска отладчика.

    > [!WARNING]
    > Как правило, при работе с этой функцией необходимо соблюдать осторожность — вы увидите соответствующее предупреждение во всплывающей подсказке. Могут отображаться и другие предупреждения. При перемещении указателя предыдущее состояние приложения не возвращается.

1. Чтобы продолжить выполнение приложения, нажмите клавишу **F5**.

    Поздравляем с завершением этого учебника!

## <a name="next-steps"></a>Следующие шаги

В этом руководстве вы узнали, как запускать отладчик, осуществлять пошаговое выполнение кода и проверять переменные. Возможно, вы захотите получить более полное представление о функциях отладчика, а также воспользоваться ссылками на дополнительные сведения.

> [!div class="nextstepaction"]
> [Первое знакомство с отладчиком](../../debugger/debugger-feature-tour.md)
