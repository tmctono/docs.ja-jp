---
title: nameof 式 - C# リファレンス
ms.date: 04/23/2020
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof expression [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: b00c5f6f97d27290fb3773dcbb422bf9fb4c425b
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916774"
---
# <a name="nameof-expression-c-reference"></a>nameof 式 (C# リファレンス)

`nameof` 式を使うと、変数、型、またはメンバーの名前が文字列定数として生成されます。

[!code-csharp-interactive[nameof expression](snippets/shared/NameOfOperator.cs#Examples)]

前の例で示されているように、型と名前空間の場合、生成される名前は通常[完全修飾](~/_csharplang/spec/basic-concepts.md#fully-qualified-names)ではありません。

[逐語的識別子](../tokens/verbatim.md)の場合、次の例に示すように、`@` 文字は名前の一部ではありません。

[!code-csharp-interactive[nameof verbatim](snippets/shared/NameOfOperator.cs#Verbatim)]

`nameof` 式はコンパイル時に評価され、実行時には影響を与えません。

`nameof` 式を使って、引数をチェックするコードの保守性を高めることができます。

[!code-csharp[nameof and argument check](snippets/shared/NameOfOperator.cs#ExceptionMessage)]

`nameof` 式は C# 6 以降で使用できます。

## <a name="c-language-specification"></a>C# 言語仕様

詳細については、[C# 言語仕様](~/_csharplang/spec/introduction.md)の「[Nameof 式](~/_csharplang/spec/expressions.md#nameof-expressions)」セクションをご覧ください。

## <a name="see-also"></a>関連項目

- [C# リファレンス](../index.md)
- [C# の演算子と式](index.md)
