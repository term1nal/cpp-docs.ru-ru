---
title: emitidl (атрибут COM C++) | Документация Майкрософт
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.emitidl
dev_langs:
- C++
helpviewer_keywords:
- emitidl attribute
ms.assetid: 85b80c56-578e-4392-ac03-8443c74ebb7d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5e11e1ce061fcf2e9ce21155dcbeb93b45b66238
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48792377"
---
# <a name="emitidl"></a>emitidl

Указывает, обрабатываются ли все последующие атрибуты IDL и помещаются в созданного IDL-файла.

## <a name="syntax"></a>Синтаксис

```cpp
[ emitidl(state, defaultimports=boolean) ];
```

### <a name="parameters"></a>Параметры

*state*<br/>
Одно из следующих возможных значений: `true`, `false`, `forced`, `restricted`, `push`, или `pop`.

- Если `true`, категории атрибуты IDL в файл исходного кода, помещаются в созданного IDL-файла. Это параметр по умолчанию для **emitidl**.

- Если `false`, категории атрибуты IDL в файл исходного кода не помещаются в созданного IDL-файла.

- Если `restricted`, позволяет атрибуты IDL в файл без [модуль](module-cpp.md) атрибута. Компилятор не создает файл IDL.

- Если `forced`, переопределяет последующая `restricted` атрибут, который требуется файл иметь `module` атрибут при наличии IDL атрибуты в файле.

- `push` позволяет сохранить текущий **emitidl** параметры во внутренний **emitidl** стека, и `pop` позволяет задать **emitidl** любое значение, которое в верхней части внутренний **emitidl** стека.

`defaultimports=`*логическое* \(необязательно)  
- Если *логическое* — **true**, docobj.idl импортируется в созданного IDL-файла. Кроме того Если файл IDL-файле с тем же именем, что .h, который был `#include` в ваш исходный код находится в том же каталоге, что в h-файл, а затем для созданного IDL-файла содержит оператор импорта для этого IDL-файла.

- Если *логическое* — **false**, docobj.idl не импортируется в созданного IDL-файла. Необходимо явно импортировать IDL-файлы с [импорта](import.md).

## <a name="remarks"></a>Примечания

После **emitidl** обнаруживается атрибут C++ в файл исходного кода, атрибуты IDL категории помещаются в созданного IDL-файла. Если не **emitidl** атрибутов, атрибуты IDL в исходном файле кода выводятся для созданного IDL-файла.

Можно иметь несколько **emitidl** атрибутов в файл исходного кода. Если `[emitidl(false)];` встречается в файле без последующей `[emitidl(true)];`, то атрибуты не обрабатываются в созданного IDL-файла.

Каждый раз, когда компилятор обнаруживает новый файл, **emitidl** неявно устанавливается значение **true**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|В любом месте|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты компилятора](compiler-attributes.md)<br/>
[Изолированные атрибуты](stand-alone-attributes.md)  
