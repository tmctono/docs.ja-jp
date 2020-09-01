---
description: partial メソッド - C# リファレンス
title: partial メソッド - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- partialmethod_CSharpKeyword
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
ms.openlocfilehash: d6c433fd30f6ec51355bdefee90d815783487c1b
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134381"
---
# <a name="partial-method-c-reference"></a>partial メソッド (C# リファレンス)

部分メソッドには、部分型の一部に定義されたシグネチャ、および部分型の別の部分に定義された実装があります。 部分メソッドを使用すると、イベント ハンドラーと同じように、開発者が実装するかどうかを決定できるメソッド フックをクラス デザイナーで提供できます。 開発者が実装を指定しない場合、コンパイラはコンパイル時にシグネチャを削除します。 部分メソッドには次の条件が適用されます。

- 部分型の両方の部分のシグネチャが一致する必要がある。

- メソッドが void を返す必要がある。

- アクセス修飾子はできない。 部分メソッドは暗黙的にプライベート メソッドになる。

部分クラスの 2 つの部分に定義された部分メソッドを次の例に示します。

[!code-csharp[csrefKeywordsContextual#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#9)]

詳細については、「[部分クラスと部分メソッド](../../programming-guide/classes-and-structs/partial-classes-and-methods.md)」を参照してください。

## <a name="see-also"></a>関連項目

- [C# リファレンス](../index.md)
- [partial 型](partial-type.md)
