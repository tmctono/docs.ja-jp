---
title: ワークフローの探索のサンプル
ms.date: 03/30/2017
ms.assetid: 82cc43f1-3c8f-4771-ac19-a75ac936e2c3
ms.openlocfilehash: b3a2d88028f3854746d4e1d2fad80aae4f6be7be
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143487"
---
# <a name="workflow-discovery-sample"></a><span data-ttu-id="3096f-102">ワークフローの探索のサンプル</span><span class="sxs-lookup"><span data-stu-id="3096f-102">Workflow Discovery Sample</span></span>
<span data-ttu-id="3096f-103">このサンプルでは、ワークフロー サービスを探索可能にする方法と、特定のサービスを検索するカスタム コード アクティビティを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3096f-103">This sample demonstrates how to make a workflow service discoverable and how to author a custom code activity that searches for a particular service.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="3096f-104">対象</span><span class="sxs-lookup"><span data-stu-id="3096f-104">Demonstrates</span></span>  
 <span data-ttu-id="3096f-105">探索検索アクティビティとワークフローの使用方法</span><span class="sxs-lookup"><span data-stu-id="3096f-105">Discovery Find Activity and Workflow Usage</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="3096f-106">ディスカッション</span><span class="sxs-lookup"><span data-stu-id="3096f-106">Discussion</span></span>  
 <span data-ttu-id="3096f-107">サンプルの最初の部分では、構成を使用してワークフロー サービスを探索可能にしています。</span><span class="sxs-lookup"><span data-stu-id="3096f-107">In the first part of the sample, a workflow service is made discoverable using configuration.</span></span> <span data-ttu-id="3096f-108">また、カスタム メタデータ (スコープなど) と共に構成を使用すると、サービスを適切に適用することができます。</span><span class="sxs-lookup"><span data-stu-id="3096f-108">Configuration can also be used to apply the service appropriately with custom metadata (such as scopes).</span></span> <span data-ttu-id="3096f-109">このサンプルは、クライアントでカスタム コード アクティビティを使用します。カスタム コード アクティビティは、探索を使用して、特定のコントラクトに一致するサービスを検索します。</span><span class="sxs-lookup"><span data-stu-id="3096f-109">On the client, the sample uses a custom code activity, which uses Discovery to search for a service matching a particular contract.</span></span> <span data-ttu-id="3096f-110">コード アクティビティは URI を出力します。この URI は、後で送信アクティビティで使用されます。</span><span class="sxs-lookup"><span data-stu-id="3096f-110">The code activity outputs a URI, which is later used by a send activity.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3096f-111">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="3096f-111">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="3096f-112">このサンプルでは、実行する適切な URL ACL が必要な HTTP エンドポイントを使用します (詳細については[、HTTP と HTTPS の構成を](../feature-details/configuring-http-and-https.md)参照してください)。</span><span class="sxs-lookup"><span data-stu-id="3096f-112">This sample uses HTTP endpoints, which must have proper URL ACLs to run (see [Configuring HTTP and HTTPS](../feature-details/configuring-http-and-https.md) for details).</span></span> <span data-ttu-id="3096f-113">権限のレベルが高いコマンド プロンプトで次のコマンドを実行すると、適切な ACL が追加されます。</span><span class="sxs-lookup"><span data-stu-id="3096f-113">Executing the following command at an elevated command prompt should add the appropriate ACLs.</span></span> <span data-ttu-id="3096f-114">シェルで変数の形式がわからない場合は、次の引数をドメインとユーザー名に置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="3096f-114">If your shell does not understand the variable format, substitute your Domain and Username for the following arguments.</span></span>  
  
     <span data-ttu-id="3096f-115">**ネットッシュ http 追加 urlacl url=http://+:8000/ \\ユーザー =%ドメイン% %ユーザー名%**</span><span class="sxs-lookup"><span data-stu-id="3096f-115">**netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\\%UserName%**</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3096f-116">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="3096f-116">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3096f-117">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3096f-117">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="3096f-118">このディレクトリが存在しない場合は[、.NET Framework 4 の Windows コミュニケーション ファウンデーション (WCF) および Windows ワークフローファウンデーション (WF) サンプル](https://www.microsoft.com/download/details.aspx?id=21459)に移動して、すべての Windows 通信基盤 (WCF) とサンプルを[!INCLUDE[wf1](../../../../includes/wf1-md.md)]ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="3096f-118">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3096f-119">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="3096f-119">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\WorkflowDiscovery`
