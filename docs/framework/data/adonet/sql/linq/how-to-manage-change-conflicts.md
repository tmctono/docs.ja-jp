---
title: '方法: 変更の競合を管理する'
ms.date: 03/30/2017
ms.assetid: cd292c51-a3d1-4c6f-8d8e-04323c36054e
ms.openlocfilehash: 49ccb08a375b612e62a8911e98f8ec08058802db
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781838"
---
# <a name="how-to-manage-change-conflicts"></a><span data-ttu-id="912a5-102">方法: 変更の競合を管理する</span><span class="sxs-lookup"><span data-stu-id="912a5-102">How to: Manage Change Conflicts</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="912a5-103">同時実行の競合を検出、評価、および解決するのに役立つ Api のコレクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="912a5-103">provides a collection of APIs to help you discover, evaluate, and resolve concurrency conflicts.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="912a5-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="912a5-104">In This Section</span></span>  
 [<span data-ttu-id="912a5-105">方法: 送信の競合を検出して解決する</span><span class="sxs-lookup"><span data-stu-id="912a5-105">How to: Detect and Resolve Conflicting Submissions</span></span>](how-to-detect-and-resolve-conflicting-submissions.md)  
 <span data-ttu-id="912a5-106">コンカレンシーの競合を検出および解決する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="912a5-106">Describes how to detect and resolve concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="912a5-107">方法: 同時実行例外をいつスローするかを指定します</span><span class="sxs-lookup"><span data-stu-id="912a5-107">How to: Specify When Concurrency Exceptions are Thrown</span></span>](how-to-specify-when-concurrency-exceptions-are-thrown.md)  
 <span data-ttu-id="912a5-108">コンカレンシーの競合をいつ通知するかを指定する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="912a5-108">Describes how to specify when you should be informed of concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="912a5-109">方法: 同時実行の競合をテストするメンバーを指定する</span><span class="sxs-lookup"><span data-stu-id="912a5-109">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)  
 <span data-ttu-id="912a5-110">メンバーに属性を設定して、そのメンバーでコンカレンシーの競合をチェックするかどうかを指定する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="912a5-110">Describes how to attribute members to specify whether they are checked for concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="912a5-111">方法: エンティティの競合情報の取得</span><span class="sxs-lookup"><span data-stu-id="912a5-111">How to: Retrieve Entity Conflict Information</span></span>](how-to-retrieve-entity-conflict-information.md)  
 <span data-ttu-id="912a5-112">エンティティの競合に関する情報を収集する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="912a5-112">Describes how to gather information about entity conflicts.</span></span>  
  
 [<span data-ttu-id="912a5-113">方法: メンバーの競合情報の取得</span><span class="sxs-lookup"><span data-stu-id="912a5-113">How to: Retrieve Member Conflict Information</span></span>](how-to-retrieve-member-conflict-information.md)  
 <span data-ttu-id="912a5-114">メンバーの競合に関する情報を収集する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="912a5-114">Describes how to gather information about member conflicts.</span></span>  
  
 [<span data-ttu-id="912a5-115">方法: データベースの値を保持して競合を解決する</span><span class="sxs-lookup"><span data-stu-id="912a5-115">How to: Resolve Conflicts by Retaining Database Values</span></span>](how-to-resolve-conflicts-by-retaining-database-values.md)  
 <span data-ttu-id="912a5-116">現在の値をデータベースの値で上書きする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="912a5-116">Describes how to overwrite current values with database values.</span></span>  
  
 [<span data-ttu-id="912a5-117">方法: データベースの値を上書きして競合を解決する</span><span class="sxs-lookup"><span data-stu-id="912a5-117">How to: Resolve Conflicts by Overwriting Database Values</span></span>](how-to-resolve-conflicts-by-overwriting-database-values.md)  
 <span data-ttu-id="912a5-118">データベースの値を上書きして現在の値を維持する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="912a5-118">Describes how to keep current values by overwriting database values.</span></span>  
  
 [<span data-ttu-id="912a5-119">方法: データベース値とマージして競合を解決する</span><span class="sxs-lookup"><span data-stu-id="912a5-119">How to: Resolve Conflicts by Merging with Database Values</span></span>](how-to-resolve-conflicts-by-merging-with-database-values.md)  
 <span data-ttu-id="912a5-120">データベースの値と現在の値をマージして競合を解決する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="912a5-120">Describes how to resolve a conflict by merging database and current values.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="912a5-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="912a5-121">Related Sections</span></span>  
 [<span data-ttu-id="912a5-122">オプティミスティック同時実行制御:概要</span><span class="sxs-lookup"><span data-stu-id="912a5-122">Optimistic Concurrency: Overview</span></span>](optimistic-concurrency-overview.md)  
 <span data-ttu-id="912a5-123">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] のオプティミスティック コンカレンシーで使用される用語を説明します。</span><span class="sxs-lookup"><span data-stu-id="912a5-123">Explains the terms that apply to optimistic concurrency in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>
