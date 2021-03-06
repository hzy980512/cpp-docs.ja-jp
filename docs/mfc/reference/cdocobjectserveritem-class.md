---
title: CDocObjectServerItem クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem::CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem::GetDocument
- AFXDOCOB/CDocObjectServerItem::OnHide
- AFXDOCOB/CDocObjectServerItem::OnShow
dev_langs:
- C++
helpviewer_keywords:
- CDocObjectServerItem [MFC], CDocObjectServerItem
- CDocObjectServerItem [MFC], GetDocument
- CDocObjectServerItem [MFC], OnHide
- CDocObjectServerItem [MFC], OnShow
ms.assetid: 530f7156-50c8-4806-9328-602c9133f622
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dc498b96dad089276b248fbb2e420dde3c0bc514
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2018
ms.locfileid: "39027139"
---
# <a name="cdocobjectserveritem-class"></a>CDocObjectServerItem クラス
OLE サーバー動詞を DocObject サーバー用に実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDocObjectServerItem : public COleServerItem  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDocObjectServerItem::CDocObjectServerItem](#cdocobjectserveritem)|`CDocObjectServerItem` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDocObjectServerItem::GetDocument](#getdocument)|項目を含むドキュメントへのポインターを取得します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDocObjectServerItem::OnHide](#onhide)|フレームワーク DocObject 項目を非表示しようとする場合は、例外をスローします。|  
|[CDocObjectServerItem::OnShow](#onshow)|DocObject アイテムの埋め込みを行うために、フレームワークによって呼び出されるアクティブな。 項目がない場合、DocObject、呼び出します[COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow)します。|  
  
## <a name="remarks"></a>Remarks  
 `CDocObjectServerItem` オーバーライド可能なメンバー関数を定義します。 [OnHide](#onhide)、 [OnOpen](http://msdn.microsoft.com/7a9b1363-6ad8-4732-9959-4e35c07644fd)、および[OnShow](#onshow)します。  
  
 使用する`CDocObjectServerItem`、確認するため、 [OnGetEmbeddedItem](../../mfc/reference/coleserverdoc-class.md#ongetembeddeditem)で上書き、 `COleServerDoc`-新しい派生クラスを返します`CDocObjectServerItem`オブジェクト。 機能で、項目を変更する必要がある場合は、独自の新しいインスタンスを作成することができます`CDocObjectServerItem`-クラスを派生します。  
  
 DocObjects については、次を参照してください。 [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md)と[COleCmdUI](../../mfc/reference/colecmdui-class.md)で、 *MFC リファレンス*します。 参照してください[インターネットの最初の手順: Active ドキュメント](../../mfc/active-documents-on-the-internet.md)と[Active ドキュメント](../../mfc/active-documents-on-the-internet.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleServerItem](../../mfc/reference/coleserveritem-class.md)  
  
 `CDocObjectServerItem`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxdocob.h  
  
##  <a name="cdocobjectserveritem"></a>  CDocObjectServerItem::CDocObjectServerItem  
 `CDocObjectServerItem` オブジェクトを構築します。  
  
```  
CDocObjectServerItem(COleServerDoc* pServerDoc, BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>パラメーター  
 *pServerDoc*  
 新しい項目の DocObject を含むドキュメントへのポインター。  
  
 *bAutoDelete*  
 リンクがリリースされたときに、オブジェクトを削除できるかどうかを示します。 引数の場合は FALSE に設定、`CDocObjectServerItem`オブジェクトは、ドキュメントのデータの不可欠な部分です。 オブジェクトがドキュメントのデータを削除するには、フレームワークを内の範囲を識別するために使用されるセカンダリ構造である場合は TRUE に設定します。  
  
##  <a name="getdocument"></a>  CDocObjectServerItem::GetDocument  
 項目を含むドキュメントへのポインターを取得します。  
  
```  
COleServerDoc* GetDocument() const;  
```  
  
### <a name="return-value"></a>戻り値  
 項目を含むドキュメントへのポインターアイテム、ドキュメントの一部でない場合は NULL です。  
  
### <a name="remarks"></a>Remarks  
 これにより、サーバーのドキュメントへの引数として渡したへのアクセス、 [CDocObjectServerItem](#cdocobjectserveritem)コンス トラクター。  
  
##  <a name="onhide"></a>  CDocObjectServerItem::OnHide  
 アイテムを非表示にするためにフレームワークによって呼び出されます。  
  
```  
virtual void OnHide();
```  
  
### <a name="remarks"></a>Remarks  
 既定の実装は、項目が DocObject 場合に例外をスローします。 アクティブな DocObject アイテムは、ビュー全体がかかるため、非表示にすることはできません。 非表示にする DocObject 項目を非アクティブ化する必要があります。 既定の実装を呼び出す項目でない場合、DocObject [COleServerItem::OnHide](../../mfc/reference/coleserveritem-class.md#onhide)します。  
  
##  <a name="onshow"></a>  CDocObjectServerItem::OnShow  
 DocObject をアイテムの埋め込みをサーバー アプリケーションに指示するためにフレームワークによって呼び出されるアクティブな。  
  
```  
virtual void OnShow();
```  
  
### <a name="remarks"></a>Remarks  
 既定の実装を呼び出す項目でない場合、DocObject [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onopen)します。 特別な DocObject アイテムを開くときの処理を実行する場合は、この関数をオーバーライドします。  
  
## <a name="see-also"></a>関連項目  
 [COleServerItem クラス](../../mfc/reference/coleserveritem-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDocObjectServer クラス](../../mfc/reference/cdocobjectserver-class.md)   
 [COleDocObjectItem クラス](../../mfc/reference/coledocobjectitem-class.md)
