---
title: Overloads
ms.date: 07/20/2015
f1_keywords:
- vb.Shadows
- shadows
helpviewer_keywords:
- shadowing
- duplicate names [Visual Basic]
- scope [Visual Basic], shadowing
- Shadows keyword [Visual Basic]
- names [Visual Basic], shadowing
ms.assetid: 6bf687cd-0544-4797-b51b-911125ec57c6
ms.openlocfilehash: e9a423fa69ad1dcd8c1d4a5b7085e5b5da548f93
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351262"
---
# <a name="shadows-visual-basic"></a><span data-ttu-id="11768-102">Shadows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="11768-102">Shadows (Visual Basic)</span></span>

<span data-ttu-id="11768-103">宣言されたプログラミング要素が、基底クラスにある、同じ名前を持つ要素、またはオーバーロードされる要素のセットを宣言し直して非表示にすることを示します。</span><span class="sxs-lookup"><span data-stu-id="11768-103">Specifies that a declared programming element redeclares and hides an identically named element, or set of overloaded elements, in a base class.</span></span>

## <a name="remarks"></a><span data-ttu-id="11768-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="11768-104">Remarks</span></span>

<span data-ttu-id="11768-105">シャドウ (*名前による非表示*とも呼ばれます) の主な目的は、クラス メンバーの定義を保持することです。</span><span class="sxs-lookup"><span data-stu-id="11768-105">The main purpose of shadowing (which is also known as *hiding by name*) is to preserve the definition of your class members.</span></span> <span data-ttu-id="11768-106">基底クラスには、既に定義されているものと同じ名前の要素を作成する変更が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="11768-106">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="11768-107">この場合、`Shadows` 修飾子は、クラスによる参照が、新しい基底クラス要素ではなく定義したメンバーに強制的に解決されるようにします。</span><span class="sxs-lookup"><span data-stu-id="11768-107">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>

<span data-ttu-id="11768-108">シャドウとオーバーライドは、どちらも継承された要素を再定義しますが、その方法は大きく異なります。</span><span class="sxs-lookup"><span data-stu-id="11768-108">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="11768-109">詳細については、「[Visual Basic におけるシャドウ](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11768-109">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>

## <a name="rules"></a><span data-ttu-id="11768-110">ルール</span><span class="sxs-lookup"><span data-stu-id="11768-110">Rules</span></span>

- <span data-ttu-id="11768-111">**宣言コンテキスト。**</span><span class="sxs-lookup"><span data-stu-id="11768-111">**Declaration Context.**</span></span> <span data-ttu-id="11768-112">`Shadows` は、クラス レベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="11768-112">You can use `Shadows` only at class level.</span></span> <span data-ttu-id="11768-113">つまり、`Shadows` 要素の宣言コンテキストはクラスにする必要があり、ソース ファイル、名前空間、インターフェイス、モジュール、構造体、またはプロシージャにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="11768-113">This means the declaration context for a `Shadows` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

  <span data-ttu-id="11768-114">1 つの宣言ステートメントでは、シャドウ要素を 1 つだけ宣言できます。</span><span class="sxs-lookup"><span data-stu-id="11768-114">You can declare only one shadowing element in a single declaration statement.</span></span>

- <span data-ttu-id="11768-115">**結合された修飾子。**</span><span class="sxs-lookup"><span data-stu-id="11768-115">**Combined Modifiers.**</span></span> <span data-ttu-id="11768-116">同じ宣言内で `Shadows` を `Overloads`、`Overrides`、または `Static` と共に指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="11768-116">You cannot specify `Shadows` together with `Overloads`, `Overrides`, or `Static` in the same declaration.</span></span>

- <span data-ttu-id="11768-117">**要素型。**</span><span class="sxs-lookup"><span data-stu-id="11768-117">**Element Types.**</span></span> <span data-ttu-id="11768-118">宣言された要素は、他の任意の種類の要素でシャドウできます。</span><span class="sxs-lookup"><span data-stu-id="11768-118">You can shadow any kind of declared element with any other kind.</span></span> <span data-ttu-id="11768-119">別のプロパティまたはプロシージャを使用してプロパティまたはプロシージャをシャドウする場合、パラメーターと戻り値の型が基底クラスのプロパティまたはプロシージャ内のパラメーターと一致する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="11768-119">If you shadow a property or procedure with another property or procedure, the parameters and the return type do not have to match those in the base class property or procedure.</span></span>

- <span data-ttu-id="11768-120">**アクセス。**</span><span class="sxs-lookup"><span data-stu-id="11768-120">**Accessing.**</span></span> <span data-ttu-id="11768-121">基底クラス内のシャドウされた要素は、通常、それをシャドウする派生クラス内からは使用できません。</span><span class="sxs-lookup"><span data-stu-id="11768-121">The shadowed element in the base class is normally unavailable from within the derived class that shadows it.</span></span> <span data-ttu-id="11768-122">ただし、次の考慮事項が適用されます。</span><span class="sxs-lookup"><span data-stu-id="11768-122">However, the following considerations apply.</span></span>

  - <span data-ttu-id="11768-123">シャドウ要素が、それを参照するコードからアクセスできない場合、参照はシャドウされた要素に解決されます。</span><span class="sxs-lookup"><span data-stu-id="11768-123">If the shadowing element is not accessible from the code referring to it, the reference is resolved to the shadowed element.</span></span> <span data-ttu-id="11768-124">たとえば、`Private` 要素が基底クラスの要素をシャドウすると、`Private` 要素へのアクセス許可を持たないコードが、代わりに基底クラスの要素にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="11768-124">For example, if a `Private` element shadows a base class element, code that does not have permission to access the `Private` element accesses the base class element instead.</span></span>

  - <span data-ttu-id="11768-125">要素をシャドウする場合でも、基底クラスの型で宣言されたオブジェクトを使用して、シャドウされた要素にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="11768-125">If you shadow an element, you can still access the shadowed element through an object declared with the type of the base class.</span></span> <span data-ttu-id="11768-126">また、`MyBase` を使用してアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="11768-126">You can also access it through `MyBase`.</span></span>

<span data-ttu-id="11768-127">`Shadows` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="11768-127">The `Shadows` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="11768-128">Class ステートメント</span><span class="sxs-lookup"><span data-stu-id="11768-128">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)

- [<span data-ttu-id="11768-129">Const ステートメント</span><span class="sxs-lookup"><span data-stu-id="11768-129">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)

- [<span data-ttu-id="11768-130">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="11768-130">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)

- [<span data-ttu-id="11768-131">Delegate ステートメント</span><span class="sxs-lookup"><span data-stu-id="11768-131">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)

- [<span data-ttu-id="11768-132">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="11768-132">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)

- [<span data-ttu-id="11768-133">Enum ステートメント</span><span class="sxs-lookup"><span data-stu-id="11768-133">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)

- [<span data-ttu-id="11768-134">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="11768-134">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)

- [<span data-ttu-id="11768-135">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="11768-135">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- [<span data-ttu-id="11768-136">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="11768-136">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)

- [<span data-ttu-id="11768-137">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="11768-137">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- [<span data-ttu-id="11768-138">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="11768-138">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)

- [<span data-ttu-id="11768-139">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="11768-139">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="11768-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="11768-140">See also</span></span>

- [<span data-ttu-id="11768-141">Shared</span><span class="sxs-lookup"><span data-stu-id="11768-141">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="11768-142">Static</span><span class="sxs-lookup"><span data-stu-id="11768-142">Static</span></span>](../../../visual-basic/language-reference/modifiers/static.md)
- [<span data-ttu-id="11768-143">Private</span><span class="sxs-lookup"><span data-stu-id="11768-143">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="11768-144">Me、My、MyBase、および MyClass</span><span class="sxs-lookup"><span data-stu-id="11768-144">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="11768-145">継承の基本</span><span class="sxs-lookup"><span data-stu-id="11768-145">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="11768-146">MustOverride</span><span class="sxs-lookup"><span data-stu-id="11768-146">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="11768-147">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="11768-147">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="11768-148">Overloads</span><span class="sxs-lookup"><span data-stu-id="11768-148">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="11768-149">Overridable</span><span class="sxs-lookup"><span data-stu-id="11768-149">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="11768-150">Overrides</span><span class="sxs-lookup"><span data-stu-id="11768-150">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="11768-151">Visual Basic におけるシャドウ</span><span class="sxs-lookup"><span data-stu-id="11768-151">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
