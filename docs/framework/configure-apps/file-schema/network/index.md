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
ms.openlocfilehash: 5e3bd1b1734fc7fba50b72785531a8b001d6d741
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "71698150"
---
# <a name="network-settings-schema"></a><span data-ttu-id="60e7d-102">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="60e7d-102">Network Settings Schema</span></span>
<span data-ttu-id="60e7d-103">ネットワーク設定は、.NET Framework がインターネットに接続する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="60e7d-103">Network settings specify how the .NET Framework connects to the Internet.</span></span>

<span data-ttu-id="60e7d-104">この \<system.net> 設定は、.NET Framework がネットワークに接続する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="60e7d-104">The \<system.net> settings specify how the .NET Framework connects to the network.</span></span> <span data-ttu-id="60e7d-105">次の表では、 [ \<system.Net> 要素 (ネットワーク設定)](system-net-element-network-settings.md)の下にある各子構成要素の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="60e7d-105">The following table describes the function of each child configuration element under the [\<system.Net> Element (Network Settings)](system-net-element-network-settings.md).</span></span>  
  
|<span data-ttu-id="60e7d-106">要素</span><span class="sxs-lookup"><span data-stu-id="60e7d-106">Element</span></span>|<span data-ttu-id="60e7d-107">説明</span><span class="sxs-lookup"><span data-stu-id="60e7d-107">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="60e7d-108">\<authenticationModules>要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="60e7d-108">\<authenticationModules> Element (Network Settings)</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="60e7d-109">インターネット要求の認証に使用されるモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="60e7d-109">Specifies the modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="60e7d-110">\<connectionManagement>要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="60e7d-110">\<connectionManagement> Element (Network Settings)</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="60e7d-111">インターネット ホストへの接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="60e7d-111">Specifies the maximum number of connections to Internet hosts.</span></span>|  
|[<span data-ttu-id="60e7d-112">\<defaultProxy>要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="60e7d-112">\<defaultProxy> Element (Network Settings)</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="60e7d-113">インターネットへの HTTP 要求のために使用するプロキシ サーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="60e7d-113">Specifies the proxy server used for HTTP requests to the Internet.</span></span>|  
|[<span data-ttu-id="60e7d-114">\<mailSettings>要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="60e7d-114">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="60e7d-115">電子メールの送信オプションの設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="60e7d-115">Contains settings for mail sending options.</span></span>|  
|[<span data-ttu-id="60e7d-116">\<requestCaching>要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="60e7d-116">\<requestCaching> Element (Network Settings)</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="60e7d-117">ネットワーク要求のキャッシュメカニズムを制御します。</span><span class="sxs-lookup"><span data-stu-id="60e7d-117">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="60e7d-118">\<webRequestModules>要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="60e7d-118">\<webRequestModules> Element (Network Settings)</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="60e7d-119">インターネット ホストから情報を要求するために使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="60e7d-119">Specifies the modules used to request information from Internet hosts.</span></span>|  
  
<span data-ttu-id="60e7d-120">この \<uri> 設定は、.NET Framework が uniform resource identifier (uri) を使用して表された web アドレスを処理する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="60e7d-120">The \<uri> settings specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span> <span data-ttu-id="60e7d-121">次の表では、 [ \<uri> 要素 (Uri 設定)](uri-element-uri-settings.md)の下にある各子構成要素の関数について説明します。</span><span class="sxs-lookup"><span data-stu-id="60e7d-121">The following table describes the function of each child configuration element under the [\<uri> Element (Uri Settings)](uri-element-uri-settings.md).</span></span>  
  
|<span data-ttu-id="60e7d-122">要素</span><span class="sxs-lookup"><span data-stu-id="60e7d-122">Element</span></span>|<span data-ttu-id="60e7d-123">説明</span><span class="sxs-lookup"><span data-stu-id="60e7d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="60e7d-124">\<idn>要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="60e7d-124">\<idn> Element (Uri Settings)</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="60e7d-125">国際化ドメイン名 (IDN) の解析がドメイン名に適用されるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="60e7d-125">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="60e7d-126">\<iriParsing>要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="60e7d-126">\<iriParsing> Element (Uri Settings)</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="60e7d-127">International Resource Identifier (IRI) 解析が、<xref:System.Uri> に適用されるかどうか、および IRI の解析規則が適用されるどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="60e7d-127">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="60e7d-128">\<schemeSettings>要素 (Uri 設定)</span><span class="sxs-lookup"><span data-stu-id="60e7d-128">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="60e7d-129"><xref:System.Uri> が特定のスキームに解析される方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="60e7d-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="60e7d-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="60e7d-130">See also</span></span>

- [<span data-ttu-id="60e7d-131">構成 (インターネット アプリケーションを)</span><span class="sxs-lookup"><span data-stu-id="60e7d-131">Configuring Internet Applications</span></span>](../../../network-programming/configuring-internet-applications.md)
- [<span data-ttu-id="60e7d-132">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="60e7d-132">Configuration File Schema</span></span>](../index.md)
