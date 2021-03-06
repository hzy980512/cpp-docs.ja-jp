---
title: lock_guard クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- mutex/std::lock_guard
- mutex/std::lock_guard::lock_guard
dev_langs:
- C++
ms.assetid: 57121f0d-9c50-481c-b971-54e64df864e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7f53732fee62906da19a5771c8598cce51fc6331
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953759"
---
# <a name="lockguard-class"></a>lock_guard クラス

オブジェクトを作成し、そのデストラクタ―が `mutex` のロックを解除するためにインスタンス化できるテンプレートを表します。

## <a name="syntax"></a>構文

```cpp
template <class Mutex>
class lock_guard;
```

## <a name="remarks"></a>Remarks

テンプレート引数 `Mutex` には *mutex 型*を指定する必要があります。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`lock_guard::mutex_type`|テンプレート引数 `Mutex` のシノニム。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[lock_guard](#lock_guard)|`lock_guard` オブジェクトを構築します。|
|[lock_guard::~lock_guard デストラクター](#dtorlock_guard_destructor)|コンストラクターに渡された `mutex` をロック解除します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<mutex >

**名前空間:** std

## <a name="lock_guard"></a>  lock_guard::lock_guard コンストラクター

`lock_guard` オブジェクトを構築します。

```cpp
explicit lock_guard(mutex_type& Mtx);

lock_guard(mutex_type& Mtx, adopt_lock_t);
```

### <a name="parameters"></a>パラメーター

*続け*A *mutex 型*オブジェクト。

### <a name="remarks"></a>Remarks

最初のコンス トラクターが型のオブジェクトを構築`lock_guard`とロック*続け*します。 場合*続け*が再帰的なミュー テックスにする必要がありますロックを解除するこのコンス トラクターが呼び出されるとします。

2 番目のコンス トラクターをロックしません*続け*します。 *続け*このコンス トラクターが呼び出されたときにロックされている必要があります。 このコンストラクターでは例外はスローされません。

## <a name="dtorlock_guard_destructor"></a>  lock_guard::~lock_guard デストラクター

コンストラクターに渡された `mutex` をロック解除します。

```cpp
~lock_guard() noexcept;
```

### <a name="remarks"></a>Remarks

デストラクターの実行時に `mutex` が存在しない場合の動作は未定義です。

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<mutex>](../standard-library/mutex.md)<br/>
