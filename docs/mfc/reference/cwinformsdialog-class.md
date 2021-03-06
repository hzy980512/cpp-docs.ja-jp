---
title: CWinFormsDialog クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog::CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog::GetControl
- AFXWINFORMS/CWinFormsDialog::GetControlHandle
- AFXWINFORMS/CWinFormsDialog::OnInitDialog
dev_langs:
- C++
helpviewer_keywords:
- CWinFormsDialog [MFC], CWinFormsDialog
- CWinFormsDialog [MFC], GetControl
- CWinFormsDialog [MFC], GetControlHandle
- CWinFormsDialog [MFC], OnInitDialog
ms.assetid: e3cec000-a578-448e-b06a-8af256312f61
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 324df7657be7f74cade6fc4b50b98d6790245ab4
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2018
ms.locfileid: "39027090"
---
# <a name="cwinformsdialog-class"></a>CWinFormsDialog クラス
Windows フォーム ユーザー コントロールをホストする MFC ダイアログ クラスのラッパーです。  
  
## <a name="syntax"></a>構文  
  
```  
template <typename TManagedControl>  
class CWinFormsDialog :   
    public CDialog  
```  
  
#### <a name="parameters"></a>パラメーター  
 `TManagedControl`  
 MFC アプリケーションに表示される .NET Framework ユーザー コントロール。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CWinFormsDialog::CWinFormsDialog](#cwinformsdialog)|`CWinFormsDialog` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CWinFormsDialog::GetControl](#getcontrol)|Windows フォーム ユーザー コントロールへの参照を取得します。|  
|[CWinFormsDialog::GetControlHandle](#getcontrolhandle)|Windows フォーム ユーザー コントロールにウィンドウ ハンドルを取得します。|  
|[CWinFormsDialog::OnInitDialog](#oninitdialog)|上の Windows フォーム ユーザー コントロールのホストを作成して、MFC ダイアログ ボックスを初期化します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|name||  
|----------|-|  
|[CWinFormsDialog::operator-&gt;](#operator_-_gt)|置換[CWinFormsDialog::GetControl](#getcontrol)式で。|  
|[CWinFormsDialog::operator TManagedControl ^](#operator_tmanagedcontrol)|Windows フォーム ユーザー コントロールへの参照として型をキャストします。|  
  
## <a name="remarks"></a>Remarks  
 `CWinFormsDialog` MFC ダイアログ クラス用のラッパーです ( [CDialog](../../mfc/reference/cdialog-class.md))、Windows フォーム ユーザー コントロールをホストします。 これにより、モーダルまたはモードレスの MFC ダイアログ ボックス上の .NET Framework コントロールの表示ができます。  
  
 Windows フォームの使用に関する詳細については、次を参照してください。 [MFC における Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)と[MFC ダイアログ ボックスとしての Windows フォーム ユーザー コントロールをホストしている](../../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxwinforms.h  
  
##  <a name="cwinformsdialog"></a>  CWinFormsDialog::CWinFormsDialog  
 `CWinFormsDialog` オブジェクトを構築します。  
  
```  
CWinFormsDialog(UINT nIDTemplate = IDD);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIDTemplate*  
 ダイアログ ボックスのテンプレート リソースの ID が含まれています。 ダイアログ エディターを使用して、ダイアログ テンプレートを作成し、アプリケーションのリソース スクリプト ファイルに格納します。 ダイアログ テンプレートの詳細については、次を参照してください。 [CDialog クラス](../../mfc/reference/cdialog-class.md)します。  
  
##  <a name="getcontrol"></a>  CWinFormsDialog::GetControl  
 Windows フォーム ユーザー コントロールへの参照を取得します。  
  
```  
inline TManagedControl^ GetControl() const;  
```  
  
### <a name="return-value"></a>戻り値  
 MFC ダイアログ ボックスで、Windows フォーム コントロールへの参照を返します。  
  
##  <a name="getcontrolhandle"></a>  CWinFormsDialog::GetControlHandle  
 Windows フォーム ユーザー コントロールにウィンドウ ハンドルを取得します。  
  
```  
inline HWND GetControlHandle() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 Windows フォーム ユーザー コントロールにウィンドウ ハンドルを返します。  
  
##  <a name="oninitdialog"></a>  CWinFormsDialog::OnInitDialog  
 上の Windows フォーム ユーザー コントロールのホストを作成して、MFC ダイアログ ボックスを初期化します。  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>戻り値  
 アプリケーションがダイアログ ボックスで、コントロールのいずれかに入力フォーカスを設定したかどうかを指定するブール値。 場合`OnInitDialog`戻り値は 0 以外の場合、Windows 入力フォーカスを設定する最初のコントロール ダイアログ ボックス。 このメソッドは、アプリケーションは、ダイアログ ボックスで、コントロールのいずれかに入力フォーカスを明示的に設定が場合にのみ、0 を返すことができます。  
  
### <a name="remarks"></a>Remarks  
 MFC ダイアログ ボックスが作成されたとき (を使用して、[作成](../../mfc/reference/cdialog-class.md#create)、 [CreateIndirect](../../mfc/reference/cdialog-class.md#createindirect)、または[DoModal](../../mfc/reference/cdialog-class.md#domodal)から継承されたメソッド[CDialog](../../mfc/reference/cdialog-class.md))、wm _ で始まるINITDIALOG メッセージが送信され、このメソッドが呼び出されます。 ダイアログ ボックス上の Windows フォーム コントロールのインスタンスを作成し、ユーザー コントロールのサイズに対応するダイアログ ボックスのサイズを調整します。 MFC ダイアログ ボックスで新しいコントロールをホストします。  
  
 ダイアログ ボックスの初期化時に、特別な処理を実行する必要がある場合は、このメンバー関数をオーバーライドします。 このメソッドの使用に関する詳細については、次を参照してください。 [CDialog::OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog)します。  
  
##  <a name="operator_-_gt"></a>  CWinFormsDialog::operator-&gt;  
 置換[CWinFormsDialog::GetControl](#getcontrol)式で。  
  
```  
inline TManagedControl^  operator->() const throw();
```  
  
### <a name="remarks"></a>Remarks  
 この演算子は、置換する便利な構文を提供します。`GetControl`式で。  
  
 Windows フォームを使用する方法の詳細については、次を参照してください。 [MFC における Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)します。  
  
##  <a name="operator_tmanagedcontrol_xor"></a>  CWinFormsDialog::operator TManagedControl ^  
 Windows フォーム ユーザー コントロールへの参照として型をキャストします。  
  
```  
inline operator TManagedControl^() const throw();
```  
  
### <a name="remarks"></a>Remarks  
 この演算子は、Windows フォーム コントロールへの参照として型をキャストします。 渡すために使用されます、 `CWinFormsDialog<TManagedControl>`  ダイアログ ボックスに、Windows フォーム ユーザー コントロールのオブジェクトへのポインターを受け取る関数をします。  
  
## <a name="see-also"></a>関連項目  
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [CWinFormsView クラス](../../mfc/reference/cwinformsview-class.md)   
 [CDialog クラス](../../mfc/reference/cdialog-class.md)
