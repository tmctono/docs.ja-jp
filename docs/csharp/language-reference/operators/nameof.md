---
title: nameof 式 - C# リファレンス
ms.date: 07/12/2019
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof expression [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: 5a68161be7bb03122d2a63ccef4365c5853862b2
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507140"
---
# <a name="nameof-expression-c-reference"></a><span data-ttu-id="b7136-102">nameof 式 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="b7136-102">nameof expression (C# reference)</span></span>

<span data-ttu-id="b7136-103">`nameof` 式を使うと、変数、型、またはメンバーの名前が文字列定数として生成されます。</span><span class="sxs-lookup"><span data-stu-id="b7136-103">A `nameof` expression produces the name of a variable, type, or member as the string constant:</span></span>

[!code-csharp-interactive[nameof expression](snippets/NameOfOperator.cs#Examples)]

<span data-ttu-id="b7136-104">前の例で示されているように、型と名前空間の場合、生成される名前は通常[完全修飾](~/_csharplang/spec/basic-concepts.md#fully-qualified-names)ではありません。</span><span class="sxs-lookup"><span data-stu-id="b7136-104">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="b7136-105">`nameof` 式はコンパイル時に評価され、実行時には影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="b7136-105">A `nameof` expression is evaluated at compile time and has no effect at run time.</span></span>

<span data-ttu-id="b7136-106">`nameof` 式を使って、引数をチェックするコードの保守性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="b7136-106">You can use a `nameof` expression to make the argument-checking code more maintainable:</span></span>

[!code-csharp[nameof and argument check](snippets/NameOfOperator.cs#ExceptionMessage)]

<span data-ttu-id="b7136-107">`nameof` 式は C# 6 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="b7136-107">A `nameof` expression is available in C# 6 and later.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b7136-108">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="b7136-108">C# language specification</span></span>

<span data-ttu-id="b7136-109">詳細については、[C# 言語仕様](~/_csharplang/spec/introduction.md)の「[Nameof 式](~/_csharplang/spec/expressions.md#nameof-expressions)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b7136-109">For more information, see the [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b7136-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="b7136-110">See also</span></span>

- [<span data-ttu-id="b7136-111">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="b7136-111">C# reference</span></span>](../index.md)
- [<span data-ttu-id="b7136-112">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="b7136-112">C# operators</span></span>](index.md)
