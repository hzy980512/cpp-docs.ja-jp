---
title: コンパイラの警告 (レベル 1) C4145 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4145
dev_langs:
- C++
helpviewer_keywords:
- C4145
ms.assetid: 0440777a-cca2-4159-aff5-e67a254ad64a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a5803c8fee49c294823da4ecdb2b04638b763c00
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33277405"
---
# <a name="compiler-warning-level-1-c4145"></a>コンパイラの警告 (レベル 1) C4145
'expression1' : switch ステートメントの制御式と関係する式 ; 式 'expression2' は、case 式と見なされます  
  
 `switch` ステートメントで、関係式をその制御式として使用した結果、 **case** ステートメントにブール値が返されます。 *expression2*を意図していましたか。  
  
## <a name="example"></a>例  
 次の例では C4145 が生成されます。  
  
```  
// C4145.cpp  
// compile with: /W1  
int main() {  
   int i = 0;  
   switch(i == 1) {   // C4145, use i instead of i == 1 to resolve  
      case 1:  
         break;  
      default:  
         break;  
   }  
}  
```