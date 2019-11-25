---
title: NetworkInformation
ms.date: 03/30/2017
helpviewer_keywords:
- Network
ms.assetid: 31b44dd3-b903-4a48-8419-40419a3e4038
ms.openlocfilehash: bc0604fd33d06521727c9aa0302ed313d8a2305f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428235"
---
# <a name="networkinformation"></a><span data-ttu-id="a051c-102">NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="a051c-102">NetworkInformation</span></span>
<span data-ttu-id="a051c-103"><xref:System.Net.NetworkInformation> 名前空間を使用すると、ネットワーク イベント、変更、統計、プロパティについての情報を収集できます。</span><span class="sxs-lookup"><span data-stu-id="a051c-103">The <xref:System.Net.NetworkInformation> namespace enables you to gather information about network events, changes, statistics, and properties.</span></span> <span data-ttu-id="a051c-104">また、<xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType> クラスを使用して、リモート ホストに到達可能かどうかを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="a051c-104">You can also determine whether a remote host is reachable by using the <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType> class.</span></span>  
  
## <a name="network-availability-and-events"></a><span data-ttu-id="a051c-105">ネットワークの可用性とイベント</span><span class="sxs-lookup"><span data-stu-id="a051c-105">Network Availability and Events</span></span>  
 <span data-ttu-id="a051c-106"><xref:System.Net.NetworkInformation.NetworkChange?displayProperty=nameWithType> クラスを使用して、ネットワークのアドレスまたは可用性が変更されたかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="a051c-106">The <xref:System.Net.NetworkInformation.NetworkChange?displayProperty=nameWithType> class enables you to determine whether the network address or availability has changed.</span></span> <span data-ttu-id="a051c-107">このクラスを使用するには、変更を処理するイベント ハンドラーを作成し、それを <xref:System.Net.NetworkInformation.NetworkAddressChangedEventHandler> または <xref:System.Net.NetworkInformation.NetworkAvailabilityChangedEventHandler> に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="a051c-107">To use this class, create an event handler to process the change, and associate it with a <xref:System.Net.NetworkInformation.NetworkAddressChangedEventHandler> or a <xref:System.Net.NetworkInformation.NetworkAvailabilityChangedEventHandler>.</span></span> <span data-ttu-id="a051c-108">詳細については、[ネットワークの可用性とアドレスの変更を検出する](how-to-detect-network-availability-and-address-changes.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a051c-108">For more information, see [How to: Detect Network Availability and Address Changes](how-to-detect-network-availability-and-address-changes.md).</span></span>  
  
## <a name="network-statistics-and-properties"></a><span data-ttu-id="a051c-109">ネットワークの統計情報とプロパティ</span><span class="sxs-lookup"><span data-stu-id="a051c-109">Network Statistics and Properties</span></span>  
 <span data-ttu-id="a051c-110">インターフェイスまたはプロトコルを使用して、ネットワークの統計情報とプロパティを収集できます。</span><span class="sxs-lookup"><span data-stu-id="a051c-110">You can gather network statistics and properties on an interface or protocol basis.</span></span> <span data-ttu-id="a051c-111"><xref:System.Net.NetworkInformation.NetworkInterface>、<xref:System.Net.NetworkInformation.NetworkInterfaceType>、<xref:System.Net.NetworkInformation.PhysicalAddress> の各クラスは、特定のネットワーク インターフェイスについての情報を提供します。一方、<xref:System.Net.NetworkInformation.IPInterfaceProperties>、<xref:System.Net.NetworkInformation.IPGlobalProperties>、<xref:System.Net.NetworkInformation.IPGlobalStatistics>、<xref:System.Net.NetworkInformation.TcpStatistics>、<xref:System.Net.NetworkInformation.UdpStatistics> の各クラスは、レイヤー 3 とレイヤー 4 のパケットについての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="a051c-111">The <xref:System.Net.NetworkInformation.NetworkInterface>, <xref:System.Net.NetworkInformation.NetworkInterfaceType>, and <xref:System.Net.NetworkInformation.PhysicalAddress> classes give information about a particular network interface, while the <xref:System.Net.NetworkInformation.IPInterfaceProperties>, <xref:System.Net.NetworkInformation.IPGlobalProperties>, <xref:System.Net.NetworkInformation.IPGlobalStatistics>, <xref:System.Net.NetworkInformation.TcpStatistics>, and <xref:System.Net.NetworkInformation.UdpStatistics> classes give information about layer 3 and layer 4 packets.</span></span> <span data-ttu-id="a051c-112">詳細については、[インターフェイス情報とプロトコル情報を取得する](how-to-get-interface-and-protocol-information.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a051c-112">For more information, see [How to: Get Interface and Protocol Information](how-to-get-interface-and-protocol-information.md).</span></span>  
  
## <a name="determine-if-a-remote-host-is-reachable"></a><span data-ttu-id="a051c-113">リモート ホストに到達可能かどうかの確認</span><span class="sxs-lookup"><span data-stu-id="a051c-113">Determine if a Remote Host is Reachable</span></span>  
 <span data-ttu-id="a051c-114"><xref:System.Net.NetworkInformation.Ping> クラスを使用して、リモート ホストがネットワークで稼働しているかどうか、また到達可能かどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="a051c-114">You can use the <xref:System.Net.NetworkInformation.Ping> class to determine whether a Remote Host is up, on the network, and reachable.</span></span> <span data-ttu-id="a051c-115">詳細については、[ホストに対して ping を実行](how-to-ping-a-host.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a051c-115">For more information, see [How to: Ping a Host](how-to-ping-a-host.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a051c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="a051c-116">See also</span></span>

- [<span data-ttu-id="a051c-117">ネットワーク プログラミングのサンプル</span><span class="sxs-lookup"><span data-stu-id="a051c-117">Network Programming Samples</span></span>](network-programming-samples.md)

<!-- to-do: review sample links
- [Network Information Technology Sample](https://archive.msdn.microsoft.com/nclsamples/Wiki/View.aspx?title=Network%20Information)
- [NetStat Tool Technology Sample](https://archive.msdn.microsoft.com/nclsamples/Wiki/View.aspx?title=NetStat%20Tool)
- [Ping Client Technology Sample](https://archive.msdn.microsoft.com/nclsamples/Wiki/View.aspx?title=Ping%20Client)
-->
