---
title: クエリの概念
ms.date: 03/30/2017
ms.assetid: 9a125749-ccb5-49d5-999d-d2db7171d74d
ms.openlocfilehash: 62af37399cda5220c429fae2d9ab619989050b00
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61767521"
---
# <a name="query-concepts"></a><span data-ttu-id="2ae54-102">クエリの概念</span><span class="sxs-lookup"><span data-stu-id="2ae54-102">Query Concepts</span></span>
<span data-ttu-id="2ae54-103">このセクションでは、[!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] で [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] クエリを設計するうえでの主要な概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ae54-103">This section describes key concepts for designing [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2ae54-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2ae54-104">In This Section</span></span>  
 [<span data-ttu-id="2ae54-105">LINQ to SQL クエリ</span><span class="sxs-lookup"><span data-stu-id="2ae54-105">LINQ to SQL Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-queries.md)  
 <span data-ttu-id="2ae54-106">一般的な [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] トピックを参照し、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 固有のアイテムについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2ae54-106">Refers to general [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] topics, and explains items specific to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="2ae54-107">リレーションシップを介したクエリの実行</span><span class="sxs-lookup"><span data-stu-id="2ae54-107">Querying Across Relationships</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-across-relationships.md)  
 <span data-ttu-id="2ae54-108">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] オブジェクト モデルで関連付けを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ae54-108">Explains how to use associations in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="2ae54-109">クエリのリモート実行とローカル実行</span><span class="sxs-lookup"><span data-stu-id="2ae54-109">Remote vs. Local Execution</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/remote-vs-local-execution.md)  
 <span data-ttu-id="2ae54-110">クエリの実行場所を指定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ae54-110">Explains how to specify where you want your query executed.</span></span>  
  
 [<span data-ttu-id="2ae54-111">遅延読み込みと即時読み込み</span><span class="sxs-lookup"><span data-stu-id="2ae54-111">Deferred versus Immediate Loading</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)  
 <span data-ttu-id="2ae54-112">関連オブジェクトをいつ読み込むかを指定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ae54-112">Describes how to specify when related objects are loaded.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2ae54-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ae54-113">Related Sections</span></span>  
 [<span data-ttu-id="2ae54-114">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="2ae54-114">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 <span data-ttu-id="2ae54-115">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] テクノロジについて説明するトピックへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="2ae54-115">Contains links to topics that explain the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology.</span></span>  
  
 [<span data-ttu-id="2ae54-116">オブジェクト ID</span><span class="sxs-lookup"><span data-stu-id="2ae54-116">Object Identity</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/object-identity.md)  
 <span data-ttu-id="2ae54-117">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] のオブジェクト識別子の概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ae54-117">Explains the concept of object identity in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="2ae54-118">LINQ クエリの概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="2ae54-118">Introduction to LINQ Queries (C#)</span></span>](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 <span data-ttu-id="2ae54-119">[!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] のクエリ操作の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ae54-119">Provides an introduction to query operations in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span>
