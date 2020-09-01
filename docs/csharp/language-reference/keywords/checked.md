---
description: checked キーワード - C# リファレンス
title: checked キーワード - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- checked_CSharpKeyword
- checked
helpviewer_keywords:
- checked keyword [C#]
ms.assetid: 718a1194-988d-48a3-b089-d6ee8bd1608d
ms.openlocfilehash: 4dd8bc02d3af89d6bab3aef55a88cb8b40704da6
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138281"
---
# <a name="checked-c-reference"></a>checked (C# リファレンス)

`checked` キーワードは、整数型の算術演算と変換に対してオーバーフロー チェックを明示的に有効にするために使用します。

既定では、定数値のみを含む式がチェック先の型の範囲外にある値を生成した場合、コンパイラ エラーが発生します。 式が 1 つ以上の非定数値を含む場合、コンパイラはオーバーフローを検出しません。 次の例で `i2` に割り当てられた式を評価しても、コンパイラ エラーは発生しません。

[!code-csharp[csrefKeywordsChecked#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#3)]

既定では、これらの非定数式のオーバーフローは実行時にもチェックされず、オーバーフロー例外も発生しません。 前の例では、2 つの正の整数の合計として -2,147,483,639 が表示されます。

オーバーフロー チェックを有効にするには、コンパイラ オプション、環境設定、または `checked` キーワードを使用します。 `checked` 式または `checked` ブロックを使用して、前の合計によって生じたオーバーフローを実行時に検出する方法を次の例に示します。 どちらの例でもオーバーフロー例外が発生します。

[!code-csharp[csrefKeywordsChecked#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#4)]

[unchecked](./unchecked.md) キーワードを使用してオーバーフロー チェックを行わないようにすることもできます。

## <a name="example"></a>例

この例では、`checked` を使用して実行時のオーバーフロー チェックを有効にする方法を示します。

[!code-csharp[csrefKeywordsChecked#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#1)]

## <a name="c-language-specification"></a>C# 言語仕様

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>関連項目

- [C# リファレンス](../index.md)
- [C# プログラミング ガイド](../../programming-guide/index.md)
- [C# のキーワード](./index.md)
- [Checked と Unchecked](./checked-and-unchecked.md)
- [unchecked](./unchecked.md)
