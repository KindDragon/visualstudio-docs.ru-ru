---
title: IDebugClassField::EnumInterfacesImplemented | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugClassField::EnumInterfacesImplemented
helpviewer_keywords:
- IDebugClassField::EnumInterfacesImplemented method
ms.assetid: e5523e45-d350-491e-a92c-fe0ca97d2052
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: a5c951ac4f6f33495dad4136a1a09c11e639e029
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "66335356"
---
# <a name="idebugclassfieldenuminterfacesimplemented"></a>IDebugClassField::EnumInterfacesImplemented
Создает перечислитель для интерфейсов, реализованных данным классом.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT EnumInterfacesImplemented( 
   IEnumDebugFields** ppEnum
);
```

```csharp
int EnumInterfacesImplemented(
   out IEnumDebugFields ppEnum
);
```

## <a name="parameters"></a>Параметры
`ppEnum`\
[out] Возвращает [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) объект, представляющий список интерфейсов, реализованных. Возвращает значение null, если интерфейсы отсутствуют.

## <a name="return-value"></a>Возвращаемое значение
 В случае успешного выполнения возвращает значение S_OK, или возвращает значение S_FALSE, если нет интерфейсы, реализованные в этом классе. В противном случае возвращается код ошибки.

## <a name="remarks"></a>Примечания
 Каждый элемент перечисления является [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) описывающий интерфейс. Обратите внимание, что неуправляемые [!INCLUDE[vcprvc](../../../code-quality/includes/vcprvc_md.md)] код не использует интерфейсы как отдельная сущность, этот метод всегда возвращает значение null для неуправляемого [!INCLUDE[vcprvc](../../../code-quality/includes/vcprvc_md.md)] кода.

## <a name="see-also"></a>См. также
- [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)
- [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)