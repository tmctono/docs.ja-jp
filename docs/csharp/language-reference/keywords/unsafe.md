---
title: unsafe キーワード - C# リファレンス
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
ms.openlocfilehash: bca12c1dd8c79a5ae17e4a9b7b75d3c7b302fb89
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2019
ms.locfileid: "65875874"
---
# <a name="unsafe-c-reference"></a><span data-ttu-id="e5996-102">unsafe (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="e5996-102">unsafe (C# Reference)</span></span>

<span data-ttu-id="e5996-103">`unsafe` キーワードは、ポインターに関連するすべての操作に必要な、unsafe コンテキストを示します。</span><span class="sxs-lookup"><span data-stu-id="e5996-103">The `unsafe` keyword denotes an unsafe context, which is required for any operation involving pointers.</span></span> <span data-ttu-id="e5996-104">詳しくは、「[アンセーフ コードとポインター](../../programming-guide/unsafe-code-pointers/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e5996-104">For more information, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md).</span></span>

<span data-ttu-id="e5996-105">`unsafe` 修飾子は、型またはメンバーの宣言で使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5996-105">You can use the `unsafe` modifier in the declaration of a type or a member.</span></span> <span data-ttu-id="e5996-106">そのため、型やメンバーの全体的なテキスト範囲が unsafe コンテキストと見なされます。</span><span class="sxs-lookup"><span data-stu-id="e5996-106">The entire textual extent of the type or member is therefore considered an unsafe context.</span></span> <span data-ttu-id="e5996-107">たとえば、次に示すのは、`unsafe` 修飾子を使用して宣言されたメソッドです。</span><span class="sxs-lookup"><span data-stu-id="e5996-107">For example, the following is a method declared with the `unsafe` modifier:</span></span>

```csharp
unsafe static void FastCopy(byte[] src, byte[] dst, int count)
{
    // Unsafe context: can use pointers here.
}
```

<span data-ttu-id="e5996-108">unsafe コンテキストのスコープはパラメーター リストからメソッドの末尾までなので、ポインターはパラメーター リストでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5996-108">The scope of the unsafe context extends from the parameter list to the end of the method, so pointers can also be used in the parameter list:</span></span>

```csharp
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}
```

<span data-ttu-id="e5996-109">また、unsafe ブロックを使用して、そのブロック内で unsafe コードを使用できるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e5996-109">You can also use an unsafe block to enable the use of an unsafe code inside this block.</span></span> <span data-ttu-id="e5996-110">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e5996-110">For example:</span></span>

```csharp
unsafe
{
    // Unsafe context: can use pointers here.
}
```

<span data-ttu-id="e5996-111">アンセーフ コードをコンパイルするには、[`-unsafe`](../compiler-options/unsafe-compiler-option.md) コンパイラ オプションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5996-111">To compile unsafe code, you must specify the [`-unsafe`](../compiler-options/unsafe-compiler-option.md) compiler option.</span></span> <span data-ttu-id="e5996-112">unsafe コードは、共通言語ランタイムでは検証できません。</span><span class="sxs-lookup"><span data-stu-id="e5996-112">Unsafe code is not verifiable by the common language runtime.</span></span>

## <a name="example"></a><span data-ttu-id="e5996-113">例</span><span class="sxs-lookup"><span data-stu-id="e5996-113">Example</span></span>

[!code-csharp[csrefKeywordsModifiers#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#22)]

## <a name="c-language-specification"></a><span data-ttu-id="e5996-114">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="e5996-114">C# language specification</span></span>

<span data-ttu-id="e5996-115">詳細については、「[C# 言語の仕様](../language-specification/index.md)」の[アンセーフ コード](~/_csharplang/spec/unsafe-code.md)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5996-115">For more information, see [Unsafe code](~/_csharplang/spec/unsafe-code.md) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="e5996-116">言語仕様は、C# の構文と使用法に関する信頼性のある情報源です。</span><span class="sxs-lookup"><span data-stu-id="e5996-116">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5996-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5996-117">See also</span></span>

- [<span data-ttu-id="e5996-118">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="e5996-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e5996-119">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="e5996-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e5996-120">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="e5996-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="e5996-121">fixed ステートメント</span><span class="sxs-lookup"><span data-stu-id="e5996-121">fixed Statement</span></span>](fixed-statement.md)
- [<span data-ttu-id="e5996-122">アンセーフ コードとポインター</span><span class="sxs-lookup"><span data-stu-id="e5996-122">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
- [<span data-ttu-id="e5996-123">固定サイズ バッファー</span><span class="sxs-lookup"><span data-stu-id="e5996-123">Fixed Size Buffers</span></span>](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
