---
title: "CCommand::ReleaseCommand | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CCommand.ReleaseCommand
- ReleaseCommand
- CCommand::ReleaseCommand
dev_langs: C++
helpviewer_keywords: ReleaseCommand method
ms.assetid: 3b58230c-13d5-45c5-b43e-bb013ecc3019
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a5787e031ca2874e201a0e904fd69aad62f767bb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ccommandreleasecommand"></a>CCommand::ReleaseCommand
Освобождает доступа к параметру, затем освобождает саму команду.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
void CCommandBase::ReleaseCommand( ) throw( );  
  
```  
  
## <a name="remarks"></a>Примечания  
 `ReleaseCommand`используется в сочетании с **закрыть**. В разделе [закрыть](../../data/oledb/ccommand-close.md) сведения об использовании.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [CCommand-класс](../../data/oledb/ccommand-class.md)   
 [CCommand::Close](../../data/oledb/ccommand-close.md)