---
title: Windows ストア アプリのネットワーク分離
ms.date: 03/30/2017
ms.assetid: b064497c-d956-46b8-838d-7a0223c7e200
ms.openlocfilehash: 390a0281f03b08322cc1bee469b601fd5a1547c4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "74802167"
---
# <a name="network-isolation-for-windows-store-apps"></a><span data-ttu-id="e33b3-102">Windows ストア アプリのネットワーク分離</span><span class="sxs-lookup"><span data-stu-id="e33b3-102">Network Isolation for Windows Store Apps</span></span>

<span data-ttu-id="e33b3-103">名前空間 <xref:System.Net>、<xref:System.Net.Http>、<xref:System.Net.Http.Headers> 内のクラスを使用して、Windows ストア アプリまたはデスクトップ アプリを開発できます。</span><span class="sxs-lookup"><span data-stu-id="e33b3-103">Classes in the <xref:System.Net>, <xref:System.Net.Http>, and <xref:System.Net.Http.Headers> namespaces can be used to develop Windows Store  apps  or desktop apps.</span></span> <span data-ttu-id="e33b3-104">Windows ストア アプリで使用する場合、これらの名前空間内のクラスは、Windows 8 で使用されるアプリケーション セキュリティ モデルの一部であるネットワーク分離の影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="e33b3-104">When used in a Windows Store app, classes in these namespaces are affected by network isolation, part of the application security model used by Windows 8.</span></span> <span data-ttu-id="e33b3-105">システムでネットワーク アクセスが許可されるように、Windows ストア アプリのアプリ マニフェストで適切なネットワーク機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e33b3-105">The appropriate network capabilities must be enabled in the app manifest for a Windows Store app for the system to allow network access.</span></span>  
  
## <a name="checklist-for-network-isolation"></a><span data-ttu-id="e33b3-106">ネットワーク分離のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="e33b3-106">Checklist for Network Isolation</span></span>  

<span data-ttu-id="e33b3-107">Windows ストア アプリに対してネットワークの分離が適切に構成されているかどうかを、このチェックリストを使って確認してください。</span><span class="sxs-lookup"><span data-stu-id="e33b3-107">Use this checklist to be sure that network isolation is configured for your Windows Store app.</span></span>  
  
1. <span data-ttu-id="e33b3-108">アプリが必要とするネットワーク アクセス要求の方向を確認します。</span><span class="sxs-lookup"><span data-stu-id="e33b3-108">Determine the direction of network access requests needed by the app.</span></span> <span data-ttu-id="e33b3-109">これには、クライアント側から開始される送信要求と、受信側が送信を要求していない受信要求とがあります。両方の種類のネットワーク要求を組み合わせたものもあります。</span><span class="sxs-lookup"><span data-stu-id="e33b3-109">This can be either outbound client-initiated requests or inbound unsolicited requests or it could be a combination of both of these network request types.</span></span>  
  
2. <span data-ttu-id="e33b3-110">アプリの通信相手となるネットワーク リソースの種類を確認します。</span><span class="sxs-lookup"><span data-stu-id="e33b3-110">Determine the type of network resources that the app will communicate with.</span></span> <span data-ttu-id="e33b3-111">アプリの通信相手は、ホーム ネットワークまたは職場ネットワーク上の信頼済みリソースである場合があります。</span><span class="sxs-lookup"><span data-stu-id="e33b3-111">An app may need to communicate with trusted resources on a Home or Work network.</span></span> <span data-ttu-id="e33b3-112">または、インターネット上のリソースと通信することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="e33b3-112">An app might need to communicate with resources on the Internet.</span></span> <span data-ttu-id="e33b3-113">その両方の種類のネットワーク リソースにアクセスする場合もあります。</span><span class="sxs-lookup"><span data-stu-id="e33b3-113">An app might need access to both types of network resources.</span></span>  
  
3. <span data-ttu-id="e33b3-114">アプリ マニフェストで、必要最小限のネットワーク分離機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="e33b3-114">Configure the minimum-required networking isolation capabilities in the app manifest.</span></span>  
  
4. <span data-ttu-id="e33b3-115">アプリを展開して実行し、トラブルシューティングのためのネットワーク分離ツールを使用してテストします。</span><span class="sxs-lookup"><span data-stu-id="e33b3-115">Deploy and run your app to test it using the network isolation tools provided for troubleshooting.</span></span>  
  
<span data-ttu-id="e33b3-116">ネットワーク機能の構成と、ネットワーク分離のトラブルシューティングに使用する分離ツールの詳細については、Windows 8.x Store 開発者向けドキュメントで、[ネットワーク分離の機能を構成する方法](https://docs.microsoft.com/previous-versions/windows/apps/hh770532(v=win.10))に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e33b3-116">For more detailed information on how to configure network capabilities and isolation tools used for troubleshooting network isolation, see [How to configure network isolation capabilities](https://docs.microsoft.com/previous-versions/windows/apps/hh770532(v=win.10)) in the Windows 8.x Store developer documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e33b3-117">参照</span><span class="sxs-lookup"><span data-stu-id="e33b3-117">See also</span></span>

- <span data-ttu-id="e33b3-118">[Web サービスへの接続](https://docs.microsoft.com/previous-versions/windows/apps/hh761504(v=win.10))</span><span class="sxs-lookup"><span data-stu-id="e33b3-118">[Connecting to a web service](https://docs.microsoft.com/previous-versions/windows/apps/hh761504(v=win.10))</span></span>
- <span data-ttu-id="e33b3-119">[ネットワーク分離のガイドラインとチェックリスト](https://docs.microsoft.com/previous-versions/windows/apps/hh770532(v=win.10))</span><span class="sxs-lookup"><span data-stu-id="e33b3-119">[Guidelines and checklist for network isolation](https://docs.microsoft.com/previous-versions/windows/apps/hh770532(v=win.10))</span></span>
- <span data-ttu-id="e33b3-120">[クイック スタート: HttpClient を使って接続する](https://docs.microsoft.com/previous-versions/windows/apps/hh781239(v=win.10))</span><span class="sxs-lookup"><span data-stu-id="e33b3-120">[Quickstart: Connecting using HttpClient](https://docs.microsoft.com/previous-versions/windows/apps/hh781239(v=win.10))</span></span>
- <span data-ttu-id="e33b3-121">[HttpClient ハンドラーを使う方法](https://docs.microsoft.com/previous-versions/windows/apps/hh781241(v=win.10))</span><span class="sxs-lookup"><span data-stu-id="e33b3-121">[How to use HttpClient handlers](https://docs.microsoft.com/previous-versions/windows/apps/hh781241(v=win.10))</span></span>
- <span data-ttu-id="e33b3-122">[HttpClient の接続をセキュリティで保護する方法](https://docs.microsoft.com/previous-versions/windows/apps/hh781240(v=win.10))</span><span class="sxs-lookup"><span data-stu-id="e33b3-122">[How to secure HttpClient connections](https://docs.microsoft.com/previous-versions/windows/apps/hh781240(v=win.10))</span></span>
- [<span data-ttu-id="e33b3-123">HttpClient のサンプル</span><span class="sxs-lookup"><span data-stu-id="e33b3-123">HttpClient Sample</span></span>](https://code.msdn.microsoft.com/windowsapps/HttpClient-sample-55700664)
