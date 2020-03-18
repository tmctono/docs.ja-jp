---
title: nameof 演算子 - C# リファレンス
ms.date: 07/12/2019
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof operator [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: ffbc801acf61bf72db1c88912dc2142a478fa280
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846273"
---
# <a name="nameof-operator-c-reference"></a><span data-ttu-id="a1cdd-102">nameof 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="a1cdd-102">nameof operator (C# reference)</span></span>

<span data-ttu-id="a1cdd-103">`nameof` 演算子を使うと、変数、型、またはメンバーの名前を文字列定数として取得できます。</span><span class="sxs-lookup"><span data-stu-id="a1cdd-103">The `nameof` operator obtains the name of a variable, type, or member as the string constant:</span></span>

[!code-csharp-interactive[nameof operator](snippets/NameOfOperator.cs#Examples)]

<span data-ttu-id="a1cdd-104">前の例で示されているように、型と名前空間の場合、生成される名前は通常[完全修飾](~/_csharplang/spec/basic-concepts.md#fully-qualified-names)ではありません。</span><span class="sxs-lookup"><span data-stu-id="a1cdd-104">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="a1cdd-105">`nameof` 演算子はコンパイル時に評価され、実行時には影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="a1cdd-105">The `nameof` operator is evaluated at compile time and has no effect at run time.</span></span>

<span data-ttu-id="a1cdd-106">`nameof` 演算子を使って、引数をチェックするコードを保守しやすくすることができます。</span><span class="sxs-lookup"><span data-stu-id="a1cdd-106">You can use the `nameof` operator to make the argument-checking code more maintainable:</span></span>

[!code-csharp[nameof and argument check](snippets/NameOfOperator.cs#ExceptionMessage)]

<span data-ttu-id="a1cdd-107">`nameof` 演算子は C# 6 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="a1cdd-107">The `nameof` operator is available in C# 6 and later.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a1cdd-108">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="a1cdd-108">C# language specification</span></span>

<span data-ttu-id="a1cdd-109">詳細については、[C# 言語仕様](~/_csharplang/spec/expressions.md#nameof-expressions)の「[Nameof 式](~/_csharplang/spec/introduction.md)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a1cdd-109">For more information, see the [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a1cdd-110">参照</span><span class="sxs-lookup"><span data-stu-id="a1cdd-110">See also</span></span>

- [<span data-ttu-id="a1cdd-111">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="a1cdd-111">C# reference</span></span>](../index.md)
- [<span data-ttu-id="a1cdd-112">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="a1cdd-112">C# operators</span></span>](index.md)
