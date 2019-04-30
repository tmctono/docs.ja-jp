---
title: トランザクション モデル
ms.date: 03/30/2017
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
ms.openlocfilehash: 8731b72d0657aa420dbb020e216c3af059916ce9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050780"
---
# <a name="transaction-models"></a><span data-ttu-id="0643e-102">トランザクション モデル</span><span class="sxs-lookup"><span data-stu-id="0643e-102">Transaction Models</span></span>
<span data-ttu-id="0643e-103">ここでは、トランザクション プログラミング モデルと、マイクロソフトが提供するインフラストラクチャ コンポーネントとの関係を説明します。</span><span class="sxs-lookup"><span data-stu-id="0643e-103">This topic describes the relationship between the transaction programming models and the infrastructure components Microsoft provides.</span></span>  
  
 <span data-ttu-id="0643e-104">トランザクションでは、Windows Communication Foundation (WCF) を使用する場合を選択する別のトランザクション モデルですが統合され一貫したモデルのさまざまなレイヤーではなくオペレーティングは理解してください。</span><span class="sxs-lookup"><span data-stu-id="0643e-104">When using transactions in Windows Communication Foundation (WCF), it is important to understand that you are not selecting between different transactional models, but rather operating at different layers of an integrated and consistent model.</span></span>  
  
 <span data-ttu-id="0643e-105">以下に、3 つの主要なトランザクション コンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0643e-105">The following sections describe the three primary transaction components.</span></span>  
  
## <a name="windows-communication-foundation-transactions"></a><span data-ttu-id="0643e-106">Windows Communication Foundation トランザクション</span><span class="sxs-lookup"><span data-stu-id="0643e-106">Windows Communication Foundation Transactions</span></span>  
 <span data-ttu-id="0643e-107">WCF でサポートされるトランザクションは、トランザクション サービスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0643e-107">The transaction support in WCF allows you write transactional services.</span></span> <span data-ttu-id="0643e-108">さらに、WS-AtomicTransaction (WS-AT) プロトコルのサポート、アプリケーションは、WCF またはサード パーティのテクノロジを使用して構築された Web サービスにトランザクションをフローできます。</span><span class="sxs-lookup"><span data-stu-id="0643e-108">In addition, with its support for the WS-AtomicTransaction (WS-AT) protocol, applications can flow transactions to Web services built using either WCF or third-party technology.</span></span>  
  
 <span data-ttu-id="0643e-109">WCF サービスまたはアプリケーションでは、WCF トランザクション機能は、属性と宣言によってを指定する方法とタイミング インフラストラクチャが作成フロー、トランザクションを同期の構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="0643e-109">In a WCF service or application, WCF transaction features provide attributes and configuration for declaratively specifying how and when the infrastructure should create, flow, and synchronize transactions.</span></span>  
  
## <a name="systemtransactions-transactions"></a><span data-ttu-id="0643e-110">System.Transactions トランザクション</span><span class="sxs-lookup"><span data-stu-id="0643e-110">System.Transactions Transactions</span></span>  
 <span data-ttu-id="0643e-111"><xref:System.Transactions> 名前空間は、<xref:System.Transactions.Transaction> クラスに基づく明示的なプログラミング モデルだけでなく、インフラストラクチャがトランザクションを自動的に管理する、<xref:System.Transactions.TransactionScope> クラスを使用した暗黙的なプログラミング モデルも提供します。</span><span class="sxs-lookup"><span data-stu-id="0643e-111">The <xref:System.Transactions> namespace provides both an explicit programming model based on the <xref:System.Transactions.Transaction> class, as well as an implicit programming model using the <xref:System.Transactions.TransactionScope> class, in which the infrastructure automatically manages transactions.</span></span>  
  
 <span data-ttu-id="0643e-112">これら 2 つのモデルを使用してトランザクション アプリケーションを作成する方法の詳細については、次を参照してください。[トランザクション アプリケーションの作成](https://go.microsoft.com/fwlink/?LinkId=94947)です。</span><span class="sxs-lookup"><span data-stu-id="0643e-112">For more information about how to create a transactional application using these two models, see [Writing a Transactional Application](https://go.microsoft.com/fwlink/?LinkId=94947).</span></span>  
  
 <span data-ttu-id="0643e-113">WCF サービスまたはアプリケーション、<xref:System.Transactions>サービス内で必要なときに、トランザクションに明示的に対話して、クライアント アプリケーション内でトランザクションを作成するために、プログラミング モデルを提供します。</span><span class="sxs-lookup"><span data-stu-id="0643e-113">In a WCF service or application, <xref:System.Transactions> provides the programming model for creating transactions within a client application and for explicitly interacting with a transaction, when required, within a service.</span></span>  
  
## <a name="msdtc-transactions"></a><span data-ttu-id="0643e-114">MSDTC トランザクション</span><span class="sxs-lookup"><span data-stu-id="0643e-114">MSDTC Transactions</span></span>  
 <span data-ttu-id="0643e-115">Microsoft 分散トランザクション コーディネーター (MSDTC) は、分散トランザクションをサポートするトランザクション マネージャーです。</span><span class="sxs-lookup"><span data-stu-id="0643e-115">The Microsoft Distributed Transaction Coordinator (MSDTC) is a transaction manager that provides support for distributed transactions.</span></span>  
  
 <span data-ttu-id="0643e-116">詳細については、次を参照してください。、 [DTC プログラマ リファレンス](https://go.microsoft.com/fwlink/?LinkId=94948)します。</span><span class="sxs-lookup"><span data-stu-id="0643e-116">For more information, see the [DTC Programmer's Reference](https://go.microsoft.com/fwlink/?LinkId=94948).</span></span>  
  
 <span data-ttu-id="0643e-117">WCF サービスまたはアプリケーションでは、MSDTC は、クライアントまたはサービス内で作成されたトランザクションの調整のインフラストラクチャを提供します。</span><span class="sxs-lookup"><span data-stu-id="0643e-117">In a WCF service or application, MSDTC provides the infrastructure for the coordination of transactions created within a client or service.</span></span>
