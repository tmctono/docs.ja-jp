---
title: 非同期通信
ms.date: 03/30/2017
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
ms.openlocfilehash: e1bc63b5d3178b8e98350dedd8eb0791e0e35589
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142877"
---
# <a name="asynchronous-communication"></a><span data-ttu-id="7f6b2-102">非同期通信</span><span class="sxs-lookup"><span data-stu-id="7f6b2-102">Asynchronous Communication</span></span>
<span data-ttu-id="7f6b2-103">このサンプルでは、2 つの異なる Windows ワークフローファンデーション (WF) サービス間の通信が既定で非同期的に行われる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7f6b2-103">This sample demonstrates how the communication between two different Windows Workflow Foundation (WF) services is done asynchronously by default.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="7f6b2-104">対象</span><span class="sxs-lookup"><span data-stu-id="7f6b2-104">Demonstrates</span></span>  
 <span data-ttu-id="7f6b2-105">[!INCLUDE[wf1](../../../../includes/wf1-md.md)] サービス間の非同期通信</span><span class="sxs-lookup"><span data-stu-id="7f6b2-105">Asynchronous communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] services.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="7f6b2-106">ディスカッション</span><span class="sxs-lookup"><span data-stu-id="7f6b2-106">Discussion</span></span>  
 <span data-ttu-id="7f6b2-107">このサンプルでは、.NET Framework が提供するメッセージング アクティビティを使用して、[!INCLUDE[wf1](../../../../includes/wf1-md.md)] アプリケーション間の非同期通信がどのように行われるのかを示します。</span><span class="sxs-lookup"><span data-stu-id="7f6b2-107">This sample shows how the communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] applications is done asynchronously by using the messaging activities provided by .NET Framework.</span></span>  
  
 <span data-ttu-id="7f6b2-108">このサンプルは、次の 3 つのプロジェクトで構成されています。</span><span class="sxs-lookup"><span data-stu-id="7f6b2-108">This sample consists of the following three projects.</span></span>  
  
 <span data-ttu-id="7f6b2-109">CreditCheckService</span><span class="sxs-lookup"><span data-stu-id="7f6b2-109">CreditCheckService</span></span>  
 <span data-ttu-id="7f6b2-110">このサービスは、特定の個人のクレジット スコアまたは取得する項目の値を受け取り、その個人にクレジットを与えるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="7f6b2-110">This service receives the credit score of a particular person or the value of the item to acquire, and then decides whether the credit is given to the person.</span></span>  
  
 <span data-ttu-id="7f6b2-111">RentalApprovalService</span><span class="sxs-lookup"><span data-stu-id="7f6b2-111">RentalApprovalService</span></span>  
 <span data-ttu-id="7f6b2-112">このサービスは、特定のクレジットを必要としている個人から申請を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="7f6b2-112">This service receives an application from a person who is in need of some credit.</span></span> <span data-ttu-id="7f6b2-113">このサービスは `CreditCheckService` と非同期で通信して、クレジットの申請が有効かどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="7f6b2-113">This service communicates asynchronously with the `CreditCheckService` to decide whether the credit application is valid.</span></span>  
  
 <span data-ttu-id="7f6b2-114">Client</span><span class="sxs-lookup"><span data-stu-id="7f6b2-114">Client</span></span>  
 <span data-ttu-id="7f6b2-115">クライアントは `RentalApprovalService` と同期通信を行い、クレジットが承認されているかどうかを調べます。</span><span class="sxs-lookup"><span data-stu-id="7f6b2-115">The client communicates synchronously with the `RentalApprovalService` to know whether the credit is approved.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="7f6b2-116">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="7f6b2-116">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="7f6b2-117">**非同期通信**ソリューションを右クリックし、[**プロパティ ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7f6b2-117">Right-click the **AsynchronousCommunication** solution and select **Properties**.</span></span>  
  
2. <span data-ttu-id="7f6b2-118">[**共通プロパティ]** で [**スタートアップ プロジェクト**] を選択し、[**複数のスタートアップ プロジェクト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7f6b2-118">In **Common Properties**, select **Startup Project**, and select **Multiple Startup Projects**.</span></span>  
  
3. <span data-ttu-id="7f6b2-119">リストの最初の位置に**レンタル承認サービス**を移動し、次に**CreditCheckService**を移動し、次に**クライアントを移動します**。</span><span class="sxs-lookup"><span data-stu-id="7f6b2-119">Move **RentalApprovalService** to the first position in the list, followed by **CreditCheckService**, followed by **Client**.</span></span> <span data-ttu-id="7f6b2-120">3 つのプロジェクトすべてに対して**開始**アクションを設定します。</span><span class="sxs-lookup"><span data-stu-id="7f6b2-120">Set the **Start** action on all three projects.</span></span>  
  
4. <span data-ttu-id="7f6b2-121">**[OK]** をクリックし、F5 キーを押してサンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="7f6b2-121">Click **OK**, and press F5 to run the sample.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7f6b2-122">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="7f6b2-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7f6b2-123">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7f6b2-123">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="7f6b2-124">このディレクトリが存在しない場合は[、.NET Framework 4 の Windows コミュニケーション ファウンデーション (WCF) および Windows ワークフローファウンデーション (WF) サンプル](https://www.microsoft.com/download/details.aspx?id=21459)に移動して、すべての Windows 通信基盤 (WCF) とサンプルを[!INCLUDE[wf1](../../../../includes/wf1-md.md)]ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="7f6b2-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7f6b2-125">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="7f6b2-125">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`
