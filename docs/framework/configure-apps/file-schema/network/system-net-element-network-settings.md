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
ms.openlocfilehash: febea73ddbc45276f97835eb4af7ee0d0d68dda5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674338"
---
# <a name="systemnet-element-network-settings"></a><span data-ttu-id="81d07-102">\<system.Net> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="81d07-102">\<system.Net> Element (Network Settings)</span></span>
<span data-ttu-id="81d07-103">.NET Framework がネットワークに接続する方法を指定するための設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="81d07-103">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
 <span data-ttu-id="81d07-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="81d07-104">\<configuration></span></span>  
<span data-ttu-id="81d07-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="81d07-105">\<system.net></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81d07-106">構文</span><span class="sxs-lookup"><span data-stu-id="81d07-106">Syntax</span></span>  
  
```xml  
<system.net>   
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="81d07-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="81d07-107">Attributes and Elements</span></span>  
 <span data-ttu-id="81d07-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="81d07-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="81d07-109">属性</span><span class="sxs-lookup"><span data-stu-id="81d07-109">Attributes</span></span>  
 <span data-ttu-id="81d07-110">なし。</span><span class="sxs-lookup"><span data-stu-id="81d07-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="81d07-111">子要素</span><span class="sxs-lookup"><span data-stu-id="81d07-111">Child Elements</span></span>  
  
|<span data-ttu-id="81d07-112">**要素**</span><span class="sxs-lookup"><span data-stu-id="81d07-112">**Element**</span></span>|<span data-ttu-id="81d07-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="81d07-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="81d07-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="81d07-114">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="81d07-115">インターネット要求の認証に使用されるモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="81d07-115">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="81d07-116">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="81d07-116">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="81d07-117">インターネット ホストへの接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="81d07-117">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="81d07-118">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="81d07-118">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="81d07-119">ハイパーテキスト転送プロトコル (HTTP: Hypertext Transfer Protocol) プロキシ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="81d07-119">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="81d07-120">mailSettings</span><span class="sxs-lookup"><span data-stu-id="81d07-120">mailSettings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="81d07-121">簡易メール転送プロトコル (SMTP) 電子メールの送信オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="81d07-121">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="81d07-122">requestCaching</span><span class="sxs-lookup"><span data-stu-id="81d07-122">requestCaching</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="81d07-123">ネットワーク要求のキャッシュ メカニズムを制御します。</span><span class="sxs-lookup"><span data-stu-id="81d07-123">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="81d07-124">settings</span><span class="sxs-lookup"><span data-stu-id="81d07-124">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="81d07-125">クラスの基本的なネットワーク オプションを構成、<xref:System.Net>および関連子名前空間。</span><span class="sxs-lookup"><span data-stu-id="81d07-125">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="81d07-126">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="81d07-126">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="81d07-127">使用してインターネット ホストから情報を要求するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="81d07-127">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="81d07-128">親要素</span><span class="sxs-lookup"><span data-stu-id="81d07-128">Parent Elements</span></span>  
  
|<span data-ttu-id="81d07-129">**要素**</span><span class="sxs-lookup"><span data-stu-id="81d07-129">**Element**</span></span>|<span data-ttu-id="81d07-130">**説明**</span><span class="sxs-lookup"><span data-stu-id="81d07-130">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="81d07-131">configuration</span><span class="sxs-lookup"><span data-stu-id="81d07-131">configuration</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="81d07-132">すべての名前空間の設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="81d07-132">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81d07-133">Remarks</span><span class="sxs-lookup"><span data-stu-id="81d07-133">Remarks</span></span>  
 <span data-ttu-id="81d07-134">[ \<System.net >](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)要素には内のクラスの設定が含まれています、<xref:System.Net>および関連子名前空間。</span><span class="sxs-lookup"><span data-stu-id="81d07-134">The [\<system.net>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="81d07-135">設定は、認証モジュール、接続の管理、メールの設定、プロキシ サーバー、およびインターネット ホストから情報を受け取るためのインターネット要求モジュールを構成します。</span><span class="sxs-lookup"><span data-stu-id="81d07-135">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81d07-136">例</span><span class="sxs-lookup"><span data-stu-id="81d07-136">Example</span></span>  
 <span data-ttu-id="81d07-137">次の例で使用される一般的な構成を示しています。<xref:System.Net>クラス。</span><span class="sxs-lookup"><span data-stu-id="81d07-137">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="81d07-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="81d07-138">See also</span></span>

- [<span data-ttu-id="81d07-139">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="81d07-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
