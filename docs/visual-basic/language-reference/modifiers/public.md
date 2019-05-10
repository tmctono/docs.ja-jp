---
title: Public (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Public
helpviewer_keywords:
- Public keyword [Visual Basic]
- Public keyword [Visual Basic], syntax
- Public access modifier
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
ms.openlocfilehash: 0b8c31facc3605ff5a77aecf7b11456b33fbab72
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64647747"
---
# <a name="public-visual-basic"></a><span data-ttu-id="a98ed-102">Public (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a98ed-102">Public (Visual Basic)</span></span>
<span data-ttu-id="a98ed-103">1 つまたは複数の宣言されたプログラミング要素にアクセス制限があるないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="a98ed-103">Specifies that one or more declared programming elements have no access restrictions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a98ed-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="a98ed-104">Remarks</span></span>  
 <span data-ttu-id="a98ed-105">コンポーネントまたはクラス ライブラリなどのコンポーネントのセットを公開している場合に、アセンブリと相互運用するコードでアクセスできるプログラミング要素は、通常します。</span><span class="sxs-lookup"><span data-stu-id="a98ed-105">If you are publishing a component or set of components, such as a class library, you usually want the programming elements to be accessible by any code that interoperates with your assembly.</span></span> <span data-ttu-id="a98ed-106">このような要素に無制限のアクセスを確保する上で宣言できます`Public`します。</span><span class="sxs-lookup"><span data-stu-id="a98ed-106">To confer such unlimited access on an element, you can declare it with `Public`.</span></span>  
  
 <span data-ttu-id="a98ed-107">パブリック アクセスは、アクセスを制限する必要がない、プログラミング要素に通常レベルです。</span><span class="sxs-lookup"><span data-stu-id="a98ed-107">Public access is the normal level for a programming element when you do not need to limit access to it.</span></span> <span data-ttu-id="a98ed-108">要素のアクセス レベルが、インターフェイス、モジュール、クラスまたは構造内で宣言されていることに注意してください。 既定値は`Public`特に宣言しない場合。</span><span class="sxs-lookup"><span data-stu-id="a98ed-108">Note that the access level of an element declared within an interface, module, class, or structure defaults to `Public` if you do not declare it otherwise.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="a98ed-109">ルール</span><span class="sxs-lookup"><span data-stu-id="a98ed-109">Rules</span></span>  
  
- <span data-ttu-id="a98ed-110">**宣言コンテキスト。**</span><span class="sxs-lookup"><span data-stu-id="a98ed-110">**Declaration Context.**</span></span> <span data-ttu-id="a98ed-111">使用することができます`Public`モジュール、インターフェイス、または名前空間レベルでのみです。</span><span class="sxs-lookup"><span data-stu-id="a98ed-111">You can use `Public` only at module, interface, or namespace level.</span></span> <span data-ttu-id="a98ed-112">これは、意味の宣言のコンテキストを`Public`要素は、ソース ファイル、名前空間、インターフェイス、モジュール、クラスまたは構造体にある必要があるあり、プロシージャにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a98ed-112">This means the declaration context for a `Public` element must be a source file, namespace, interface, module, class, or structure, and cannot be a procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="a98ed-113">動作</span><span class="sxs-lookup"><span data-stu-id="a98ed-113">Behavior</span></span>  
  
- <span data-ttu-id="a98ed-114">**アクセス レベルです。**</span><span class="sxs-lookup"><span data-stu-id="a98ed-114">**Access Level.**</span></span> <span data-ttu-id="a98ed-115">モジュール、クラスまたは構造体にアクセスできるすべてのコードがアクセスできるその`Public`要素。</span><span class="sxs-lookup"><span data-stu-id="a98ed-115">All code that can access a module, class, or structure can access its `Public` elements.</span></span>  
  
- <span data-ttu-id="a98ed-116">**既定のアクセス。**</span><span class="sxs-lookup"><span data-stu-id="a98ed-116">**Default Access.**</span></span> <span data-ttu-id="a98ed-117">パブリック アクセスに既定のプロシージャ内のローカル変数は、それらでアクセス修飾子を使用できません。</span><span class="sxs-lookup"><span data-stu-id="a98ed-117">Local variables inside a procedure default to public access, and you cannot use any access modifiers on them.</span></span>  
  
- <span data-ttu-id="a98ed-118">**アクセス修飾子。**</span><span class="sxs-lookup"><span data-stu-id="a98ed-118">**Access Modifiers.**</span></span> <span data-ttu-id="a98ed-119">アクセス レベルを指定するキーワードが呼び出される*アクセス修飾子*します。</span><span class="sxs-lookup"><span data-stu-id="a98ed-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="a98ed-120">アクセス修飾子の比較は、次を参照してください。[アクセス レベルを Visual Basic で](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)します。</span><span class="sxs-lookup"><span data-stu-id="a98ed-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="a98ed-121">`Public` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a98ed-121">The `Public` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="a98ed-122">Class ステートメント</span><span class="sxs-lookup"><span data-stu-id="a98ed-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="a98ed-123">Const ステートメント</span><span class="sxs-lookup"><span data-stu-id="a98ed-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="a98ed-124">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="a98ed-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="a98ed-125">Delegate ステートメント</span><span class="sxs-lookup"><span data-stu-id="a98ed-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="a98ed-126">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="a98ed-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="a98ed-127">Enum ステートメント</span><span class="sxs-lookup"><span data-stu-id="a98ed-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="a98ed-128">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="a98ed-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="a98ed-129">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="a98ed-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="a98ed-130">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="a98ed-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="a98ed-131">Module ステートメント</span><span class="sxs-lookup"><span data-stu-id="a98ed-131">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="a98ed-132">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="a98ed-132">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="a98ed-133">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="a98ed-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="a98ed-134">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="a98ed-134">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="a98ed-135">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="a98ed-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="a98ed-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="a98ed-136">See also</span></span>

- [<span data-ttu-id="a98ed-137">Protected</span><span class="sxs-lookup"><span data-stu-id="a98ed-137">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="a98ed-138">Friend</span><span class="sxs-lookup"><span data-stu-id="a98ed-138">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="a98ed-139">Private</span><span class="sxs-lookup"><span data-stu-id="a98ed-139">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="a98ed-140">Private Protected</span><span class="sxs-lookup"><span data-stu-id="a98ed-140">Private Protected</span></span>](private-protected.md)
- [<span data-ttu-id="a98ed-141">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="a98ed-141">Protected Friend</span></span>](protected-friend.md)
- [<span data-ttu-id="a98ed-142">Visual Basic でのアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="a98ed-142">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="a98ed-143">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="a98ed-143">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="a98ed-144">構造体</span><span class="sxs-lookup"><span data-stu-id="a98ed-144">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="a98ed-145">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="a98ed-145">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
