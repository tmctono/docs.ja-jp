---
title: セキュリティ
ms.date: 03/30/2017
ms.assetid: 737ec121-bfc5-4b75-a504-2d53c2c8af39
ms.openlocfilehash: c27ac9cf41436332d560e11987e3ce4b68576895
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004693"
---
# <a name="security"></a><span data-ttu-id="62a60-102">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="62a60-102">Security</span></span>
<span data-ttu-id="62a60-103">SQL Workflow Instance Store は、次のデータベース セキュリティ ロールを使用して、永続性データベースのインスタンス状態情報へのアクセスをセキュリティ保護します。</span><span class="sxs-lookup"><span data-stu-id="62a60-103">The SQL Workflow Instance Store uses the following database security roles to secure access to instance state information in the persistence database.</span></span>  
  
- <span data-ttu-id="62a60-104">**System.Activities.DurableInstancing.InstanceStoreUsers**します。</span><span class="sxs-lookup"><span data-stu-id="62a60-104">**System.Activities.DurableInstancing.InstanceStoreUsers**.</span></span> <span data-ttu-id="62a60-105">このロールには、パブリック ビューへの読み取りおよび書き込みのアクセス権と、インスタンスの作成、読み込み、保存に関連するストアド プロシージャへの実行権限があります。</span><span class="sxs-lookup"><span data-stu-id="62a60-105">This role has read and write access to public views and execution rights to stored procedures that are involved in creating, loading and saving instances.</span></span>  
  
- <span data-ttu-id="62a60-106">**System.Activities.DurableInstancing.InstanceStoreObservers**します。</span><span class="sxs-lookup"><span data-stu-id="62a60-106">**System.Activities.DurableInstancing.InstanceStoreObservers**.</span></span> <span data-ttu-id="62a60-107">このロールには、パブリック ビューへの読み取り専用アクセス権があります。</span><span class="sxs-lookup"><span data-stu-id="62a60-107">This role has read-only access to public views.</span></span>  
  
- <span data-ttu-id="62a60-108">**System.Activities.DurableInstancing.WorkflowActivationUsers**します。</span><span class="sxs-lookup"><span data-stu-id="62a60-108">**System.Activities.DurableInstancing.WorkflowActivationUsers**.</span></span> <span data-ttu-id="62a60-109">このロールには、インスタンスのアクティベーション プロセスにかかわるストアド プロシージャへの実行権限があります。</span><span class="sxs-lookup"><span data-stu-id="62a60-109">This role has execution rights to stored procedures that are involved in the instance activation process.</span></span> <span data-ttu-id="62a60-110">インスタンスのアクティブ化の詳細については、次を参照してください。[インスタンスのアクティベーション](instance-activation.md)します。</span><span class="sxs-lookup"><span data-stu-id="62a60-110">For more information about instance activation, see [Instance Activation](instance-activation.md).</span></span> <span data-ttu-id="62a60-111">汎用ホスト ([!INCLUDE[dublin](../../../includes/dublin-md.md)] のワークフロー管理サービスなど) を実行するユーザー アカウントは、このデータベース ロールに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62a60-111">The user account under which a generic host (such as the Workflow Management Service of [!INCLUDE[dublin](../../../includes/dublin-md.md)]) runs should be added to this database role.</span></span>  
  
 <span data-ttu-id="62a60-112">Windows Server App Fabric で永続化ストアのセキュリティの詳細については、次を参照してください[App Fabric の永続化ストアのセキュリティの構成。](https://go.microsoft.com/fwlink/?LinkId=201208)</span><span class="sxs-lookup"><span data-stu-id="62a60-112">For more information about security for persistence stores with Windows Server App Fabric, see [Security Configuration for Persistence Stores in App Fabric](https://go.microsoft.com/fwlink/?LinkId=201208)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="62a60-113">インスタンス ストア内にある固有のインスタンス データへのアクセス権を持つクライアントは、同じインスタンス ストア内にあるその他すべてのインスタンスにもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="62a60-113">A client that has access to its own instance data in the instance store has access to all other instances in the same instance store.</span></span> <span data-ttu-id="62a60-114">インスタンス ストアでは、インスタンス レベルでセキュリティ アクセス許可を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="62a60-114">The instance store does not support specifying security permissions at the instance level.</span></span> <span data-ttu-id="62a60-115">個別のインスタンス ストアを作成し、ストアごとに、各グループやユーザーのアクセス権を設定します。</span><span class="sxs-lookup"><span data-stu-id="62a60-115">You should create separate instance stores and map different groups/users to have access to different stores.</span></span>
