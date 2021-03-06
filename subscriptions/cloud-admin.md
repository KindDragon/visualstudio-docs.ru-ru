---
title: Настройка администраторов для облачных подписок | Документы Майкрософт
author: evanwindom
ms.author: jaunger
manager: lank
ms.date: 07/17/2019
ms.topic: conceptual
description: Настройка администраторов для облачных подписок
ms.openlocfilehash: 62a350e6061444e3c75878dfd89739011c4641d5
ms.sourcegitcommit: 57866dd72fd0e15ce61128df70729b427a2d02eb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2019
ms.locfileid: "68315205"
---
# <a name="set-up-administrators-for-visual-studio-cloud-subscriptions"></a>Настройка администраторов для облачных подписок Visual Studio

Облачные подписки Visual Studio управляются администраторами. Они могут назначать подписки, изменять назначения, добавлять или удалять подписки и выполнять другие задачи управления подписками.

## <a name="the-azure-subscription-owner-is-the-first-administrator"></a>Владелец подписки Azure является первым администратором

При приобретении облачных подписок Visual Studio владелец используемой для приобретений подписки Azure автоматически становится администратором подписок.

Вы можете приобрести облачные подписки с помощью [Visual Studio Marketplace](https://marketplace.visualstudio.com/subscriptions) или обратившись к поставщику облачных решений. При покупке через Visual Studio Marketplace в конце процедуры приобретения вам будет предоставлена возможность управления пользователями. При выборе этого параметра вы будете перенаправлены на портал администрирования подписок Visual Studio — [https://manage.visualstudio.com](https://manage.visualstudio.com).

После приобретения подписки вы можете заходить на [портал администрирования](https://manage.visualstudio.com) в любое время. Просто выполните вход на портал и выберите соответствующую подписку Azure в верхнем левом углу.

Владельцы подписок Azure, используемой для приобретения облачных подписок, также могут назначать дополнительных администраторов.

## <a name="add-administrators"></a>Добавление администраторов

Чтобы добавить администраторов:

1. Подключитесь к порталу Azure на сайте [portal.azure.com](https://portal.azure.com).
2. Войдите с помощью учетной записи, используемой для приобретения облачных подписок Visual Studio.
3. В области навигации слева прокрутите вниз до **Управление затратами + выставление счетов**.
4. В списке **Мои подписки** выберите подписку Azure, которая использовалась для покупки.
5. Нажмите кнопку **Управление доступом**, расположенную в верхней части списка в области навигации слева.
6. Нажмите на вкладку **Добавить** в верхней части страницы.
7. Выберите команду **Добавить назначение ролей**.
8. На всплывающей панели справа щелкните раскрывающийся список **Роль** в верхней части панели, прокрутите список вниз и выберите **Администратор доступа пользователей**.
9. В списке пользователей прокрутите вниз до пользователя, которого хотите сделать администратором, и выберите его. 
10. Нажмите кнопку **Сохранить**.
11. Перейдите на вкладку **Назначения ролей**, чтобы убедиться, что выбранный пользователь отображается в качестве администратора доступа пользователей.

Новый администратор может теперь войти на [портал администрирования](https://manage.visualstudio.com), выбрать из списка в верхнем левом углу страницы подписку Azure, которая была использована для приобретения облачных подписок, и начать управлять этими подписками.

> [!NOTE]
> Если пользователи, для которых вы не настраивали права администраторов, могут изменять облачные подписки, возможно, у них есть роли в базовой подписке Azure, позволяющие управлять подписками. Это могут быть следующие роли: владелец, участник, администратор служб или соадминистратор. Дополнительные сведения см. в статье [Добавить менеджеров по выставлению счетов](/azure/devops/organizations/billing/add-backup-billing-managers?view=vsts).

Сведения об облачных подписках Visual Studio см. в статье [Обзор](vscloud-overview.md) в разделе "Приобретение подписок". Чтобы приобрести облачные подписки Visual Studio, посетите Visual Studio Marketplace по адресу [https://marketplace.visualstudio.com/subscriptions](https://marketplace.visualstudio.com/subscription).
