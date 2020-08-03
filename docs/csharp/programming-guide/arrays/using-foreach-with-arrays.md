---
title: 配列での foreach の使用 - C# プログラミング ガイド
description: C# で foreach ステートメントを使用すると、配列の要素が反復処理されます。 1 次元配列の場合、foreach によってインデックスの昇順で要素が処理されます。
ms.date: 05/23/2018
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
ms.openlocfilehash: d924a3ef3351cbb30b809a1542f35314ee721852
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474541"
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a>配列での foreach の使用 (C# プログラミング ガイド)

[foreach](../../language-reference/keywords/foreach-in.md) ステートメントでは、配列の要素の反復処理を、簡単かつ安全に行うことができます。

1 次元配列の場合、`foreach` ステートメントは、インデックス 0 から始まりインデックス `Length - 1` で終わるインデックスの昇順で要素を処理します。

 [!code-csharp[csProgGuideArrays#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#28)]

多次元配列の場合、右端の次元のインデックスが最初に加算されていき、次にその左の次元、またその左、というような方法で各要素がトラバースされます。

 [!code-csharp[csProgGuideArrays#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#29)]

ただし、多次元配列では、入れ子になった [for](../../language-reference/keywords/for.md) ループを使用した方が、配列要素を処理する順序をより厳密に制御できます。

## <a name="see-also"></a>関連項目

- <xref:System.Array>
- [C# プログラミング ガイド](../index.md)
- [配列](index.md)
- [1 次元配列](single-dimensional-arrays.md)
- [多次元配列](multidimensional-arrays.md)
- [ジャグ配列](jagged-arrays.md)
