---
title: Hosting2
ms.date: 03/30/2017
ms.assetid: 0820c7e5-0b50-4cde-80e7-74e346513002
ms.openlocfilehash: 72190c23951fbade1a92be559a291190d080532e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597268"
---
# <a name="hosting"></a><span data-ttu-id="89049-102">Hosting</span><span class="sxs-lookup"><span data-stu-id="89049-102">Hosting</span></span>
<span data-ttu-id="89049-103">このセクションのトピックでは、サービス ホスティングについて説明します。</span><span class="sxs-lookup"><span data-stu-id="89049-103">The topics in the section describe service hosting.</span></span> <span data-ttu-id="89049-104">サービスは、インターネットインフォメーションサービス (IIS)、windows プロセスアクティブ化サービス (WAS)、Windows Server AppFabric、Windows サービス、またはマネージアプリケーションによってホストできます。このオプションは、多くの場合、*自己ホスト*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="89049-104">A service can be hosted by Internet Information Services (IIS), Windows Process Activation Service (WAS), Windows Server AppFabric, a Windows service, or by a managed application—this option is often referred to as *self hosting*.</span></span>  
  
 <span data-ttu-id="89049-105">信頼されていないホストからサービスや拡張機能を実行すると、セキュリティが損なわれるので注意してください。</span><span class="sxs-lookup"><span data-stu-id="89049-105">It is important to note that running a service or any extension from an untrusted host compromises security.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="89049-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="89049-106">In This Section</span></span>  
 [<span data-ttu-id="89049-107">インターネット インフォメーション サービスでのホスティング</span><span class="sxs-lookup"><span data-stu-id="89049-107">Hosting in Internet Information Services</span></span>](hosting-in-internet-information-services.md)  
 <span data-ttu-id="89049-108">Windows Communication Foundation (WCF) サービスがインターネットインフォメーションサービスまたは[Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff384253(v=azure.10))でどのようにホストされるかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="89049-108">Describes how a Windows Communication Foundation (WCF) service is hosted in Internet Information Services or [Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff384253(v=azure.10)).</span></span>  
  
 [<span data-ttu-id="89049-109">Windows プロセス アクティブ化サービスでのホスティング</span><span class="sxs-lookup"><span data-stu-id="89049-109">Hosting in Windows Process Activation Service</span></span>](hosting-in-windows-process-activation-service.md)  
 <span data-ttu-id="89049-110">WCF サービスが Windows プロセスアクティブ化サービスによってどのようにホストされるかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="89049-110">Describes how a WCF service is hosted by Windows Process Activation Service.</span></span>  
  
 [<span data-ttu-id="89049-111">Windows サービス アプリケーションのホスト</span><span class="sxs-lookup"><span data-stu-id="89049-111">Hosting in a Windows Service Application</span></span>](hosting-in-a-windows-service-application.md)  
 <span data-ttu-id="89049-112">WCF サービスが Windows サービスによってどのようにホストされるかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="89049-112">Describes how a WCF service is hosted by a Windows service.</span></span>  
  
 [<span data-ttu-id="89049-113">マネージド アプリケーションのホスト</span><span class="sxs-lookup"><span data-stu-id="89049-113">Hosting in a Managed Application</span></span>](hosting-in-a-managed-application.md)  
 <span data-ttu-id="89049-114">マネージアプリケーションでの WCF サービスのホスト方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="89049-114">Describes how a WCF service is hosted in a managed application.</span></span>  
  
 [<span data-ttu-id="89049-115">IIS と WAS における構成ベースのアクティブ化</span><span class="sxs-lookup"><span data-stu-id="89049-115">Configuration-Based Activation in IIS and WAS</span></span>](configuration-based-activation-in-iis-and-was.md)  
 <span data-ttu-id="89049-116">.Svc ファイルを使用せずに、IIS または WAS で WCF サービスをホストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="89049-116">Describes how a WCF service is hosted under IIS or WAS without using a .svc file.</span></span>  
  
 [<span data-ttu-id="89049-117">複数の IIS サイト バインディングのサポート</span><span class="sxs-lookup"><span data-stu-id="89049-117">Supporting Multiple IIS Site Bindings</span></span>](supporting-multiple-iis-site-bindings.md)  
 <span data-ttu-id="89049-118">1 つの Web サイト上で同じ URI スキームを使用してサービスの複数のベース アドレスを指定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="89049-118">Describes how to specify multiple base addresses for a service using the same URI scheme on a single Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89049-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="89049-119">See also</span></span>

- [<span data-ttu-id="89049-120">ホスティング サービス</span><span class="sxs-lookup"><span data-stu-id="89049-120">Hosting Services</span></span>](../hosting-services.md)
- <span data-ttu-id="89049-121">[AppFabric のホスティング機能](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="89049-121">[Windows Server App Fabric Hosting Features](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span></span>
