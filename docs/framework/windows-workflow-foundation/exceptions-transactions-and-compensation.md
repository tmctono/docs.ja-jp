---
title: 例外、トランザクション、および補正
ms.date: 03/30/2017
helpviewer_keywords:
- programming [WF], error handling
ms.assetid: 694db4f9-7387-4b13-8f9f-b923b18c7490
ms.openlocfilehash: c4d66e252561ad7b896ff8092e80013c51bd463c
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709472"
---
# <a name="exceptions-transactions-and-compensation"></a><span data-ttu-id="9e011-102">例外、トランザクション、および補正</span><span class="sxs-lookup"><span data-stu-id="9e011-102">Exceptions, Transactions, and Compensation</span></span>
[!INCLUDE[wf1](../../../includes/wf1-md.md)] <span data-ttu-id="9e011-103">には、ワークフロー内のランタイム エラー条件を処理するさまざまな機構が用意されています。</span><span class="sxs-lookup"><span data-stu-id="9e011-103">provides several different mechanisms for handling run-time error conditions in workflows.</span></span> <span data-ttu-id="9e011-104">ワークフローでは、例外ハンドラー、トランザクション、キャンセル、および補正の組み合わせを使用して、エラー条件の処理と適切な回復を行えます。</span><span class="sxs-lookup"><span data-stu-id="9e011-104">Workflows can use a combination of exception handlers, transactions, cancellation, and compensation to handle and recover gracefully from error conditions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9e011-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9e011-105">In This Section</span></span>  
 [<span data-ttu-id="9e011-106">例外</span><span class="sxs-lookup"><span data-stu-id="9e011-106">Exceptions</span></span>](exceptions.md)  
 <span data-ttu-id="9e011-107">
  <xref:System.Activities.Statements.TryCatch> アクティビティを使用して、ワークフローで例外を処理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9e011-107">Demonstrates how to use the <xref:System.Activities.Statements.TryCatch> activity to handle exceptions in a workflow.</span></span>  
  
 [<span data-ttu-id="9e011-108">トランザクション</span><span class="sxs-lookup"><span data-stu-id="9e011-108">Transactions</span></span>](workflow-transactions.md)  
 <span data-ttu-id="9e011-109">
  <xref:System.Activities.Statements.TransactionScope> アクティビティを利用してワークフローでトランザクションを使用する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="9e011-109">Demonstrates how to use the <xref:System.Activities.Statements.TransactionScope> activity to use transactions in a workflow.</span></span>  
  
 [<span data-ttu-id="9e011-110">補正</span><span class="sxs-lookup"><span data-stu-id="9e011-110">Compensation</span></span>](compensation.md)  
 <span data-ttu-id="9e011-111">ワークフローの補正について説明します。また、<xref:System.Activities.Statements.CompensableActivity>、<xref:System.Activities.Statements.Compensate>、および <xref:System.Activities.Statements.Confirm> などの補正アクティビティを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9e011-111">Describes compensation in workflows and demonstrates how to use compensation activities such as <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate>, and <xref:System.Activities.Statements.Confirm>.</span></span>  
  
 [<span data-ttu-id="9e011-112">キャンセル</span><span class="sxs-lookup"><span data-stu-id="9e011-112">Cancellation</span></span>](modeling-cancellation-behavior-in-workflows.md)  
 <span data-ttu-id="9e011-113">組み込みのアクティビティとカスタム アクティビティを使用してワークフローでキャンセル処理を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9e011-113">Describes how to perform cancellation handling in workflows using built-in activities as well as custom activities.</span></span>  
  
 [<span data-ttu-id="9e011-114">ワークフローのデバッグ</span><span class="sxs-lookup"><span data-stu-id="9e011-114">Debugging Workflows</span></span>](debugging-workflows.md)  
 <span data-ttu-id="9e011-115">ワークフローをデバッグする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9e011-115">Describes how to debug workflows.</span></span>
