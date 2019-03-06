---
title: Friend (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Friend
helpviewer_keywords:
- Friend keyword [Visual Basic]
- Friend access modifier
- Friend keyword [Visual Basic], syntax
- Protected Friend keyword combination
- Friend keyword [Visual Basic], and Protected
ms.assetid: b664605e-1c79-4728-b996-aa59c50846bc
ms.openlocfilehash: 1e6dbaa9201d5c9cd902412797b2427ec488d014
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371412"
---
# <a name="friend-visual-basic"></a><span data-ttu-id="3e598-102">Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3e598-102">Friend (Visual Basic)</span></span>
<span data-ttu-id="3e598-103">1 つまたは複数の宣言されたプログラミング要素にその宣言を含むアセンブリ内からのみアクセスできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="3e598-103">Specifies that one or more declared programming elements are accessible only from within the assembly that contains their declaration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e598-104">コメント</span><span class="sxs-lookup"><span data-stu-id="3e598-104">Remarks</span></span>  
 <span data-ttu-id="3e598-105">多くの場合、クラスとそれらを宣言するコンポーネントによってだけでなく、アセンブリ全体で使用される構造体などのプログラミング要素にします。</span><span class="sxs-lookup"><span data-stu-id="3e598-105">In many cases, you want programming elements such as classes and structures to be used by the entire assembly, not only by the component that declares them.</span></span> <span data-ttu-id="3e598-106">ただし、(たとえば、アプリケーションが専用) 場合、アセンブリ外部のコードでアクセスできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e598-106">However, you might not want them to be accessible by code outside the assembly (for example, if the application is proprietary).</span></span> <span data-ttu-id="3e598-107">この方法で要素へのアクセスを制限する場合は、使用して宣言できます、`Friend`修飾子。</span><span class="sxs-lookup"><span data-stu-id="3e598-107">If you want to limit access to an element in this way, you can declare it by using the `Friend` modifier.</span></span>  
  
 <span data-ttu-id="3e598-108">その他のクラス、構造、およびモジュールを同じコンパイルでコード アセンブリはすべてにアクセスできる、`Friend`そのアセンブリ内の要素。</span><span class="sxs-lookup"><span data-stu-id="3e598-108">Code in other classes, structures, and modules that are compiled to the same assembly can access all the `Friend` elements in that assembly.</span></span>  
  
 <span data-ttu-id="3e598-109">`Friend` アクセスは、アプリケーションのプログラミング要素の任意のレベルでは多くの場合と`Friend`インターフェイス、モジュール、クラスまたは構造のレベルで既定のアクセス。</span><span class="sxs-lookup"><span data-stu-id="3e598-109">`Friend` access is often the preferred level for an application's programming elements, and `Friend` is the default access level of an interface, a module, a class, or a structure.</span></span>  
  
 <span data-ttu-id="3e598-110">使用することができます`Friend`モジュール、インターフェイス、または名前空間レベルでのみです。</span><span class="sxs-lookup"><span data-stu-id="3e598-110">You can use `Friend` only at the module, interface, or namespace level.</span></span> <span data-ttu-id="3e598-111">宣言コンテキストはそのため、`Friend`ソース ファイル、名前空間、インターフェイス、モジュール、クラスまたは構造体を要素として使用することがあります。 プロシージャをすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3e598-111">Therefore, the declaration context for a `Friend` element must be a source file, a namespace, an interface, a module, a class, or a structure; it can't be a procedure.</span></span>  

> [!NOTE]
> <span data-ttu-id="3e598-112">使用することも、 [Protected Friend](protected-friend.md)アクセス修飾子、クラス メンバーに、派生クラスとクラスが定義されている同じアセンブリからそのクラス内からアクセスできるようします。</span><span class="sxs-lookup"><span data-stu-id="3e598-112">You can also use the [Protected Friend](protected-friend.md) access modifier, which makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span></span> <span data-ttu-id="3e598-113">使用して、同じアセンブリ内の派生クラスからそのクラス内からのメンバーへのアクセスを制限する、[Private Protected](private-protected.md)アクセス修飾子。</span><span class="sxs-lookup"><span data-stu-id="3e598-113">To restrict access to a member from within its class and from derived classes in the same assembly, you use the [Private Protected](private-protected.md) access modifier.</span></span>

 <span data-ttu-id="3e598-114">比較について`Friend`および他のアクセス修飾子を参照してください[アクセス レベルを Visual Basic で](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)します。</span><span class="sxs-lookup"><span data-stu-id="3e598-114">For a comparison of `Friend` and the other access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3e598-115">別のアセンブリがフレンド アセンブリ、型とメンバーとしてマークされているすべてのアクセスを許可するかを指定することができます`Friend`します。</span><span class="sxs-lookup"><span data-stu-id="3e598-115">You can specify that another assembly is a friend assembly, which allows it to access all types and members that are marked as `Friend`.</span></span> <span data-ttu-id="3e598-116">詳細については、[Friend アセンブリ](../../../standard/assembly/friend-assemblies.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e598-116">For more information, see [Friend Assemblies](../../../standard/assembly/friend-assemblies.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e598-117">例</span><span class="sxs-lookup"><span data-stu-id="3e598-117">Example</span></span>  
 <span data-ttu-id="3e598-118">次のクラスは、`Friend`修飾子を特定のメンバーへのアクセスに同じアセンブリ内の他のプログラミング要素を許可します。</span><span class="sxs-lookup"><span data-stu-id="3e598-118">The following class uses the `Friend` modifier to allow other programming elements within the same assembly to access certain members.</span></span>  
  
 [!code-vb[VbVbalrAccessModifiers#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalraccessmodifiers/vb/class1.vb#1)]  
  
## <a name="usage"></a><span data-ttu-id="3e598-119">使用法</span><span class="sxs-lookup"><span data-stu-id="3e598-119">Usage</span></span>  
 <span data-ttu-id="3e598-120">使用することができます、`Friend`これらのコンテキストでの修飾子。</span><span class="sxs-lookup"><span data-stu-id="3e598-120">You can use the `Friend` modifier in these contexts:</span></span>  
  
 [<span data-ttu-id="3e598-121">Class ステートメント</span><span class="sxs-lookup"><span data-stu-id="3e598-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="3e598-122">Const ステートメント</span><span class="sxs-lookup"><span data-stu-id="3e598-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="3e598-123">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="3e598-123">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="3e598-124">Delegate ステートメント</span><span class="sxs-lookup"><span data-stu-id="3e598-124">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="3e598-125">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="3e598-125">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="3e598-126">Enum ステートメント</span><span class="sxs-lookup"><span data-stu-id="3e598-126">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="3e598-127">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="3e598-127">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="3e598-128">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="3e598-128">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="3e598-129">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="3e598-129">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="3e598-130">Module ステートメント</span><span class="sxs-lookup"><span data-stu-id="3e598-130">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="3e598-131">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="3e598-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="3e598-132">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="3e598-132">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="3e598-133">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="3e598-133">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="3e598-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e598-134">See also</span></span>
- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="3e598-135">Public</span><span class="sxs-lookup"><span data-stu-id="3e598-135">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="3e598-136">Protected</span><span class="sxs-lookup"><span data-stu-id="3e598-136">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="3e598-137">Private</span><span class="sxs-lookup"><span data-stu-id="3e598-137">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="3e598-138">Private Protected</span><span class="sxs-lookup"><span data-stu-id="3e598-138">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="3e598-139">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="3e598-139">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="3e598-140">Visual Basic でのアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="3e598-140">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="3e598-141">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="3e598-141">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="3e598-142">構造体</span><span class="sxs-lookup"><span data-stu-id="3e598-142">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="3e598-143">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="3e598-143">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
