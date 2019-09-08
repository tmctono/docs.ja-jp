---
title: '方法: データベース値を維持することで競合を解決する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b475cf72-9e64-4f6e-99c1-af7737bc85ef
ms.openlocfilehash: e42f48a188741c3ddff44f6444fa351192c8175f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793337"
---
# <a name="how-to-resolve-conflicts-by-retaining-database-values"></a><span data-ttu-id="74c57-102">方法: データベース値を維持することで競合を解決する</span><span class="sxs-lookup"><span data-stu-id="74c57-102">How to: Resolve Conflicts by Retaining Database Values</span></span>
<span data-ttu-id="74c57-103">変更内容を再送信する前に、データベース内の予期した値と実際の値の違いを調整するために、<xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues> を使用することで、データベース内の値を維持できます。</span><span class="sxs-lookup"><span data-stu-id="74c57-103">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues> to retain the values found in the database.</span></span> <span data-ttu-id="74c57-104">この場合、オブジェクト モデル内の現在の値は上書きされます。</span><span class="sxs-lookup"><span data-stu-id="74c57-104">The current values in the object model are then overwritten.</span></span> <span data-ttu-id="74c57-105">詳細については[、「オプティミスティック同時実行制御」を参照してください。概要](optimistic-concurrency-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="74c57-105">For more information, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="74c57-106">どの場合も、データベースから最新のデータを取得することで、まずクライアントのレコードが更新されます。</span><span class="sxs-lookup"><span data-stu-id="74c57-106">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="74c57-107">この処理によって、次の更新処理が同じコンカレンシー チェックで失敗することを防止できます。</span><span class="sxs-lookup"><span data-stu-id="74c57-107">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74c57-108">例</span><span class="sxs-lookup"><span data-stu-id="74c57-108">Example</span></span>  
 <span data-ttu-id="74c57-109">このシナリオでは、ユーザー 1 が変更内容を送信しようとしたときに <xref:System.Data.Linq.ChangeConflictException> 例外がスローされます。途中でユーザー 2 が Assistant 列と Department  列を変更したためです。</span><span class="sxs-lookup"><span data-stu-id="74c57-109">In this scenario, a <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="74c57-110">次の表は、この状況を示しています。</span><span class="sxs-lookup"><span data-stu-id="74c57-110">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="74c57-111">管理者</span><span class="sxs-lookup"><span data-stu-id="74c57-111">Manager</span></span>|<span data-ttu-id="74c57-112">Assistant</span><span class="sxs-lookup"><span data-stu-id="74c57-112">Assistant</span></span>|<span data-ttu-id="74c57-113">Department</span><span class="sxs-lookup"><span data-stu-id="74c57-113">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="74c57-114">ユーザー 1 およびユーザー 2 が照会した最初のデータベース状態</span><span class="sxs-lookup"><span data-stu-id="74c57-114">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="74c57-115">Alfreds</span><span class="sxs-lookup"><span data-stu-id="74c57-115">Alfreds</span></span>|<span data-ttu-id="74c57-116">Maria</span><span class="sxs-lookup"><span data-stu-id="74c57-116">Maria</span></span>|<span data-ttu-id="74c57-117">販売</span><span class="sxs-lookup"><span data-stu-id="74c57-117">Sales</span></span>|  
|<span data-ttu-id="74c57-118">ユーザー 1 が送信しようとした変更内容</span><span class="sxs-lookup"><span data-stu-id="74c57-118">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="74c57-119">Alfred</span><span class="sxs-lookup"><span data-stu-id="74c57-119">Alfred</span></span>||<span data-ttu-id="74c57-120">マーケティング</span><span class="sxs-lookup"><span data-stu-id="74c57-120">Marketing</span></span>|  
|<span data-ttu-id="74c57-121">ユーザー 2 が既に送信した変更内容</span><span class="sxs-lookup"><span data-stu-id="74c57-121">User2 has already submitted these changes.</span></span>||<span data-ttu-id="74c57-122">Mary</span><span class="sxs-lookup"><span data-stu-id="74c57-122">Mary</span></span>|<span data-ttu-id="74c57-123">サービス</span><span class="sxs-lookup"><span data-stu-id="74c57-123">Service</span></span>|  
  
 <span data-ttu-id="74c57-124">ユーザー 1 は、この競合を解決するために、新しいデータベース値でオブジェクト モデルの現在の値を上書きすることに決めます。</span><span class="sxs-lookup"><span data-stu-id="74c57-124">User1 decides to resolve this conflict by having the newer database values overwrite the current values in the object model.</span></span>  
  
 <span data-ttu-id="74c57-125">ユーザー 1 が <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues> を使用して競合を解決すると、データベース内の結果は次の表のようになります。</span><span class="sxs-lookup"><span data-stu-id="74c57-125">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues>, the result in the database is as follows in the table:</span></span>  
  
||<span data-ttu-id="74c57-126">管理者</span><span class="sxs-lookup"><span data-stu-id="74c57-126">Manager</span></span>|<span data-ttu-id="74c57-127">Assistant</span><span class="sxs-lookup"><span data-stu-id="74c57-127">Assistant</span></span>|<span data-ttu-id="74c57-128">Department</span><span class="sxs-lookup"><span data-stu-id="74c57-128">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="74c57-129">競合解決後の新しい状態</span><span class="sxs-lookup"><span data-stu-id="74c57-129">New state after conflict resolution.</span></span>|<span data-ttu-id="74c57-130">Alfreds</span><span class="sxs-lookup"><span data-stu-id="74c57-130">Alfreds</span></span><br /><br /> <span data-ttu-id="74c57-131">(元の値)</span><span class="sxs-lookup"><span data-stu-id="74c57-131">(original)</span></span>|<span data-ttu-id="74c57-132">Mary</span><span class="sxs-lookup"><span data-stu-id="74c57-132">Mary</span></span><br /><br /> <span data-ttu-id="74c57-133">(ユーザー 2 の値)</span><span class="sxs-lookup"><span data-stu-id="74c57-133">(from User2)</span></span>|<span data-ttu-id="74c57-134">サービス</span><span class="sxs-lookup"><span data-stu-id="74c57-134">Service</span></span><br /><br /> <span data-ttu-id="74c57-135">(ユーザー 2 の値)</span><span class="sxs-lookup"><span data-stu-id="74c57-135">(from User2)</span></span>|  
  
 <span data-ttu-id="74c57-136">オブジェクト モデルの現在の値をデータベース値で上書きする方法を次のコード例に示します</span><span class="sxs-lookup"><span data-stu-id="74c57-136">The following example code shows how to overwrite current values in the object model with the database values.</span></span> <span data-ttu-id="74c57-137">(個々のメンバーの競合に対する検査やカスタム ハンドリングは行われません)。</span><span class="sxs-lookup"><span data-stu-id="74c57-137">(No inspection or custom handling of individual member conflicts occurs.)</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="74c57-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="74c57-138">See also</span></span>

- [<span data-ttu-id="74c57-139">方法: 変更の競合を管理する</span><span class="sxs-lookup"><span data-stu-id="74c57-139">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
