---
title: Friend
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
ms.openlocfilehash: 98f8ed947c9f4376c5778011a3a91ca8b094f9ec
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351559"
---
# <a name="friend-visual-basic"></a><span data-ttu-id="08109-102">Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="08109-102">Friend (Visual Basic)</span></span>
<span data-ttu-id="08109-103">1つ以上の宣言されたプログラミング要素が、その宣言を含むアセンブリ内からのみアクセス可能であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="08109-103">Specifies that one or more declared programming elements are accessible only from within the assembly that contains their declaration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08109-104">コメント</span><span class="sxs-lookup"><span data-stu-id="08109-104">Remarks</span></span>  
 <span data-ttu-id="08109-105">多くの場合、クラスや構造体などのプログラミング要素は、それを宣言するコンポーネントだけでなく、アセンブリ全体で使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08109-105">In many cases, you want programming elements such as classes and structures to be used by the entire assembly, not only by the component that declares them.</span></span> <span data-ttu-id="08109-106">ただし、アセンブリ外部のコードからアクセスできないようにすることもできます (アプリケーションが独自に作成されている場合など)。</span><span class="sxs-lookup"><span data-stu-id="08109-106">However, you might not want them to be accessible by code outside the assembly (for example, if the application is proprietary).</span></span> <span data-ttu-id="08109-107">この方法で要素へのアクセスを制限する場合は、`Friend` 修飾子を使用して宣言できます。</span><span class="sxs-lookup"><span data-stu-id="08109-107">If you want to limit access to an element in this way, you can declare it by using the `Friend` modifier.</span></span>  
  
 <span data-ttu-id="08109-108">同じアセンブリにコンパイルされる他のクラス、構造体、およびモジュール内のコードは、そのアセンブリ内のすべての `Friend` 要素にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="08109-108">Code in other classes, structures, and modules that are compiled to the same assembly can access all the `Friend` elements in that assembly.</span></span>  
  
 <span data-ttu-id="08109-109">多くの場合、`Friend` アクセスはアプリケーションのプログラミング要素に優先されるレベルであり、`Friend` はインターフェイス、モジュール、クラス、または構造体の既定のアクセスレベルです。</span><span class="sxs-lookup"><span data-stu-id="08109-109">`Friend` access is often the preferred level for an application's programming elements, and `Friend` is the default access level of an interface, a module, a class, or a structure.</span></span>  
  
 <span data-ttu-id="08109-110">`Friend` は、モジュール、インターフェイス、または名前空間レベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="08109-110">You can use `Friend` only at the module, interface, or namespace level.</span></span> <span data-ttu-id="08109-111">したがって、`Friend` 要素の宣言コンテキストは、ソースファイル、名前空間、インターフェイス、モジュール、クラス、または構造体である必要があります。プロシージャを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="08109-111">Therefore, the declaration context for a `Friend` element must be a source file, a namespace, an interface, a module, a class, or a structure; it can't be a procedure.</span></span>  

> [!NOTE]
> <span data-ttu-id="08109-112">[Protected Friend](protected-friend.md)アクセス修飾子を使用することもできます。これにより、クラスメンバーは、クラス内、派生クラス、およびクラスが定義されている同じアセンブリからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="08109-112">You can also use the [Protected Friend](protected-friend.md) access modifier, which makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span></span> <span data-ttu-id="08109-113">クラス内および同じアセンブリ内の派生クラスからメンバーへのアクセスを制限するには、[プライベート Protected](private-protected.md)アクセス修飾子を使用します。</span><span class="sxs-lookup"><span data-stu-id="08109-113">To restrict access to a member from within its class and from derived classes in the same assembly, you use the [Private Protected](private-protected.md) access modifier.</span></span>

 <span data-ttu-id="08109-114">`Friend` とその他のアクセス修飾子の比較については、「 [Visual Basic のアクセスレベル](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08109-114">For a comparison of `Friend` and the other access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="08109-115">別のアセンブリがフレンドアセンブリであることを指定できます。これにより、`Friend`としてマークされているすべての型とメンバーにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="08109-115">You can specify that another assembly is a friend assembly, which allows it to access all types and members that are marked as `Friend`.</span></span> <span data-ttu-id="08109-116">詳細については、[Friend アセンブリ](../../../standard/assembly/friend.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="08109-116">For more information, see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>

## <a name="example"></a><span data-ttu-id="08109-117">例</span><span class="sxs-lookup"><span data-stu-id="08109-117">Example</span></span>  
 <span data-ttu-id="08109-118">次のクラスは、`Friend` 修飾子を使用して、同じアセンブリ内の他のプログラミング要素が特定のメンバーにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="08109-118">The following class uses the `Friend` modifier to allow other programming elements within the same assembly to access certain members.</span></span>  
  
 [!code-vb[VbVbalrAccessModifiers#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalraccessmodifiers/vb/class1.vb#1)]  
  
## <a name="usage"></a><span data-ttu-id="08109-119">使用法</span><span class="sxs-lookup"><span data-stu-id="08109-119">Usage</span></span>  
 <span data-ttu-id="08109-120">これらのコンテキストでは、`Friend` 修飾子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="08109-120">You can use the `Friend` modifier in these contexts:</span></span>  
  
 [<span data-ttu-id="08109-121">Class ステートメント</span><span class="sxs-lookup"><span data-stu-id="08109-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="08109-122">Const ステートメント</span><span class="sxs-lookup"><span data-stu-id="08109-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="08109-123">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="08109-123">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="08109-124">Delegate ステートメント</span><span class="sxs-lookup"><span data-stu-id="08109-124">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="08109-125">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="08109-125">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="08109-126">Enum ステートメント</span><span class="sxs-lookup"><span data-stu-id="08109-126">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="08109-127">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="08109-127">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="08109-128">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="08109-128">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="08109-129">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="08109-129">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="08109-130">Module ステートメント</span><span class="sxs-lookup"><span data-stu-id="08109-130">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="08109-131">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="08109-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="08109-132">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="08109-132">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="08109-133">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="08109-133">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="08109-134">参照</span><span class="sxs-lookup"><span data-stu-id="08109-134">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="08109-135">Public</span><span class="sxs-lookup"><span data-stu-id="08109-135">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="08109-136">Protected</span><span class="sxs-lookup"><span data-stu-id="08109-136">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="08109-137">Private</span><span class="sxs-lookup"><span data-stu-id="08109-137">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="08109-138">Private Protected</span><span class="sxs-lookup"><span data-stu-id="08109-138">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="08109-139">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="08109-139">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="08109-140">Visual Basic のアクセスレベル</span><span class="sxs-lookup"><span data-stu-id="08109-140">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="08109-141">手順</span><span class="sxs-lookup"><span data-stu-id="08109-141">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="08109-142">構造体</span><span class="sxs-lookup"><span data-stu-id="08109-142">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="08109-143">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="08109-143">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
