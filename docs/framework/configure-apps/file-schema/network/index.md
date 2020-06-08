---
title: ネットワーク設定スキーマ
description: .NET Framework がインターネットに接続し、Uri を処理する方法を指定するネットワーク設定のスキーマについて説明します。
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
ms.openlocfilehash: 6a22d7f1608db2e8909d0ead11e9110ec8a8a2c5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504577"
---
# <a name="network-settings-schema"></a><span data-ttu-id="f9587-103">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="f9587-103">Network Settings Schema</span></span>
<span data-ttu-id="f9587-104">ネットワーク設定は、.NET Framework がインターネットに接続する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="f9587-104">Network settings specify how the .NET Framework connects to the Internet.</span></span>

<span data-ttu-id="f9587-105">この \<system.net> 設定は、.NET Framework がネットワークに接続する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="f9587-105">The \<system.net> settings specify how the .NET Framework connects to the network.</span></span> <span data-ttu-id="f9587-106">次の表では、 [ \<system.Net> 要素 (ネットワーク設定)](system-net-element-network-settings.md)の下にある各子構成要素の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="f9587-106">The following table describes the function of each child configuration element under the [\<system.Net> Element (Network Settings)](system-net-element-network-settings.md).</span></span>  
  
|<span data-ttu-id="f9587-107">要素</span><span class="sxs-lookup"><span data-stu-id="f9587-107">Element</span></span>|<span data-ttu-id="f9587-108">説明</span><span class="sxs-lookup"><span data-stu-id="f9587-108">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9587-109">\<authenticationModules>要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="f9587-109">\<authenticationModules> Element (Network Settings)</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="f9587-110">インターネット要求の認証に使用されるモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="f9587-110">Specifies the modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="f9587-111">\<connectionManagement>要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="f9587-111">\<connectionManagement> Element (Network Settings)</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="f9587-112">インターネット ホストへの接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="f9587-112">Specifies the maximum number of connections to Internet hosts.</span></span>|  
|[<span data-ttu-id="f9587-113">\<defaultProxy>要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="f9587-113">\<defaultProxy> Element (Network Settings)</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="f9587-114">インターネットへの HTTP 要求のために使用するプロキシ サーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="f9587-114">Specifies the proxy server used for HTTP requests to the Internet.</span></span>|  
|[<span data-ttu-id="f9587-115">\<mailSettings>要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="f9587-115">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="f9587-116">電子メールの送信オプションの設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f9587-116">Contains settings for mail sending options.</span></span>|  
|[<span data-ttu-id="f9587-117">\<requestCaching>要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="f9587-117">\<requestCaching> Element (Network Settings)</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="f9587-118">ネットワーク要求のキャッシュメカニズムを制御します。</span><span class="sxs-lookup"><span data-stu-id="f9587-118">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="f9587-119">\<webRequestModules>要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="f9587-119">\<webRequestModules> Element (Network Settings)</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="f9587-120">インターネット ホストから情報を要求するために使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="f9587-120">Specifies the modules used to request information from Internet hosts.</span></span>|  
  
<span data-ttu-id="f9587-121">この \<uri> 設定は、.NET Framework が uniform resource identifier (uri) を使用して表された web アドレスを処理する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="f9587-121">The \<uri> settings specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span> <span data-ttu-id="f9587-122">次の表では、 [ \<uri> 要素 (Uri 設定)](uri-element-uri-settings.md)の下にある各子構成要素の関数について説明します。</span><span class="sxs-lookup"><span data-stu-id="f9587-122">The following table describes the function of each child configuration element under the [\<uri> Element (Uri Settings)](uri-element-uri-settings.md).</span></span>  
  
|<span data-ttu-id="f9587-123">要素</span><span class="sxs-lookup"><span data-stu-id="f9587-123">Element</span></span>|<span data-ttu-id="f9587-124">説明</span><span class="sxs-lookup"><span data-stu-id="f9587-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9587-125">\<idn>要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="f9587-125">\<idn> Element (Uri Settings)</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="f9587-126">国際化ドメイン名 (IDN) の解析がドメイン名に適用されるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f9587-126">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="f9587-127">\<iriParsing>要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="f9587-127">\<iriParsing> Element (Uri Settings)</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="f9587-128">International Resource Identifier (IRI) 解析が、<xref:System.Uri> に適用されるかどうか、および IRI の解析規則が適用されるどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f9587-128">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="f9587-129">\<schemeSettings>要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="f9587-129">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="f9587-130"><xref:System.Uri> が特定のスキームに解析される方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="f9587-130">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f9587-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9587-131">See also</span></span>

- [<span data-ttu-id="f9587-132">構成 (インターネット アプリケーションを)</span><span class="sxs-lookup"><span data-stu-id="f9587-132">Configuring Internet Applications</span></span>](../../../network-programming/configuring-internet-applications.md)
- [<span data-ttu-id="f9587-133">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="f9587-133">Configuration File Schema</span></span>](../index.md)
