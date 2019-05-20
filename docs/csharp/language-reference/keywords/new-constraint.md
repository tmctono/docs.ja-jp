---
title: new 制約 - C# リファレンス
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
ms.openlocfilehash: 32fcb13e1f217707d53300c532169b1a1759fa7e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633406"
---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="5d24c-102">new 制約 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="5d24c-102">new constraint (C# Reference)</span></span>

<span data-ttu-id="5d24c-103">`new` 制約は、ジェネリック クラス宣言内のすべての型引数に、パブリックでパラメーターなしのコンストラクターが必要であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="5d24c-103">The `new` constraint specifies that any type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="5d24c-104">new 制約を使用する場合、型を抽象型にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="5d24c-104">To use the new constraint, the type cannot be abstract.</span></span>

## <a name="example"></a><span data-ttu-id="5d24c-105">例</span><span class="sxs-lookup"><span data-stu-id="5d24c-105">Example</span></span>

<span data-ttu-id="5d24c-106">`new` 制約は、次の例に示すように、ジェネリック クラスである型の新しいインスタンスを作成する場合に型パラメーターに適用されます。</span><span class="sxs-lookup"><span data-stu-id="5d24c-106">Apply the `new` constraint to a type parameter when your generic class creates new instances of the type, as shown in the following example:</span></span>

[!code-csharp[csrefKeywordsOperator#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#5)]

## <a name="example"></a><span data-ttu-id="5d24c-107">例</span><span class="sxs-lookup"><span data-stu-id="5d24c-107">Example</span></span>

<span data-ttu-id="5d24c-108">`new()` 制約を別の制約と併用する場合、この制約を最後に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d24c-108">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>

[!code-csharp[csrefKeywordsOperator#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#6)]

<span data-ttu-id="5d24c-109">詳細については、「[型パラメーターの制約](../../programming-guide/generics/constraints-on-type-parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d24c-109">For more information, see [Constraints on Type Parameters](../../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5d24c-110">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="5d24c-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="5d24c-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d24c-111">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="5d24c-112">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="5d24c-112">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="5d24c-113">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="5d24c-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5d24c-114">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="5d24c-114">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="5d24c-115">演算子のキーワード</span><span class="sxs-lookup"><span data-stu-id="5d24c-115">Operator Keywords</span></span>](operator-keywords.md)
- [<span data-ttu-id="5d24c-116">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="5d24c-116">Generics</span></span>](../../programming-guide/generics/index.md)
