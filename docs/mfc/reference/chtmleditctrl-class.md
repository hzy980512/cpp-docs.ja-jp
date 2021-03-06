---
title: CHtmlEditCtrl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl::CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl::Create
- AFXHTML/CHtmlEditCtrl::GetDHtmlDocument
- AFXHTML/CHtmlEditCtrl::GetStartDocument
dev_langs:
- C++
helpviewer_keywords:
- CHtmlEditCtrl [MFC], CHtmlEditCtrl
- CHtmlEditCtrl [MFC], Create
- CHtmlEditCtrl [MFC], GetDHtmlDocument
- CHtmlEditCtrl [MFC], GetStartDocument
ms.assetid: 0fc4a238-b05f-4874-9edc-6a6701f064d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4cc8cdc389edc8abbc424ec8277f759e7f3d81bb
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37338569"
---
# <a name="chtmleditctrl-class"></a>CHtmlEditCtrl クラス
MFC ウィンドウ内の WebBrowser ActiveX コントロールの機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CHtmlEditCtrl: public CWnd,   
    public CHtmlEditCtrlBase<CHtmlEditCtrl>  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CHtmlEditCtrl::CHtmlEditCtrl](#chtmleditctrl)|`CHtmlEditCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CHtmlEditCtrl::Create](#create)|WebBrowser ActiveX コントロールを作成しにアタッチします、`CHtmlEditCtrl`オブジェクト。 この関数では、WebBrowser ActiveX コントロールが編集モードに自動的に保存されます。|  
|[CHtmlEditCtrl::GetDHtmlDocument](#getdhtmldocument)|取得、 [IHTMLDocument2](https://msdn.microsoft.com/library/aa752574.aspx)ドキュメント上のインターフェイスは、コンテナー内の WebBrowser コントロールに現在読み込まれています。|  
|[CHtmlEditCtrl::GetStartDocument](#getstartdocument)|内の WebBrowser コントロールでのロードに既定のドキュメントの URL を取得します。|  
  
## <a name="remarks"></a>Remarks  
 ホスト型の WebBrowser コントロールが自動的には、作成後にモードを編集します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHtmlEditCtrl`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxhtml.h  
  
##  <a name="chtmleditctrl"></a>  CHtmlEditCtrl::CHtmlEditCtrl  
 `CHtmlEditCtrl` オブジェクトを構築します。  
  
```  
CHtmlEditCtrl();
```  
  
##  <a name="create"></a>  CHtmlEditCtrl::Create  
 WebBrowser ActiveX コントロールを作成しにアタッチします、`CHtmlEditCtrl`オブジェクト。 WebBrowser ActiveX コントロールが自動的に既定のドキュメントに移動しに配置し、編集モードを使用してこの関数です。  
  
```  
virtual BOOL Create(
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    int nID,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *したとき*  
 このパラメーターは使用されません。  
  
 *dwStyle*  
 このパラメーターは使用されません。  
  
 *rect*  
 コントロールのサイズと位置を指定します。  
  
 *pParentWnd*  
 コントロールの親ウィンドウを指定します。 NULL は指定できません。  
  
 *nID*  
 コントロールの ID を指定します  
  
 *pContext*  
 このパラメーターは使用されません。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、true を返します。  
  
##  <a name="getdhtmldocument"></a>  CHtmlEditCtrl::GetDHtmlDocument  
 取得、 [IHTMLDocument2](https://msdn.microsoft.com/library/aa752574.aspx)ドキュメント上のインターフェイスは、コンテナー内の WebBrowser コントロールに現在読み込まれて  
  
```  
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *ppDocument*  
 ドキュメントのインターフェイスです。  
  
##  <a name="getstartdocument"></a>  CHtmlEditCtrl::GetStartDocument  
 内の WebBrowser コントロールでのロードに既定のドキュメントの URL を取得します。  
  
```  
virtual LPCTSTR GetStartDocument();
```  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)

