---
title: Private
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: 0c855c4e08b365b4cb75ab062d2ec304a79612ab
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347916"
---
# <a name="private-visual-basic"></a><span data-ttu-id="ea4bf-102">Private (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ea4bf-102">Private (Visual Basic)</span></span>
<span data-ttu-id="ea4bf-103">1つ以上の宣言されたプログラミング要素が、含まれている型の中からを含め、宣言コンテキスト内からのみアクセス可能であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="ea4bf-103">Specifies that one or more declared programming elements are accessible only from within their declaration context, including from within any contained types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea4bf-104">コメント</span><span class="sxs-lookup"><span data-stu-id="ea4bf-104">Remarks</span></span>  
 <span data-ttu-id="ea4bf-105">プログラミング要素が独自の機能を表している場合、または機密データが含まれている場合は、通常、できるだけ厳密にアクセスを制限することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ea4bf-105">If a programming element represents proprietary functionality, or contains confidential data, you usually want to limit access to it as strictly as possible.</span></span> <span data-ttu-id="ea4bf-106">最大の制限を達成するには、それを定義するモジュール、クラス、または構造体だけがアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="ea4bf-106">You achieve the maximum limitation by allowing only the module, class, or structure that defines it to access it.</span></span> <span data-ttu-id="ea4bf-107">この方法で要素へのアクセスを制限するには、`Private`で要素を宣言します。</span><span class="sxs-lookup"><span data-stu-id="ea4bf-107">To limit access to an element in this way, you can declare it with `Private`.</span></span>  

> [!NOTE]
> <span data-ttu-id="ea4bf-108">[Private Protected](private-protected.md)アクセス修飾子を使用することもできます。これにより、メンバーは、そのクラス内から、およびそれを含むアセンブリに配置されている派生クラスからアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="ea4bf-108">You can also use the [Private Protected](private-protected.md) access modifier, which makes a member accessible from within that class and from derived classes located in its containing assembly.</span></span>

## <a name="rules"></a><span data-ttu-id="ea4bf-109">ルール</span><span class="sxs-lookup"><span data-stu-id="ea4bf-109">Rules</span></span>  

- <span data-ttu-id="ea4bf-110">**宣言コンテキスト。**</span><span class="sxs-lookup"><span data-stu-id="ea4bf-110">**Declaration Context.**</span></span> <span data-ttu-id="ea4bf-111">`Private` は、モジュール レベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ea4bf-111">You can use `Private` only at module level.</span></span> <span data-ttu-id="ea4bf-112">つまり、`Private` 要素の宣言コンテキストは、モジュール、クラス、または構造体である必要があり、ソースファイル、名前空間、インターフェイス、またはプロシージャにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ea4bf-112">This means the declaration context for a `Private` element must be a module, class, or structure, and cannot be a source file, namespace, interface, or procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="ea4bf-113">動作</span><span class="sxs-lookup"><span data-stu-id="ea4bf-113">Behavior</span></span>  
  
- <span data-ttu-id="ea4bf-114">**アクセス レベル。**</span><span class="sxs-lookup"><span data-stu-id="ea4bf-114">**Access Level.**</span></span> <span data-ttu-id="ea4bf-115">宣言コンテキスト内のすべてのコードは、その `Private` 要素にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ea4bf-115">All code within a declaration context can access its `Private` elements.</span></span> <span data-ttu-id="ea4bf-116">これには、入れ子になったクラスや列挙体の代入式など、含まれている型内のコードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ea4bf-116">This includes code within a contained type, such as a nested class or an assignment expression in an enumeration.</span></span> <span data-ttu-id="ea4bf-117">宣言コンテキストの外部のコードは、その `Private` 要素にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="ea4bf-117">No code outside of the declaration context can access its `Private` elements.</span></span>  
  
- <span data-ttu-id="ea4bf-118">**アクセス修飾子。**</span><span class="sxs-lookup"><span data-stu-id="ea4bf-118">**Access Modifiers.**</span></span> <span data-ttu-id="ea4bf-119">アクセスレベルを指定するキーワードは、*アクセス修飾子*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="ea4bf-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="ea4bf-120">アクセス修飾子の比較については、「[Visual Basic でのアクセス レベル](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea4bf-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="ea4bf-121">`Private` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="ea4bf-121">The `Private` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="ea4bf-122">Class ステートメント</span><span class="sxs-lookup"><span data-stu-id="ea4bf-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="ea4bf-123">Const ステートメント</span><span class="sxs-lookup"><span data-stu-id="ea4bf-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="ea4bf-124">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="ea4bf-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="ea4bf-125">Delegate ステートメント</span><span class="sxs-lookup"><span data-stu-id="ea4bf-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="ea4bf-126">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="ea4bf-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="ea4bf-127">Enum ステートメント</span><span class="sxs-lookup"><span data-stu-id="ea4bf-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="ea4bf-128">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="ea4bf-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="ea4bf-129">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="ea4bf-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="ea4bf-130">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="ea4bf-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="ea4bf-131">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="ea4bf-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="ea4bf-132">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="ea4bf-132">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="ea4bf-133">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="ea4bf-133">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="ea4bf-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea4bf-134">See also</span></span>

- [<span data-ttu-id="ea4bf-135">Public</span><span class="sxs-lookup"><span data-stu-id="ea4bf-135">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="ea4bf-136">Protected</span><span class="sxs-lookup"><span data-stu-id="ea4bf-136">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="ea4bf-137">Friend</span><span class="sxs-lookup"><span data-stu-id="ea4bf-137">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="ea4bf-138">Private Protected</span><span class="sxs-lookup"><span data-stu-id="ea4bf-138">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="ea4bf-139">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="ea4bf-139">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="ea4bf-140">Visual Basic でのアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="ea4bf-140">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="ea4bf-141">手順</span><span class="sxs-lookup"><span data-stu-id="ea4bf-141">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="ea4bf-142">構造体</span><span class="sxs-lookup"><span data-stu-id="ea4bf-142">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="ea4bf-143">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="ea4bf-143">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
