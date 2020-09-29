---
title: Implements 句
ms.date: 07/20/2015
f1_keywords:
- vb.ImplementsClause
helpviewer_keywords:
- interface implementation [Visual Basic], reimplementation
- interface members [Visual Basic], reimplementation
- interface members [Visual Basic], Implements keyword
- interface members
- members [Visual Basic], reimplementation
- interface implementation [Visual Basic], Implements keyword
- interface members [Visual Basic], implementing
- Implements keyword [Visual Basic]
- Implements statement [Visual Basic], about Implements
- members [Visual Basic], implementing
- members [Visual Basic], Implements keyword
- reimplementation
ms.assetid: 5252cdf9-964d-4fc6-af0f-0449b7126b5a
ms.openlocfilehash: 7c95cf76b1bac24e2a0f20857b8984d54ebbea85
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866165"
---
# <a name="implements-clause-visual-basic"></a><span data-ttu-id="96227-102">Implements 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96227-102">Implements Clause (Visual Basic)</span></span>

<span data-ttu-id="96227-103">クラスまたは構造体のメンバーがインターフェイスで定義されているメンバーの実装を提供していることを示します。</span><span class="sxs-lookup"><span data-stu-id="96227-103">Indicates that a class or structure member is providing the implementation for a member defined in an interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96227-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="96227-104">Remarks</span></span>  

<span data-ttu-id="96227-105">`Implements` キーワードは、[Implements ステートメント](implements-statement.md)と同じではありません。</span><span class="sxs-lookup"><span data-stu-id="96227-105">The `Implements` keyword is not the same as the [Implements Statement](implements-statement.md).</span></span> <span data-ttu-id="96227-106">`Implements` ステートメントを使用して、クラスまたは構造体が 1 つ以上のインターフェイスを実装することを指定し、メンバーごとに `Implements` キーワードを使用して、実装するインターフェイスとメンバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="96227-106">You use the `Implements` statement to specify that a class or structure implements one or more interfaces, and then for each member you use the `Implements` keyword to specify which interface and which member it implements.</span></span>

<span data-ttu-id="96227-107">クラスまたは構造体がインターフェイスを実装する場合は、[Class ステートメント](class-statement.md)または [Structure ステートメント](structure-statement.md)の直後に `Implements` ステートメントを含める必要があります。また、インターフェイスによって定義されたすべてのメンバーを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96227-107">If a class or structure implements an interface, it must include the `Implements` statement immediately after the [Class Statement](class-statement.md) or [Structure Statement](structure-statement.md), and it must implement all the members defined by the interface.</span></span>

## <a name="reimplementation"></a><span data-ttu-id="96227-108">再実装</span><span class="sxs-lookup"><span data-stu-id="96227-108">Reimplementation</span></span>  

<span data-ttu-id="96227-109">派生クラスでは、基底クラスによって既に実装されているインターフェイス メンバーを再実装できます。</span><span class="sxs-lookup"><span data-stu-id="96227-109">In a derived class, you can reimplement an interface member that the base class has already implemented.</span></span> <span data-ttu-id="96227-110">これは、基底クラスのメンバーのオーバーライドとは、次の点で異なります。</span><span class="sxs-lookup"><span data-stu-id="96227-110">This is different from overriding the base class member in the following respects:</span></span>

- <span data-ttu-id="96227-111">基底クラスのメンバーは、再実装するために [Overridable](../modifiers/overridable.md) である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="96227-111">The base class member does not need to be [Overridable](../modifiers/overridable.md) to be reimplemented.</span></span>
- <span data-ttu-id="96227-112">別の名前を使用してメンバーを再実装できます。</span><span class="sxs-lookup"><span data-stu-id="96227-112">You can reimplement the member with a different name.</span></span>

<span data-ttu-id="96227-113">`Implements` キーワードは、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="96227-113">The `Implements` keyword can be used in the following contexts:</span></span>

- [<span data-ttu-id="96227-114">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="96227-114">Event Statement</span></span>](event-statement.md)
- [<span data-ttu-id="96227-115">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="96227-115">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="96227-116">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="96227-116">Property Statement</span></span>](property-statement.md)
- [<span data-ttu-id="96227-117">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="96227-117">Sub Statement</span></span>](sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="96227-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="96227-118">See also</span></span>

- [<span data-ttu-id="96227-119">Implements ステートメント</span><span class="sxs-lookup"><span data-stu-id="96227-119">Implements Statement</span></span>](implements-statement.md)
- [<span data-ttu-id="96227-120">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="96227-120">Interface Statement</span></span>](interface-statement.md)
- [<span data-ttu-id="96227-121">Class ステートメント</span><span class="sxs-lookup"><span data-stu-id="96227-121">Class Statement</span></span>](class-statement.md)
- [<span data-ttu-id="96227-122">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="96227-122">Structure Statement</span></span>](structure-statement.md)
