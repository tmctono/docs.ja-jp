---
title: オーバーライド
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
ms.openlocfilehash: 04f1cb27d6a8366c2dd13f8fdc1d975d382f1cfd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351383"
---
# <a name="overrides-visual-basic"></a><span data-ttu-id="82e61-102">Overrides (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="82e61-102">Overrides (Visual Basic)</span></span>

<span data-ttu-id="82e61-103">プロパティまたはプロシージャが基本クラスから継承された同じ名前のプロパティまたはプロシージャをオーバーライドすることを示します。</span><span class="sxs-lookup"><span data-stu-id="82e61-103">Specifies that a property or procedure overrides an identically named property or procedure inherited from a base class.</span></span>

## <a name="rules"></a><span data-ttu-id="82e61-104">ルール</span><span class="sxs-lookup"><span data-stu-id="82e61-104">Rules</span></span>

- <span data-ttu-id="82e61-105">**宣言コンテキスト。**</span><span class="sxs-lookup"><span data-stu-id="82e61-105">**Declaration Context.**</span></span> <span data-ttu-id="82e61-106">`Overrides` は、プロパティまたはプロシージャの宣言ステートメントでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="82e61-106">You can use `Overrides` only in a property or procedure declaration statement.</span></span>

- <span data-ttu-id="82e61-107">**結合された修飾子。**</span><span class="sxs-lookup"><span data-stu-id="82e61-107">**Combined Modifiers.**</span></span> <span data-ttu-id="82e61-108">同じ宣言内で `Shadows` または `Shared` と共に `Overrides` を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="82e61-108">You cannot specify `Overrides` together with `Shadows` or `Shared` in the same declaration.</span></span> <span data-ttu-id="82e61-109">オーバーライドする要素は暗黙的にオーバーライド可能であるため、`Overridable` と `Overrides` を結合することはできません。</span><span class="sxs-lookup"><span data-stu-id="82e61-109">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>

- <span data-ttu-id="82e61-110">**一致する署名。**</span><span class="sxs-lookup"><span data-stu-id="82e61-110">**Matching Signatures.**</span></span> <span data-ttu-id="82e61-111">この宣言のシグネチャは、オーバーライドするプロパティまたはプロシージャの*シグネチャ*と完全に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82e61-111">The signature of this declaration must exactly match the *signature* of the property or procedure that it overrides.</span></span> <span data-ttu-id="82e61-112">つまり、パラメーター リストには、同じ数のパラメーターを、同じ順序、同じデータ型で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82e61-112">This means the parameter lists must have the same number of parameters, in the same order, with the same data types.</span></span>

  <span data-ttu-id="82e61-113">オーバーライドする宣言は、シグネチャに加え、次の点でも完全に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="82e61-113">In addition to the signature, the overriding declaration must also exactly match the following:</span></span>

  - <span data-ttu-id="82e61-114">アクセス レベル</span><span class="sxs-lookup"><span data-stu-id="82e61-114">The access level</span></span>

  - <span data-ttu-id="82e61-115">戻り値の型 (戻り値がある場合)</span><span class="sxs-lookup"><span data-stu-id="82e61-115">The return type, if any</span></span>

- <span data-ttu-id="82e61-116">**汎用署名。**</span><span class="sxs-lookup"><span data-stu-id="82e61-116">**Generic Signatures.**</span></span> <span data-ttu-id="82e61-117">ジェネリック プロシージャでは、シグネチャに型パラメーターの数が含まれます。</span><span class="sxs-lookup"><span data-stu-id="82e61-117">For a generic procedure, the signature includes the number of type parameters.</span></span> <span data-ttu-id="82e61-118">したがって、オーバーライドする宣言は、その点でも基底クラスのバージョンに一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="82e61-118">Therefore, the overriding declaration must match the base class version in that respect as well.</span></span>

- <span data-ttu-id="82e61-119">**追加の一致。**</span><span class="sxs-lookup"><span data-stu-id="82e61-119">**Additional Matching.**</span></span> <span data-ttu-id="82e61-120">この宣言は、基底クラスのバージョンのシグネチャに一致していることに加え、次の点でも基底クラスと一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="82e61-120">In addition to matching the signature of the base class version, this declaration must also match it in the following respects:</span></span>

  - <span data-ttu-id="82e61-121">アクセスレベル修飾子 ( [Public](../../../visual-basic/language-reference/modifiers/public.md)など)</span><span class="sxs-lookup"><span data-stu-id="82e61-121">Access-level modifier (such as [Public](../../../visual-basic/language-reference/modifiers/public.md))</span></span>

  - <span data-ttu-id="82e61-122">各パラメーターのメカニズムを渡す ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md)または[ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span><span class="sxs-lookup"><span data-stu-id="82e61-122">Passing mechanism of each parameter ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span></span>

  - <span data-ttu-id="82e61-123">ジェネリック プロシージャの型パラメーターごとの制約リスト</span><span class="sxs-lookup"><span data-stu-id="82e61-123">Constraint lists on each type parameter of a generic procedure</span></span>

- <span data-ttu-id="82e61-124">**シャドウとオーバーライド。**</span><span class="sxs-lookup"><span data-stu-id="82e61-124">**Shadowing and Overriding.**</span></span> <span data-ttu-id="82e61-125">シャドウとオーバーライドは、どちらも継承された要素を再定義しますが、その方法は大きく異なります。</span><span class="sxs-lookup"><span data-stu-id="82e61-125">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="82e61-126">詳細については、「 [Visual Basic でのシャドウ](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82e61-126">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>

<span data-ttu-id="82e61-127">`Overrides` を使用する場合は、ライブラリ API と C# が連携しやすくなるように、コンパイラが暗黙的に `Overloads` を追加します。</span><span class="sxs-lookup"><span data-stu-id="82e61-127">If you use `Overrides`, the compiler implicitly adds `Overloads` so that your library APIs work with C# more easily.</span></span>

<span data-ttu-id="82e61-128">`Overrides` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="82e61-128">The `Overrides` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="82e61-129">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="82e61-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- [<span data-ttu-id="82e61-130">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="82e61-130">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- [<span data-ttu-id="82e61-131">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="82e61-131">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="82e61-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="82e61-132">See also</span></span>

- [<span data-ttu-id="82e61-133">MyBase</span><span class="sxs-lookup"><span data-stu-id="82e61-133">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="82e61-134">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="82e61-134">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="82e61-135">Overridable</span><span class="sxs-lookup"><span data-stu-id="82e61-135">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="82e61-136">キーワード</span><span class="sxs-lookup"><span data-stu-id="82e61-136">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="82e61-137">Visual Basic でのシャドウ処理</span><span class="sxs-lookup"><span data-stu-id="82e61-137">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="82e61-138">Visual Basic におけるジェネリック型</span><span class="sxs-lookup"><span data-stu-id="82e61-138">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="82e61-139">型リスト</span><span class="sxs-lookup"><span data-stu-id="82e61-139">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
