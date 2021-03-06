---
title: -SafeMode (devenv.exe)
ms.date: 12/10/2018
ms.topic: reference
helpviewer_keywords:
- /SafeMode Devenv switch
- Devenv, /SafeMode switch
- SafeMode switch
ms.assetid: b191f6a5-8f12-47ec-bcc7-b68149a22aa8
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f180a45b274ec3042b7e150a43b5e8681fafcfed
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/01/2020
ms.locfileid: "75593594"
---
# <a name="safemode-devenvexe"></a>/SafeMode (devenv.exe)

Запускает Visual Studio в безопасном режиме, загружая только среду и службы по умолчанию.

## <a name="syntax"></a>Синтаксис

```shell
devenv /SafeMode
```

## <a name="remarks"></a>Примечания

Этот параметр запрещает загрузку пакетов VSPackage сторонних производителей при запуске Visual Studio, обеспечивая стабильное выполнение.

## <a name="example"></a>Пример

В приведенном ниже примере Visual Studio запускается в безопасном режиме.

```shell
devenv /safemode
```

## <a name="see-also"></a>См. также

- [Параметры командной строки для devenv](../../ide/reference/devenv-command-line-switches.md)
