---
title: コンパイラ エラー C3003 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3003
dev_langs:
- C++
helpviewer_keywords:
- C3003
ms.assetid: 22e74f99-bb7f-4518-ab0d-934d5d49bcc7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 48e3cdcb4df846414cc231999f85da05e3bb9995
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33241309"
---
# <a name="compiler-error-c3003"></a>コンパイラ エラー C3003
'directive': OpenMP ディレクティブ名は、ディレクティブ句の後には使用できません  
  
 OpenMP ディレクティブの名前は、OpenMP ディレクティブの句の後に続けることはできません。  
  
 次の例では C3003 が生成されます。  
  
```  
// C3003.c  
// compile with: /openmp  
int main()  
{  
   int x, y, z;  
   #pragma omp parallel shared(x, y, z) for   // C3003  
}  
```