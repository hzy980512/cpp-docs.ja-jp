---
title: omp_get_num_procs |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_get_num_procs
dev_langs:
- C++
helpviewer_keywords:
- omp_get_num_procs OpenMP function
ms.assetid: 14a10b8f-e59b-4211-a292-687648c9f760
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b5d7e380e903f2d29896956eb8df1653c2c2bc7e
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691431"
---
# <a name="ompgetnumprocs"></a>omp_get_num_procs
関数が呼び出されたときに使用できるプロセッサの数を返します。  
  
## <a name="syntax"></a>構文  
  
```  
int omp_get_num_procs();  
```  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [3.1.5 omp_get_num_procs 関数](../../../parallel/openmp/3-1-5-omp-get-num-procs-function.md)です。  
  
## <a name="example"></a>例  
  
```  
// omp_get_num_procs.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main( )   
{  
    printf_s("%d\n", omp_get_num_procs( ));  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_num_procs( ));  
        }  
}  
```  
  
```Output  
// Expect the following output when the example is run on a two-processor machine:  
2  
2  
```  
  
## <a name="see-also"></a>関連項目  
 [関数](../../../parallel/openmp/reference/openmp-functions.md)