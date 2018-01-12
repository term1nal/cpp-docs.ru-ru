---
title: "Как: задание определенных политик планировщика | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- specifying scheduler policies [Concurrency Runtime]
- scheduler policies, specifying [Concurrency Runtime]
ms.assetid: 9c5149f9-ac34-4ff3-9e79-0bad103e4e6b
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: af30b38a89eb7e4b50c7d31be2d3ba6572843b1e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-specify-specific-scheduler-policies"></a>Практическое руководство. Задание определенных политик планировщика
Политики планировщика позволяют управлять стратегией, которую планировщик применяет при управлении задачами. В этом разделе показано, как использовать политики планировщика для повышения приоритета потока задачи, которая выводит индикатор хода выполнения на консоль.  
  
 Пример использования пользовательских политик планировщика совместно с асинхронными агентами см. в разделе [как: создание агентов, используйте определенные политики планировщика](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md).  
  
## <a name="example"></a>Пример  
 В следующем примере выполняется две задачи параллельно. Первая задача вычисляет n<sup>й</sup> числом Фибоначчи. Вторая задача выводит индикатор хода выполнения на консоль.  
  
 Первая задача использует рекурсивный развернутого для вычисления числа Фибоначчи. То есть каждая задача рекурсивно создает подзадачи для вычисления общего результата. Задача, которая используется рекурсивная декомпозиция может использовать все доступные ресурсы и тем самым незадействованным другие задачи. В этом примере задачу, которая выводит индикатор хода выполнения может не получить своевременный доступ к вычислительным ресурсам.  
  
 Чтобы обеспечить задачу, которая выводит сообщение о ходе выполнения, адекватный доступ к вычислительным ресурсам, в этом примере используется действия, описанные в [как: управление экземпляром планировщика](../../parallel/concrt/how-to-manage-a-scheduler-instance.md) для создания экземпляра планировщика с пользовательской политикой. Пользовательская политика задает приоритет потока для с наивысшим приоритетом.  
  
 В этом примере используется [concurrency::call](../../parallel/concrt/reference/call-class.md) и [concurrency::timer](../../parallel/concrt/reference/timer-class.md) классы для печати индикатор хода выполнения. Эти классы имеют варианты конструкторов, принимающие ссылку на [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) объекта, который планирует их. В примере используется планировщик по умолчанию для планирования задачи, которая вычисляет числа Фибоначчи и экземпляр планировщика для планирования задачи, который выводит индикатор хода выполнения.  
  
 Чтобы продемонстрировать преимущества использования планировщика с пользовательской политикой, в этом примере вся задача выполняется два раза. В примере сначала используется планировщик по умолчанию для планирования обеих задач. В примере затем используется планировщик по умолчанию для планирования первой задачи и планировщик с пользовательской политикой для планирования второй задачи.  
  
 [!code-cpp[concrt-scheduler-policy#1](../../parallel/concrt/codesnippet/cpp/how-to-specify-specific-scheduler-policies_1.cpp)]  
  
 В этом примере формируются следующие данные:  
  
```Output  
Default scheduler:  
...........................................................................done  
Scheduler that has a custom policy:  
...........................................................................done  
```  
  
 Несмотря на то, что оба набора задач дают одинаковый результат, версии, использующей настраиваемую политику включает задачу, которая выводит индикатор хода выполнения для запуска с повышенными приоритетом, чтобы более отзывчивое.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или вставить его в файл с именем `scheduler-policy.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **CL.exe/EHsc scheduler-policy.cpp**  
  
## <a name="see-also"></a>См. также  
 [Политики планировщика](../../parallel/concrt/scheduler-policies.md)   
 [Как: управление экземпляром планировщика](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)   
 [Практическое руководство. Создание агентов, использующих определенные политики планировщика](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)
