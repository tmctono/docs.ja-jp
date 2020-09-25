---
title: <system.Net> 要素 (ネットワーク設定)
description: <system.Net> network settings 要素には、.NET Framework が .NET Framework のネットワークオプションに接続する方法を指定する設定が含まれています。
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
ms.openlocfilehash: 80d54df40c6798e146013b4f2d867386ae35169c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201721"
---
# <a name="systemnet-element-network-settings"></a><span data-ttu-id="14c7a-103">\<system.Net> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="14c7a-103">\<system.Net> Element (Network Settings)</span></span>

<span data-ttu-id="14c7a-104">.NET Framework がネットワークに接続する方法を指定するための設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="14c7a-104">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.net>**  
  
## <a name="syntax"></a><span data-ttu-id="14c7a-105">構文</span><span class="sxs-lookup"><span data-stu-id="14c7a-105">Syntax</span></span>  
  
```xml  
<system.net>
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14c7a-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="14c7a-106">Attributes and Elements</span></span>  

 <span data-ttu-id="14c7a-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="14c7a-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14c7a-108">属性</span><span class="sxs-lookup"><span data-stu-id="14c7a-108">Attributes</span></span>  

 <span data-ttu-id="14c7a-109">なし。</span><span class="sxs-lookup"><span data-stu-id="14c7a-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="14c7a-110">子要素</span><span class="sxs-lookup"><span data-stu-id="14c7a-110">Child Elements</span></span>  
  
|<span data-ttu-id="14c7a-111">**要素**</span><span class="sxs-lookup"><span data-stu-id="14c7a-111">**Element**</span></span>|<span data-ttu-id="14c7a-112">**説明**</span><span class="sxs-lookup"><span data-stu-id="14c7a-112">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="14c7a-113">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="14c7a-113">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="14c7a-114">インターネット要求を認証するために使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="14c7a-114">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="14c7a-115">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="14c7a-115">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="14c7a-116">インターネットホストへの接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="14c7a-116">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="14c7a-117">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="14c7a-117">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="14c7a-118">ハイパーテキスト転送プロトコル (HTTP: Hypertext Transfer Protocol) プロキシ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="14c7a-118">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="14c7a-119">mailSettings</span><span class="sxs-lookup"><span data-stu-id="14c7a-119">mailSettings</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="14c7a-120">SMTP (Simple Mail Transport Protocol) メール送信オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="14c7a-120">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="14c7a-121">Requestcaching></span><span class="sxs-lookup"><span data-stu-id="14c7a-121">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="14c7a-122">ネットワーク要求のキャッシュメカニズムを制御します。</span><span class="sxs-lookup"><span data-stu-id="14c7a-122">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="14c7a-123">設定</span><span class="sxs-lookup"><span data-stu-id="14c7a-123">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="14c7a-124">および関連する子名前空間のクラスの基本的なネットワークオプションを構成し <xref:System.Net> ます。</span><span class="sxs-lookup"><span data-stu-id="14c7a-124">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="14c7a-125">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="14c7a-125">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="14c7a-126">インターネットホストから情報を要求するために使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="14c7a-126">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="14c7a-127">親要素</span><span class="sxs-lookup"><span data-stu-id="14c7a-127">Parent Elements</span></span>  
  
|<span data-ttu-id="14c7a-128">**要素**</span><span class="sxs-lookup"><span data-stu-id="14c7a-128">**Element**</span></span>|<span data-ttu-id="14c7a-129">**説明**</span><span class="sxs-lookup"><span data-stu-id="14c7a-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="14c7a-130">configuration</span><span class="sxs-lookup"><span data-stu-id="14c7a-130">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="14c7a-131">すべての名前空間の設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="14c7a-131">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14c7a-132">解説</span><span class="sxs-lookup"><span data-stu-id="14c7a-132">Remarks</span></span>  

 <span data-ttu-id="14c7a-133">[\<system.net>](system-net-element-network-settings.md)要素には、 <xref:System.Net> および関連する子名前空間のクラスの設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="14c7a-133">The [\<system.net>](system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="14c7a-134">この設定では、インターネットホストから情報を受信するための認証モジュール、接続管理、メール設定、プロキシサーバー、およびインターネット要求モジュールを構成します。</span><span class="sxs-lookup"><span data-stu-id="14c7a-134">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14c7a-135">例</span><span class="sxs-lookup"><span data-stu-id="14c7a-135">Example</span></span>  

 <span data-ttu-id="14c7a-136">次の例は、クラスによって使用される一般的な構成を示して <xref:System.Net> います。</span><span class="sxs-lookup"><span data-stu-id="14c7a-136">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="14c7a-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="14c7a-137">See also</span></span>

- [<span data-ttu-id="14c7a-138">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="14c7a-138">Network Settings Schema</span></span>](index.md)
