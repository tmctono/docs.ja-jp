---
title: Overrides
ms.date: 07/20/2015
f1_keywords:
- Overrides
- vb.Overrides
helpviewer_keywords:
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- Overrides keyword [Visual Basic]
- overriding, Overrides keyword
- properties [Visual Basic], overriding
ms.assetid: 9f5e6144-ce10-465e-842b-1a8f8760af90
ms.openlocfilehash: 657f838b2959a5b6a7cef5ff18295a4ada709e9a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392029"
---
# <a name="overrides-visual-basic"></a><span data-ttu-id="0d88a-102">Overrides (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0d88a-102">Overrides (Visual Basic)</span></span>

<span data-ttu-id="0d88a-103">プロパティまたはプロシージャが基本クラスから継承された同じ名前のプロパティまたはプロシージャをオーバーライドすることを示します。</span><span class="sxs-lookup"><span data-stu-id="0d88a-103">Specifies that a property or procedure overrides an identically named property or procedure inherited from a base class.</span></span>

## <a name="rules"></a><span data-ttu-id="0d88a-104">ルール</span><span class="sxs-lookup"><span data-stu-id="0d88a-104">Rules</span></span>

- <span data-ttu-id="0d88a-105">**宣言コンテキスト。**</span><span class="sxs-lookup"><span data-stu-id="0d88a-105">**Declaration Context.**</span></span> <span data-ttu-id="0d88a-106">`Overrides` は、プロパティまたはプロシージャの宣言ステートメントでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="0d88a-106">You can use `Overrides` only in a property or procedure declaration statement.</span></span>

- <span data-ttu-id="0d88a-107">**結合された修飾子。**</span><span class="sxs-lookup"><span data-stu-id="0d88a-107">**Combined Modifiers.**</span></span> <span data-ttu-id="0d88a-108">同じ宣言内で `Overrides` を `Shadows` または `Shared` と共に指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="0d88a-108">You cannot specify `Overrides` together with `Shadows` or `Shared` in the same declaration.</span></span> <span data-ttu-id="0d88a-109">オーバーライドする要素は暗黙的にオーバーライド可能であるため、`Overridable` と `Overrides` を結合することはできません。</span><span class="sxs-lookup"><span data-stu-id="0d88a-109">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>

- <span data-ttu-id="0d88a-110">**シグネチャの一致。**</span><span class="sxs-lookup"><span data-stu-id="0d88a-110">**Matching Signatures.**</span></span> <span data-ttu-id="0d88a-111">この宣言のシグネチャは、オーバーライドされるプロパティまたはプロシージャの*シグネチャ*と完全に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d88a-111">The signature of this declaration must exactly match the *signature* of the property or procedure that it overrides.</span></span> <span data-ttu-id="0d88a-112">つまり、パラメーター リストには、同じ数のパラメーターを、同じ順序、同じデータ型で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d88a-112">This means the parameter lists must have the same number of parameters, in the same order, with the same data types.</span></span>

  <span data-ttu-id="0d88a-113">オーバーライドする宣言は、シグネチャに加え、次の点でも完全に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d88a-113">In addition to the signature, the overriding declaration must also exactly match the following:</span></span>

  - <span data-ttu-id="0d88a-114">アクセス レベル</span><span class="sxs-lookup"><span data-stu-id="0d88a-114">The access level</span></span>

  - <span data-ttu-id="0d88a-115">戻り値の型 (戻り値がある場合)</span><span class="sxs-lookup"><span data-stu-id="0d88a-115">The return type, if any</span></span>

- <span data-ttu-id="0d88a-116">**ジェネリック シグネチャ。**</span><span class="sxs-lookup"><span data-stu-id="0d88a-116">**Generic Signatures.**</span></span> <span data-ttu-id="0d88a-117">ジェネリック プロシージャでは、シグネチャに型パラメーターの数が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0d88a-117">For a generic procedure, the signature includes the number of type parameters.</span></span> <span data-ttu-id="0d88a-118">したがって、オーバーライドする宣言は、その点でも基底クラスのバージョンに一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d88a-118">Therefore, the overriding declaration must match the base class version in that respect as well.</span></span>

- <span data-ttu-id="0d88a-119">**その他の一致。**</span><span class="sxs-lookup"><span data-stu-id="0d88a-119">**Additional Matching.**</span></span> <span data-ttu-id="0d88a-120">この宣言は、基底クラスのバージョンのシグネチャに一致していることに加え、次の点でも基底クラスと一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d88a-120">In addition to matching the signature of the base class version, this declaration must also match it in the following respects:</span></span>

  - <span data-ttu-id="0d88a-121">アクセス レベル修飾子 ([Public](public.md) など)</span><span class="sxs-lookup"><span data-stu-id="0d88a-121">Access-level modifier (such as [Public](public.md))</span></span>

  - <span data-ttu-id="0d88a-122">各パラメーターの引き渡し方法 ([ByVal](byval.md) または [ByRef](byref.md))</span><span class="sxs-lookup"><span data-stu-id="0d88a-122">Passing mechanism of each parameter ([ByVal](byval.md) or [ByRef](byref.md))</span></span>

  - <span data-ttu-id="0d88a-123">ジェネリック プロシージャの型パラメーターごとの制約リスト</span><span class="sxs-lookup"><span data-stu-id="0d88a-123">Constraint lists on each type parameter of a generic procedure</span></span>

- <span data-ttu-id="0d88a-124">**シャドウとオーバーライド。**</span><span class="sxs-lookup"><span data-stu-id="0d88a-124">**Shadowing and Overriding.**</span></span> <span data-ttu-id="0d88a-125">シャドウとオーバーライドは、どちらも継承された要素を再定義しますが、その方法は大きく異なります。</span><span class="sxs-lookup"><span data-stu-id="0d88a-125">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="0d88a-126">詳細については、「[Visual Basic におけるシャドウ](../../programming-guide/language-features/declared-elements/shadowing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d88a-126">For more information, see [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span></span>

<span data-ttu-id="0d88a-127">`Overrides` を使用する場合は、ライブラリ API と C# が連携しやすくなるように、コンパイラが暗黙的に `Overloads` を追加します。</span><span class="sxs-lookup"><span data-stu-id="0d88a-127">If you use `Overrides`, the compiler implicitly adds `Overloads` so that your library APIs work with C# more easily.</span></span>

<span data-ttu-id="0d88a-128">`Overrides` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="0d88a-128">The `Overrides` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="0d88a-129">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="0d88a-129">Function Statement</span></span>](../statements/function-statement.md)

- [<span data-ttu-id="0d88a-130">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="0d88a-130">Property Statement</span></span>](../statements/property-statement.md)

- [<span data-ttu-id="0d88a-131">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="0d88a-131">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="0d88a-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d88a-132">See also</span></span>

- [<span data-ttu-id="0d88a-133">MustOverride</span><span class="sxs-lookup"><span data-stu-id="0d88a-133">MustOverride</span></span>](mustoverride.md)
- [<span data-ttu-id="0d88a-134">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="0d88a-134">NotOverridable</span></span>](notoverridable.md)
- [<span data-ttu-id="0d88a-135">Overridable</span><span class="sxs-lookup"><span data-stu-id="0d88a-135">Overridable</span></span>](overridable.md)
- [<span data-ttu-id="0d88a-136">キーワード</span><span class="sxs-lookup"><span data-stu-id="0d88a-136">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="0d88a-137">Visual Basic におけるシャドウ</span><span class="sxs-lookup"><span data-stu-id="0d88a-137">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="0d88a-138">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0d88a-138">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="0d88a-139">型リスト</span><span class="sxs-lookup"><span data-stu-id="0d88a-139">Type List</span></span>](../statements/type-list.md)
