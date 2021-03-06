---
title: Как синхронизировать наборы правил проекта кода с политикой возврата командного проекта | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.selecttfsruleset
ms.assetid: 9b02f934-2db6-41ec-aaff-9c31ceec2f04
caps.latest.revision: 14
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 3c6e7550940f9d2efa5ca228123310f1b861ee76
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2019
ms.locfileid: "72651602"
---
# <a name="how-to-synchronize-code-project-rule-sets-with-team-project-check-in-policy"></a>Практическое руководство. Синхронизация наборов правил проекта кода с политикой возврата командного проекта
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Вы синхронизируете параметры анализа кода для проектов кода с политикой возврата для командного проекта, указывая набор правил, который содержит по крайней мере правила, указанные в наборе правил для политики возврата. Руководитель разработчика может сообщить имя и расположение набора правил для политики возврата. Чтобы убедиться в том, что для анализа кода проекта используется правильный набор правил, можно использовать один из следующих параметров:

- Если политика возврата использует один из встроенных наборов правил Майкрософт, откройте диалоговое окно Свойства для проекта кода, отобразите страницу анализ кода и выберите набор правил на странице анализ кода в параметрах проекта кода. Стандартные наборы правил Майкрософт автоматически устанавливаются вместе с Visual Studio и не должны редактироваться. Если наборы правил не редактируются, то правила в политике и локальных наборах правил гарантированно совпадают.

- Если политика возврата использует настраиваемый набор правил, выполните операцию Get с файлом набора правил в системе управления версиями, чтобы создать локальную копию. Затем укажите это локальное расположение в параметрах анализа кода для проекта кода. Правила гарантированно сопоставлены, если набор правил для политики возврата обновлен.

     При сопоставлении расположения системы управления версиями с локальной папкой, которая находится в той же связи с корнем проекта в качестве проекта кода, расположение правила устанавливается с использованием относительного пути. Относительный путь гарантирует, что параметр проекта кода для анализа кода можно будет переместить на другие компьютеры.

- Настройте копию набора правил для политики возврата для проекта кода. Убедитесь, что новый набор правил содержит все правила в политике возврата, а также другие правила, которые необходимо включить. Необходимо убедиться, что набор правил включает все правила в наборе правил для политики возврата.

### <a name="to-specify-a-microsoft-standard-rule-set"></a>Указание набора стандартных правил Майкрософт

1. В **Обозреватель решений**щелкните правой кнопкой мыши проект кода и выберите пункт **свойства**.

2. Щелкните **анализ кода**.

3. В списке **выполнить этот набор правил** выберите набор правил политики возврата.

### <a name="to-specify-a-custom-check-in-policy-rule-set"></a>Указание пользовательского набора правил политики возврата

1. При необходимости выполните операцию Get с файлом набора правил, который указывает политику возврата.

2. В **Обозреватель решений**щелкните правой кнопкой мыши проект кода и выберите пункт **свойства**.

3. Щелкните **анализ кода**.

4. В списке **выполнить этот набор правил** щелкните **\<Browse... >** .

5. В диалоговом окне **Открыть** укажите файл набора правил политики возврата.

### <a name="to-create-a-custom-rule-set-for-a-code-project"></a>Создание настраиваемого набора правил для проекта кода

1. Выполните одну из процедур, описанных выше в этом разделе, чтобы выбрать политику возврата для командного проекта на странице анализ кода диалогового окна Параметры проекта.

2. Нажмите кнопку **Открыть**.

3. Добавление и удаление правил с помощью редактора набора правил.

     Дополнительные сведения см. в разделе [Создание настраиваемых наборов правил](../code-quality/creating-custom-code-analysis-rule-sets.md).

4. Сохраните измененный набор правил в RuleSet-файл на локальном компьютере или в UNC-путь.

5. Откройте диалоговое окно Свойства для проекта кода и отобразите страницу **анализ кода** .

6. В списке **выполнить этот набор правил** щелкните **\<Browse... >** .

7. В диалоговом окне **Открыть** укажите файл набора правил.
