---
title: implicit - C# リファレンス
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- implicit
- implicit_CSharpKeyword
helpviewer_keywords:
- implicit keyword [C#]
ms.assetid: 34db590e-eb3a-4f11-88d0-ffb3cd753dab
ms.openlocfilehash: 00fe1a02b52ef2ddc393bc7424efa73fc4059a9c
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2019
ms.locfileid: "67610108"
---
# <a name="implicit-c-reference"></a><span data-ttu-id="25dea-102">implicit (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="25dea-102">implicit (C# Reference)</span></span>

<span data-ttu-id="25dea-103">`implicit` キーワードを使用して、暗黙のユーザー定義型変換演算子を宣言します。</span><span class="sxs-lookup"><span data-stu-id="25dea-103">The `implicit` keyword is used to declare an implicit user-defined type conversion operator.</span></span> <span data-ttu-id="25dea-104">変換を実行してもデータ損失が発生しないことが保証されている場合に、ユーザー定義型とその他の型との間の暗黙の変換を有効にするために使用します。</span><span class="sxs-lookup"><span data-stu-id="25dea-104">Use it to enable implicit conversions between a user-defined type and another type, if the conversion is guaranteed not to cause a loss of data.</span></span>

## <a name="example"></a><span data-ttu-id="25dea-105">例</span><span class="sxs-lookup"><span data-stu-id="25dea-105">Example</span></span>

[!code-csharp[csrefKeywordsConversion#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#5)]

<span data-ttu-id="25dea-106">暗黙の変換では不要なキャストを省略できるため、ソース コードが読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="25dea-106">By eliminating unnecessary casts, implicit conversions can improve source code readability.</span></span> <span data-ttu-id="25dea-107">ただし、暗黙の変換では、一方の型からもう一方の型に明示的にキャストする必要がないため、予期しない結果が生じないように注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="25dea-107">However, because implicit conversions do not require programmers to explicitly cast from one type to the other, care must be taken to prevent unexpected results.</span></span> <span data-ttu-id="25dea-108">プログラマーが意識しなくても安全に使用できるように、通常、暗黙の変換演算子は、例外をスローしたり情報を失ったりしてはなりません。</span><span class="sxs-lookup"><span data-stu-id="25dea-108">In general, implicit conversion operators should never throw exceptions and never lose information so that they can be used safely without the programmer's awareness.</span></span> <span data-ttu-id="25dea-109">このような条件を満たすことができない変換演算子は、`explicit` でマークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="25dea-109">If a conversion operator cannot meet those criteria, it should be marked `explicit`.</span></span> <span data-ttu-id="25dea-110">詳細については、「[変換演算子の使用](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25dea-110">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="25dea-111">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="25dea-111">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="25dea-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="25dea-112">See also</span></span>

- [<span data-ttu-id="25dea-113">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="25dea-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="25dea-114">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="25dea-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="25dea-115">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="25dea-115">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="25dea-116">explicit</span><span class="sxs-lookup"><span data-stu-id="25dea-116">explicit</span></span>](explicit.md)
- [<span data-ttu-id="25dea-117">演算子のオーバーロード</span><span class="sxs-lookup"><span data-stu-id="25dea-117">Operator overloading</span></span>](../operators/operator-overloading.md)
- [<span data-ttu-id="25dea-118">方法: 構造体間にユーザー定義の変換を実装する</span><span class="sxs-lookup"><span data-stu-id="25dea-118">How to: Implement User-Defined Conversions Between Structs</span></span>](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
