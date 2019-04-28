---
title: Private (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: d6e28e5e87c3a88e4db3fc81177894683dbb0908
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920446"
---
# <a name="private-visual-basic"></a><span data-ttu-id="09180-102">Private (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09180-102">Private (Visual Basic)</span></span>
<span data-ttu-id="09180-103">1 つまたは複数の宣言されたプログラミング要素に内に含まれる任意の型を含む、宣言のコンテキストからのみアクセスできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="09180-103">Specifies that one or more declared programming elements are accessible only from within their declaration context, including from within any contained types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09180-104">コメント</span><span class="sxs-lookup"><span data-stu-id="09180-104">Remarks</span></span>  
 <span data-ttu-id="09180-105">プログラミング要素は、独自の機能または機密データを含む、通常はできるだけ厳密にへのアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="09180-105">If a programming element represents proprietary functionality, or contains confidential data, you usually want to limit access to it as strictly as possible.</span></span> <span data-ttu-id="09180-106">最大の制限は、モジュール、クラス、またはそれへのアクセスを定義する構造のみを許可することで実現します。</span><span class="sxs-lookup"><span data-stu-id="09180-106">You achieve the maximum limitation by allowing only the module, class, or structure that defines it to access it.</span></span> <span data-ttu-id="09180-107">この方法で要素へのアクセスを制限するために宣言できます`Private`します。</span><span class="sxs-lookup"><span data-stu-id="09180-107">To limit access to an element in this way, you can declare it with `Private`.</span></span>  

> [!NOTE]
> <span data-ttu-id="09180-108">使用することも、[Private Protected](private-protected.md)メンバーにそのクラス内、および、含んでいるアセンブリにある派生クラスからアクセスできるよう、アクセス修飾子。</span><span class="sxs-lookup"><span data-stu-id="09180-108">You can also use the [Private Protected](private-protected.md) access modifier, which makes a member accessible from within that class and from derived classes located in its containing assembly.</span></span>

## <a name="rules"></a><span data-ttu-id="09180-109">ルール</span><span class="sxs-lookup"><span data-stu-id="09180-109">Rules</span></span>  

- <span data-ttu-id="09180-110">**宣言コンテキスト。**</span><span class="sxs-lookup"><span data-stu-id="09180-110">**Declaration Context.**</span></span> <span data-ttu-id="09180-111">`Private` は、モジュール レベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="09180-111">You can use `Private` only at module level.</span></span> <span data-ttu-id="09180-112">これは、意味の宣言のコンテキストを`Private`要素は、モジュール、クラス、または構造体にある必要があるあり、ソース ファイル、名前空間、インターフェイス、またはプロシージャにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="09180-112">This means the declaration context for a `Private` element must be a module, class, or structure, and cannot be a source file, namespace, interface, or procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="09180-113">動作</span><span class="sxs-lookup"><span data-stu-id="09180-113">Behavior</span></span>  
  
- <span data-ttu-id="09180-114">**アクセス レベルです。**</span><span class="sxs-lookup"><span data-stu-id="09180-114">**Access Level.**</span></span> <span data-ttu-id="09180-115">宣言コンテキスト内ですべてのコードがアクセスできるその`Private`要素。</span><span class="sxs-lookup"><span data-stu-id="09180-115">All code within a declaration context can access its `Private` elements.</span></span> <span data-ttu-id="09180-116">これには、入れ子になったクラスまたは列挙型の代入式などの包含の種類の中でコードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="09180-116">This includes code within a contained type, such as a nested class or an assignment expression in an enumeration.</span></span> <span data-ttu-id="09180-117">宣言コンテキストの外側でコードがアクセスできない、`Private`要素。</span><span class="sxs-lookup"><span data-stu-id="09180-117">No code outside of the declaration context can access its `Private` elements.</span></span>  
  
- <span data-ttu-id="09180-118">**アクセス修飾子。**</span><span class="sxs-lookup"><span data-stu-id="09180-118">**Access Modifiers.**</span></span> <span data-ttu-id="09180-119">アクセス レベルを指定するキーワードが呼び出される*アクセス修飾子*します。</span><span class="sxs-lookup"><span data-stu-id="09180-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="09180-120">アクセス修飾子の比較は、次を参照してください。[アクセス レベルを Visual Basic で](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)します。</span><span class="sxs-lookup"><span data-stu-id="09180-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="09180-121">`Private` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="09180-121">The `Private` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="09180-122">Class ステートメント</span><span class="sxs-lookup"><span data-stu-id="09180-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="09180-123">Const ステートメント</span><span class="sxs-lookup"><span data-stu-id="09180-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="09180-124">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="09180-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="09180-125">Delegate ステートメント</span><span class="sxs-lookup"><span data-stu-id="09180-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="09180-126">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="09180-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="09180-127">Enum ステートメント</span><span class="sxs-lookup"><span data-stu-id="09180-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="09180-128">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="09180-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="09180-129">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="09180-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="09180-130">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="09180-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="09180-131">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="09180-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="09180-132">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="09180-132">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="09180-133">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="09180-133">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="09180-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="09180-134">See also</span></span>

- [<span data-ttu-id="09180-135">Public</span><span class="sxs-lookup"><span data-stu-id="09180-135">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="09180-136">Protected</span><span class="sxs-lookup"><span data-stu-id="09180-136">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="09180-137">Friend</span><span class="sxs-lookup"><span data-stu-id="09180-137">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="09180-138">Private Protected</span><span class="sxs-lookup"><span data-stu-id="09180-138">Private Protected</span></span>](./private-protected.md)
- <span data-ttu-id="09180-139">[Protected Friend](./protected-friend.md)[Visual Basic でのレベルのアクセス](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)</span><span class="sxs-lookup"><span data-stu-id="09180-139">[Protected Friend](./protected-friend.md)    [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)</span></span>
- [<span data-ttu-id="09180-140">手順</span><span class="sxs-lookup"><span data-stu-id="09180-140">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="09180-141">構造体</span><span class="sxs-lookup"><span data-stu-id="09180-141">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="09180-142">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="09180-142">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
