---
title: As 句
ms.date: 07/20/2015
f1_keywords:
- vb.as
helpviewer_keywords:
- constraints, Visual Basic generic types
- As keyword [Visual Basic], statement syntax
- As keyword [Visual Basic]
ms.assetid: b4281ec8-2be5-49f7-aae8-ae0a96265b0d
ms.openlocfilehash: cf1acbfeee150f1ea353ce134a4e94dab9928e8a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350171"
---
# <a name="as-clause-visual-basic"></a><span data-ttu-id="595dd-102">As 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="595dd-102">As Clause (Visual Basic)</span></span>
<span data-ttu-id="595dd-103">では、宣言ステートメントまたはジェネリック型パラメーターの制約リストのデータ型を識別する `As` 句が導入されています。</span><span class="sxs-lookup"><span data-stu-id="595dd-103">Introduces an `As` clause, which identifies a data type in a declaration statement or a constraint list on a generic type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="595dd-104">コメント</span><span class="sxs-lookup"><span data-stu-id="595dd-104">Remarks</span></span>  
 <span data-ttu-id="595dd-105">キーワード `As` は次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="595dd-105">The `As` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="595dd-106">Aggregate 句</span><span class="sxs-lookup"><span data-stu-id="595dd-106">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)  
  
 [<span data-ttu-id="595dd-107">Class ステートメント</span><span class="sxs-lookup"><span data-stu-id="595dd-107">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="595dd-108">Const ステートメント</span><span class="sxs-lookup"><span data-stu-id="595dd-108">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="595dd-109">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="595dd-109">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="595dd-110">Delegate ステートメント</span><span class="sxs-lookup"><span data-stu-id="595dd-110">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="595dd-111">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="595dd-111">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="595dd-112">Enum ステートメント</span><span class="sxs-lookup"><span data-stu-id="595dd-112">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="595dd-113">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="595dd-113">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="595dd-114">For...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="595dd-114">For...Next Statements</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
  
 [<span data-ttu-id="595dd-115">For Each...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="595dd-115">For Each...Next Statements</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
  
 [<span data-ttu-id="595dd-116">From 句</span><span class="sxs-lookup"><span data-stu-id="595dd-116">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
  
 [<span data-ttu-id="595dd-117">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="595dd-117">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="595dd-118">Group Join 句</span><span class="sxs-lookup"><span data-stu-id="595dd-118">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)  
  
 [<span data-ttu-id="595dd-119">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="595dd-119">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="595dd-120">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="595dd-120">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="595dd-121">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="595dd-121">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="595dd-122">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="595dd-122">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="595dd-123">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="595dd-123">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
 [<span data-ttu-id="595dd-124">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="595dd-124">Try...Catch...Finally Statements</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="595dd-125">参照</span><span class="sxs-lookup"><span data-stu-id="595dd-125">See also</span></span>

- [<span data-ttu-id="595dd-126">方法 : 新しい変数を作成する</span><span class="sxs-lookup"><span data-stu-id="595dd-126">How to: Create a New Variable</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-create-a-new-variable.md)
- [<span data-ttu-id="595dd-127">データの種類</span><span class="sxs-lookup"><span data-stu-id="595dd-127">Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="595dd-128">変数宣言</span><span class="sxs-lookup"><span data-stu-id="595dd-128">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="595dd-129">型リスト</span><span class="sxs-lookup"><span data-stu-id="595dd-129">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="595dd-130">Visual Basic におけるジェネリック型</span><span class="sxs-lookup"><span data-stu-id="595dd-130">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="595dd-131">キーワード</span><span class="sxs-lookup"><span data-stu-id="595dd-131">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
