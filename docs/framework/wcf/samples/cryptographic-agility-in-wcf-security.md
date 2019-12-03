---
title: WCF セキュリティにおける暗号化の機敏性
ms.date: 03/30/2017
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
ms.openlocfilehash: 2dbacd53876ded76ea212dd5656cd2dded4a6e48
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714922"
---
# <a name="cryptographic-agility-in-wcf-security"></a><span data-ttu-id="51e35-102">WCF セキュリティにおける暗号化の機敏性</span><span class="sxs-lookup"><span data-stu-id="51e35-102">Cryptographic agility in WCF security</span></span>

<span data-ttu-id="51e35-103">このサンプルでは、標準/カスタムアルゴリズムでを指定して、Windows Communication Foundation (WCF) クライアントおよびサービスでの暗号化アジャイル実装を提供する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="51e35-103">This sample shows how to specify in a standard/custom algorithm to provide a cryptographic agile implementation in a Windows Communication Foundation (WCF) client and service.</span></span> <span data-ttu-id="51e35-104">サンプルは、以下のプロジェクトで構成されます。</span><span class="sxs-lookup"><span data-stu-id="51e35-104">The sample is composed of the following projects:</span></span>

<span data-ttu-id="51e35-105">**サービス**</span><span class="sxs-lookup"><span data-stu-id="51e35-105">**Service**</span></span>

<span data-ttu-id="51e35-106">これは、`ICalculator` インターフェイスを実装し、セキュリティで保護されたセッションと信頼できるセッションが無効になっている <xref:System.ServiceModel.WSHttpBinding> を使用してエンドポイントをセキュリティで保護する、自己ホスト型 WCF サービスです。</span><span class="sxs-lookup"><span data-stu-id="51e35-106">This is a self-hosted WCF service that implements the `ICalculator` interface and secures the endpoint using the <xref:System.ServiceModel.WSHttpBinding> with secure session and reliable session disabled.</span></span> <span data-ttu-id="51e35-107">このサービスは、カスタム `SecurityAlgorithmSuite` クラスを定義し、メッセージのセキュリティを確保するために使用される暗号化アルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="51e35-107">The service defines a custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>

<span data-ttu-id="51e35-108">**クライアント**</span><span class="sxs-lookup"><span data-stu-id="51e35-108">**Client**</span></span>

<span data-ttu-id="51e35-109">これは、認証が成功した後にサービスにアクセスする WCF クライアントです。</span><span class="sxs-lookup"><span data-stu-id="51e35-109">This is a WCF client that accesses the service after successful authentication.</span></span> <span data-ttu-id="51e35-110">このクライアントは、`ICalculator` インターフェイスによって公開され、サービスによって実装される操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="51e35-110">It invokes the operations exposed by the `ICalculator` interface and implemented by the service.</span></span> <span data-ttu-id="51e35-111">このクライアントも、同じカスタム `SecurityAlgorithmSuite` クラスを定義し、メッセージのセキュリティを確保するために使用される暗号化アルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="51e35-111">The client also defines the same custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>

## <a name="to-use-this-sample"></a><span data-ttu-id="51e35-112">このサンプルを使用するには</span><span class="sxs-lookup"><span data-stu-id="51e35-112">To use this sample</span></span>

1. <span data-ttu-id="51e35-113">Visual Studio 2012 で、CryptoAgility 性 .sln ソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="51e35-113">Open the CryptoAgility.sln solution in Visual Studio 2012.</span></span>

2. <span data-ttu-id="51e35-114">Ctrl キーと Shift キーを押しながら B キーを押して、ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="51e35-114">Press CTRL+SHIFT+B to build the solution.</span></span>

3. <span data-ttu-id="51e35-115">ファイルエクスプローラーを開き、\WCF\Basic\Security\CryptoAgility\Service\bin ディレクトリに移動して、管理者特権で service .exe ファイルを実行します。そのためには、service .exe を右クリックし、 **[管理者として実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="51e35-115">Open File Explorer and navigate to the \WCF\Basic\Security\CryptoAgility\Service\bin directory and run the service.exe file with administrator privileges by right-clicking service.exe and selecting **Run as administrator**.</span></span>

4. <span data-ttu-id="51e35-116">\WCF\Basic\Security\CryptoAgility\Client\bin ディレクトリに移動して、client.exe ファイルを通常の方法で実行します。</span><span class="sxs-lookup"><span data-stu-id="51e35-116">Navigate to \WCF\Basic\Security\CryptoAgility\Client\bin directory and run the client.exe file normally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="51e35-117">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="51e35-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="51e35-118">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="51e35-118">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="51e35-119">このディレクトリが存在しない場合は、 [Windows Communication Foundation (wcf) および Windows Workflow Foundation (WF) のサンプルの .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459)にアクセスして、すべての WINDOWS COMMUNICATION FOUNDATION (wcf) と [!INCLUDE[wf1](../../../../includes/wf1-md.md)] サンプルをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="51e35-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="51e35-120">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="51e35-120">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`

## <a name="see-also"></a><span data-ttu-id="51e35-121">参照</span><span class="sxs-lookup"><span data-stu-id="51e35-121">See also</span></span>

- [<span data-ttu-id="51e35-122">Windows Communication Foundation のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="51e35-122">Windows Communication Foundation Security</span></span>](../feature-details/security.md)
