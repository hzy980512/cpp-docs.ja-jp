---
title: _com_error::HRESULTToWCode |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::HRESULTToWCode
dev_langs:
- C++
helpviewer_keywords:
- HRESULTToWCode method [C++]
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dbcbd73f1a4a6d80ed30a5d70ca43d5fe45677f9
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37941718"
---
# <a name="comerrorhresulttowcode"></a>_com_error::HRESULTToWCode
**Microsoft 固有の仕様**  
  
 16 ビットに 32 ビットの HRESULT をマップ`wCode`します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      static WORD HRESULTToWCode(  
   HRESULT hr   
) throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 *hr*  
 16 ビットにマップする 32 ビット HRESULT`wCode`します。  
  
## <a name="return-value"></a>戻り値  
 16 ビット`wCode`32 ビット HRESULT からマップされます。  
  
## <a name="remarks"></a>Remarks  
 参照してください[_com_error::wcode](../cpp/com-error-wcode.md)詳細についてはします。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_error::wcode](../cpp/com-error-wcode.md)   
 [_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)   
 [_com_error クラス](../cpp/com-error-class.md)