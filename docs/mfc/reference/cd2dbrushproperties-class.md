---
title: CD2DBrushProperties クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties::CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties::CommonInit
dev_langs:
- C++
helpviewer_keywords:
- CD2DBrushProperties [MFC], CD2DBrushProperties
- CD2DBrushProperties [MFC], CommonInit
ms.assetid: c77d717f-0a16-4d74-b2ce-0ae1766ed6f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 897be7063385566f2fd0e717eba0f89b335c2c48
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36950414"
---
# <a name="cd2dbrushproperties-class"></a>CD2DBrushProperties クラス
`D2D1_BRUSH_PROPERTIES`のラッパー。  
  
## <a name="syntax"></a>構文  
  
```  
class CD2DBrushProperties : public D2D1_BRUSH_PROPERTIES;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DBrushProperties::CD2DBrushProperties](#cd2dbrushproperties)|オーバーロードされます。 作成、`CD2D_BRUSH_PROPERTIES`構造体|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DBrushProperties::CommonInit](#commoninit)|オブジェクトを初期化します|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `D2D1_BRUSH_PROPERTIES`  
  
 `CD2DBrushProperties`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="cd2dbrushproperties"></a>  CD2DBrushProperties::CD2DBrushProperties  
 CD2D_BRUSH_PROPERTIES 構造を作成します。  
  
```  
CD2DBrushProperties();  
CD2DBrushProperties(FLOAT _opacity);

 
CD2DBrushProperties(
    D2D1_MATRIX_3X2_F _transform,  
    FLOAT _opacity = 1.);
```  
  
### <a name="parameters"></a>パラメーター  
 *_opacity*  
 ブラシの基本の不透明度。 既定値は 1.0 です。  
  
 *_transform*  
 ブラシに適用する変換  
  
##  <a name="commoninit"></a>  CD2DBrushProperties::CommonInit  
 オブジェクトを初期化します  
  
```  
void CommonInit();
```  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)
