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
ms.openlocfilehash: c314db90a1a0f89613e20897387bdec8ec534837
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778730"
---
# <a name="shadows-visual-basic"></a><span data-ttu-id="67c48-102">Shadows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67c48-102">Shadows (Visual Basic)</span></span>
<span data-ttu-id="67c48-103">宣言されたプログラミング要素を宣言し、同じ名前を持つ要素、または基底クラスのオーバー ロードされた要素のセットを非表示にすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="67c48-103">Specifies that a declared programming element redeclares and hides an identically named element, or set of overloaded elements, in a base class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67c48-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="67c48-104">Remarks</span></span>  
 <span data-ttu-id="67c48-105">シャドウの主な目的は、(あるとも呼ばれます*名前による隠ぺい*)、クラスのメンバーの定義を維持しています。</span><span class="sxs-lookup"><span data-stu-id="67c48-105">The main purpose of shadowing (which is also known as *hiding by name*) is to preserve the definition of your class members.</span></span> <span data-ttu-id="67c48-106">基底クラスには、既に定義されている 1 つとして同じ名前の要素を作成する変更を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="67c48-106">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="67c48-107">このような場合、`Shadows`するメンバーに解決するのには、クラスを通じて参照修飾子強制的に基本クラスの新しい要素の代わりに定義されました。</span><span class="sxs-lookup"><span data-stu-id="67c48-107">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>  
  
 <span data-ttu-id="67c48-108">シャドウとオーバーライドは、どちらも継承された要素を再定義しますが、その方法は大きく異なります。</span><span class="sxs-lookup"><span data-stu-id="67c48-108">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="67c48-109">詳細については、次を参照してください。 [Visual Basic におけるシャドウ](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)します。</span><span class="sxs-lookup"><span data-stu-id="67c48-109">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="67c48-110">ルール</span><span class="sxs-lookup"><span data-stu-id="67c48-110">Rules</span></span>  
  
- <span data-ttu-id="67c48-111">**宣言コンテキスト。**</span><span class="sxs-lookup"><span data-stu-id="67c48-111">**Declaration Context.**</span></span> <span data-ttu-id="67c48-112">使用することができます`Shadows`クラス レベルでのみです。</span><span class="sxs-lookup"><span data-stu-id="67c48-112">You can use `Shadows` only at class level.</span></span> <span data-ttu-id="67c48-113">これは、意味の宣言のコンテキストを`Shadows`要素は、クラスでなければなりませんし、ソース ファイル、名前空間、インターフェイス、モジュール、構造体、またはプロシージャにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="67c48-113">This means the declaration context for a `Shadows` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>  
  
     <span data-ttu-id="67c48-114">1 つの宣言ステートメントで 1 つだけのシャドウ要素を宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="67c48-114">You can declare only one shadowing element in a single declaration statement.</span></span>  
  
- <span data-ttu-id="67c48-115">**結合された修飾子。**</span><span class="sxs-lookup"><span data-stu-id="67c48-115">**Combined Modifiers.**</span></span> <span data-ttu-id="67c48-116">指定することはできません`Shadows`と共に`Overloads`、 `Overrides`、または`Static`同じ宣言内。</span><span class="sxs-lookup"><span data-stu-id="67c48-116">You cannot specify `Shadows` together with `Overloads`, `Overrides`, or `Static` in the same declaration.</span></span>  
  
- <span data-ttu-id="67c48-117">**要素の型。**</span><span class="sxs-lookup"><span data-stu-id="67c48-117">**Element Types.**</span></span> <span data-ttu-id="67c48-118">宣言された要素は、他の任意の種類の要素でシャドウできます。</span><span class="sxs-lookup"><span data-stu-id="67c48-118">You can shadow any kind of declared element with any other kind.</span></span> <span data-ttu-id="67c48-119">プロパティまたはプロシージャを別のプロパティまたはプロシージャをシャドウする場合、パラメーターと戻り値の型は基底クラスのプロパティまたはプロシージャの一致する必要ありません。</span><span class="sxs-lookup"><span data-stu-id="67c48-119">If you shadow a property or procedure with another property or procedure, the parameters and the return type do not have to match those in the base class property or procedure.</span></span>  
  
- <span data-ttu-id="67c48-120">**アクセスします。**</span><span class="sxs-lookup"><span data-stu-id="67c48-120">**Accessing.**</span></span> <span data-ttu-id="67c48-121">基本クラスのシャドウされた要素は、それをシャドウする派生クラス内で通常利用ではありません。</span><span class="sxs-lookup"><span data-stu-id="67c48-121">The shadowed element in the base class is normally unavailable from within the derived class that shadows it.</span></span> <span data-ttu-id="67c48-122">ただし、次の考慮事項が適用されます。</span><span class="sxs-lookup"><span data-stu-id="67c48-122">However, the following considerations apply.</span></span>  
  
    - <span data-ttu-id="67c48-123">シャドウする要素が参照するコードからアクセスできない場合は、シャドウされた要素への参照が解決されます。</span><span class="sxs-lookup"><span data-stu-id="67c48-123">If the shadowing element is not accessible from the code referring to it, the reference is resolved to the shadowed element.</span></span> <span data-ttu-id="67c48-124">たとえば場合、`Private`要素をシャドウする基本クラスの要素では、コードへのアクセス許可がない、`Private`要素が代わりに基本クラスの要素にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="67c48-124">For example, if a `Private` element shadows a base class element, code that does not have permission to access the `Private` element accesses the base class element instead.</span></span>  
  
    - <span data-ttu-id="67c48-125">要素をシャドウする場合は、基底クラスの型で宣言されたオブジェクトを介してシャドウされた要素を引き続きアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="67c48-125">If you shadow an element, you can still access the shadowed element through an object declared with the type of the base class.</span></span> <span data-ttu-id="67c48-126">を通じてアクセスすることも`MyBase`します。</span><span class="sxs-lookup"><span data-stu-id="67c48-126">You can also access it through `MyBase`.</span></span>  
  
 <span data-ttu-id="67c48-127">`Shadows` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="67c48-127">The `Shadows` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="67c48-128">Class ステートメント</span><span class="sxs-lookup"><span data-stu-id="67c48-128">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="67c48-129">Const ステートメント</span><span class="sxs-lookup"><span data-stu-id="67c48-129">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="67c48-130">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="67c48-130">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="67c48-131">Delegate ステートメント</span><span class="sxs-lookup"><span data-stu-id="67c48-131">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="67c48-132">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="67c48-132">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="67c48-133">Enum ステートメント</span><span class="sxs-lookup"><span data-stu-id="67c48-133">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="67c48-134">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="67c48-134">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="67c48-135">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="67c48-135">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="67c48-136">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="67c48-136">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="67c48-137">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="67c48-137">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="67c48-138">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="67c48-138">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="67c48-139">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="67c48-139">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="67c48-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="67c48-140">See also</span></span>

- [<span data-ttu-id="67c48-141">Shared</span><span class="sxs-lookup"><span data-stu-id="67c48-141">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="67c48-142">Static</span><span class="sxs-lookup"><span data-stu-id="67c48-142">Static</span></span>](../../../visual-basic/language-reference/modifiers/static.md)
- [<span data-ttu-id="67c48-143">Private</span><span class="sxs-lookup"><span data-stu-id="67c48-143">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="67c48-144">Me、My、MyBase、および MyClass</span><span class="sxs-lookup"><span data-stu-id="67c48-144">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="67c48-145">継承の基本</span><span class="sxs-lookup"><span data-stu-id="67c48-145">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="67c48-146">MustOverride</span><span class="sxs-lookup"><span data-stu-id="67c48-146">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="67c48-147">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="67c48-147">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="67c48-148">Overloads</span><span class="sxs-lookup"><span data-stu-id="67c48-148">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="67c48-149">Overridable</span><span class="sxs-lookup"><span data-stu-id="67c48-149">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="67c48-150">Overrides</span><span class="sxs-lookup"><span data-stu-id="67c48-150">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="67c48-151">Visual Basic におけるシャドウ</span><span class="sxs-lookup"><span data-stu-id="67c48-151">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
