---
title: CRichEditCntrItem クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CRichEditCntrItem
- AFXRICH/CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::SyncToRichEditObject
dev_langs:
- C++
helpviewer_keywords:
- CRichEditCntrItem [MFC], CRichEditCntrItem
- CRichEditCntrItem [MFC], SyncToRichEditObject
ms.assetid: 6c0b4efe-0fb8-4621-b5e1-fdcb8ec48c3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2a0566ef5eead5950f2b4de1f6e1a220f79bcfbe
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37849328"
---
# <a name="cricheditcntritem-class"></a>CRichEditCntrItem クラス
[CRichEditView](../../mfc/reference/cricheditview-class.md)と[CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)MFC のドキュメント ビュー アーキテクチャのコンテキストでリッチ エディット コントロールの機能を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CRichEditCntrItem : public COleClientItem  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CRichEditCntrItem::CRichEditCntrItem](#cricheditcntritem)|`CRichEditCntrItem` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CRichEditCntrItem::SyncToRichEditObject](#synctoricheditobject)|別の種類として、項目をアクティブにします。|  
  
## <a name="remarks"></a>Remarks  
 「リッチ エディット コントロール」をユーザーは入力し、テキストの編集ウィンドウです。 テキストは、文字および段落の書式設定に割り当てることができるし、埋め込み OLE オブジェクトを含めることができます。 リッチ エディット コントロールでは、テキストの書式設定のプログラミング インターフェイスを提供します。 ただし、アプリケーションでは、書式設定操作をユーザーに使用できるようにするために必要なすべてのユーザー インターフェイス コンポーネントを実装する必要があります。  
  
 `CRichEditView` テキストとテキストの書式設定特性を保持します。 `CRichEditDoc` ビューでは OLE クライアント アイテムの一覧を保持します。 `CRichEditCntrItem` コンテナー側 OLE クライアント アイテムへのアクセスを提供します。  
  
 この Windows コモン コントロール (つまり、 [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)および関連クラス) は以降 Windows 95/98 および Windows NT 3.51 の下で実行中のプログラムにのみ使用できます。  
  
 MFC アプリケーションの豊富な編集コンテナーの項目を使用しての例は、次を参照してください。、[ワードパッド](../../visual-cpp-samples.md)サンプル アプリケーション。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleClientItem](../../mfc/reference/coleclientitem-class.md)  
  
 `CRichEditCntrItem`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxrich.h  
  
##  <a name="cricheditcntritem"></a>  CRichEditCntrItem::CRichEditCntrItem  
 作成するには、この関数を呼び出し、`CRichEditCntrItem`オブジェクトおよびコンテナーのドキュメントに追加します。  
  
```  
CRichEditCntrItem(
    REOBJECT* preo = NULL,  
    CRichEditDoc* pContainer = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *preo*  
 ポインター、 [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) OLE 項目を記述する構造体。 新しい`CRichEditCntrItem`この OLE アイテム オブジェクトが構築されます。 場合*preo*が null の場合、クライアントの項目が空です。  
  
 *pContainer*  
 この項目を格納するコンテナーのドキュメントへのポインター。 場合*pContainer*が null の場合、明示的に呼び出す必要がある[COleDocument::AddItem](../../mfc/reference/coledocument-class.md#additem)ドキュメントにこのクライアントの項目を追加します。  
  
### <a name="remarks"></a>Remarks  
 この関数では、OLE の初期化は実行されません。  
  
 詳細については、次を参照してください。、 [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) Windows SDK の構造体。  
  
##  <a name="synctoricheditobject"></a>  CRichEditCntrItem::SyncToRichEditObject  
 デバイスの側面を同期するには、この関数を呼び出す[型](http://msdn.microsoft.com/library/windows/desktop/ms690318)、この`CRichEditCntrltem`によって指定される*reo*します。  
  
```  
void SyncToRichEditObject(REOBJECT& reo);
```  
  
### <a name="parameters"></a>パラメーター  
 *reo*  
 参照、 [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) OLE 項目を記述する構造体。  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。[型](http://msdn.microsoft.com/library/windows/desktop/ms690318)Windows SDK に含まれています。  
  
## <a name="see-also"></a>関連項目  
 [ワードパッドの MFC サンプル](../../visual-cpp-samples.md)   
 [COleClientItem クラス](../../mfc/reference/coleclientitem-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CRichEditDoc クラス](../../mfc/reference/cricheditdoc-class.md)   
 [CRichEditView クラス](../../mfc/reference/cricheditview-class.md)
