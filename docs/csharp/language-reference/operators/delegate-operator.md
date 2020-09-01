---
description: delegate 演算子 - C# リファレンス
title: delegate 演算子 - C# リファレンス
ms.date: 07/18/2019
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: 1dfaaf40c0f5a19534adef3be7e3c917bc95c4a8
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89122252"
---
# <a name="delegate-operator-c-reference"></a>delegate 演算子 (C# リファレンス)

`delegate` 演算子を使うと、デリゲート型に変換できる匿名メソッドを作成できます。

[!code-csharp-interactive[anonymous method](snippets/shared/DelegateOperator.cs#AnonymousMethod)]

> [!NOTE]
> C# 3 以降では、匿名関数を作成するためのより簡潔で表現性に優れた方法がラムダ式によって提供されています。 ラムダ式を作成するには、[=> 演算子](lambda-operator.md)を使います。
>
> [!code-csharp-interactive[lambda expression](snippets/shared/DelegateOperator.cs#Lambda)]
>
> 外部変数のキャプチャなど、ラムダ式の機能の詳細については、[ラムダ式](lambda-expressions.md)に関するページをご覧ください。

`delegate` 演算子を使用する際に、パラメーター リストを省略する場合があります。 そうした場合、次の例に示すように、作成された匿名メソッドは任意のパラメーター リストを持つデリゲート型に変換できます。

[!code-csharp-interactive[no parameter list](snippets/shared/DelegateOperator.cs#WithoutParameterList)]

これは、ラムダ式でサポートされていない匿名メソッドの唯一の機能です。 それ以外の場合は、すべてラムダ式を使用してインライン コードを書くことをお勧めします。

`delegate` キーワードは、[デリゲート型](../builtin-types/reference-types.md#the-delegate-type)を宣言するためにも使います。

## <a name="c-language-specification"></a>C# 言語仕様

詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の[無名関数の式](~/_csharplang/spec/expressions.md#anonymous-function-expressions)に関するセクションを参照してください。

## <a name="see-also"></a>関連項目

- [C# リファレンス](../index.md)
- [C# の演算子と式](index.md)
- [=> 演算子](lambda-operator.md)
