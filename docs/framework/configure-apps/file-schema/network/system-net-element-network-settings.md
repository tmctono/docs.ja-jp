---
title: <system.Net> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
ms.openlocfilehash: 88098f2afaad9728e38c4f9935b45f45826a0ca9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154557"
---
# <a name="systemnet-element-network-settings"></a><span data-ttu-id="ba9a7-102">\<system.Net> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="ba9a7-102">\<system.Net> Element (Network Settings)</span></span>
<span data-ttu-id="ba9a7-103">.NET Framework がネットワークに接続する方法を指定するための設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ba9a7-103">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
[<span data-ttu-id="ba9a7-104">**\<構成>**</span><span class="sxs-lookup"><span data-stu-id="ba9a7-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="ba9a7-105">&nbsp;&nbsp;**\<system.net>**</span><span class="sxs-lookup"><span data-stu-id="ba9a7-105">&nbsp;&nbsp;**\<system.net>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba9a7-106">構文</span><span class="sxs-lookup"><span data-stu-id="ba9a7-106">Syntax</span></span>  
  
```xml  
<system.net>
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba9a7-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ba9a7-107">Attributes and Elements</span></span>  
 <span data-ttu-id="ba9a7-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ba9a7-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba9a7-109">属性</span><span class="sxs-lookup"><span data-stu-id="ba9a7-109">Attributes</span></span>  
 <span data-ttu-id="ba9a7-110">[なし] :</span><span class="sxs-lookup"><span data-stu-id="ba9a7-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ba9a7-111">子要素</span><span class="sxs-lookup"><span data-stu-id="ba9a7-111">Child Elements</span></span>  
  
|<span data-ttu-id="ba9a7-112">**Element**</span><span class="sxs-lookup"><span data-stu-id="ba9a7-112">**Element**</span></span>|<span data-ttu-id="ba9a7-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="ba9a7-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ba9a7-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="ba9a7-114">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="ba9a7-115">インターネット要求の認証に使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="ba9a7-115">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="ba9a7-116">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="ba9a7-116">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="ba9a7-117">インターネット ホストへの接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="ba9a7-117">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="ba9a7-118">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="ba9a7-118">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="ba9a7-119">ハイパーテキスト転送プロトコル (HTTP: Hypertext Transfer Protocol) プロキシ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="ba9a7-119">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="ba9a7-120">メール設定</span><span class="sxs-lookup"><span data-stu-id="ba9a7-120">mailSettings</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="ba9a7-121">簡易メール転送プロトコル (SMTP) メール送信オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="ba9a7-121">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="ba9a7-122">要求キャッシュ</span><span class="sxs-lookup"><span data-stu-id="ba9a7-122">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="ba9a7-123">ネットワーク要求のキャッシュ メカニズムを制御します。</span><span class="sxs-lookup"><span data-stu-id="ba9a7-123">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="ba9a7-124">設定</span><span class="sxs-lookup"><span data-stu-id="ba9a7-124">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="ba9a7-125">関連する子名前空間のクラスの<xref:System.Net>基本的なネットワーク オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="ba9a7-125">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="ba9a7-126">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="ba9a7-126">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="ba9a7-127">インターネット ホストからの情報を要求するために使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="ba9a7-127">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ba9a7-128">親要素</span><span class="sxs-lookup"><span data-stu-id="ba9a7-128">Parent Elements</span></span>  
  
|<span data-ttu-id="ba9a7-129">**Element**</span><span class="sxs-lookup"><span data-stu-id="ba9a7-129">**Element**</span></span>|<span data-ttu-id="ba9a7-130">**説明**</span><span class="sxs-lookup"><span data-stu-id="ba9a7-130">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ba9a7-131">構成</span><span class="sxs-lookup"><span data-stu-id="ba9a7-131">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="ba9a7-132">すべての名前空間の設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ba9a7-132">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba9a7-133">解説</span><span class="sxs-lookup"><span data-stu-id="ba9a7-133">Remarks</span></span>  
 <span data-ttu-id="ba9a7-134">system.net>要素には、<xref:System.Net>および関連する子名前空間のクラスの設定が含まれます。 [ \<](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="ba9a7-134">The [\<system.net>](system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="ba9a7-135">この設定では、インターネット ホストから情報を受信するための認証モジュール、接続管理、メール設定、プロキシ サーバー、およびインターネット要求モジュールを構成します。</span><span class="sxs-lookup"><span data-stu-id="ba9a7-135">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba9a7-136">例</span><span class="sxs-lookup"><span data-stu-id="ba9a7-136">Example</span></span>  
 <span data-ttu-id="ba9a7-137">クラスで使用される一般的な構成の<xref:System.Net>例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ba9a7-137">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient" />  
      <add type="System.Net.NegotiateClient" />  
      <add type="System.Net.KerberosClient" />  
      <add type="System.Net.NtlmClient" />  
      <add type="System.Net.BasicClient" />  
    </authenticationModules>  
    <connectionManagement>  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="https"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="file"  
           type="System.Net.FileWebRequestCreator"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ba9a7-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="ba9a7-138">See also</span></span>

- [<span data-ttu-id="ba9a7-139">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="ba9a7-139">Network Settings Schema</span></span>](index.md)
