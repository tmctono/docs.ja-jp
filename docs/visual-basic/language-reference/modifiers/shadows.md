---
title: Shadows (Visual Basic)
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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351262"
---
# <a name="shadows-visual-basic"></a><span data-ttu-id="6e60d-102">Shadows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6e60d-102">Shadows (Visual Basic)</span></span>

<span data-ttu-id="6e60d-103">宣言されたプログラミング要素が、基底クラスで同じ名前を持つ要素、またはオーバーロードされた要素のセットを直しし、非表示にすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="6e60d-103">Specifies that a declared programming element redeclares and hides an identically named element, or set of overloaded elements, in a base class.</span></span>

## <a name="remarks"></a><span data-ttu-id="6e60d-104">コメント</span><span class="sxs-lookup"><span data-stu-id="6e60d-104">Remarks</span></span>

<span data-ttu-id="6e60d-105">シャドウの主な目的は (*名前で非表示*とも呼ばれます)、クラスメンバーの定義を保持することです。</span><span class="sxs-lookup"><span data-stu-id="6e60d-105">The main purpose of shadowing (which is also known as *hiding by name*) is to preserve the definition of your class members.</span></span> <span data-ttu-id="6e60d-106">基本クラスには、既に定義されているものと同じ名前の要素を作成する変更が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6e60d-106">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="6e60d-107">この場合、`Shadows` 修飾子は、新しい基底クラス要素ではなく、定義したメンバーに解決されるように、クラスを通じて参照を強制します。</span><span class="sxs-lookup"><span data-stu-id="6e60d-107">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>

<span data-ttu-id="6e60d-108">シャドウとオーバーライドは、どちらも継承された要素を再定義しますが、その方法は大きく異なります。</span><span class="sxs-lookup"><span data-stu-id="6e60d-108">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="6e60d-109">詳細については、「[Visual Basic でのシャドウ](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e60d-109">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>

## <a name="rules"></a><span data-ttu-id="6e60d-110">ルール</span><span class="sxs-lookup"><span data-stu-id="6e60d-110">Rules</span></span>

- <span data-ttu-id="6e60d-111">**宣言コンテキスト。**</span><span class="sxs-lookup"><span data-stu-id="6e60d-111">**Declaration Context.**</span></span> <span data-ttu-id="6e60d-112">`Shadows` はクラスレベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6e60d-112">You can use `Shadows` only at class level.</span></span> <span data-ttu-id="6e60d-113">つまり、`Shadows` 要素の宣言コンテキストはクラスである必要があり、ソースファイル、名前空間、インターフェイス、モジュール、構造体、またはプロシージャにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6e60d-113">This means the declaration context for a `Shadows` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

  <span data-ttu-id="6e60d-114">1つの宣言ステートメントでは、シャドウ要素を1つだけ宣言できます。</span><span class="sxs-lookup"><span data-stu-id="6e60d-114">You can declare only one shadowing element in a single declaration statement.</span></span>

- <span data-ttu-id="6e60d-115">**結合された修飾子。**</span><span class="sxs-lookup"><span data-stu-id="6e60d-115">**Combined Modifiers.**</span></span> <span data-ttu-id="6e60d-116">同じ宣言内で `Overloads`、`Overrides`、または `Static` と共に `Shadows` を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="6e60d-116">You cannot specify `Shadows` together with `Overloads`, `Overrides`, or `Static` in the same declaration.</span></span>

- <span data-ttu-id="6e60d-117">**要素の型。**</span><span class="sxs-lookup"><span data-stu-id="6e60d-117">**Element Types.**</span></span> <span data-ttu-id="6e60d-118">宣言された要素は、他の任意の種類の要素でシャドウできます。</span><span class="sxs-lookup"><span data-stu-id="6e60d-118">You can shadow any kind of declared element with any other kind.</span></span> <span data-ttu-id="6e60d-119">別のプロパティまたはプロシージャを使用してプロパティまたはプロシージャをシャドウする場合、パラメーターと戻り値の型は、基底クラスのプロパティまたはプロシージャ内のパラメーターと一致する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6e60d-119">If you shadow a property or procedure with another property or procedure, the parameters and the return type do not have to match those in the base class property or procedure.</span></span>

- <span data-ttu-id="6e60d-120">\*\*アクセス。</span><span class="sxs-lookup"><span data-stu-id="6e60d-120">**Accessing.**</span></span> <span data-ttu-id="6e60d-121">\*\* 基底クラスのシャドウされた要素は、通常、それをシャドウする派生クラス内からは使用できません。</span><span class="sxs-lookup"><span data-stu-id="6e60d-121">The shadowed element in the base class is normally unavailable from within the derived class that shadows it.</span></span> <span data-ttu-id="6e60d-122">ただし、次の考慮事項が適用されます。</span><span class="sxs-lookup"><span data-stu-id="6e60d-122">However, the following considerations apply.</span></span>

  - <span data-ttu-id="6e60d-123">シャドウしている要素が、それを参照するコードからアクセスできない場合は、シャドウされた要素に参照が解決されます。</span><span class="sxs-lookup"><span data-stu-id="6e60d-123">If the shadowing element is not accessible from the code referring to it, the reference is resolved to the shadowed element.</span></span> <span data-ttu-id="6e60d-124">たとえば、`Private` 要素が基本クラス要素をシャドウする場合、`Private` 要素にアクセスするためのアクセス許可を持たないコードは、代わりに基本クラス要素にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="6e60d-124">For example, if a `Private` element shadows a base class element, code that does not have permission to access the `Private` element accesses the base class element instead.</span></span>

  - <span data-ttu-id="6e60d-125">要素をシャドウする場合でも、基底クラスの型で宣言されたオブジェクトを使用して、シャドウされた要素にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6e60d-125">If you shadow an element, you can still access the shadowed element through an object declared with the type of the base class.</span></span> <span data-ttu-id="6e60d-126">また、`MyBase`経由でアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6e60d-126">You can also access it through `MyBase`.</span></span>

<span data-ttu-id="6e60d-127">`Shadows` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="6e60d-127">The `Shadows` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="6e60d-128">Class ステートメント</span><span class="sxs-lookup"><span data-stu-id="6e60d-128">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)

- [<span data-ttu-id="6e60d-129">Const ステートメント</span><span class="sxs-lookup"><span data-stu-id="6e60d-129">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)

- [<span data-ttu-id="6e60d-130">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="6e60d-130">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)

- [<span data-ttu-id="6e60d-131">Delegate ステートメント</span><span class="sxs-lookup"><span data-stu-id="6e60d-131">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)

- [<span data-ttu-id="6e60d-132">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="6e60d-132">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)

- [<span data-ttu-id="6e60d-133">Enum ステートメント</span><span class="sxs-lookup"><span data-stu-id="6e60d-133">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)

- [<span data-ttu-id="6e60d-134">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="6e60d-134">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)

- [<span data-ttu-id="6e60d-135">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="6e60d-135">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- [<span data-ttu-id="6e60d-136">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="6e60d-136">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)

- [<span data-ttu-id="6e60d-137">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="6e60d-137">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- [<span data-ttu-id="6e60d-138">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="6e60d-138">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)

- [<span data-ttu-id="6e60d-139">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="6e60d-139">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="6e60d-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e60d-140">See also</span></span>

- [<span data-ttu-id="6e60d-141">Shared</span><span class="sxs-lookup"><span data-stu-id="6e60d-141">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="6e60d-142">Static</span><span class="sxs-lookup"><span data-stu-id="6e60d-142">Static</span></span>](../../../visual-basic/language-reference/modifiers/static.md)
- [<span data-ttu-id="6e60d-143">Private</span><span class="sxs-lookup"><span data-stu-id="6e60d-143">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="6e60d-144">Me、My、MyBase、および MyClass</span><span class="sxs-lookup"><span data-stu-id="6e60d-144">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="6e60d-145">継承の基本</span><span class="sxs-lookup"><span data-stu-id="6e60d-145">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="6e60d-146">MyBase</span><span class="sxs-lookup"><span data-stu-id="6e60d-146">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="6e60d-147">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="6e60d-147">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="6e60d-148">Overloads</span><span class="sxs-lookup"><span data-stu-id="6e60d-148">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="6e60d-149">Overridable</span><span class="sxs-lookup"><span data-stu-id="6e60d-149">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="6e60d-150">Overrides</span><span class="sxs-lookup"><span data-stu-id="6e60d-150">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="6e60d-151">Visual Basic におけるシャドウ</span><span class="sxs-lookup"><span data-stu-id="6e60d-151">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
