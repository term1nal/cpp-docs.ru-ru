---
title: (C++ COM атрибут nonextensible) | Документация Майкрософт
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.nonextensible
dev_langs:
- C++
helpviewer_keywords:
- nonextensible attribute
ms.assetid: c7ef1554-809f-4ea0-a7cd-dc7786d40c3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 84f14cccdd4dd142f2fa6e17e48c37a3fecb94ea
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48792376"
---
# <a name="nonextensible"></a>nonextensible

Указывает, что `IDispatch` реализация содержит только свойства и методы, перечисленных в описании интерфейса и не может быть расширен с помощью дополнительных членов во время выполнения.

## <a name="syntax"></a>Синтаксис

```cpp
[nonextensible]
```

## <a name="remarks"></a>Примечания

**Nonextensible** атрибут C++ имеет ту же функциональность, что [nonextensible](/windows/desktop/Midl/nonextensible) описании атрибута MIDL.

Использование **nonextensible** также требуется [oleautomation](oleautomation.md) атрибута.

## <a name="example"></a>Пример

В следующем коде показано один из способов использования **nonextensible** атрибут:

```cpp
// cpp_attr_ref_nonextensible.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="ATLFIRELib")];
[export] typedef long HRESULT;

[dual, nonextensible, ms_union, oleautomation,
uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl
{
   HRESULT procedure (int i);
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**interface**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|`dual` и `oleautomation`, или `dispinterface`|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)  