---
title: num_threads | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- num_threads
dev_langs:
- C++
helpviewer_keywords:
- num_threads OpenMP clause
ms.assetid: 09a56fc8-25c7-43e4-bbb5-71cb955d0b93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 27e39d7db36c121add3598387de52ecb878059b5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405272"
---
# <a name="numthreads"></a>num_threads

Задает количество потоков в группе потоков.

## <a name="syntax"></a>Синтаксис

```
num_threads(num)
```

### <a name="parameters"></a>Параметры

*num*<br/>
Число потоков

## <a name="remarks"></a>Примечания

`num_threads` Предложение имеет ту же функциональность, что [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) функции.

`num_threads` область применения следующих директив:

- [parallel](../../../parallel/openmp/reference/parallel.md)

- [for](../../../parallel/openmp/reference/for-openmp.md)

- [Разделы](../../../parallel/openmp/reference/sections-openmp.md)

Дополнительные сведения см. в разделе [2.3 конструкция parallel](../../../parallel/openmp/2-3-parallel-construct.md).

## <a name="example"></a>Пример

См. в разделе [параллельных](../../../parallel/openmp/reference/parallel.md) пример использования `num_threads` предложение.

## <a name="see-also"></a>См. также

[Предложения](../../../parallel/openmp/reference/openmp-clauses.md)