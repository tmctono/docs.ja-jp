---
title: オブジェクトとしての配列 - C# プログラミング ガイド
description: C# の配列は、抽出基本データ型 Array のオブジェクトです。 Length プロパティなど、Array のプロパティとその他のクラス メンバーを使用できます。
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
ms.openlocfilehash: 984def3ef74b07d7099fae6cae6d6f8ce7e03e12
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474723"
---
# <a name="arrays-as-objects-c-programming-guide"></a>オブジェクトとしての配列 (C# プログラミング ガイド)

C# の配列は、実際はオブジェクトです。C や C++ の場合のように、単なるアドレス指定可能な連続メモリ領域ではありません。 <xref:System.Array> はすべての配列型の抽象基本データ型で、 <xref:System.Array> のプロパティとその他のクラス メンバーを使用できます。 この例としては、<xref:System.Array.Length%2A> プロパティを使用して、配列の長さを取得します。 `numbers` 配列の長さ `5` を `lengthOfNumbers` という変数に代入するコードは、次のようになります。

[!code-csharp[csProgGuideArrays#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#3)]

<xref:System.Array> クラスには、配列の並べ替え、検索、コピーを行うための便利なメソッドやプロパティが他にも多数用意されています。

## <a name="example"></a>例

次の例では、<xref:System.Array.Rank%2A> プロパティを使用して、配列の次元数を表示します。

[!code-csharp[csProgGuideArrays#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#2)]

## <a name="see-also"></a>関連項目

- [C# プログラミング ガイド](../index.md)
- [配列](./index.md)
- [1 次元配列](./single-dimensional-arrays.md)
- [多次元配列](./multidimensional-arrays.md)
- [ジャグ配列](./jagged-arrays.md)
