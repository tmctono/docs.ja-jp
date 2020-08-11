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
# <a name="nameof-expression-c-reference"></a><span data-ttu-id="b8d5f-102">nameof 式 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="b8d5f-102">nameof expression (C# reference)</span></span>

<span data-ttu-id="b8d5f-103">`nameof` 式を使うと、変数、型、またはメンバーの名前が文字列定数として生成されます。</span><span class="sxs-lookup"><span data-stu-id="b8d5f-103">A `nameof` expression produces the name of a variable, type, or member as the string constant:</span></span>

[!code-csharp-interactive[nameof expression](snippets/shared/NameOfOperator.cs#Examples)]

<span data-ttu-id="b8d5f-104">前の例で示されているように、型と名前空間の場合、生成される名前は通常[完全修飾](~/_csharplang/spec/basic-concepts.md#fully-qualified-names)ではありません。</span><span class="sxs-lookup"><span data-stu-id="b8d5f-104">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="b8d5f-105">[逐語的識別子](../tokens/verbatim.md)の場合、次の例に示すように、`@` 文字は名前の一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="b8d5f-105">In the case of [verbatim identifiers](../tokens/verbatim.md), the `@` character is not the part of a name, as the following example shows:</span></span>

[!code-csharp-interactive[nameof verbatim](snippets/shared/NameOfOperator.cs#Verbatim)]

<span data-ttu-id="b8d5f-106">`nameof` 式はコンパイル時に評価され、実行時には影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="b8d5f-106">A `nameof` expression is evaluated at compile time and has no effect at run time.</span></span>

<span data-ttu-id="b8d5f-107">`nameof` 式を使って、引数をチェックするコードの保守性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="b8d5f-107">You can use a `nameof` expression to make the argument-checking code more maintainable:</span></span>

[!code-csharp[nameof and argument check](snippets/shared/NameOfOperator.cs#ExceptionMessage)]

<span data-ttu-id="b8d5f-108">`nameof` 式は C# 6 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="b8d5f-108">A `nameof` expression is available in C# 6 and later.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b8d5f-109">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="b8d5f-109">C# language specification</span></span>

<span data-ttu-id="b8d5f-110">詳細については、[C# 言語仕様](~/_csharplang/spec/introduction.md)の「[Nameof 式](~/_csharplang/spec/expressions.md#nameof-expressions)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b8d5f-110">For more information, see the [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b8d5f-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="b8d5f-111">See also</span></span>

- [<span data-ttu-id="b8d5f-112">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="b8d5f-112">C# reference</span></span>](../index.md)
- [<span data-ttu-id="b8d5f-113">C# の演算子と式</span><span class="sxs-lookup"><span data-stu-id="b8d5f-113">C# operators and expressions</span></span>](index.md)
