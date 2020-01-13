---
title: 暗黙的に型指定される配列 - C# プログラミング ガイド
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], implicitly-typed
- implicitly-typed arrays [C#]
- C# language, implicitly typed arrays
ms.assetid: e05be95c-6732-403d-ae42-b35f057cbbea
ms.openlocfilehash: 943760af30422cd333fdff65cdf678108c9d9564
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705718"
---
# <a name="implicitly-typed-arrays-c-programming-guide"></a><span data-ttu-id="acddc-102">暗黙的に型指定される配列 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="acddc-102">Implicitly Typed Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="acddc-103">配列インスタンスの型が、配列初期化子で指定された要素から推論される暗黙的に型指定された配列を作成できます。</span><span class="sxs-lookup"><span data-stu-id="acddc-103">You can create an implicitly-typed array in which the type of the array instance is inferred from the elements specified in the array initializer.</span></span> <span data-ttu-id="acddc-104">暗黙的に型指定された変数の規則は、暗黙的に型指定された配列にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="acddc-104">The rules for any implicitly-typed variable also apply to implicitly-typed arrays.</span></span> <span data-ttu-id="acddc-105">詳細については、「[暗黙的に型指定されるローカル変数](../classes-and-structs/implicitly-typed-local-variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acddc-105">For more information, see [Implicitly Typed Local Variables](../classes-and-structs/implicitly-typed-local-variables.md).</span></span>

<span data-ttu-id="acddc-106">暗黙的に型指定された配列は通常、匿名型、オブジェクト、コレクション初期化子と共にクエリ式で使用されます。</span><span class="sxs-lookup"><span data-stu-id="acddc-106">Implicitly-typed arrays are usually used in query expressions together with anonymous types and object and collection initializers.</span></span>

<span data-ttu-id="acddc-107">次の例では、暗黙的に型指定された配列を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="acddc-107">The following examples show how to create an implicitly-typed array:</span></span>

[!code-csharp[csProgGuideLINQ#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#37)]

<span data-ttu-id="acddc-108">前の例で、暗黙的に型指定された配列では、初期化ステートメントの左側では角かっこが使用されていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="acddc-108">In the previous example, notice that with implicitly-typed arrays, no square brackets are used on the left side of the initialization statement.</span></span> <span data-ttu-id="acddc-109">また、ジャグ配列は、1 次元の配列と同じように `new []` を使用して初期化されます。</span><span class="sxs-lookup"><span data-stu-id="acddc-109">Note also that jagged arrays are initialized by using `new []` just like single-dimension arrays.</span></span>

## <a name="implicitly-typed-arrays-in-object-initializers"></a><span data-ttu-id="acddc-110">オブジェクト初期化子で暗黙的に型指定された配列</span><span class="sxs-lookup"><span data-stu-id="acddc-110">Implicitly-typed Arrays in Object Initializers</span></span>

<span data-ttu-id="acddc-111">配列を含む匿名型を作成するときには、型のオブジェクトの初期化子で配列を暗黙的に型指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="acddc-111">When you create an anonymous type that contains an array, the array must be implicitly typed in the type's object initializer.</span></span> <span data-ttu-id="acddc-112">次の例では、`contacts` は、匿名型の暗黙的に型指定された配列で、それぞれが `PhoneNumbers` という名前の配列を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="acddc-112">In the following example, `contacts` is an implicitly-typed array of anonymous types, each of which contains an array named `PhoneNumbers`.</span></span> <span data-ttu-id="acddc-113">`var` キーワードは、オブジェクト初期化子内で使用されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="acddc-113">Note that the `var` keyword is not used inside the object initializers.</span></span>

[!code-csharp[csProgGuideLINQ#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#38)]

## <a name="see-also"></a><span data-ttu-id="acddc-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="acddc-114">See also</span></span>

- [<span data-ttu-id="acddc-115">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="acddc-115">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="acddc-116">暗黙的に型指定されるローカル変数</span><span class="sxs-lookup"><span data-stu-id="acddc-116">Implicitly Typed Local Variables</span></span>](../classes-and-structs/implicitly-typed-local-variables.md)
- [<span data-ttu-id="acddc-117">配列</span><span class="sxs-lookup"><span data-stu-id="acddc-117">Arrays</span></span>](./index.md)
- [<span data-ttu-id="acddc-118">匿名型</span><span class="sxs-lookup"><span data-stu-id="acddc-118">Anonymous Types</span></span>](../classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="acddc-119">オブジェクト初期化子とコレクション初期化子</span><span class="sxs-lookup"><span data-stu-id="acddc-119">Object and Collection Initializers</span></span>](../classes-and-structs/object-and-collection-initializers.md)
- [<span data-ttu-id="acddc-120">var</span><span class="sxs-lookup"><span data-stu-id="acddc-120">var</span></span>](../../language-reference/keywords/var.md)
- [<span data-ttu-id="acddc-121">C# での LINQ</span><span class="sxs-lookup"><span data-stu-id="acddc-121">LINQ in C#</span></span>](../../linq/index.md)
