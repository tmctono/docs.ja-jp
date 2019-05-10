---
title: Protected (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Protected
helpviewer_keywords:
- Protected Friend keyword combination
- Protected keyword [Visual Basic], and Friend
- Protected keyword [Visual Basic], syntax
- Protected access modifier
- Protected keyword [Visual Basic]
ms.assetid: 74ad3d56-309f-49d2-b60c-1d0157d010e8
ms.openlocfilehash: 86758c68f0f3bfe214a695f656d3924eadd27e31
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64642687"
---
# <a name="protected-visual-basic"></a><span data-ttu-id="3b24a-102">Protected (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3b24a-102">Protected (Visual Basic)</span></span>
<span data-ttu-id="3b24a-103">1 つまたは複数のプログラミング要素が宣言されていることを指定するメンバー アクセス修飾子は、独自のクラス内または派生クラスからのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3b24a-103">A member access modifier that specifies that one or more declared programming elements are accessible only from within their own class or from a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b24a-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="3b24a-104">Remarks</span></span>  
 <span data-ttu-id="3b24a-105">クラスで宣言されたプログラミング要素が機密データまたは制限付きのコードを格納することもありますし、要素へのアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="3b24a-105">Sometimes a programming element declared in a class contains sensitive data or restricted code, and you want to limit access to the element.</span></span> <span data-ttu-id="3b24a-106">ただし、クラスが継承可能でないと、派生クラスの階層が期待どおり場合、これらの派生クラスのデータまたはコードにアクセスするために必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="3b24a-106">However, if the class is inheritable and you expect a hierarchy of derived classes, it might be necessary for these derived classes to access the data or code.</span></span> <span data-ttu-id="3b24a-107">このような場合は、基底クラスとすべての派生クラスの両方にアクセスできる要素をします。</span><span class="sxs-lookup"><span data-stu-id="3b24a-107">In such a case, you want the element to be accessible both from the base class and from all derived classes.</span></span> <span data-ttu-id="3b24a-108">この方法で要素へのアクセスを制限するために宣言できます`Protected`します。</span><span class="sxs-lookup"><span data-stu-id="3b24a-108">To limit access to an element in this manner, you can declare it with `Protected`.</span></span>  

> [!NOTE]
> <span data-ttu-id="3b24a-109">`Protected`アクセス修飾子は、その他の 2 つの修飾子と組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="3b24a-109">The `Protected` access modifier can be combined with two other modifiers:</span></span>
> - <span data-ttu-id="3b24a-110">[Protected Friend](protected-friend.md)修飾子は、クラス メンバーを同じアセンブリのクラスが定義されていると、派生クラスからそのクラス内からアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3b24a-110">The [Protected Friend](protected-friend.md) modifier makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span></span> 
> - <span data-ttu-id="3b24a-111">[Private Protected](private-protected.md)修飾子により、クラス メンバー アクセス、含んでいるアセンブリ内でのみ、派生型です。</span><span class="sxs-lookup"><span data-stu-id="3b24a-111">The [Private Protected](private-protected.md) modifier makes a class member accessible by derived types, but only within its containing assembly.</span></span>
  
## <a name="rules"></a><span data-ttu-id="3b24a-112">ルール</span><span class="sxs-lookup"><span data-stu-id="3b24a-112">Rules</span></span>  
  
- <span data-ttu-id="3b24a-113">**宣言コンテキスト。**</span><span class="sxs-lookup"><span data-stu-id="3b24a-113">**Declaration Context.**</span></span> <span data-ttu-id="3b24a-114">使用することができます`Protected`クラス レベルでのみです。</span><span class="sxs-lookup"><span data-stu-id="3b24a-114">You can use `Protected` only at the class level.</span></span> <span data-ttu-id="3b24a-115">これは、意味の宣言のコンテキストを`Protected`要素は、クラスでなければなりませんし、ソース ファイル、名前空間、インターフェイス、モジュール、構造体、またはプロシージャにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3b24a-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>  

## <a name="behavior"></a><span data-ttu-id="3b24a-116">動作</span><span class="sxs-lookup"><span data-stu-id="3b24a-116">Behavior</span></span>  
  
- <span data-ttu-id="3b24a-117">**アクセス レベルです。**</span><span class="sxs-lookup"><span data-stu-id="3b24a-117">**Access Level.**</span></span> <span data-ttu-id="3b24a-118">クラスのすべてのコードは、その要素にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3b24a-118">All code in a class can access its elements.</span></span> <span data-ttu-id="3b24a-119">すべての基本クラスから派生したクラス内のコードにアクセスできます、`Protected`基底クラスの要素。</span><span class="sxs-lookup"><span data-stu-id="3b24a-119">Code in any class that derives from a base class can access all the `Protected` elements of the base class.</span></span> <span data-ttu-id="3b24a-120">これは、派生のすべてのジェネレーションに当てはまります。</span><span class="sxs-lookup"><span data-stu-id="3b24a-120">This is true for all generations of derivation.</span></span> <span data-ttu-id="3b24a-121">これは、クラスにアクセスできることを意味`Protected`基底クラスの基底クラスの要素。</span><span class="sxs-lookup"><span data-stu-id="3b24a-121">This means that a class can access `Protected` elements of the base class of the base class, and so on.</span></span>  
  
     <span data-ttu-id="3b24a-122">保護されたアクセスは、スーパー セットまたはサブセットのフレンド アクセスではありません。</span><span class="sxs-lookup"><span data-stu-id="3b24a-122">Protected access is not a superset or subset of friend access.</span></span>  
  
- <span data-ttu-id="3b24a-123">**アクセス修飾子。**</span><span class="sxs-lookup"><span data-stu-id="3b24a-123">**Access Modifiers.**</span></span> <span data-ttu-id="3b24a-124">アクセス レベルを指定するキーワードが呼び出される*アクセス修飾子*します。</span><span class="sxs-lookup"><span data-stu-id="3b24a-124">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="3b24a-125">アクセス修飾子の比較は、次を参照してください。[アクセス レベルを Visual Basic で](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)します。</span><span class="sxs-lookup"><span data-stu-id="3b24a-125">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="3b24a-126">`Protected` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="3b24a-126">The `Protected` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="3b24a-127">Class ステートメント</span><span class="sxs-lookup"><span data-stu-id="3b24a-127">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="3b24a-128">Const ステートメント</span><span class="sxs-lookup"><span data-stu-id="3b24a-128">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="3b24a-129">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="3b24a-129">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="3b24a-130">Delegate ステートメント</span><span class="sxs-lookup"><span data-stu-id="3b24a-130">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="3b24a-131">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="3b24a-131">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="3b24a-132">Enum ステートメント</span><span class="sxs-lookup"><span data-stu-id="3b24a-132">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="3b24a-133">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="3b24a-133">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="3b24a-134">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="3b24a-134">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="3b24a-135">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="3b24a-135">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="3b24a-136">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="3b24a-136">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="3b24a-137">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="3b24a-137">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="3b24a-138">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="3b24a-138">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="3b24a-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b24a-139">See also</span></span>

- [<span data-ttu-id="3b24a-140">Public</span><span class="sxs-lookup"><span data-stu-id="3b24a-140">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="3b24a-141">Friend</span><span class="sxs-lookup"><span data-stu-id="3b24a-141">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="3b24a-142">Private</span><span class="sxs-lookup"><span data-stu-id="3b24a-142">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="3b24a-143">Private Protected</span><span class="sxs-lookup"><span data-stu-id="3b24a-143">Private Protected</span></span>](private-protected.md)
- [<span data-ttu-id="3b24a-144">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="3b24a-144">Protected Friend</span></span>](protected-friend.md)
- [<span data-ttu-id="3b24a-145">Visual Basic でのアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="3b24a-145">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="3b24a-146">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="3b24a-146">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="3b24a-147">構造体</span><span class="sxs-lookup"><span data-stu-id="3b24a-147">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="3b24a-148">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="3b24a-148">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
