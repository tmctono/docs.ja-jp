---
title: HttpListener
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP
ms.assetid: 5b89d3fb-3c9a-49e2-af1f-c34c020c68ac
ms.openlocfilehash: d3fecb9fe78ca54f68d3c5a97dae5d5dd9fbb28d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075419"
---
# <a name="httplistener"></a><span data-ttu-id="5b89d-102">HttpListener</span><span class="sxs-lookup"><span data-stu-id="5b89d-102">HttpListener</span></span>
<span data-ttu-id="5b89d-103"><xref:System.Net.HttpListener> クラスは、プログラムによって制御できる HTTP プロトコル リスナーを提供します。</span><span class="sxs-lookup"><span data-stu-id="5b89d-103">The <xref:System.Net.HttpListener> class provides a programmatically controlled HTTP protocol listener.</span></span> <span data-ttu-id="5b89d-104">リスナーは、<xref:System.Net.HttpListener> オブジェクトの有効期間にわたってアクティブで、アプリケーション内で実行されます。</span><span class="sxs-lookup"><span data-stu-id="5b89d-104">The listener is active for the lifetime of the <xref:System.Net.HttpListener> object and runs within your application.</span></span>  
  
## <a name="httpsys"></a><span data-ttu-id="5b89d-105">HTTP.SYS</span><span class="sxs-lookup"><span data-stu-id="5b89d-105">HTTP.SYS</span></span>  
 <span data-ttu-id="5b89d-106"><xref:System.Net.HttpListener> クラスは、Windows のすべての HTTP トラフィックを処理するカーネル モード リスナーである HTTP.sys の上に構築されています。</span><span class="sxs-lookup"><span data-stu-id="5b89d-106">The <xref:System.Net.HttpListener> class is built on top of HTTP.sys, which is the kernel mode listener that handles all HTTP traffic for Windows.</span></span> <span data-ttu-id="5b89d-107">HTTP.sys は、接続管理、帯域幅の調整、および Web サーバーのログ記録を提供します。</span><span class="sxs-lookup"><span data-stu-id="5b89d-107">HTTP.sys provides connection management, bandwidth throttling, and Web server logging.</span></span> <span data-ttu-id="5b89d-108">SSL 証明書の追加には `HttpCfg.exe` ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="5b89d-108">Use the `HttpCfg.exe` tool to add SSL certificates.</span></span> <span data-ttu-id="5b89d-109">詳細については、[サーバー](https://go.microsoft.com/fwlink/?LinkID=178285) ドキュメントで、[HttpCfg.exe](https://go.microsoft.com/fwlink/?LinkID=178284) ツールのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b89d-109">For more information, see the documentation on the [HttpCfg.exe](https://go.microsoft.com/fwlink/?LinkID=178284) tool in the [Server](https://go.microsoft.com/fwlink/?LinkID=178285) documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b89d-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b89d-110">See also</span></span>

- <xref:System.Net.HttpListener>
- <xref:System.Net.HttpWebRequest>
- <xref:System.Net.HttpWebResponse>
- [<span data-ttu-id="5b89d-111">HTTP サーバー</span><span class="sxs-lookup"><span data-stu-id="5b89d-111">HTTP Server</span></span>](https://go.microsoft.com/fwlink/?LinkID=178285)
- [<span data-ttu-id="5b89d-112">インターネット インフォメーションにおけるセキュリティ強化</span><span class="sxs-lookup"><span data-stu-id="5b89d-112">Security Enhancements in Internet Information</span></span>](https://go.microsoft.com/fwlink/?LinkID=178286)
- [<span data-ttu-id="5b89d-113">HttpListener ASPX ホスト アプリケーションのサンプル</span><span class="sxs-lookup"><span data-stu-id="5b89d-113">HttpListener ASPX Host Application Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=179560)
- [<span data-ttu-id="5b89d-114">HttpListener テクノロジのサンプル</span><span class="sxs-lookup"><span data-stu-id="5b89d-114">HttpListener Technology Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=179558)
- [<span data-ttu-id="5b89d-115">ネットワーク プログラミングのサンプル</span><span class="sxs-lookup"><span data-stu-id="5b89d-115">Network Programming Samples</span></span>](../../../docs/framework/network-programming/network-programming-samples.md)
