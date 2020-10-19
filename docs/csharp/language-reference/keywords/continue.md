---
description: continue ステートメント - C# リファレンス
title: continue ステートメント - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
ms.openlocfilehash: 6c70934c3b861e1a1433e5c0b95bb32e9d717c53
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877653"
---
# <a name="continue-c-reference"></a>continue (C# リファレンス)

`continue` ステートメントは、それを囲んでいる [while](./while.md)、[do](./do.md)、[for](./for.md)、または [foreach](./foreach-in.md) ステートメントの次の反復処理にコントロールを渡します。

## <a name="example"></a>例

この例では、1 から 10 までカウントするようカウンターが初期化されます。 `continue` ステートメントと式 `(i < 9)` を組み合わせて使用すると、`for` 本文の `continue` から終わりまでのステートメントが、`i` が 9 未満のイテレーションではスキップされます。 `for` ループの最後の 2 つのイテレーション (i == 9 と i == 10) では、`continue` ステートメントは実行されず、`i` の値がコンソールに出力されます。

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a>C# 言語仕様

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>関連項目

- [C# リファレンス](../index.md)
- [C# プログラミング ガイド](../../programming-guide/index.md)
- [C# のキーワード](./index.md)
- [break ステートメント](/cpp/cpp/break-statement-cpp)
