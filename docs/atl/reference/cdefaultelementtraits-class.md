---
title: Класс CDefaultElementTraits | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CDefaultElementTraits
- atlcoll/ATL::CDefaultElementTraits
dev_langs:
- C++
helpviewer_keywords:
- CDefaultElementTraits class
ms.assetid: ac5ee610-7957-4b7c-92b6-38ff72e4118e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 44822df983021846e9b4168343252affd971accd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097280"
---
# <a name="cdefaultelementtraits-class"></a>Класс CDefaultElementTraits

Этот класс предоставляет функции и методы по умолчанию для класса коллекции.

## <a name="syntax"></a>Синтаксис

```
template <typename T>
class CDefaultElementTraits : public CElementTraitsBase<T>,
    public CDefaultHashTraits<T>,
    public CDefaultCompareTraits<T>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных, хранимых в коллекции.

## <a name="remarks"></a>Примечания

Этот класс предоставляет статические функции по умолчанию и методы для перемещения, копирования, сравнение и хэширования элементов, сохраненную в объекте класса коллекции. Этот класс является производным, его функции и методы из [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md), [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md), и [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)и используемой [ CElementTraits](../../atl/reference/celementtraits-class.md), [CPrimitiveElementTraits](../../atl/reference/cprimitiveelementtraits-class.md), и [CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md).

Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
