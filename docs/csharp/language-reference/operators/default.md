---
title: 既定値式 - C# リファレンス
description: 既定値式を使用して、型の既定値を取得します
ms.date: 03/13/2020
f1_keywords:
- default_CSharpKeyword
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: 92ad8e919567e1f9f57e6875d53c4055eb960829
ms.sourcegitcommit: e078b7540a8293ca1b604c9c0da1ff1506f0170b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "91997640"
---
# <a name="default-value-expressions-c-reference"></a>既定値式 (C# リファレンス)

既定値式を使用すると、型の[既定値](../builtin-types/default-values.md)が生成されます。 既定値式には、次の 2 種類があります: [default 演算子](#default-operator)の呼び出しと、[default リテラル](#default-literal)です。

また、[`switch` ステートメント](../keywords/switch.md)内の既定の case ラベルとして、`default` キーワードを使うこともできます。

## <a name="default-operator"></a>default 演算子

`default` 演算子への引数では、次の例で示すように、型または型パラメーターの名前を指定する必要があります。

[!code-csharp-interactive[default of T](snippets/shared/DefaultOperator.cs#WithOperand)]

## <a name="default-literal"></a>default リテラル

C# 7.1 以降では、`default` リテラルを使って、コンパイラが式の型を推論できる場合に、型の既定値を生成できます。 `default` リテラル式では、`T` が推定型である式 `default(T)` と同じ値が生成されます。 `default` リテラルは、次のいずれの場合でも使用できます。

- 変数の代入または初期化。
- [省略可能なメソッド パラメーター](../../methods.md#optional-parameters-and-arguments)の既定値の宣言。
- メソッド呼び出しでの引数値の指定。
- [`return` ステートメント](../keywords/return.md)内、または[式のようなメンバー](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)内の式として。

`default` リテラルの使い方の例を次に示します。

[!code-csharp-interactive[default literal](snippets/shared/DefaultOperator.cs#DefaultLiteral)]

## <a name="c-language-specification"></a>C# 言語仕様

詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の「[既定値の式](~/_csharplang/spec/expressions.md#default-value-expressions)」セクションをご覧ください。

`default` リテラルについて詳しくは、[機能提案メモ](~/_csharplang/proposals/csharp-7.1/target-typed-default.md)をご覧ください。

## <a name="see-also"></a>関連項目

- [C# リファレンス](../index.md)
- [C# の演算子と式](index.md)
- [C# 型の既定値](../builtin-types/default-values.md)
- [.NET のジェネリック](../../../standard/generics/index.md)
