---
title: delegate 演算子 - C# リファレンス
ms.date: 07/18/2019
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: 33c438b88f1e993f4648786da9b20b91961b7ee1
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062991"
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

## <a name="see-also"></a>参照

- [C# リファレンス](../index.md)
- [C# の演算子と式](index.md)
- [=> 演算子](lambda-operator.md)
