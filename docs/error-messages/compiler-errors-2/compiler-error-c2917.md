---
title: コンパイラ エラー C2917 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2917
dev_langs:
- C++
helpviewer_keywords:
- C2917
ms.assetid: ec9da9ee-0f37-47b3-87dd-19ef5a14dc4c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ecc5f8634505dc8b63cb4cbdbbb9aa31973e7475
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33254551"
---
# <a name="compiler-error-c2917"></a>コンパイラ エラー C2917
'name' : 無効なテンプレートのパラメーターです。  
  
 テンプレートのパラメーター リストに、テンプレートのパラメーターでない識別子が含まれています。  
  
## <a name="example"></a>例  
 次の例では C2917 が生成されます。  
  
```  
// C2917.cpp  
// compile with: /c  
template<class T> class Vector {  
   void sort();  
};  
  
template<class T*> void Vector<T>::sort() {}   // C2917  
// try the following line instead  
// template<class T> void Vector<T>::sort() {}  
```