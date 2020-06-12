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
ms.openlocfilehash: 4afc2800a98ceeda8eeb3a1fada0b82c2e8bcedb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408459"
---
# <a name="as-clause-visual-basic"></a><span data-ttu-id="23c63-102">As 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23c63-102">As Clause (Visual Basic)</span></span>
<span data-ttu-id="23c63-103">宣言ステートメントのデータ型またはジェネリック型パラメーターの制約リストを識別する `As` 句について紹介します。</span><span class="sxs-lookup"><span data-stu-id="23c63-103">Introduces an `As` clause, which identifies a data type in a declaration statement or a constraint list on a generic type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23c63-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="23c63-104">Remarks</span></span>  
 <span data-ttu-id="23c63-105">キーワード `As` は次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="23c63-105">The `As` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="23c63-106">Aggregate 句</span><span class="sxs-lookup"><span data-stu-id="23c63-106">Aggregate Clause</span></span>](../queries/aggregate-clause.md)  
  
 [<span data-ttu-id="23c63-107">Class ステートメント</span><span class="sxs-lookup"><span data-stu-id="23c63-107">Class Statement</span></span>](class-statement.md)  
  
 [<span data-ttu-id="23c63-108">Const ステートメント</span><span class="sxs-lookup"><span data-stu-id="23c63-108">Const Statement</span></span>](const-statement.md)  
  
 [<span data-ttu-id="23c63-109">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="23c63-109">Declare Statement</span></span>](declare-statement.md)  
  
 [<span data-ttu-id="23c63-110">Delegate ステートメント</span><span class="sxs-lookup"><span data-stu-id="23c63-110">Delegate Statement</span></span>](delegate-statement.md)  
  
 [<span data-ttu-id="23c63-111">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="23c63-111">Dim Statement</span></span>](dim-statement.md)  
  
 [<span data-ttu-id="23c63-112">Enum ステートメント</span><span class="sxs-lookup"><span data-stu-id="23c63-112">Enum Statement</span></span>](enum-statement.md)  
  
 [<span data-ttu-id="23c63-113">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="23c63-113">Event Statement</span></span>](event-statement.md)  
  
 [<span data-ttu-id="23c63-114">For...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="23c63-114">For...Next Statements</span></span>](for-next-statement.md)  
  
 [<span data-ttu-id="23c63-115">For Each...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="23c63-115">For Each...Next Statements</span></span>](for-each-next-statement.md)  
  
 [<span data-ttu-id="23c63-116">From 句</span><span class="sxs-lookup"><span data-stu-id="23c63-116">From Clause</span></span>](../queries/from-clause.md)  
  
 [<span data-ttu-id="23c63-117">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="23c63-117">Function Statement</span></span>](function-statement.md)  
  
 [<span data-ttu-id="23c63-118">Group Join 句</span><span class="sxs-lookup"><span data-stu-id="23c63-118">Group Join Clause</span></span>](../queries/group-join-clause.md)  
  
 [<span data-ttu-id="23c63-119">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="23c63-119">Interface Statement</span></span>](interface-statement.md)  
  
 [<span data-ttu-id="23c63-120">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="23c63-120">Operator Statement</span></span>](operator-statement.md)  
  
 [<span data-ttu-id="23c63-121">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="23c63-121">Property Statement</span></span>](property-statement.md)  
  
 [<span data-ttu-id="23c63-122">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="23c63-122">Structure Statement</span></span>](structure-statement.md)  
  
 [<span data-ttu-id="23c63-123">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="23c63-123">Sub Statement</span></span>](sub-statement.md)  
  
 [<span data-ttu-id="23c63-124">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="23c63-124">Try...Catch...Finally Statements</span></span>](try-catch-finally-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="23c63-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="23c63-125">See also</span></span>

- [<span data-ttu-id="23c63-126">方法: 新しい変数を作成する</span><span class="sxs-lookup"><span data-stu-id="23c63-126">How to: Create a New Variable</span></span>](../../programming-guide/language-features/variables/how-to-create-a-new-variable.md)
- [<span data-ttu-id="23c63-127">データの種類</span><span class="sxs-lookup"><span data-stu-id="23c63-127">Data Types</span></span>](../../programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="23c63-128">変数宣言</span><span class="sxs-lookup"><span data-stu-id="23c63-128">Variable Declaration</span></span>](../../programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="23c63-129">型リスト</span><span class="sxs-lookup"><span data-stu-id="23c63-129">Type List</span></span>](type-list.md)
- [<span data-ttu-id="23c63-130">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="23c63-130">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="23c63-131">キーワード</span><span class="sxs-lookup"><span data-stu-id="23c63-131">Keywords</span></span>](../keywords/index.md)
