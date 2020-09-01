---
description: new 制約 - C# リファレンス
title: new 制約 - C# リファレンス
ms.date: 07/20/2015
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
ms.openlocfilehash: f7b097729fe973aba7b85c48e1b1033aade83080
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139451"
---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="f8101-103">new 制約 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="f8101-103">new constraint (C# Reference)</span></span>

<span data-ttu-id="f8101-104">`new` 制約は、ジェネリック クラス宣言内の型引数に、パブリックでパラメーターなしのコンストラクターが必要であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="f8101-104">The `new` constraint specifies that a type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="f8101-105">`new` 制約を使用する場合、型を抽象型にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f8101-105">To use the `new` constraint, the type cannot be abstract.</span></span>

<span data-ttu-id="f8101-106">`new` 制約は、次の例に示すように、ジェネリック クラスである型の新しいインスタンスを作成する場合に型パラメーターに適用されます。</span><span class="sxs-lookup"><span data-stu-id="f8101-106">Apply the `new` constraint to a type parameter when a generic class creates new instances of the type, as shown in the following example:</span></span>

[!code-csharp[csrefKeywordsOperator#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#5)]

<span data-ttu-id="f8101-107">`new()` 制約を別の制約と併用する場合、この制約を最後に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8101-107">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>

[!code-csharp[csrefKeywordsOperator#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#6)]

<span data-ttu-id="f8101-108">詳細については、「[型パラメーターの制約](../../programming-guide/generics/constraints-on-type-parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8101-108">For more information, see [Constraints on Type Parameters](../../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

<span data-ttu-id="f8101-109">`new` キーワードは、[型のインスタンスの作成](../operators/new-operator.md)に使用することも、または[メンバーの宣言修飾子](new-modifier.md)として使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="f8101-109">You can also use the `new` keyword to [create an instance of a type](../operators/new-operator.md) or as a [member declaration modifier](new-modifier.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f8101-110">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="f8101-110">C# language specification</span></span>

<span data-ttu-id="f8101-111">詳細については、[C# 言語仕様](~/_csharplang/spec/introduction.md)の「[型パラメーターの制約](~/_csharplang/spec/classes.md#type-parameter-constraints)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8101-111">For more information, see the [Type parameter constraints](~/_csharplang/spec/classes.md#type-parameter-constraints) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f8101-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8101-112">See also</span></span>

- [<span data-ttu-id="f8101-113">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="f8101-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f8101-114">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="f8101-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f8101-115">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="f8101-115">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="f8101-116">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="f8101-116">Generics</span></span>](../../programming-guide/generics/index.md)
