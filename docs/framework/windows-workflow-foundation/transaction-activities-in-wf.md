---
title: WF におけるトランザクションのアクティビティ
ms.date: 03/30/2017
ms.assetid: fb33378e-82c6-4ea0-870f-76dc77e7f0fe
ms.openlocfilehash: 7ffd64abdc6edf45174d4b756833d65ec0ef747c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670262"
---
# <a name="transaction-activities-in-wf"></a><span data-ttu-id="9be8e-102">WF におけるトランザクションのアクティビティ</span><span class="sxs-lookup"><span data-stu-id="9be8e-102">Transaction Activities in WF</span></span>
<span data-ttu-id="9be8e-103">[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] には、トランザクションや、補正、取り消しをモデル化するためのシステム指定のアクティビティがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="9be8e-103">The [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] has several system-provided activities for modeling transactions, compensation, and cancellation.</span></span> <span data-ttu-id="9be8e-104">これらのプログラミング モデルにより、ビジネス ロジックとエラー処理の変更の場合に、ワークフローは進行を続けることができます。</span><span class="sxs-lookup"><span data-stu-id="9be8e-104">These programming models allow the workflow to continue forward progress in the event of changes in business logic and error handling.</span></span> <span data-ttu-id="9be8e-105">トランザクション、補正、およびキャンセルの詳細については、次を参照してください。[トランザクション](workflow-transactions.md)、[補正](compensation.md)、および[キャンセル](modeling-cancellation-behavior-in-workflows.md)します。</span><span class="sxs-lookup"><span data-stu-id="9be8e-105">For more information about transactions, compensation, and cancellation, see [Transactions](workflow-transactions.md), [Compensation](compensation.md), and [Cancellation](modeling-cancellation-behavior-in-workflows.md).</span></span>  
  
## <a name="transaction-activities"></a><span data-ttu-id="9be8e-106">トランザクションのアクティビティ</span><span class="sxs-lookup"><span data-stu-id="9be8e-106">Transaction Activities</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.CancellationScope>|<span data-ttu-id="9be8e-107">アクティビティの形式のキャンセル ロジックを、アクティビティとしても表される実行のメイン パスに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="9be8e-107">Associates cancellation logic, in the form of an activity, with a main path of execution, also expressed as an activity.</span></span>|  
|<xref:System.Activities.Statements.CompensableActivity>|<span data-ttu-id="9be8e-108">子アクティビティの補正をサポートします。</span><span class="sxs-lookup"><span data-stu-id="9be8e-108">Supports compensation of its child activities.</span></span>|  
|<xref:System.Activities.Statements.Compensate>|<span data-ttu-id="9be8e-109"><xref:System.Activities.Statements.CompensableActivity> の補正ハンドラーを明示的に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9be8e-109">Explicitly invokes the compensation handler of a <xref:System.Activities.Statements.CompensableActivity>.</span></span>|  
|<xref:System.Activities.Statements.Confirm>|<span data-ttu-id="9be8e-110"><xref:System.Activities.Statements.CompensableActivity> の確認ハンドラーを明示的に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9be8e-110">Explicitly invokes the confirmation handler of a <xref:System.Activities.Statements.CompensableActivity>.</span></span>|  
|<xref:System.Activities.Statements.TransactionScope>|<span data-ttu-id="9be8e-111">トランザクションの境界を設定します。</span><span class="sxs-lookup"><span data-stu-id="9be8e-111">Demarcates a transaction boundary.</span></span>|  
|<xref:System.ServiceModel.Activities.TransactedReceiveScope>|<span data-ttu-id="9be8e-112">受信したメッセージによって開始されるトランザクションの有効期間のスコープを設定します。</span><span class="sxs-lookup"><span data-stu-id="9be8e-112">Scopes the lifetime of a transaction that is initiated by a received message.</span></span> <span data-ttu-id="9be8e-113">トランザクションは、開始メッセージでワークフローにフローすることも、メッセージの受信時にディスパッチャーが作成することも可能です。</span><span class="sxs-lookup"><span data-stu-id="9be8e-113">The transaction may be flowed into the workflow on the initiating message, or created by the dispatcher when the message is received.</span></span> <span data-ttu-id="9be8e-114">**注:**<xref:System.ServiceModel.Activities.TransactedReceiveScope>にある、**メッセージング**のセクション、**ツールボックス**します。</span><span class="sxs-lookup"><span data-stu-id="9be8e-114">**Note:**  The <xref:System.ServiceModel.Activities.TransactedReceiveScope> is located in the **Messaging** section of the **Toolbox**.</span></span>|
