---
title: ソース コードの編成 (C++ テンプレート) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 50569c5d-0219-4966-9bcf-a8689074ad1d
author: mikeblome
ms.author: mblome
ms.openlocfilehash: ef23b1a12305be9ecf181beb085bb686e81b083b
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939755"
---
# <a name="source-code-organization-c-templates"></a>ソース コードの編成 (C++ テンプレート)

クラス テンプレートを定義するときに必要なときに、メンバーの定義がコンパイラに認識されているようにソース コードを整理する必要があります。   使用する選択肢がある場合、*包含モデル*または*明示的なインスタンス化*モデル。 包含モデルでは、テンプレートを使用するすべてのファイルのメンバーの定義が含まれます。 この方法が最も簡単なと、どのような具象型は、テンプレートで使用できる点で最大の柔軟性を提供します。 その欠点は、コンパイル時間を増やすことができます。 影響は、重要なは、プロジェクトの場合や含まれるファイル自体が大きい。 明示的なインスタンス化アプローチでは、テンプレート自体には、具象クラスまたはクラス メンバーの特定の種類がインスタンス化します。  このアプローチは、コンパイルの時間を短縮できますが、テンプレートの実行者が前もって有効にするクラスのみに使用量を制限します。 一般に、コンパイル時間が問題になっていない場合は、信頼モデルを使用することをお勧めします。

## <a name="background"></a>背景

テンプレートは、コンパイラが、テンプレート、またはそのメンバーのいずれかのオブジェクト コードを生成しないという点で通常のクラスと同様にはできません。 テンプレートは、具象型でインスタンス化されるまで、生成に何もないです。 コンパイラが検出した場合、テンプレートのインスタンス化など`MyClass<int> mc;`とそのシグネチャを持つクラスが存在しないまだ、新しいクラスを生成します。 使用される任意のメンバー関数のコードを生成しようとします。 これらの定義がないファイルのかどうかは #included、直接的または間接的にコンパイルされる .cpp ファイルで、コンパイラに表示されないようにします。  コンパイラの観点から必ずしもエラーのためを場合、リンカーが検索に別の翻訳単位で、関数を定義することがあります。  発生させる、リンカーがそのコードを見つけられない場合、**未解決の外部**エラー。

## <a name="the-inclusion-model"></a>信頼モデル

テンプレートの定義を翻訳単位全体で表示されるようにする最も簡単で最も一般的な方法は、ヘッダー ファイル自体に定義を格納します。  テンプレートを使用するすべての .cpp ファイルは単に #include ヘッダー。 これは、標準ライブラリで使用されるアプローチです。

```cpp
#ifndef MYARRAY
#define MYARRAY
#include <iostream>

template<typename T, size_t N>
class MyArray
{
    T arr[N];
public:
    // Full definitions:
    MyArray(){}
    void Print()
    {
        for (const auto v : arr)
        {
            std::cout << v << " , ";
        }
    }

    T& operator[](int i)
   {
       return arr[i];
   } 
};
#endif
```

このアプローチでは、コンパイラは、完全なテンプレートの定義にアクセスし、任意の型のオンデマンドでテンプレートをインスタンス化できます。 シンプルで維持するために比較的簡単になります。 ただし、包含モデルでは、コンパイル時間の観点からコストがあります。   このコストは、大規模なプログラムで重要な場合に特にテンプレート ヘッダー自体 #includes 他のヘッダー。 すべての .cpp ファイルを #includes ヘッダーは関数テンプレートとすべての定義のコピーを取得します。 リンカーは関数については、複数の定義と最終的はありませんが、この作業を行う時間がかかるようにものを選別することは、一般にします。 小さいプログラムでは、その余分なコンパイル時は重要ではありません。

## <a name="the-explicit-instantiation-model"></a>明示的なインスタンス化モデル

コード型の包含モデルでは、プロジェクトの実際のテンプレートをインスタンス化に使用される型のセットがある明確場合は、.h および .cpp ファイルにテンプレート コードを分離 .cpp ファイルで明示的にインスタンス化のテンプレートとことができます。 これによりオブジェクトのコードを生成するユーザー インスタンスに到達したときに、コンパイラが表示されます。

明示的なインスタンス化を作成するには、インスタンスを作成するエンティティの署名後に、キーワードのテンプレートを使用します。 型またはメンバーを指定できます。 型を明示的にインスタンス化する場合は、すべてのメンバーがインスタンス化されます。

```cpp
template MyArray<double, 5>;
```

```cpp
//MyArray.h
#ifndef MYARRAY
#define MYARRAY

template<typename T, size_t N>
class MyArray
{
    T arr[N];
public:
    MyArray();
    void Print();
    T& operator[](int i);
};
#endif

//MyArray.cpp
#include "stdafx.h"
#include <iostream>
#include "MyArray.h"

using namespace std;

template<typename T, size_t N>
MyArray<T,N>::MyArray(){}

template<typename T, size_t N>
void MyArray<T,N>::Print()
{
    for(const auto v : arr)
    {
        cout << v << "'";
    }
    cout << endl;
}

template MyArray<double, 5>;template MyArray<string, 5>;
```

前の例では、明示的なインスタンス生成は .cpp ファイルの下部には。 A`MyArray`にのみ使用できます**二重**または`String`型。

> [!NOTE]
> C++ 11 で、**エクスポート**キーワードは、テンプレートの定義のコンテキストで非推奨とされました。 実際にこれはほとんど影響ほとんどのコンパイラがサポートしないためです。
