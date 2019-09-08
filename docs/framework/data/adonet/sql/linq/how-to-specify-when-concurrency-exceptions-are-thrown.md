---
title: '方法: コンカレンシー例外をいつスローするかを指定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 344ae068-ff63-4a2e-8b00-af22e143675f
ms.openlocfilehash: c0f41d23264bbe5c9130cb5a0b03686331bc92b1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781622"
---
# <a name="how-to-specify-when-concurrency-exceptions-are-thrown"></a><span data-ttu-id="c8a8c-102">方法: コンカレンシー例外をいつスローするかを指定する</span><span class="sxs-lookup"><span data-stu-id="c8a8c-102">How to: Specify When Concurrency Exceptions are Thrown</span></span>
<span data-ttu-id="c8a8c-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] では、オプティミスティック コンカレンシーの競合によってオブジェクトが更新されないときに <xref:System.Data.Linq.ChangeConflictException> 例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c8a8c-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], a <xref:System.Data.Linq.ChangeConflictException> exception is thrown when objects do not update because of optimistic concurrency conflicts.</span></span> <span data-ttu-id="c8a8c-104">詳細については[、「オプティミスティック同時実行制御」を参照してください。概要](optimistic-concurrency-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c8a8c-104">For more information, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span>  
  
 <span data-ttu-id="c8a8c-105">変更内容をデータベースに送信する前に、コンカレンシー例外をどの時点でスローするかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c8a8c-105">Before you submit your changes to the database, you can specify when concurrency exceptions should be thrown:</span></span>  
  
- <span data-ttu-id="c8a8c-106">例外を最初のエラーの時点でスローします (<xref:System.Data.Linq.ConflictMode.FailOnFirstConflict>)。</span><span class="sxs-lookup"><span data-stu-id="c8a8c-106">Throw the exception at the first failure (<xref:System.Data.Linq.ConflictMode.FailOnFirstConflict>).</span></span>  
  
- <span data-ttu-id="c8a8c-107">更新の再試行を決められた回数繰り返し、すべてのエラー情報を集積してから、この情報を例外で報告します (<xref:System.Data.Linq.ConflictMode.ContinueOnConflict>)。</span><span class="sxs-lookup"><span data-stu-id="c8a8c-107">Finish all update tries, accumulate all failures, and report the accumulated failures in the exception (<xref:System.Data.Linq.ConflictMode.ContinueOnConflict>).</span></span>  
  
 <span data-ttu-id="c8a8c-108"><xref:System.Data.Linq.ChangeConflictException> 例外がスローされると、例外を通じて <xref:System.Data.Linq.ChangeConflictCollection> コレクションにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c8a8c-108">When thrown, the <xref:System.Data.Linq.ChangeConflictException> exception provides access to a <xref:System.Data.Linq.ChangeConflictCollection> collection.</span></span> <span data-ttu-id="c8a8c-109">このコレクションを使用して、個々の競合 (それぞれが 1 回の更新失敗に対応する) の詳細情報を取得したり、<xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A> コレクションにアクセスしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="c8a8c-109">This collection provides details for each conflict (mapped to a single failed update try), including access to the <xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A> collection.</span></span> <span data-ttu-id="c8a8c-110">各メンバー競合は、コンカレンシー チェックでエラーになった更新の 1 つのメンバーに対応します。</span><span class="sxs-lookup"><span data-stu-id="c8a8c-110">Each member conflict maps to a single member in the update that failed the concurrency check.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8a8c-111">例</span><span class="sxs-lookup"><span data-stu-id="c8a8c-111">Example</span></span>  
 <span data-ttu-id="c8a8c-112">両方の値の例を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="c8a8c-112">The following code shows examples of both values.</span></span>  
  
 [!code-csharp[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c8a8c-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8a8c-113">See also</span></span>

- [<span data-ttu-id="c8a8c-114">方法: 変更の競合を管理する</span><span class="sxs-lookup"><span data-stu-id="c8a8c-114">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
- [<span data-ttu-id="c8a8c-115">データの変更と変更の送信</span><span class="sxs-lookup"><span data-stu-id="c8a8c-115">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
