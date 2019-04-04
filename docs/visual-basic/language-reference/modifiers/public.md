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
ms.openlocfilehash: 0c85564503f3c83e436044cd92ee3014945f1ef3
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818385"
---
# <a name="public-visual-basic"></a><span data-ttu-id="8181a-102">Public (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8181a-102">Public (Visual Basic)</span></span>
<span data-ttu-id="8181a-103">1 つまたは複数の宣言されたプログラミング要素にアクセス制限があるないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="8181a-103">Specifies that one or more declared programming elements have no access restrictions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8181a-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="8181a-104">Remarks</span></span>  
 <span data-ttu-id="8181a-105">コンポーネントまたはクラス ライブラリなどのコンポーネントのセットを公開している場合に、アセンブリと相互運用するコードでアクセスできるプログラミング要素は、通常します。</span><span class="sxs-lookup"><span data-stu-id="8181a-105">If you are publishing a component or set of components, such as a class library, you usually want the programming elements to be accessible by any code that interoperates with your assembly.</span></span> <span data-ttu-id="8181a-106">このような要素に無制限のアクセスを確保する上で宣言できます`Public`します。</span><span class="sxs-lookup"><span data-stu-id="8181a-106">To confer such unlimited access on an element, you can declare it with `Public`.</span></span>  
  
 <span data-ttu-id="8181a-107">パブリック アクセスは、アクセスを制限する必要がない、プログラミング要素に通常レベルです。</span><span class="sxs-lookup"><span data-stu-id="8181a-107">Public access is the normal level for a programming element when you do not need to limit access to it.</span></span> <span data-ttu-id="8181a-108">要素のアクセス レベルが、インターフェイス、モジュール、クラスまたは構造内で宣言されていることに注意してください。 既定値は`Public`特に宣言しない場合。</span><span class="sxs-lookup"><span data-stu-id="8181a-108">Note that the access level of an element declared within an interface, module, class, or structure defaults to `Public` if you do not declare it otherwise.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="8181a-109">ルール</span><span class="sxs-lookup"><span data-stu-id="8181a-109">Rules</span></span>  
  
-   <span data-ttu-id="8181a-110">**宣言コンテキスト。**</span><span class="sxs-lookup"><span data-stu-id="8181a-110">**Declaration Context.**</span></span> <span data-ttu-id="8181a-111">使用することができます`Public`モジュール、インターフェイス、または名前空間レベルでのみです。</span><span class="sxs-lookup"><span data-stu-id="8181a-111">You can use `Public` only at module, interface, or namespace level.</span></span> <span data-ttu-id="8181a-112">これは、意味の宣言のコンテキストを`Public`要素は、ソース ファイル、名前空間、インターフェイス、モジュール、クラスまたは構造体にある必要があるあり、プロシージャにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8181a-112">This means the declaration context for a `Public` element must be a source file, namespace, interface, module, class, or structure, and cannot be a procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="8181a-113">動作</span><span class="sxs-lookup"><span data-stu-id="8181a-113">Behavior</span></span>  
  
-   <span data-ttu-id="8181a-114">**アクセス レベルです。**</span><span class="sxs-lookup"><span data-stu-id="8181a-114">**Access Level.**</span></span> <span data-ttu-id="8181a-115">モジュール、クラスまたは構造体にアクセスできるすべてのコードがアクセスできるその`Public`要素。</span><span class="sxs-lookup"><span data-stu-id="8181a-115">All code that can access a module, class, or structure can access its `Public` elements.</span></span>  
  
-   <span data-ttu-id="8181a-116">**既定のアクセス。**</span><span class="sxs-lookup"><span data-stu-id="8181a-116">**Default Access.**</span></span> <span data-ttu-id="8181a-117">パブリック アクセスに既定のプロシージャ内のローカル変数は、それらでアクセス修飾子を使用できません。</span><span class="sxs-lookup"><span data-stu-id="8181a-117">Local variables inside a procedure default to public access, and you cannot use any access modifiers on them.</span></span>  
  
-   <span data-ttu-id="8181a-118">**アクセス修飾子。**</span><span class="sxs-lookup"><span data-stu-id="8181a-118">**Access Modifiers.**</span></span> <span data-ttu-id="8181a-119">アクセス レベルを指定するキーワードが呼び出される*アクセス修飾子*します。</span><span class="sxs-lookup"><span data-stu-id="8181a-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="8181a-120">アクセス修飾子の比較は、[アクセス レベルを Visual Basic で](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8181a-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="8181a-121">`Public` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="8181a-121">The `Public` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="8181a-122">Class ステートメント</span><span class="sxs-lookup"><span data-stu-id="8181a-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="8181a-123">Const ステートメント</span><span class="sxs-lookup"><span data-stu-id="8181a-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="8181a-124">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="8181a-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="8181a-125">Delegate ステートメント</span><span class="sxs-lookup"><span data-stu-id="8181a-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="8181a-126">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="8181a-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="8181a-127">Enum ステートメント</span><span class="sxs-lookup"><span data-stu-id="8181a-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="8181a-128">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="8181a-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="8181a-129">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="8181a-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="8181a-130">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="8181a-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="8181a-131">Module ステートメント</span><span class="sxs-lookup"><span data-stu-id="8181a-131">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="8181a-132">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="8181a-132">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="8181a-133">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="8181a-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="8181a-134">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="8181a-134">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="8181a-135">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="8181a-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="8181a-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="8181a-136">See also</span></span>

- [<span data-ttu-id="8181a-137">Protected</span><span class="sxs-lookup"><span data-stu-id="8181a-137">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="8181a-138">Friend</span><span class="sxs-lookup"><span data-stu-id="8181a-138">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="8181a-139">Private</span><span class="sxs-lookup"><span data-stu-id="8181a-139">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="8181a-140">Private Protected</span><span class="sxs-lookup"><span data-stu-id="8181a-140">Private Protected</span></span>](private-protected.md)
- [<span data-ttu-id="8181a-141">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="8181a-141">Protected Friend</span></span>](protected-friend.md)
- [<span data-ttu-id="8181a-142">Visual Basic でのアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="8181a-142">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="8181a-143">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="8181a-143">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="8181a-144">構造体</span><span class="sxs-lookup"><span data-stu-id="8181a-144">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="8181a-145">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="8181a-145">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
