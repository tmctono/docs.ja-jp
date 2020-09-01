---
description: value コンテキスト キーワード - C# リファレンス
title: value コンテキスト キーワード - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: f72e9f097880d9de725a85a0973001baaefd9a9c
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141739"
---
# <a name="value-c-reference"></a>value (C# リファレンス)

コンテキスト キーワード `value` は、`set` アクセサーの [property](../../programming-guide/classes-and-structs/properties.md) と [indexer](../../programming-guide/indexers/index.md) 宣言で使用されます。 これは、メソッドの入力パラメーターに似ています。 `value` という単語は、クライアント コードでプロパティまたはインデクサーに割り当てる値を表します。 次の例の `MyDerivedClass` には、`Name` というプロパティがあります。このプロパティは `value` パラメーターを使用して、バッキング フィールド `name` に新しい文字列を割り当てます。 クライアント コードから見ると、演算は簡単な代入演算として記述されます。

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

詳細については、[プロパティ](../../programming-guide/classes-and-structs/properties.md)と[インデクサー](../../programming-guide/indexers/index.md)に関するページを参照してください。

## <a name="c-language-specification"></a>C# 言語仕様

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>関連項目

- [C# リファレンス](../index.md)
- [C# プログラミング ガイド](../../programming-guide/index.md)
- [C# のキーワード](index.md)
