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
ms.openlocfilehash: 810e942394c75c192e4423afe4c674ef3a2b9900
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697503"
---
# <a name="systemnet-element-network-settings"></a><span data-ttu-id="05cee-102">\<system.Net> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="05cee-102">\<system.Net> Element (Network Settings)</span></span>
<span data-ttu-id="05cee-103">.NET Framework がネットワークに接続する方法を指定するための設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="05cee-103">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
[<span data-ttu-id="05cee-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="05cee-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="05cee-105">&nbsp; @ no__t-1 **@no__t 3net.tcp >**</span><span class="sxs-lookup"><span data-stu-id="05cee-105">&nbsp;&nbsp;**\<system.net>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05cee-106">構文</span><span class="sxs-lookup"><span data-stu-id="05cee-106">Syntax</span></span>  
  
```xml  
<system.net>   
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05cee-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="05cee-107">Attributes and Elements</span></span>  
 <span data-ttu-id="05cee-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="05cee-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05cee-109">属性</span><span class="sxs-lookup"><span data-stu-id="05cee-109">Attributes</span></span>  
 <span data-ttu-id="05cee-110">[なし] :</span><span class="sxs-lookup"><span data-stu-id="05cee-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="05cee-111">子要素</span><span class="sxs-lookup"><span data-stu-id="05cee-111">Child Elements</span></span>  
  
|<span data-ttu-id="05cee-112">**要素**</span><span class="sxs-lookup"><span data-stu-id="05cee-112">**Element**</span></span>|<span data-ttu-id="05cee-113">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="05cee-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="05cee-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="05cee-114">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="05cee-115">インターネット要求を認証するために使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="05cee-115">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="05cee-116">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="05cee-116">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="05cee-117">インターネットホストへの接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="05cee-117">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="05cee-118">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="05cee-118">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="05cee-119">ハイパーテキスト転送プロトコル (HTTP: Hypertext Transfer Protocol) プロキシ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="05cee-119">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="05cee-120">mailSettings</span><span class="sxs-lookup"><span data-stu-id="05cee-120">mailSettings</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="05cee-121">簡易メール転送プロトコル (SMTP) 電子メールの送信オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="05cee-121">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="05cee-122">requestCaching</span><span class="sxs-lookup"><span data-stu-id="05cee-122">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="05cee-123">ネットワーク要求のキャッシュメカニズムを制御します。</span><span class="sxs-lookup"><span data-stu-id="05cee-123">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="05cee-124">settings</span><span class="sxs-lookup"><span data-stu-id="05cee-124">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="05cee-125">@No__t-0 および関連する子名前空間のクラスの基本的なネットワークオプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="05cee-125">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="05cee-126">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="05cee-126">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="05cee-127">インターネットホストから情報を要求するために使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="05cee-127">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="05cee-128">親要素</span><span class="sxs-lookup"><span data-stu-id="05cee-128">Parent Elements</span></span>  
  
|<span data-ttu-id="05cee-129">**要素**</span><span class="sxs-lookup"><span data-stu-id="05cee-129">**Element**</span></span>|<span data-ttu-id="05cee-130">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="05cee-130">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="05cee-131">configuration</span><span class="sxs-lookup"><span data-stu-id="05cee-131">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="05cee-132">すべての名前空間の設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="05cee-132">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05cee-133">コメント</span><span class="sxs-lookup"><span data-stu-id="05cee-133">Remarks</span></span>  
 <span data-ttu-id="05cee-134">[@No__t 1system. net >](system-net-element-network-settings.md)要素には、<xref:System.Net> および関連する子名前空間のクラスの設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="05cee-134">The [\<system.net>](system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="05cee-135">この設定では、インターネットホストから情報を受信するための認証モジュール、接続管理、メール設定、プロキシサーバー、およびインターネット要求モジュールを構成します。</span><span class="sxs-lookup"><span data-stu-id="05cee-135">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05cee-136">例</span><span class="sxs-lookup"><span data-stu-id="05cee-136">Example</span></span>  
 <span data-ttu-id="05cee-137">次の例は、<xref:System.Net> クラスで使用される一般的な構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="05cee-137">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="05cee-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="05cee-138">See also</span></span>

- [<span data-ttu-id="05cee-139">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="05cee-139">Network Settings Schema</span></span>](index.md)
