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
ms.openlocfilehash: 35bf1a65e0b8f24a1263adc480719c69b95dff9b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351294"
---
# <a name="public-visual-basic"></a><span data-ttu-id="41ba7-102">Public (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="41ba7-102">Public (Visual Basic)</span></span>
<span data-ttu-id="41ba7-103">1つ以上の宣言されたプログラミング要素にアクセス制限がないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="41ba7-103">Specifies that one or more declared programming elements have no access restrictions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41ba7-104">コメント</span><span class="sxs-lookup"><span data-stu-id="41ba7-104">Remarks</span></span>  
 <span data-ttu-id="41ba7-105">クラスライブラリなど、コンポーネントまたはコンポーネントのセットを発行する場合は、通常、アセンブリと相互運用できるコードでプログラミング要素にアクセスできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="41ba7-105">If you are publishing a component or set of components, such as a class library, you usually want the programming elements to be accessible by any code that interoperates with your assembly.</span></span> <span data-ttu-id="41ba7-106">要素に対して無制限のアクセス権を付与するには、`Public`で宣言します。</span><span class="sxs-lookup"><span data-stu-id="41ba7-106">To confer such unlimited access on an element, you can declare it with `Public`.</span></span>  
  
 <span data-ttu-id="41ba7-107">パブリックアクセスは、プログラミング要素へのアクセスを制限する必要がない場合の通常のレベルです。</span><span class="sxs-lookup"><span data-stu-id="41ba7-107">Public access is the normal level for a programming element when you do not need to limit access to it.</span></span> <span data-ttu-id="41ba7-108">インターフェイス、モジュール、クラス、または構造体で宣言されている要素のアクセスレベルは、既定では、宣言しない場合は `Public` になることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="41ba7-108">Note that the access level of an element declared within an interface, module, class, or structure defaults to `Public` if you do not declare it otherwise.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="41ba7-109">ルール</span><span class="sxs-lookup"><span data-stu-id="41ba7-109">Rules</span></span>  
  
- <span data-ttu-id="41ba7-110">**宣言コンテキスト。**</span><span class="sxs-lookup"><span data-stu-id="41ba7-110">**Declaration Context.**</span></span> <span data-ttu-id="41ba7-111">`Public` は、モジュール、インターフェイス、または名前空間レベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="41ba7-111">You can use `Public` only at module, interface, or namespace level.</span></span> <span data-ttu-id="41ba7-112">つまり、`Public` 要素の宣言コンテキストは、ソースファイル、名前空間、インターフェイス、モジュール、クラス、または構造体である必要があり、プロシージャにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="41ba7-112">This means the declaration context for a `Public` element must be a source file, namespace, interface, module, class, or structure, and cannot be a procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="41ba7-113">動作</span><span class="sxs-lookup"><span data-stu-id="41ba7-113">Behavior</span></span>  
  
- <span data-ttu-id="41ba7-114">**アクセスレベル。**</span><span class="sxs-lookup"><span data-stu-id="41ba7-114">**Access Level.**</span></span> <span data-ttu-id="41ba7-115">モジュール、クラス、または構造体にアクセスできるすべてのコードは、その `Public` 要素にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="41ba7-115">All code that can access a module, class, or structure can access its `Public` elements.</span></span>  
  
- <span data-ttu-id="41ba7-116">**既定のアクセス。**</span><span class="sxs-lookup"><span data-stu-id="41ba7-116">**Default Access.**</span></span> <span data-ttu-id="41ba7-117">プロシージャ内のローカル変数は、既定でパブリックアクセスに設定されているので、アクセス修飾子を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="41ba7-117">Local variables inside a procedure default to public access, and you cannot use any access modifiers on them.</span></span>  
  
- <span data-ttu-id="41ba7-118">**アクセス修飾子。**</span><span class="sxs-lookup"><span data-stu-id="41ba7-118">**Access Modifiers.**</span></span> <span data-ttu-id="41ba7-119">アクセスレベルを指定するキーワードは、*アクセス修飾子*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="41ba7-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="41ba7-120">アクセス修飾子の比較については、「[Visual Basic のアクセスレベル](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41ba7-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="41ba7-121">`Public` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="41ba7-121">The `Public` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="41ba7-122">Class ステートメント</span><span class="sxs-lookup"><span data-stu-id="41ba7-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="41ba7-123">Const ステートメント</span><span class="sxs-lookup"><span data-stu-id="41ba7-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="41ba7-124">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="41ba7-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="41ba7-125">Delegate ステートメント</span><span class="sxs-lookup"><span data-stu-id="41ba7-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="41ba7-126">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="41ba7-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="41ba7-127">Enum ステートメント</span><span class="sxs-lookup"><span data-stu-id="41ba7-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="41ba7-128">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="41ba7-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="41ba7-129">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="41ba7-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="41ba7-130">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="41ba7-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="41ba7-131">Module ステートメント</span><span class="sxs-lookup"><span data-stu-id="41ba7-131">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="41ba7-132">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="41ba7-132">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="41ba7-133">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="41ba7-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="41ba7-134">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="41ba7-134">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="41ba7-135">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="41ba7-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="41ba7-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="41ba7-136">See also</span></span>

- [<span data-ttu-id="41ba7-137">Protected</span><span class="sxs-lookup"><span data-stu-id="41ba7-137">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="41ba7-138">Friend</span><span class="sxs-lookup"><span data-stu-id="41ba7-138">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="41ba7-139">Private</span><span class="sxs-lookup"><span data-stu-id="41ba7-139">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="41ba7-140">Private Protected</span><span class="sxs-lookup"><span data-stu-id="41ba7-140">Private Protected</span></span>](private-protected.md)
- [<span data-ttu-id="41ba7-141">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="41ba7-141">Protected Friend</span></span>](protected-friend.md)
- [<span data-ttu-id="41ba7-142">Visual Basic のアクセスレベル</span><span class="sxs-lookup"><span data-stu-id="41ba7-142">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="41ba7-143">手順</span><span class="sxs-lookup"><span data-stu-id="41ba7-143">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="41ba7-144">構造体</span><span class="sxs-lookup"><span data-stu-id="41ba7-144">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="41ba7-145">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="41ba7-145">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
