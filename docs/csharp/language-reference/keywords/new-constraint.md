---
title: new 制約 - C# リファレンス
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
ms.openlocfilehash: 7c788be52010cdfadbd3c03f9e570815d25bdbef
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2019
ms.locfileid: "67401495"
---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="3d4a3-102">new 制約 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="3d4a3-102">new constraint (C# Reference)</span></span>

<span data-ttu-id="3d4a3-103">`new` 制約は、ジェネリック クラス宣言内の型引数に、パブリックでパラメーターなしのコンストラクターが必要であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="3d4a3-103">The `new` constraint specifies that a type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="3d4a3-104">`new` 制約を使用する場合、型を抽象型にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3d4a3-104">To use the `new` constraint, the type cannot be abstract.</span></span>

<span data-ttu-id="3d4a3-105">`new` 制約は、次の例に示すように、ジェネリック クラスである型の新しいインスタンスを作成する場合に型パラメーターに適用されます。</span><span class="sxs-lookup"><span data-stu-id="3d4a3-105">Apply the `new` constraint to a type parameter when a generic class creates new instances of the type, as shown in the following example:</span></span>

[!code-csharp[csrefKeywordsOperator#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#5)]

<span data-ttu-id="3d4a3-106">`new()` 制約を別の制約と併用する場合、この制約を最後に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d4a3-106">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>

[!code-csharp[csrefKeywordsOperator#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#6)]

<span data-ttu-id="3d4a3-107">詳細については、「[型パラメーターの制約](../../programming-guide/generics/constraints-on-type-parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d4a3-107">For more information, see [Constraints on Type Parameters](../../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

<span data-ttu-id="3d4a3-108">`new` キーワードは、[型のインスタンスの作成](../operators/new-operator.md)に使用することも、または[メンバーの宣言修飾子](new-modifier.md)として使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="3d4a3-108">You can also use the `new` keyword to [create an instance of a type](../operators/new-operator.md) or as a [member declaration modifier](new-modifier.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="3d4a3-109">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="3d4a3-109">C# language specification</span></span>

<span data-ttu-id="3d4a3-110">詳細については、[C# 言語仕様](~/_csharplang/spec/introduction.md)の「[型パラメーターの制約](~/_csharplang/spec/classes.md#type-parameter-constraints)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d4a3-110">For more information, see the [Type parameter constraints](~/_csharplang/spec/classes.md#type-parameter-constraints) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3d4a3-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="3d4a3-111">See also</span></span>

- [<span data-ttu-id="3d4a3-112">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="3d4a3-112">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="3d4a3-113">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="3d4a3-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3d4a3-114">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="3d4a3-114">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="3d4a3-115">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="3d4a3-115">Generics</span></span>](../../programming-guide/generics/index.md)
