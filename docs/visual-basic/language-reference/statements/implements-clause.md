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
ms.openlocfilehash: f114aee75356e59eafd9d3ba6af9c64402cb374f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345873"
---
# <a name="implements-clause-visual-basic"></a><span data-ttu-id="af121-102">Implements 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af121-102">Implements Clause (Visual Basic)</span></span>
<span data-ttu-id="af121-103">クラスまたは構造体のメンバーが、インターフェイスで定義されているメンバーの実装を提供していることを示します。</span><span class="sxs-lookup"><span data-stu-id="af121-103">Indicates that a class or structure member is providing the implementation for a member defined in an interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af121-104">コメント</span><span class="sxs-lookup"><span data-stu-id="af121-104">Remarks</span></span>  
<span data-ttu-id="af121-105">`Implements` キーワードは[Implements ステートメント](../../../visual-basic/language-reference/statements/implements-statement.md)と同じではありません。</span><span class="sxs-lookup"><span data-stu-id="af121-105">The `Implements` keyword is not the same as the [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span> <span data-ttu-id="af121-106">`Implements` ステートメントを使用して、クラスまたは構造体が1つ以上のインターフェイスを実装することを指定し、各メンバーに対して `Implements` キーワードを使用して、実装するインターフェイスとメンバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="af121-106">You use the `Implements` statement to specify that a class or structure implements one or more interfaces, and then for each member you use the `Implements` keyword to specify which interface and which member it implements.</span></span>

<span data-ttu-id="af121-107">クラスまたは構造体がインターフェイスを実装する場合は、[クラスステートメント](../../../visual-basic/language-reference/statements/class-statement.md)または[構造体ステートメント](../../../visual-basic/language-reference/statements/structure-statement.md)の直後に `Implements` ステートメントを含める必要があります。また、インターフェイスで定義されているすべてのメンバーを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af121-107">If a class or structure implements an interface, it must include the `Implements` statement immediately after the [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) or [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md), and it must implement all the members defined by the interface.</span></span>

## <a name="reimplementation"></a><span data-ttu-id="af121-108">再実装</span><span class="sxs-lookup"><span data-stu-id="af121-108">Reimplementation</span></span>  
<span data-ttu-id="af121-109">派生クラスでは、基底クラスに既に実装されているインターフェイスメンバーを再実装できます。</span><span class="sxs-lookup"><span data-stu-id="af121-109">In a derived class, you can reimplement an interface member that the base class has already implemented.</span></span> <span data-ttu-id="af121-110">これは、次の点で基底クラスのメンバーをオーバーライドすることとは異なります。</span><span class="sxs-lookup"><span data-stu-id="af121-110">This is different from overriding the base class member in the following respects:</span></span>

- <span data-ttu-id="af121-111">基底クラスのメンバーは、再実装として[オーバーライド](../../../visual-basic/language-reference/modifiers/overridable.md)可能である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="af121-111">The base class member does not need to be [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) to be reimplemented.</span></span>
- <span data-ttu-id="af121-112">別の名前を使用してメンバーを再実装できます。</span><span class="sxs-lookup"><span data-stu-id="af121-112">You can reimplement the member with a different name.</span></span>

<span data-ttu-id="af121-113">`Implements` キーワードは、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="af121-113">The `Implements` keyword can be used in the following contexts:</span></span>

- [<span data-ttu-id="af121-114">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="af121-114">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="af121-115">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="af121-115">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="af121-116">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="af121-116">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="af121-117">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="af121-117">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="af121-118">参照</span><span class="sxs-lookup"><span data-stu-id="af121-118">See also</span></span>

- [<span data-ttu-id="af121-119">Implements ステートメント</span><span class="sxs-lookup"><span data-stu-id="af121-119">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="af121-120">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="af121-120">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="af121-121">Class ステートメント</span><span class="sxs-lookup"><span data-stu-id="af121-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="af121-122">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="af121-122">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
