---
title: Задача GenerateTrustInfo | Документы Майкрософт
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, GenerateTrustInfo task
- GenerateTrustInfo task [MSBuild]
ms.assetid: 3ca60816-4bb0-4fef-ae43-ca0bfb63def3
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5b9c32681af56595f8b00feab4979a3ec45f1588
ms.sourcegitcommit: 2ae2436dc3484b9dfa10e0483afba1e5a02a52eb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/25/2020
ms.locfileid: "77578691"
---
# <a name="generatetrustinfo-task"></a>GenerateTrustInfo - задача
Создает доверие к приложению из базового манифеста и из параметров `TargetZone` и `ExcludedPermissions`.

## <a name="parameters"></a>Параметры
 В следующей таблице приводятся параметры задачи `GenerateTrustInfo` .

|Параметр|Описание|
|---------------|-----------------|
|`ApplicationDependencies`|Необязательный параметр <xref:Microsoft.Build.Framework.ITaskItem>`[]` .<br /><br /> Указывает зависимые сборки.|
|`BaseManifest`|Необязательный параметр <xref:Microsoft.Build.Framework.ITaskItem>.<br /><br /> Указывает базовый манифест, на основе которого будет сформировано доверие к приложению.|
|`ExcludedPermissions`|Необязательный параметр `String`.<br /><br /> Задает одно или несколько значений идентификаторов разрешений, разделенных точкой с запятой, которые должны быть исключены из набора разрешений зоны по умолчанию.|
|`TargetZone`|Необязательный параметр `String`.<br /><br /> Определяет набор разрешений зоны по умолчанию, получаемый из политики компьютера.|
|`TrustInfoFile`|Необязательный выходной параметр <xref:Microsoft.Build.Framework.ITaskItem>.<br /><br /> Указывает файл, содержащий сведения о безопасности доверия приложения.|

## <a name="remarks"></a>Примечания
 Помимо параметров, перечисленных в таблице, эта задача наследует параметры от класса <xref:Microsoft.Build.Tasks.TaskExtension>, который сам является производным от класса <xref:Microsoft.Build.Utilities.Task>. Список этих дополнительных параметров и их описания см. в статье [Базовый класс TaskExtension](../msbuild/taskextension-base-class.md).

## <a name="see-also"></a>См. также
- [Задачи](../msbuild/msbuild-tasks.md)
- [Справочные сведения о задачах](../msbuild/msbuild-task-reference.md)