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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154557"
---
# <a name="systemnet-element-network-settings"></a><span data-ttu-id="9766d-102">\<system.Net> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="9766d-102">\<system.Net> Element (Network Settings)</span></span>
<span data-ttu-id="9766d-103">.NET Framework がネットワークに接続する方法を指定するための設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9766d-103">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.net>**  
  
## <a name="syntax"></a><span data-ttu-id="9766d-104">構文</span><span class="sxs-lookup"><span data-stu-id="9766d-104">Syntax</span></span>  
  
```xml  
<system.net>
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9766d-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9766d-105">Attributes and Elements</span></span>  
 <span data-ttu-id="9766d-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9766d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9766d-107">属性</span><span class="sxs-lookup"><span data-stu-id="9766d-107">Attributes</span></span>  
 <span data-ttu-id="9766d-108">なし。</span><span class="sxs-lookup"><span data-stu-id="9766d-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9766d-109">子要素</span><span class="sxs-lookup"><span data-stu-id="9766d-109">Child Elements</span></span>  
  
|<span data-ttu-id="9766d-110">**要素**</span><span class="sxs-lookup"><span data-stu-id="9766d-110">**Element**</span></span>|<span data-ttu-id="9766d-111">**説明**</span><span class="sxs-lookup"><span data-stu-id="9766d-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="9766d-112">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="9766d-112">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="9766d-113">インターネット要求を認証するために使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="9766d-113">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="9766d-114">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="9766d-114">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="9766d-115">インターネットホストへの接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="9766d-115">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="9766d-116">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="9766d-116">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="9766d-117">ハイパーテキスト転送プロトコル (HTTP: Hypertext Transfer Protocol) プロキシ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="9766d-117">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="9766d-118">mailSettings</span><span class="sxs-lookup"><span data-stu-id="9766d-118">mailSettings</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="9766d-119">SMTP (Simple Mail Transport Protocol) メール送信オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="9766d-119">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="9766d-120">Requestcaching></span><span class="sxs-lookup"><span data-stu-id="9766d-120">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="9766d-121">ネットワーク要求のキャッシュメカニズムを制御します。</span><span class="sxs-lookup"><span data-stu-id="9766d-121">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="9766d-122">設定</span><span class="sxs-lookup"><span data-stu-id="9766d-122">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="9766d-123">および関連する子名前空間のクラスの基本的なネットワークオプションを構成し <xref:System.Net> ます。</span><span class="sxs-lookup"><span data-stu-id="9766d-123">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="9766d-124">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="9766d-124">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="9766d-125">インターネットホストから情報を要求するために使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="9766d-125">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9766d-126">親要素</span><span class="sxs-lookup"><span data-stu-id="9766d-126">Parent Elements</span></span>  
  
|<span data-ttu-id="9766d-127">**要素**</span><span class="sxs-lookup"><span data-stu-id="9766d-127">**Element**</span></span>|<span data-ttu-id="9766d-128">**説明**</span><span class="sxs-lookup"><span data-stu-id="9766d-128">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="9766d-129">configuration</span><span class="sxs-lookup"><span data-stu-id="9766d-129">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="9766d-130">すべての名前空間の設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9766d-130">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9766d-131">解説</span><span class="sxs-lookup"><span data-stu-id="9766d-131">Remarks</span></span>  
 <span data-ttu-id="9766d-132">[\<system.net>](system-net-element-network-settings.md)要素には、 <xref:System.Net> および関連する子名前空間のクラスの設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9766d-132">The [\<system.net>](system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="9766d-133">この設定では、インターネットホストから情報を受信するための認証モジュール、接続管理、メール設定、プロキシサーバー、およびインターネット要求モジュールを構成します。</span><span class="sxs-lookup"><span data-stu-id="9766d-133">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9766d-134">例</span><span class="sxs-lookup"><span data-stu-id="9766d-134">Example</span></span>  
 <span data-ttu-id="9766d-135">次の例は、クラスによって使用される一般的な構成を示して <xref:System.Net> います。</span><span class="sxs-lookup"><span data-stu-id="9766d-135">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9766d-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="9766d-136">See also</span></span>

- [<span data-ttu-id="9766d-137">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="9766d-137">Network Settings Schema</span></span>](index.md)
