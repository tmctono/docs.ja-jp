---
title: トランザクション アプリケーションの作成
description: .NET でトランザクション アプリケーションを作成します。 Transaction クラスまたは TransactionScope クラスでそれぞれ、明示的または暗黙的なプログラミング モデルを使用します。
ms.date: 03/30/2017
ms.assetid: a4d891f2-6fc8-4395-93c6-6819492406e0
ms.openlocfilehash: b4cc33939128e61a69db319491a7d2d60ab9a819
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186667"
---
# <a name="writing-a-transactional-application"></a><span data-ttu-id="31e57-104">トランザクション アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="31e57-104">Writing a Transactional Application</span></span>

<span data-ttu-id="31e57-105">トランザクション アプリケーションのプログラマは、<xref:System.Transactions> 名前空間に用意されている 2 つのプログラミング モデルを活用して、トランザクションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="31e57-105">As a transactional application programmer, you can take advantage of the two programming models provided by the <xref:System.Transactions> namespace to create a transaction.</span></span> <span data-ttu-id="31e57-106"><xref:System.Transactions.Transaction> クラスを使用した明示的なプログラミング モデルを使用できるほか、<xref:System.Transactions.TransactionScope> クラスを使用して、トランザクションが自動的にインフラストラクチャによって管理される暗黙的なプログラミング モデルも利用できます。</span><span class="sxs-lookup"><span data-stu-id="31e57-106">You can utilize the explicit programming model by using the <xref:System.Transactions.Transaction> class, or the implicit programming model in which transactions are automatically managed by the infrastructure, by using the <xref:System.Transactions.TransactionScope> class.</span></span> <span data-ttu-id="31e57-107">開発では、暗黙的なトランザクション モデルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="31e57-107">We recommend that you use the implicit transaction model for development.</span></span> <span data-ttu-id="31e57-108">トランザクション スコープの使用方法については、「[トランザクション スコープを使用した暗黙的なトランザクションの実装](implementing-an-implicit-transaction-using-transaction-scope.md)」のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="31e57-108">You can find more information on how to use a transaction scope in the [Implementing an Implicit Transaction using Transaction Scope](implementing-an-implicit-transaction-using-transaction-scope.md) topic.</span></span>  
  
 <span data-ttu-id="31e57-109">両モデルとも、プログラムが整合性の取れた状態に達した時点で、トランザクションのコミットをサポートします。</span><span class="sxs-lookup"><span data-stu-id="31e57-109">Both models support committing a transaction when the program reaches a consistent state.</span></span> <span data-ttu-id="31e57-110">コミットが成功すると、トランザクションは永続的にコミットされます。</span><span class="sxs-lookup"><span data-stu-id="31e57-110">If the commit succeeds, the transaction is durably committed.</span></span> <span data-ttu-id="31e57-111">コミットが失敗すると、トランザクションは中止されます。</span><span class="sxs-lookup"><span data-stu-id="31e57-111">If the commit fails, the transaction aborts.</span></span> <span data-ttu-id="31e57-112">アプリケーション プログラムがトランザクションを完了できない場合は、トランザクションを中止してその処理内容を取り消すことを試みます。</span><span class="sxs-lookup"><span data-stu-id="31e57-112">If the application program cannot successfully complete the transaction, it attempts to abort and undo the transaction's effects.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="31e57-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="31e57-113">In This Section</span></span>  
  
### <a name="creating-a-transaction"></a><span data-ttu-id="31e57-114">トランザクションの作成</span><span class="sxs-lookup"><span data-stu-id="31e57-114">Creating a Transaction</span></span>  

 <span data-ttu-id="31e57-115"><xref:System.Transactions> 名前空間には、トランザクションを作成する 2 つのモデルが用意されています。</span><span class="sxs-lookup"><span data-stu-id="31e57-115">The <xref:System.Transactions> namespace provides two models for creating a transaction.</span></span> <span data-ttu-id="31e57-116">これらのモデルは、以下のトピックで取り上げられています。</span><span class="sxs-lookup"><span data-stu-id="31e57-116">These models are covered in the following topics.</span></span>  
  
 [<span data-ttu-id="31e57-117">トランザクション スコープを使用した暗黙的なトランザクションの実装</span><span class="sxs-lookup"><span data-stu-id="31e57-117">Implementing an Implicit Transaction using Transaction Scope</span></span>](implementing-an-implicit-transaction-using-transaction-scope.md)  
  
 <span data-ttu-id="31e57-118"><xref:System.Transactions> 名前空間がサポートする、<xref:System.Transactions.TransactionScope> クラスを使用した暗黙的なトランザクションの作成について説明します。</span><span class="sxs-lookup"><span data-stu-id="31e57-118">Describes how the <xref:System.Transactions> namespace supports creating implicit transactions using the <xref:System.Transactions.TransactionScope> class.</span></span>  
  
 [<span data-ttu-id="31e57-119">CommittableTransaction を使用した明示的なトランザクションの実装</span><span class="sxs-lookup"><span data-stu-id="31e57-119">Implementing an Explicit Transaction using CommittableTransaction</span></span>](implementing-an-explicit-transaction-using-committabletransaction.md)  
  
 <span data-ttu-id="31e57-120"><xref:System.Transactions> 名前空間がサポートする、<xref:System.Transactions.CommittableTransaction> クラスを使用した明示的なトランザクションの作成について説明します。</span><span class="sxs-lookup"><span data-stu-id="31e57-120">Describes how the <xref:System.Transactions> namespace supports creating explicit transactions using the <xref:System.Transactions.CommittableTransaction> class.</span></span>  
  
### <a name="escalating-transaction-management"></a><span data-ttu-id="31e57-121">トランザクション管理のエスカレート</span><span class="sxs-lookup"><span data-stu-id="31e57-121">Escalating Transaction Management</span></span>  

 <span data-ttu-id="31e57-122">トランザクションが別のアプリケーション ドメインにあるリソースにアクセスする必要がある場合、または別の永続的なリソース マネージャーに参加する場合は、トランザクションが MSDTC によって管理されるよう自動的にエスカレートされます。</span><span class="sxs-lookup"><span data-stu-id="31e57-122">When a transaction needs to access a resource in another application domain, or if you want to enlist in another durable resource manager, the transaction is automatically escalated to be managed by the MSDTC.</span></span> <span data-ttu-id="31e57-123">トランザクションのエスカレーションの詳細については、「[トランザクション管理のエスカレーション](transaction-management-escalation.md)」のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="31e57-123">Transaction escalation is covered in the [Transaction Management Escalation](transaction-management-escalation.md) topic.</span></span>  
  
### <a name="concurrency"></a><span data-ttu-id="31e57-124">コンカレンシー</span><span class="sxs-lookup"><span data-stu-id="31e57-124">Concurrency</span></span>  

 <span data-ttu-id="31e57-125">「[DependentTransaction によるコンカレンシーの管理](managing-concurrency-with-dependenttransaction.md)」のトピックでは、<xref:System.Transactions.DependentTransaction> クラスを使用して、非同期タスク間でコンカレンシーを実現する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="31e57-125">The topic [Managing Concurrency with DependentTransaction](managing-concurrency-with-dependenttransaction.md) demonstrates how concurrency can be achieved between asynchronous tasks by using the <xref:System.Transactions.DependentTransaction> class.</span></span>  
  
### <a name="com-interop"></a><span data-ttu-id="31e57-126">COM+ 相互運用</span><span class="sxs-lookup"><span data-stu-id="31e57-126">COM+ Interop</span></span>  

 <span data-ttu-id="31e57-127">「[Enterprise Services および COM+ トランザクションとの相互運用性](interoperability-with-enterprise-services-and-com-transactions.md)」のトピックでは、分散トランザクションを COM+ トランザクションと連係させる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="31e57-127">The topic [Interoperability with Enterprise Services and COM+ Transactions](interoperability-with-enterprise-services-and-com-transactions.md) illustrates how you can make your distributed transactions interact with COM+ transactions.</span></span>  
  
### <a name="diagnostics"></a><span data-ttu-id="31e57-128">診断</span><span class="sxs-lookup"><span data-stu-id="31e57-128">Diagnostics</span></span>  

 <span data-ttu-id="31e57-129">「[診断トレース](diagnostic-traces.md)」では、<xref:System.Transactions> インフラストラクチャによって生成されるトレース コードを使用して、アプリケーションのエラーのトラブルシューティングを行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="31e57-129">[Diagnostic Traces](diagnostic-traces.md) describes how you can use the trace codes that are generated by the <xref:System.Transactions> infrastructure to troubleshoot errors in your applications.</span></span>  
  
### <a name="working-within-aspnet"></a><span data-ttu-id="31e57-130">ASP.NET 内での使用</span><span class="sxs-lookup"><span data-stu-id="31e57-130">Working within ASP.NET</span></span>  

 <span data-ttu-id="31e57-131">「[ASP.NET での System.Transactions の使用](using-system-transactions-in-aspnet.md)」のトピックでは、ASP.NET アプリケーション内で <xref:System.Transactions> を正しく使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="31e57-131">The [Using System.Transactions in ASP.NET](using-system-transactions-in-aspnet.md) topic describes how you can successfully use <xref:System.Transactions> inside an ASP.NET application.</span></span>
