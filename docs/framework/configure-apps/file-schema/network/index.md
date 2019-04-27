---
title: ネットワーク設定スキーマ
ms.date: 03/30/2017
helpviewer_keywords:
- elements [.NET Framework], network configuration elements
- sending data, network configuration elements
- receiving data, network configuration elements
- configuration settings [.NET Framework], networks
- Internet, network configuration elements
- network configuration elements
- network settings
- connections [.NET Framework], network configuration elements
- network resources, network configuration elements
ms.assetid: f1de5a0f-76c5-4833-819f-5222b8146340
ms.openlocfilehash: 71d945e6046a8648a812de939f197429bc695808
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674533"
---
# <a name="network-settings-schema"></a><span data-ttu-id="b8515-102">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="b8515-102">Network Settings Schema</span></span>
<span data-ttu-id="b8515-103">ネットワーク設定は、.NET Framework がインターネットに接続する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="b8515-103">Network settings specify how the .NET Framework connects to the Internet.</span></span> <span data-ttu-id="b8515-104">次の表では、[\<system.Net > 要素 (ネットワーク設定)](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) の下にある各子構成要素の関数について説明します。</span><span class="sxs-lookup"><span data-stu-id="b8515-104">The following table describes the function of each child configuration element under the [\<system.Net> Element (Network Settings)](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md).</span></span>  
  
|<span data-ttu-id="b8515-105">要素</span><span class="sxs-lookup"><span data-stu-id="b8515-105">Element</span></span>|<span data-ttu-id="b8515-106">説明</span><span class="sxs-lookup"><span data-stu-id="b8515-106">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b8515-107">\<authenticationModules> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="b8515-107">\<authenticationModules> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="b8515-108">インターネット要求の認証に使用されるモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="b8515-108">Specifies the modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="b8515-109">\<connectionManagement> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="b8515-109">\<connectionManagement> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="b8515-110">インターネット ホストへの接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="b8515-110">Specifies the maximum number of connections to Internet hosts.</span></span>|  
|[<span data-ttu-id="b8515-111">\<defaultProxy> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="b8515-111">\<defaultProxy> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="b8515-112">インターネットへの HTTP 要求のために使用するプロキシ サーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="b8515-112">Specifies the proxy server used for HTTP requests to the Internet.</span></span>|  
|[<span data-ttu-id="b8515-113">\<mailSettings> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="b8515-113">\<mailSettings> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="b8515-114">電子メールの送信オプションの設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b8515-114">Contains settings for mail sending options.</span></span>|  
|[<span data-ttu-id="b8515-115">\<requestCaching> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="b8515-115">\<requestCaching> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="b8515-116">ネットワーク要求のキャッシュ メカニズムを制御します。</span><span class="sxs-lookup"><span data-stu-id="b8515-116">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="b8515-117">\<webRequestModules> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="b8515-117">\<webRequestModules> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="b8515-118">インターネット ホストから情報を要求するために使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="b8515-118">Specifies the modules used to request information from Internet hosts.</span></span>|  
  
 <span data-ttu-id="b8515-119">Uri の設定は、.NET Framework での Uniform Resource Identifier (URI) を使用して表現された Web アドレスの処理方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="b8515-119">Uri settings specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span> <span data-ttu-id="b8515-120">次の表では、[\<Uri> 要素 (Uri 設定)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md) の下にある各子構成要素の関数について説明します。</span><span class="sxs-lookup"><span data-stu-id="b8515-120">The following table describes the function of each child configuration element under the [\<Uri> Element (Uri Settings)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md).</span></span>  
  
|<span data-ttu-id="b8515-121">要素</span><span class="sxs-lookup"><span data-stu-id="b8515-121">Element</span></span>|<span data-ttu-id="b8515-122">説明</span><span class="sxs-lookup"><span data-stu-id="b8515-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b8515-123">\<idn> 要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="b8515-123">\<idn> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|<span data-ttu-id="b8515-124">国際化ドメイン名 (IDN) の解析がドメイン名に適用されるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b8515-124">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="b8515-125">\<iriParsing> 要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="b8515-125">\<iriParsing> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|<span data-ttu-id="b8515-126">International Resource Identifier (IRI) 解析が、<xref:System.Uri> に適用されるかどうか、および IRI の解析規則が適用されるどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b8515-126">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="b8515-127">\<schemeSettings> 要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="b8515-127">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="b8515-128"><xref:System.Uri> が特定のスキームに解析される方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="b8515-128">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b8515-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="b8515-129">See also</span></span>

- [<span data-ttu-id="b8515-130">インターネット アプリケーションの構成</span><span class="sxs-lookup"><span data-stu-id="b8515-130">Configuring Internet Applications</span></span>](../../../../../docs/framework/network-programming/configuring-internet-applications.md)
- [<span data-ttu-id="b8515-131">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="b8515-131">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
