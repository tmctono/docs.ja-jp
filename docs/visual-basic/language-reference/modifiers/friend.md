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
ms.openlocfilehash: 3e30267c8aa11ce97b3b3064ff0954378dab57af
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959802"
---
# <a name="friend-visual-basic"></a><span data-ttu-id="49d00-102">Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49d00-102">Friend (Visual Basic)</span></span>
<span data-ttu-id="49d00-103">1つ以上の宣言されたプログラミング要素が、その宣言を含むアセンブリ内からのみアクセス可能であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="49d00-103">Specifies that one or more declared programming elements are accessible only from within the assembly that contains their declaration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49d00-104">コメント</span><span class="sxs-lookup"><span data-stu-id="49d00-104">Remarks</span></span>  
 <span data-ttu-id="49d00-105">多くの場合、クラスや構造体などのプログラミング要素は、それを宣言するコンポーネントだけでなく、アセンブリ全体で使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49d00-105">In many cases, you want programming elements such as classes and structures to be used by the entire assembly, not only by the component that declares them.</span></span> <span data-ttu-id="49d00-106">ただし、アセンブリ外部のコードからアクセスできないようにすることもできます (アプリケーションが独自に作成されている場合など)。</span><span class="sxs-lookup"><span data-stu-id="49d00-106">However, you might not want them to be accessible by code outside the assembly (for example, if the application is proprietary).</span></span> <span data-ttu-id="49d00-107">この方法で要素へのアクセスを制限する場合は、 `Friend`修飾子を使用して宣言できます。</span><span class="sxs-lookup"><span data-stu-id="49d00-107">If you want to limit access to an element in this way, you can declare it by using the `Friend` modifier.</span></span>  
  
 <span data-ttu-id="49d00-108">同じアセンブリにコンパイルされる他のクラス、構造体、およびモジュール内のコードは、 `Friend`そのアセンブリ内のすべての要素にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="49d00-108">Code in other classes, structures, and modules that are compiled to the same assembly can access all the `Friend` elements in that assembly.</span></span>  
  
 <span data-ttu-id="49d00-109">`Friend`多くの場合、アクセスはアプリケーションのプログラミング要素`Friend`に優先されるレベルであり、インターフェイス、モジュール、クラス、または構造体の既定のアクセスレベルです。</span><span class="sxs-lookup"><span data-stu-id="49d00-109">`Friend` access is often the preferred level for an application's programming elements, and `Friend` is the default access level of an interface, a module, a class, or a structure.</span></span>  
  
 <span data-ttu-id="49d00-110">は、モジュール`Friend` 、インターフェイス、または名前空間レベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="49d00-110">You can use `Friend` only at the module, interface, or namespace level.</span></span> <span data-ttu-id="49d00-111">したがって、 `Friend`要素の宣言コンテキストは、ソースファイル、名前空間、インターフェイス、モジュール、クラス、または構造体である必要があります。プロシージャにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="49d00-111">Therefore, the declaration context for a `Friend` element must be a source file, a namespace, an interface, a module, a class, or a structure; it can't be a procedure.</span></span>  

> [!NOTE]
> <span data-ttu-id="49d00-112">[Protected Friend](protected-friend.md)アクセス修飾子を使用することもできます。これにより、クラスメンバーは、クラス内、派生クラス、およびクラスが定義されている同じアセンブリからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="49d00-112">You can also use the [Protected Friend](protected-friend.md) access modifier, which makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span></span> <span data-ttu-id="49d00-113">使用して、同じアセンブリ内の派生クラスからそのクラス内からのメンバーへのアクセスを制限する、[Private Protected](private-protected.md)アクセス修飾子。</span><span class="sxs-lookup"><span data-stu-id="49d00-113">To restrict access to a member from within its class and from derived classes in the same assembly, you use the [Private Protected](private-protected.md) access modifier.</span></span>

 <span data-ttu-id="49d00-114">とその他の`Friend`アクセス修飾子の比較については、「 [Visual Basic のアクセスレベル](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49d00-114">For a comparison of `Friend` and the other access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="49d00-115">別のアセンブリがフレンドアセンブリであることを指定できます。これにより、として`Friend`マークされているすべての型とメンバーにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="49d00-115">You can specify that another assembly is a friend assembly, which allows it to access all types and members that are marked as `Friend`.</span></span> <span data-ttu-id="49d00-116">詳細については、[Friend アセンブリ](../../../standard/assembly/friend-assemblies.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="49d00-116">For more information, see [Friend Assemblies](../../../standard/assembly/friend-assemblies.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="49d00-117">例</span><span class="sxs-lookup"><span data-stu-id="49d00-117">Example</span></span>  
 <span data-ttu-id="49d00-118">次のクラスは、 `Friend`修飾子を使用して、同じアセンブリ内の他のプログラミング要素が特定のメンバーにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="49d00-118">The following class uses the `Friend` modifier to allow other programming elements within the same assembly to access certain members.</span></span>  
  
 [!code-vb[VbVbalrAccessModifiers#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalraccessmodifiers/vb/class1.vb#1)]  
  
## <a name="usage"></a><span data-ttu-id="49d00-119">使用法</span><span class="sxs-lookup"><span data-stu-id="49d00-119">Usage</span></span>  
 <span data-ttu-id="49d00-120">修飾子は、 `Friend`次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="49d00-120">You can use the `Friend` modifier in these contexts:</span></span>  
  
 [<span data-ttu-id="49d00-121">Class ステートメント</span><span class="sxs-lookup"><span data-stu-id="49d00-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="49d00-122">Const ステートメント</span><span class="sxs-lookup"><span data-stu-id="49d00-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="49d00-123">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="49d00-123">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="49d00-124">Delegate ステートメント</span><span class="sxs-lookup"><span data-stu-id="49d00-124">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="49d00-125">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="49d00-125">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="49d00-126">Enum ステートメント</span><span class="sxs-lookup"><span data-stu-id="49d00-126">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="49d00-127">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="49d00-127">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="49d00-128">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="49d00-128">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="49d00-129">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="49d00-129">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="49d00-130">Module ステートメント</span><span class="sxs-lookup"><span data-stu-id="49d00-130">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="49d00-131">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="49d00-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="49d00-132">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="49d00-132">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="49d00-133">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="49d00-133">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="49d00-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="49d00-134">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="49d00-135">Public</span><span class="sxs-lookup"><span data-stu-id="49d00-135">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="49d00-136">Protected</span><span class="sxs-lookup"><span data-stu-id="49d00-136">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="49d00-137">Private</span><span class="sxs-lookup"><span data-stu-id="49d00-137">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="49d00-138">Private Protected</span><span class="sxs-lookup"><span data-stu-id="49d00-138">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="49d00-139">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="49d00-139">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="49d00-140">Visual Basic のアクセスレベル</span><span class="sxs-lookup"><span data-stu-id="49d00-140">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="49d00-141">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="49d00-141">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="49d00-142">構造体</span><span class="sxs-lookup"><span data-stu-id="49d00-142">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="49d00-143">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="49d00-143">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
