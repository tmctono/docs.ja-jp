---
title: '@ - C# リファレンス'
ms.date: 02/09/2017
f1_keywords:
- '@_CSharpKeyword'
- '@'
helpviewer_keywords:
- '@ special character [C#]'
- '@ language element [C#]'
ms.assetid: 89bc7e53-85f5-478a-866d-1cca003c4e8c
ms.openlocfilehash: a3446eceb0d3c415e36ea1d2c7d8d6d34f65350d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712417"
---
# <a name="-c-reference"></a><span data-ttu-id="6ae4f-102">@ (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="6ae4f-102">@ (C# Reference)</span></span>

<span data-ttu-id="6ae4f-103">特殊文字 `@` は、逐語的識別子として機能します。</span><span class="sxs-lookup"><span data-stu-id="6ae4f-103">The `@` special character serves as a verbatim identifier.</span></span> <span data-ttu-id="6ae4f-104">これは次の目的に使用できます。</span><span class="sxs-lookup"><span data-stu-id="6ae4f-104">It can be used in the following ways:</span></span>

1. <span data-ttu-id="6ae4f-105">C# のキーワードを識別子として使用できるようにする。</span><span class="sxs-lookup"><span data-stu-id="6ae4f-105">To enable C# keywords to be used as identifiers.</span></span> <span data-ttu-id="6ae4f-106">コード要素のプレフィックスとして `@` 文字を使用すると、その要素はC# のキーワードではなく、識別子としてコンパイラに解釈されます。</span><span class="sxs-lookup"><span data-stu-id="6ae4f-106">The `@` character prefixes a code element that the compiler is to interpret as an identifier rather than a C# keyword.</span></span> <span data-ttu-id="6ae4f-107">次の例では、`@` 文字を使用して、`for` ループで使用する `for` という識別子を定義しています。</span><span class="sxs-lookup"><span data-stu-id="6ae4f-107">The following example uses the `@` character to define an identifier named `for` that it uses in a `for` loop.</span></span>

   [!code-csharp[verbatim1](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#1)]

1. <span data-ttu-id="6ae4f-108">文字列リテラルを逐語的に解釈することを示す。</span><span class="sxs-lookup"><span data-stu-id="6ae4f-108">To indicate that a string literal is to be interpreted verbatim.</span></span> <span data-ttu-id="6ae4f-109">このインスタンス内の `@` 文字は、*逐語的文字列リテラル*を定義します。</span><span class="sxs-lookup"><span data-stu-id="6ae4f-109">The `@` character in this instance defines a *verbatim string literal*.</span></span> <span data-ttu-id="6ae4f-110">単純なエスケープ シーケンス (バック スラッシュの `"\\"` など)、16 進数のエスケープ シーケンス (大文字 A の `"\x0041"` など)、Unicode のエスケープ シーケンス (大文字 A の `"\u0041"` など) は、リテラルに解釈されます。</span><span class="sxs-lookup"><span data-stu-id="6ae4f-110">Simple escape sequences (such as `"\\"` for a backslash), hexadecimal escape sequences (such as `"\x0041"` for an uppercase A), and Unicode escape sequences (such as `"\u0041"` for an uppercase A) are interpreted literally.</span></span> <span data-ttu-id="6ae4f-111">引用符のエスケープ シーケンス (`""`) だけは、リテラルに解釈することはできません。一重引用符が生成されます。</span><span class="sxs-lookup"><span data-stu-id="6ae4f-111">Only a quote escape sequence (`""`) is not interpreted literally; it produces a single quotation mark.</span></span> <span data-ttu-id="6ae4f-112">また、逐語的な[補間文字列](interpolated.md)の場合、中かっこエスケープ シーケンス (`{{` と `}}`) は文字どおり解釈されません。単一の中かっこ文字が生成されます。</span><span class="sxs-lookup"><span data-stu-id="6ae4f-112">Additionally, in case of a verbatim [interpolated string](interpolated.md) brace escape sequences (`{{` and `}}`) are not interpreted literally; they produce single brace characters.</span></span> <span data-ttu-id="6ae4f-113">次の例では、2 つの同じファイル パスを定義しています。一方は通常の文字列リテラルを使用して、もう一方は 逐語的文字列リテラルを使用して定義しています。</span><span class="sxs-lookup"><span data-stu-id="6ae4f-113">The following example defines two identical file paths, one by using a regular string literal and the other by using a verbatim string literal.</span></span> <span data-ttu-id="6ae4f-114">これは、逐語的文字列リテラルの一般的な用途の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="6ae4f-114">This is one of the more common uses of verbatim string literals.</span></span>

   [!code-csharp[verbatim2](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#2)]

   <span data-ttu-id="6ae4f-115">次の例は、同じ文字シーケンスを通常の文字列リテラルと 逐語的文字列リテラルで定義した場合の結果を示したものです。</span><span class="sxs-lookup"><span data-stu-id="6ae4f-115">The following example illustrates the effect of defining a regular string literal and a verbatim string literal that contain identical character sequences.</span></span>

   [!code-csharp[verbatim3](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#3)]

1. <span data-ttu-id="6ae4f-116">名前の競合がある場合に、コンパイラが属性を区別できるようにする。</span><span class="sxs-lookup"><span data-stu-id="6ae4f-116">To enable the compiler to distinguish between attributes in cases of a naming conflict.</span></span> <span data-ttu-id="6ae4f-117">属性は <xref:System.Attribute> の派生クラスです。</span><span class="sxs-lookup"><span data-stu-id="6ae4f-117">An attribute is a class that derives from <xref:System.Attribute>.</span></span> <span data-ttu-id="6ae4f-118">通常、その型の名前には **Attribute** サフィックスが含まれます。これは、コンパイラがその規則を強制していない場合でも同様です。</span><span class="sxs-lookup"><span data-stu-id="6ae4f-118">Its type name typically includes the suffix **Attribute**, although the compiler does not enforce this convention.</span></span> <span data-ttu-id="6ae4f-119">そのため属性は、完全な型名 (たとえば、`[InfoAttribute]`) か、短縮名 (たとえば、`[Info]`) によってコード内から参照できます。</span><span class="sxs-lookup"><span data-stu-id="6ae4f-119">The attribute can then be referenced in code either by its full type name (for example, `[InfoAttribute]` or its shortened name (for example, `[Info]`).</span></span> <span data-ttu-id="6ae4f-120">ただし、短縮された 2 つの属性型名が同じである場合、一方の型名に **Attribute** サフィックスが含まれていて、もう一方に含まれていないと、名前の競合が発生します。</span><span class="sxs-lookup"><span data-stu-id="6ae4f-120">However, a naming conflict occurs if two shortened attribute type names are identical, and one type name includes the **Attribute** suffix but the other does not.</span></span> <span data-ttu-id="6ae4f-121">たとえば、次のコードでは、`Info` と `InfoAttribute` のどちらの属性が `Example` クラスに適用されるかをコンパイラが判断できないため、コンパイルが失敗します。</span><span class="sxs-lookup"><span data-stu-id="6ae4f-121">For example, the following code fails to compile because the compiler cannot determine whether the `Info` or `InfoAttribute` attribute is applied to the `Example` class.</span></span> <span data-ttu-id="6ae4f-122">詳細については、[CS1614](../compiler-messages/cs1614.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ae4f-122">See [CS1614](../compiler-messages/cs1614.md) for more information.</span></span>

   [!code-csharp[verbatim4](../../../../samples/snippets/csharp/language-reference/keywords/verbatim2.cs#1)]

## <a name="see-also"></a><span data-ttu-id="6ae4f-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ae4f-123">See also</span></span>

- [<span data-ttu-id="6ae4f-124">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="6ae4f-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6ae4f-125">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="6ae4f-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="6ae4f-126">C# 特殊文字</span><span class="sxs-lookup"><span data-stu-id="6ae4f-126">C# Special Characters</span></span>](./index.md)
