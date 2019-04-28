---
title: Implements 句 (Visual Basic)
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
ms.openlocfilehash: 05de1d9f8966c17d84deba34f27819cce4aff3fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61637766"
---
# <a name="implements-clause-visual-basic"></a><span data-ttu-id="81cd5-102">Implements 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81cd5-102">Implements Clause (Visual Basic)</span></span>
<span data-ttu-id="81cd5-103">クラスまたは構造体のメンバーがインターフェイスで定義されているメンバーの実装を提供することを示します。</span><span class="sxs-lookup"><span data-stu-id="81cd5-103">Indicates that a class or structure member is providing the implementation for a member defined in an interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81cd5-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="81cd5-104">Remarks</span></span>  
<span data-ttu-id="81cd5-105">`Implements`キーワードがないと同じ、 [Implements ステートメント](../../../visual-basic/language-reference/statements/implements-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="81cd5-105">The `Implements` keyword is not the same as the [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span> <span data-ttu-id="81cd5-106">使用する、`Implements`クラスまたは構造体は、1 つまたは複数のインターフェイスを実装および使用する各メンバーに対して、指定のステートメント、`Implements`インターフェイスとメンバーを指定するキーワードを実装します。</span><span class="sxs-lookup"><span data-stu-id="81cd5-106">You use the `Implements` statement to specify that a class or structure implements one or more interfaces, and then for each member you use the `Implements` keyword to specify which interface and which member it implements.</span></span>

<span data-ttu-id="81cd5-107">含めることはクラスまたは構造体、インターフェイスを実装する場合、`Implements`ステートメントの直後に、 [Class ステートメント](../../../visual-basic/language-reference/statements/class-statement.md)または[Structure ステートメント](../../../visual-basic/language-reference/statements/structure-statement.md)、およびすべてのメンバーを実装する必要がありますインターフェイスによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="81cd5-107">If a class or structure implements an interface, it must include the `Implements` statement immediately after the [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) or [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md), and it must implement all the members defined by the interface.</span></span>

## <a name="reimplementation"></a><span data-ttu-id="81cd5-108">再実装</span><span class="sxs-lookup"><span data-stu-id="81cd5-108">Reimplementation</span></span>  
<span data-ttu-id="81cd5-109">派生クラスでは、基底クラスが実装済みインターフェイスのメンバーを再実装できます。</span><span class="sxs-lookup"><span data-stu-id="81cd5-109">In a derived class, you can reimplement an interface member that the base class has already implemented.</span></span> <span data-ttu-id="81cd5-110">これは、次の点で基底クラスのメンバーのオーバーライドとは異なります。</span><span class="sxs-lookup"><span data-stu-id="81cd5-110">This is different from overriding the base class member in the following respects:</span></span>

- <span data-ttu-id="81cd5-111">基底クラスのメンバーがある必要はありません[Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)実装するためにします。</span><span class="sxs-lookup"><span data-stu-id="81cd5-111">The base class member does not need to be [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) to be reimplemented.</span></span>
- <span data-ttu-id="81cd5-112">別の名前を持つメンバーを再実装できます。</span><span class="sxs-lookup"><span data-stu-id="81cd5-112">You can reimplement the member with a different name.</span></span>

<span data-ttu-id="81cd5-113">`Implements`キーワードは、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="81cd5-113">The `Implements` keyword can be used in the following contexts:</span></span>
- [<span data-ttu-id="81cd5-114">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="81cd5-114">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="81cd5-115">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="81cd5-115">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="81cd5-116">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="81cd5-116">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="81cd5-117">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="81cd5-117">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="81cd5-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="81cd5-118">See also</span></span>

- [<span data-ttu-id="81cd5-119">Implements ステートメント</span><span class="sxs-lookup"><span data-stu-id="81cd5-119">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="81cd5-120">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="81cd5-120">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="81cd5-121">Class ステートメント</span><span class="sxs-lookup"><span data-stu-id="81cd5-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="81cd5-122">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="81cd5-122">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
