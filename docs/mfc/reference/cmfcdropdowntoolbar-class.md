---
title: CMFCDropDownToolBar クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::AllowShowOnPaneMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::LoadBitmap
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::LoadToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnLButtonUp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnMouseMove
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnSendCommand
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnUpdateCmdUI
dev_langs:
- C++
helpviewer_keywords:
- CMFCDropDownToolBar [MFC], AllowShowOnPaneMenu
- CMFCDropDownToolBar [MFC], LoadBitmap
- CMFCDropDownToolBar [MFC], LoadToolBar
- CMFCDropDownToolBar [MFC], OnLButtonUp
- CMFCDropDownToolBar [MFC], OnMouseMove
- CMFCDropDownToolBar [MFC], OnSendCommand
- CMFCDropDownToolBar [MFC], OnUpdateCmdUI
ms.assetid: 78818ec5-83ce-42fa-a0d4-2d9d5ecc8770
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6e12799f10fe86ef5dd556eac4e344aa972e2503
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2018
ms.locfileid: "39027311"
---
# <a name="cmfcdropdowntoolbar-class"></a>CMFCDropDownToolBar クラス
ユーザーがトップレベルのツール バー ボタンを押し続けたときに表示されるツール バーです。  
  
   [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
## <a name="syntax"></a>構文  
  
```  
class CMFCDropDownToolBar : public CMFCToolBar  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCDropDownToolBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|(`CPane::AllowShowOnPaneMenu` をオーバーライドします)。|  
|[CMFCDropDownToolBar::LoadBitmap](#loadbitmap)|(上書き[CMFCToolBar::LoadBitmap](../../mfc/reference/cmfctoolbar-class.md#loadbitmap))。|  
|[CMFCDropDownToolBar::LoadToolBar](#loadtoolbar)|(上書き[CMFCToolBar::LoadToolBar](../../mfc/reference/cmfctoolbar-class.md#loadtoolbar))。|  
|[CMFCDropDownToolBar::OnLButtonUp](#onlbuttonup)||  
|[CMFCDropDownToolBar::OnMouseMove](#onmousemove)||  
|[CMFCDropDownToolBar::OnSendCommand](#onsendcommand)|(`CMFCToolBar::OnSendCommand` をオーバーライドします)。|  
|[CMFCDropDownToolBar::OnUpdateCmdUI](#onupdatecmdui)|(上書き[CMFCToolBar::OnUpdateCmdUI](http://msdn.microsoft.com/571a38ab-2a56-4968-9796-273516126f80))。|  
  
### <a name="remarks"></a>Remarks  
 A`CMFCDropDownToolBar`オブジェクトは、ポップアップ メニューの動作では、ツールバーの外観を結合します。 ユーザーが押すし、ドロップダウン ツール バー ボタンを保持 (を参照してください[CMFCDropDownToolbarButton クラス](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md))、ドロップダウン ツールバーが表示され、ユーザーはまでスクロールし、マウスを解放してドロップダウン ツール バーからボタンを選択することができますボタンをクリックします。 ドロップダウン ツールバー ボタンを選択すると、そのボタンが最上位レベルのツールバーの現在のボタンとして表示されます。  
  
 ドロップダウン ツールバーのカスタマイズや、ドッキングされていることはできませんし、ティアオフ状態はありません。  
  
 次の図は、`CMFCDropDownToolBar`オブジェクト。  
  
 ![CMFCDropDownToolbar の例](../../mfc/reference/media/cmfcdropdown.png "cmfcdropdown")  
  
 作成する、`CMFCDropDownToolBar`オブジェクトの通常のツールバーを作成すると同じ方法 (を参照してください[CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md))。  
  
 親ツールバーのドロップダウン ツール バーを挿入します。  
  
 1. 親ツール バー リソースでボタンのダミー リソース ID を予約します。  
  
 2. 作成、`CMFCDropDownToolBarButton`ドロップダウン ツール バーを格納しているオブジェクト (詳細については、次を参照してください。 [CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md#cmfcdropdowntoolbarbutton))。  
  
 3. ダミー ボタンに置き換える、`CMFCDropDownToolBarButton`オブジェクトを使用して[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)します。  
  
 ツール バー ボタンの詳細については、次を参照してください。[チュートリアル: ツールバーにコントロールを配置する](../../mfc/walkthrough-putting-controls-on-toolbars.md)します。 ドロップダウン ツール バーの例は、サンプル プロジェクト VisualStudioDemo を参照してください。  
  
## <a name="example"></a>例  
 次の例では、使用する方法、`Create`メソッドで、`CMFCDropDownToolBar`クラス。 このコード スニペットの一部、 [Visual Studio のデモ サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#29](../../mfc/codesnippet/cpp/cmfcdropdowntoolbar-class_1.h)]  
[!code-cpp[NVC_MFC_VisualStudioDemo#30](../../mfc/codesnippet/cpp/cmfcdropdowntoolbar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxdropdowntoolbar.h  
  
##  <a name="allowshowonpanemenu"></a>  CMFCDropDownToolBar::AllowShowOnPaneMenu  

  
```  
virtual BOOL AllowShowOnPaneMenu() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="loadbitmap"></a>  CMFCDropDownToolBar::LoadBitmap  
 アプリケーション リソースからツール バー イメージを読み込みます。  
  
```  
virtual BOOL LoadBitmap(
    UINT uiResID,  
    UINT uiColdResID=0,  
    UINT uiMenuResID=0,  
    BOOL bLocked=FALSE,  
    UINT uiDisabledResID=0,  
    UINT uiMenuDisabledResID=0);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uiResID*  
 ツール バーのホット イメージを参照するビットマップのリソース ID。  
  
 [in]*uiColdResID*  
 ツール バーのコールド イメージを参照するビットマップのリソース ID。  
  
 [in]*uiMenuResID*  
 ツール バーの通常のメニュー イメージを参照するビットマップのリソース ID。  
  
 [in]*ブロック*  
 ツールバーをロックする場合は TRUEそれ以外の場合は FALSE です。  
  
 [in]*uiDisabledResID*  
 ツール バーの無効イメージを参照するビットマップのリソース ID。  
  
 [in]*uiMenuDisabledResID*  
 メニューの無効イメージを参照するビットマップのリソース ID です。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は 0 以外。それ以外の場合は 0。  
  
### <a name="remarks"></a>Remarks  
 [Cmfctoolbar::loadtoolbarex](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex)メソッドは、ツールバーに関連付けられているイメージを読み込むには、このメソッドを呼び出します。 このメソッドをオーバーライドして、イメージ リソースのカスタムの読み込みを実行します。  
  
 ツール バーの作成後に、 `LoadBitmapEx` メソッドを呼び出して追加のイメージを読み込みます。  
  
##  <a name="loadtoolbar"></a>  CMFCDropDownToolBar::LoadToolBar  

  
```  
virtual BOOL LoadToolBar(
    UINT uiResID,  
    UINT uiColdResID = 0,  
    UINT uiMenuResID = 0,
    BOOL = FALSE,  
    UINT uiDisabledResID = 0,  
    UINT uiMenuDisabledResID = 0,  
    UINT uiHotResID = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uiResID*  
 [in]*uiColdResID*  
 [in]*uiMenuResID*  
 [in]*BOOL*  
 [in]*uiDisabledResID*  
 [in]*uiMenuDisabledResID*  
 [in]*uiHotResID*  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onlbuttonup"></a>  CMFCDropDownToolBar::OnLButtonUp  

  
```  
afx_msg void OnLButtonUp(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nFlags*  
 [in]*ポイント*  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onmousemove"></a>  CMFCDropDownToolBar::OnMouseMove  

  
```  
afx_msg void OnMouseMove(
    UINT nFlags,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nFlags*  
 [in]*ポイント*  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onsendcommand"></a>  CMFCDropDownToolBar::OnSendCommand  

  
```  
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pButton*  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onupdatecmdui"></a>  CMFCDropDownToolBar::OnUpdateCmdUI  

  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pTarget*  
 [in]*持たず*  
  
### <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBar::Create](../../mfc/reference/cmfctoolbar-class.md#create)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [CMFCDropDownToolbarButton クラス](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)   
 [チュートリアル: ツール バーへのコントロールの追加](../../mfc/walkthrough-putting-controls-on-toolbars.md)



