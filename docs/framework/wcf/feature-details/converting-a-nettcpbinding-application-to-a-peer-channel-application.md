---
title: NetTcpBinding アプリケーションからピア チャネル アプリケーションへの変換
ms.date: 03/30/2017
ms.assetid: d4137292-a923-4b8f-8594-42276f2d3ce2
ms.openlocfilehash: b89afbe59b73288ba357fa55ec5d55c1fb18352b
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65582787"
---
# <a name="converting-a-nettcpbinding-application-to-a-peer-channel-application"></a><span data-ttu-id="dcee3-102">NetTcpBinding アプリケーションからピア チャネル アプリケーションへの変換</span><span class="sxs-lookup"><span data-stu-id="dcee3-102">Converting a NetTcpBinding Application to a Peer Channel Application</span></span>
<span data-ttu-id="dcee3-103">[!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] を使用するクライアント間の接続は、その接続パラメーターを記述するバインディングを使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="dcee3-103">You can create connections between clients using the [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] by using bindings that describe the parameters of the connection.</span></span> <span data-ttu-id="dcee3-104">ピア ツー ピア接続を使用する .NET Framework アプリケーションへの変換には、クライアント接続を行うときに、このテクノロジをサポートするバインディングが必要です。</span><span class="sxs-lookup"><span data-stu-id="dcee3-104">Converting a .NET Framework application to use peer-to-peer connections requires a binding that supports this technology when making client connections.</span></span> <span data-ttu-id="dcee3-105">ピア チャネルには、<xref:System.ServiceModel.NetPeerTcpBinding> と呼ばれるバインディングが用意されています。このバインディングは、<xref:System.ServiceModel.NetTcpBinding> と同じような方法で使用できます。</span><span class="sxs-lookup"><span data-stu-id="dcee3-105">Peer Channel provides a binding called <xref:System.ServiceModel.NetPeerTcpBinding>, which you can use in a similar way to the <xref:System.ServiceModel.NetTcpBinding>.</span></span> <span data-ttu-id="dcee3-106">主な違いは、リゾルバー サービスの仕様とセキュリティ設定の定義です。</span><span class="sxs-lookup"><span data-stu-id="dcee3-106">Key differences include specifying a resolver service and defining security settings.</span></span>  
  
 <span data-ttu-id="dcee3-107">アプリケーションでリゾルバーとセキュリティの既定の設定を使用する場合、通常のクライアント/サーバー ベースのアプリケーションは、アプリケーションの構成ファイルでバインディング名を "NetTcpBinding" から "NetPeerTcpBinding" に変更するだけで、ピア チャネルを使用するように変換できます。アプリケーションのコード ベースを変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dcee3-107">If an application is using the default resolver and security settings, converting a normal client/server-based application to use Peer Channel entails changing the name of the binding from "NetTcpBinding" to "NetPeerTcpBinding" in the application’s configuration file—you do not have to change the application code base.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcee3-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="dcee3-108">See also</span></span>

- [<span data-ttu-id="dcee3-109">ピア チャネル アプリケーションの構築</span><span class="sxs-lookup"><span data-stu-id="dcee3-109">Building a Peer Channel Application</span></span>](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)
- [<span data-ttu-id="dcee3-110">システム標準のバインディング</span><span class="sxs-lookup"><span data-stu-id="dcee3-110">System-Provided Bindings</span></span>](../../../../docs/framework/wcf/system-provided-bindings.md)
