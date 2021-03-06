---
title: Создание проекта ИИ на основе имеющегося кода
author: lisawong19
ms.author: liwong
manager: routlaw
ms.date: 11/13/2017
ms.topic: conceptual
ms.workload:
- multiple
ms.openlocfilehash: 0981a276a21e1b3f816c6a182df29f1c4adb0d1c
ms.sourcegitcommit: 57bc1c3887838d707c13feff72a677b3bad3be4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72777444"
---
# <a name="create-an-ai-project-from-existing-code"></a>Создание проекта ИИ на основе имеющегося кода

[Установив инструменты Visual Studio для сценариев ИИ](installation.md), вы можете легко перенести существующий код Python в проект Visual Studio.

> [!Important]
> Описанный здесь процесс не перемещает и не копирует исходные файлы. Если вы хотите работать с копией, сначала создайте дубликат папки.

1. Запустите Visual Studio и последовательно выберите **"Файл" > "Создать" > "Проект"** .

2. В диалоговом окне **Создание проекта** найдите **Инструменты ИИ**, выберите шаблон **На основе существующего кода Python**, укажите имя и расположение проекта, а затем нажмите кнопку **ОК**.

   ![Создание нового проекта из существующего кода, шаг 1](media/create-project-existing/new-ai-project.png)

3. В появившемся мастере задайте путь к существующему коду, выберите фильтр по типам файлов и укажите все нужные вашему проекту пути поиска, после чего нажмите кнопку **ОК**. Если вы не знаете пути поиска, оставьте это поле пустым.

   ![Создание нового проекта из существующего кода, шаг 2](media/create-project-existing/azurebatch-newproject.png)

   Если существующий код входит в проект решения "Машинное обучение Azure", установите флажок **Является папкой решения "Машинное обучение Azure"** , чтобы корректно преобразовать важные сведения о конфигурации решения "Машинное обучение Azure" (например, используемую учетную запись экспериментирования, рабочую область, контексты вычислений).

4. Чтобы указать файл запуска, найдите его в **обозревателе решений**, щелкните его правой кнопкой мыши и выберите пункт **Задать как файл запуска**.

5. Запустите программу, нажав клавиши **CTRL**+**F5** или выбрав пункты **Отладка > Запуск без отладки**.

> [!div class="nextstepaction"]
> [Учебник. Работа с Python в Visual Studio](../python/tutorial-working-with-python-in-visual-studio-step-00-installation.md)

## <a name="see-also"></a>См. также

- [Определение существующего окружения Python вручную](../python/managing-python-environments-in-visual-studio.md#manually-identify-an-existing-environment)
