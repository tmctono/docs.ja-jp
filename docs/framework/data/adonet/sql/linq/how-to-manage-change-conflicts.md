---
title: '方法: 変更の競合を管理する'
ms.date: 03/30/2017
ms.assetid: cd292c51-a3d1-4c6f-8d8e-04323c36054e
ms.openlocfilehash: 49ccb08a375b612e62a8911e98f8ec08058802db
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781838"
---
# <a name="how-to-manage-change-conflicts"></a><span data-ttu-id="07465-102">方法: 変更の競合を管理する</span><span class="sxs-lookup"><span data-stu-id="07465-102">How to: Manage Change Conflicts</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="07465-103">には、コンカレンシーの競合の発見、評価、および解決に使用できる API が用意されています。</span><span class="sxs-lookup"><span data-stu-id="07465-103">provides a collection of APIs to help you discover, evaluate, and resolve concurrency conflicts.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="07465-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="07465-104">In This Section</span></span>  
 [<span data-ttu-id="07465-105">方法: 送信の競合を検出および解決する</span><span class="sxs-lookup"><span data-stu-id="07465-105">How to: Detect and Resolve Conflicting Submissions</span></span>](how-to-detect-and-resolve-conflicting-submissions.md)  
 <span data-ttu-id="07465-106">コンカレンシーの競合を検出および解決する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="07465-106">Describes how to detect and resolve concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="07465-107">方法: コンカレンシー例外をいつスローするかを指定する</span><span class="sxs-lookup"><span data-stu-id="07465-107">How to: Specify When Concurrency Exceptions are Thrown</span></span>](how-to-specify-when-concurrency-exceptions-are-thrown.md)  
 <span data-ttu-id="07465-108">コンカレンシーの競合をいつ通知するかを指定する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="07465-108">Describes how to specify when you should be informed of concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="07465-109">方法: コンカレンシーの競合を検査するメンバーを指定する</span><span class="sxs-lookup"><span data-stu-id="07465-109">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)  
 <span data-ttu-id="07465-110">メンバーに属性を設定して、そのメンバーでコンカレンシーの競合をチェックするかどうかを指定する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="07465-110">Describes how to attribute members to specify whether they are checked for concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="07465-111">方法: エンティティの競合情報を取得する</span><span class="sxs-lookup"><span data-stu-id="07465-111">How to: Retrieve Entity Conflict Information</span></span>](how-to-retrieve-entity-conflict-information.md)  
 <span data-ttu-id="07465-112">エンティティの競合に関する情報を収集する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="07465-112">Describes how to gather information about entity conflicts.</span></span>  
  
 [<span data-ttu-id="07465-113">方法: メンバーの競合情報を取得する</span><span class="sxs-lookup"><span data-stu-id="07465-113">How to: Retrieve Member Conflict Information</span></span>](how-to-retrieve-member-conflict-information.md)  
 <span data-ttu-id="07465-114">メンバーの競合に関する情報を収集する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="07465-114">Describes how to gather information about member conflicts.</span></span>  
  
 [<span data-ttu-id="07465-115">方法: データベース値を維持することで競合を解決する</span><span class="sxs-lookup"><span data-stu-id="07465-115">How to: Resolve Conflicts by Retaining Database Values</span></span>](how-to-resolve-conflicts-by-retaining-database-values.md)  
 <span data-ttu-id="07465-116">現在の値をデータベースの値で上書きする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="07465-116">Describes how to overwrite current values with database values.</span></span>  
  
 [<span data-ttu-id="07465-117">方法: データベース値を上書きすることで競合を解決する</span><span class="sxs-lookup"><span data-stu-id="07465-117">How to: Resolve Conflicts by Overwriting Database Values</span></span>](how-to-resolve-conflicts-by-overwriting-database-values.md)  
 <span data-ttu-id="07465-118">データベースの値を上書きして現在の値を維持する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="07465-118">Describes how to keep current values by overwriting database values.</span></span>  
  
 [<span data-ttu-id="07465-119">方法: データベース値とマージすることで競合を解決する</span><span class="sxs-lookup"><span data-stu-id="07465-119">How to: Resolve Conflicts by Merging with Database Values</span></span>](how-to-resolve-conflicts-by-merging-with-database-values.md)  
 <span data-ttu-id="07465-120">データベースの値と現在の値をマージして競合を解決する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="07465-120">Describes how to resolve a conflict by merging database and current values.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="07465-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="07465-121">Related Sections</span></span>  
 [<span data-ttu-id="07465-122">オプティミスティック コンカレンシー: 概要</span><span class="sxs-lookup"><span data-stu-id="07465-122">Optimistic Concurrency: Overview</span></span>](optimistic-concurrency-overview.md)  
 <span data-ttu-id="07465-123">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] のオプティミスティック コンカレンシーで使用される用語を説明します。</span><span class="sxs-lookup"><span data-stu-id="07465-123">Explains the terms that apply to optimistic concurrency in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>
