---
title: '方法: Net.TCP ポート共有サービスを有効にする'
ms.date: 03/30/2017
helpviewer_keywords:
- port sharing [WCF]
- activation services [WCF]
ms.assetid: c9175af4-c27c-4765-bf45-b8f7528a7282
ms.openlocfilehash: 20db0ef427a5e791bd6b8dcef90bf7911ae0d4a9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59343481"
---
# <a name="how-to-enable-the-nettcp-port-sharing-service"></a><span data-ttu-id="d4b30-102">方法: Net.TCP ポート共有サービスを有効にする</span><span class="sxs-lookup"><span data-stu-id="d4b30-102">How to: Enable the Net.TCP Port Sharing Service</span></span>
<span data-ttu-id="d4b30-103">Windows Communication Foundation (WCF) は、複数のプロセスで TCP ポート共有が簡単に、Net.TCP ポート共有サービスと呼ばれる Windows サービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4b30-103">Windows Communication Foundation (WCF) uses a Windows service called the Net.TCP Port Sharing Service to facilitate the sharing of TCP ports across multiple processes.</span></span> <span data-ttu-id="d4b30-104">このサービスは、WCF の一部としてインストールされますが、サービスのセキュリティ予防措置としてデフォルトが有効でないとようにする必要があります手動で有効にする最初の使用前にします。</span><span class="sxs-lookup"><span data-stu-id="d4b30-104">This service is installed as part of WCF, but the service is not enabled by default as a security precaution and so must be manually enabled prior to first use.</span></span> <span data-ttu-id="d4b30-105">このトピックでは、Microsoft 管理コンソール (MMC) スナップインを使用して、Net TCP ポート共有サービスを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d4b30-105">This topic describes how to configure the Net TCP Port Sharing Service using the Microsoft Management Console (MMC) snap-In.</span></span>  
  
 <span data-ttu-id="d4b30-106">Net.TCP ポート共有サービスを有効にするし、手動で開始するを参照してください。[方法。ポート共有を使用する WCF サービスを構成する](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md)このサービスを使用するサービスを構成する方法についてはします。</span><span class="sxs-lookup"><span data-stu-id="d4b30-106">After you enable the Net.TCP Port Sharing Service and start it manually, see [How to: Configure a WCF Service to Use Port Sharing](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md) for information about how to configure your service to use this service.</span></span>  
  
 <span data-ttu-id="d4b30-107">Net.tcp:// ポート共有を使用するサンプルを参照してください、 [Net.TCP ポート共有のサンプル](../../../../docs/framework/wcf/samples/net-tcp-port-sharing-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="d4b30-107">For a sample that uses net.tcp:// port sharing, see the [Net.TCP Port Sharing Sample](../../../../docs/framework/wcf/samples/net-tcp-port-sharing-sample.md).</span></span>  
  
### <a name="to-enable-the-nettcp-port-sharing-service-using-mmc"></a><span data-ttu-id="d4b30-108">MMC を使用して Net.TCP ポート共有サービスを有効にするには</span><span class="sxs-lookup"><span data-stu-id="d4b30-108">To enable the Net.TCP Port Sharing Service using MMC</span></span>  
  
1. <span data-ttu-id="d4b30-109">スタート メニューからコマンド プロンプト ウィンドウを開き、入力のいずれかのサービス管理コンソールを開く`services.msc`またはを実行を開き、入力`services.msc` ボックスにします。</span><span class="sxs-lookup"><span data-stu-id="d4b30-109">From the Start menu, open the Services Management Console either by opening a Command Prompt window and typing `services.msc` or by opening Run and typing `services.msc` into the Open box.</span></span>  
  
2. <span data-ttu-id="d4b30-110">**名前**サービスの一覧の列を右クリックし、 **Net.Tcp Port Sharing Service**を選択し、**プロパティ** メニューから。</span><span class="sxs-lookup"><span data-stu-id="d4b30-110">In the **Name** column of the list of services, right-click the **Net.Tcp Port Sharing Service**, and select **Properties** from the menu.</span></span>  
  
3. <span data-ttu-id="d4b30-111">サービスの手動起動を有効にする、**プロパティ**ウィンドウを選択、**全般** タブで、し、、**スタートアップの種類**ボックスの 手動とクリックして**適用**します。</span><span class="sxs-lookup"><span data-stu-id="d4b30-111">To enable the manual start-up of the service, in the **Properties** window select the **General** tab, and in the **Startup type** box select Manual, and then click **Apply**.</span></span>  
  
4. <span data-ttu-id="d4b30-112">サービスの状態 領域で、サービスを開始するには、クリックして、**開始**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4b30-112">To start the service,  in the Service status area, click the **Start** button.</span></span> <span data-ttu-id="d4b30-113">これで、サービスの状態には "開始" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d4b30-113">The service status should now display "Started".</span></span>  
  
5. <span data-ttu-id="d4b30-114">サービスの一覧を返すをクリックして、 **OK**、MMC コンソールを終了するとします。</span><span class="sxs-lookup"><span data-stu-id="d4b30-114">To return to the list of services, click the **OK**, and exit the MMC Console.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4b30-115">例</span><span class="sxs-lookup"><span data-stu-id="d4b30-115">Example</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4b30-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4b30-116">See also</span></span>

- [<span data-ttu-id="d4b30-117">Net.TCP ポート共有</span><span class="sxs-lookup"><span data-stu-id="d4b30-117">Net.TCP Port Sharing</span></span>](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)
- [<span data-ttu-id="d4b30-118">Net.TCP ポート共有サービスを構成する</span><span class="sxs-lookup"><span data-stu-id="d4b30-118">Configuring the Net.TCP Port Sharing Service</span></span>](../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
