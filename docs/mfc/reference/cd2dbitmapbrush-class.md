---
title: CD2DBitmapBrush クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::Attach
- AFXRENDERTARGET/CD2DBitmapBrush::Create
- AFXRENDERTARGET/CD2DBitmapBrush::Destroy
- AFXRENDERTARGET/CD2DBitmapBrush::Detach
- AFXRENDERTARGET/CD2DBitmapBrush::Get
- AFXRENDERTARGET/CD2DBitmapBrush::GetBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::GetExtendModeX
- AFXRENDERTARGET/CD2DBitmapBrush::GetExtendModeY
- AFXRENDERTARGET/CD2DBitmapBrush::GetInterpolationMode
- AFXRENDERTARGET/CD2DBitmapBrush::SetBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::SetExtendModeX
- AFXRENDERTARGET/CD2DBitmapBrush::SetExtendModeY
- AFXRENDERTARGET/CD2DBitmapBrush::SetInterpolationMode
- AFXRENDERTARGET/CD2DBitmapBrush::CommonInit
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmapBrushProperties
dev_langs:
- C++
helpviewer_keywords:
- CD2DBitmapBrush [MFC], CD2DBitmapBrush
- CD2DBitmapBrush [MFC], Attach
- CD2DBitmapBrush [MFC], Create
- CD2DBitmapBrush [MFC], Destroy
- CD2DBitmapBrush [MFC], Detach
- CD2DBitmapBrush [MFC], Get
- CD2DBitmapBrush [MFC], GetBitmap
- CD2DBitmapBrush [MFC], GetExtendModeX
- CD2DBitmapBrush [MFC], GetExtendModeY
- CD2DBitmapBrush [MFC], GetInterpolationMode
- CD2DBitmapBrush [MFC], SetBitmap
- CD2DBitmapBrush [MFC], SetExtendModeX
- CD2DBitmapBrush [MFC], SetExtendModeY
- CD2DBitmapBrush [MFC], SetInterpolationMode
- CD2DBitmapBrush [MFC], CommonInit
- CD2DBitmapBrush [MFC], m_pBitmap
- CD2DBitmapBrush [MFC], m_pBitmapBrush
- CD2DBitmapBrush [MFC], m_pBitmapBrushProperties
ms.assetid: 46ebbe34-66e0-44c8-af1d-d129e851de5e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 23728966dfd6bd759c16b364da063c7f80687b5e
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954492"
---
# <a name="cd2dbitmapbrush-class"></a>CD2DBitmapBrush クラス
ID2D1BitmapBrush のラッパーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CD2DBitmapBrush : public CD2DBrush;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DBitmapBrush::CD2DBitmapBrush](#cd2dbitmapbrush)|オーバーロードされます。 ファイルから CD2DBitmapBrush オブジェクトを構築します。|  
|[CD2DBitmapBrush:: ~ CD2DBitmapBrush](#dtor)|デストラクターです。 D2D ビットマップ ブラシ オブジェクトが破棄されるときに呼び出されます。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DBitmapBrush::Attach](#attach)|既存のリソースのインターフェイス オブジェクトへの接続|  
|[CD2DBitmapBrush::Create](#create)|CD2DBitmapBrush を作成します。 (上書き[CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create))。|  
|[CD2DBitmapBrush::Destroy](#destroy)|CD2DBitmapBrush オブジェクトを破棄します。 (上書き[CD2DBrush::Destroy](../../mfc/reference/cd2dbrush-class.md#destroy))。|  
|[CD2DBitmapBrush::Detach](#detach)|オブジェクトからリソースのインターフェイスの関連付けを解除します。|  
|[CD2DBitmapBrush::Get](#get)|返します ID2D1BitmapBrush インターフェイス|  
|[CD2DBitmapBrush::GetBitmap](#getbitmap)|ソースを取得しますビットマップを描画するブラシを使用します。|  
|[CD2DBitmapBrush::GetExtendModeX](#getextendmodex)|メソッドを取得します、ブラシ水平方向にタイルがそのビットマップを越える領域|  
|[CD2DBitmapBrush::GetExtendModeY](#getextendmodey)|メソッドを取得します、ブラシ垂直方向にタイルがそのビットマップを越える領域|  
|[CD2DBitmapBrush::GetInterpolationMode](#getinterpolationmode)|ブラシ ビットマップのスケールまたは回転したときに使用される補間メソッドを取得します|  
|[CD2DBitmapBrush::SetBitmap](#setbitmap)|このブラシが描画に使用するビットマップのソースを指定します|  
|[CD2DBitmapBrush::SetExtendModeX](#setextendmodex)|そのビットマップを越える領域が水平方向にタイル ブラシ方法を指定します|  
|[CD2DBitmapBrush::SetExtendModeY](#setextendmodey)|ブラシが垂直方向にそのビットマップを超えてが領域をタイル方法を指定します|  
|[CD2DBitmapBrush::SetInterpolationMode](#setinterpolationmode)|ブラシ ビットマップのスケールまたは回転したときに使用される補間モードを指定します|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DBitmapBrush::CommonInit](#commoninit)|オブジェクトを初期化します|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DBitmapBrush::operator ID2D1BitmapBrush *](#operator_id2d1bitmapbrush_star)|返します ID2D1BitmapBrush インターフェイス|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[CD2DBitmapBrush::m_pBitmap](#m_pbitmap)|CD2DBitmap オブジェクトへのポインターを格納します。|  
|[CD2DBitmapBrush::m_pBitmapBrush](#m_pbitmapbrush)|ID2D1BitmapBrush オブジェクトへのポインターを格納します。|  
|[CD2DBitmapBrush::m_pBitmapBrushProperties](#m_pbitmapbrushproperties)|ブラシのプロパティをビットマップします。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 `CD2DBitmapBrush`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="dtor"></a>  CD2DBitmapBrush:: ~ CD2DBitmapBrush  
 デストラクターです。 D2D ビットマップ ブラシ オブジェクトが破棄されるときに呼び出されます。  
  
```  
virtual ~CD2DBitmapBrush();
```  
  
##  <a name="attach"></a>  CD2DBitmapBrush::Attach  
 既存のリソースのインターフェイス オブジェクトへの接続  
  
```  
void Attach(ID2D1BitmapBrush* pResource);
```  
  
### <a name="parameters"></a>パラメーター  
 *pResource*  
 既存のリソースのインターフェイスです。 NULL をすることはできません。  
  
##  <a name="cd2dbitmapbrush"></a>  CD2DBitmapBrush::CD2DBitmapBrush  
 CD2DBitmapBrush オブジェクトを構築します。  
  
```  
CD2DBitmapBrush(
    CRenderTarget* pParentTarget,  
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);

 
CD2DBitmapBrush(
    CRenderTarget* pParentTarget,  
    UINT uiResID,  
    LPCTSTR lpszType = NULL,  
    CD2DSizeU sizeDest = CD2DSizeU(0, 0), 
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);

 
CD2DBitmapBrush(
    CRenderTarget* pParentTarget,  
    LPCTSTR lpszImagePath,  
    CD2DSizeU sizeDest = CD2DSizeU(0, 0), 
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *pParentTarget*  
 レンダー ターゲットへのポインター。  
  
 *pBitmapBrushProperties*  
 拡張モードとビットマップのブラシの補間モードへのポインター。  
  
 *pBrushProperties*  
 不透明度およびブラシの変換へのポインター。  
  
 *bAutoDestroy*  
 所有者 (pParentTarget) によって、オブジェクトが破棄されることを示します。  
  
 *uiResID*  
 リソースのリソース ID 番号。  
  
 *lpszType*  
 リソースの種類を表す null で終わる文字列へのポインター。  
  
 *sizeDest*  
 ビットマップの送信先のサイズ。  
  
 *lpszImagePath*  
 ファイルの名前を表す null で終わる文字列へのポインター。  
  
##  <a name="commoninit"></a>  CD2DBitmapBrush::CommonInit  
 オブジェクトを初期化します  
  
```  
void CommonInit(D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties);
```  
  
### <a name="parameters"></a>パラメーター  
 *pBitmapBrushProperties*  
 ビットマップのブラシのプロパティへのポインター。  
  
##  <a name="create"></a>  CD2DBitmapBrush::Create  
 CD2DBitmapBrush を作成します。  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 *pRenderTarget*  
 レンダー ターゲットへのポインター。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 それ以外の場合、HRESULT エラー コードを返します。  
  
##  <a name="destroy"></a>  CD2DBitmapBrush::Destroy  
 CD2DBitmapBrush オブジェクトを破棄します。  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>  CD2DBitmapBrush::Detach  
 オブジェクトからリソースのインターフェイスの関連付けを解除します。  
  
```  
ID2D1BitmapBrush* Detach();
```  
  
### <a name="return-value"></a>戻り値  
 デタッチされたリソースのインターフェイスへのポインター。  
  
##  <a name="get"></a>  CD2DBitmapBrush::Get  
 返します ID2D1BitmapBrush インターフェイス  
  
```  
ID2D1BitmapBrush* Get();
```  
  
### <a name="return-value"></a>戻り値  
 ID2D1BitmapBrush インターフェイスまたはオブジェクトがまだ初期化されていない場合は、NULL へのポインター。  
  
##  <a name="getbitmap"></a>  CD2DBitmapBrush::GetBitmap  
 ソースを取得しますビットマップを描画するブラシを使用します。  
  
```  
CD2DBitmap* GetBitmap();
```  
  
### <a name="return-value"></a>戻り値  
 CD2DBitmap オブジェクトまたはオブジェクトがまだ初期化されていない場合は、NULL へのポインター。  
  
##  <a name="getextendmodex"></a>  CD2DBitmapBrush::GetExtendModeX  
 メソッドを取得します、ブラシ水平方向にタイルがそのビットマップを越える領域  
  
```  
D2D1_EXTEND_MODE GetExtendModeX() const;  
```  
  
### <a name="return-value"></a>戻り値  
 そのビットマップを越える領域が水平方向にタイル ブラシ方法を指定する値  
  
##  <a name="getextendmodey"></a>  CD2DBitmapBrush::GetExtendModeY  
 メソッドを取得します、ブラシ垂直方向にタイルがそのビットマップを越える領域  
  
```  
D2D1_EXTEND_MODE GetExtendModeY() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ブラシが垂直方向にそのビットマップを超えてが領域をタイル方法を指定する値  
  
##  <a name="getinterpolationmode"></a>  CD2DBitmapBrush::GetInterpolationMode  
 ブラシ ビットマップのスケールまたは回転したときに使用される補間メソッドを取得します  
  
```  
D2D1_BITMAP_INTERPOLATION_MODE GetInterpolationMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ブラシ ビットマップのスケールまたは回転したときに使用される補間メソッド  
  
##  <a name="m_pbitmap"></a>  CD2DBitmapBrush::m_pBitmap  
 CD2DBitmap オブジェクトへのポインターを格納します。  
  
```  
CD2DBitmap* m_pBitmap;  
```  
  
##  <a name="m_pbitmapbrush"></a>  CD2DBitmapBrush::m_pBitmapBrush  
 ID2D1BitmapBrush オブジェクトへのポインターを格納します。  
  
```  
ID2D1BitmapBrush* m_pBitmapBrush;  
```  
  
##  <a name="m_pbitmapbrushproperties"></a>  CD2DBitmapBrush::m_pBitmapBrushProperties  
 ブラシのプロパティをビットマップします。  
  
```  
D2D1_BITMAP_BRUSH_PROPERTIES* m_pBitmapBrushProperties;  
```  
  
##  <a name="operator_id2d1bitmapbrush_star"></a>  CD2DBitmapBrush::operator ID2D1BitmapBrush *  
 返します ID2D1BitmapBrush インターフェイス  
  
```  
operator ID2D1BitmapBrush*();
```   
  
### <a name="return-value"></a>戻り値  
 ID2D1BitmapBrush インターフェイスまたはオブジェクトがまだ初期化されていない場合は、NULL へのポインター。  
  
##  <a name="setbitmap"></a>  CD2DBitmapBrush::SetBitmap  
 このブラシが描画に使用するビットマップのソースを指定します  
  
```  
void SetBitmap(CD2DBitmap* pBitmap);
```  
  
### <a name="parameters"></a>パラメーター  
 *pBitmap*  
 ブラシで使用されるビットマップのソース  
  
##  <a name="setextendmodex"></a>  CD2DBitmapBrush::SetExtendModeX  
 そのビットマップを越える領域が水平方向にタイル ブラシ方法を指定します  
  
```  
void SetExtendModeX(D2D1_EXTEND_MODE extendModeX);
```  
  
### <a name="parameters"></a>パラメーター  
 *extendModeX*  
 そのビットマップを越える領域が水平方向にタイル ブラシ方法を指定する値  
  
##  <a name="setextendmodey"></a>  CD2DBitmapBrush::SetExtendModeY  
 ブラシが垂直方向にそのビットマップを超えてが領域をタイル方法を指定します  
  
```  
void SetExtendModeY(D2D1_EXTEND_MODE extendModeY);
```  
  
### <a name="parameters"></a>パラメーター  
 *extendModeY*  
 ブラシが垂直方向にそのビットマップを超えてが領域をタイル方法を指定する値  
  
##  <a name="setinterpolationmode"></a>  CD2DBitmapBrush::SetInterpolationMode  
 ブラシ ビットマップのスケールまたは回転したときに使用される補間モードを指定します  
  
```  
void SetInterpolationMode(D2D1_BITMAP_INTERPOLATION_MODE interpolationMode);
```  
  
### <a name="parameters"></a>パラメーター  
 *interpolationMode*  
 ブラシ ビットマップのスケールまたは回転したときに使用される補間モード  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)
