---
title: <ipv6> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/ipv6
- http://schemas.microsoft.com/.NetConfiguration/v2.0#ipv6
helpviewer_keywords:
- <ipv6> element
- ipv6 element
ms.assetid: 10b79aef-327b-4718-a892-e11f55e4d169
ms.openlocfilehash: d89c2e2c6943aca38f8a71092ba3121447a77574
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664094"
---
# <a name="ipv6-element-network-settings"></a><span data-ttu-id="155b7-102">\<ipv6> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="155b7-102">\<ipv6> Element (Network Settings)</span></span>
<span data-ttu-id="155b7-103"><xref:System.Net.Dns> クラスの廃止されたメンバーからインターネット プロトコル バージョン 6 (IPv6) 応答を有効にします。</span><span class="sxs-lookup"><span data-stu-id="155b7-103">Enables Internet Protocol version 6 (IPv6) responses from obsolete members of the <xref:System.Net.Dns> class.</span></span>  
  
 <span data-ttu-id="155b7-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="155b7-104">\<configuration></span></span>  
<span data-ttu-id="155b7-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="155b7-105">\<system.net></span></span>  
<span data-ttu-id="155b7-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="155b7-106">\<settings></span></span>  
<span data-ttu-id="155b7-107">\<ipv6 ></span><span class="sxs-lookup"><span data-stu-id="155b7-107">\<ipv6></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="155b7-108">構文</span><span class="sxs-lookup"><span data-stu-id="155b7-108">Syntax</span></span>  
  
```xml  
<ipv6  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="155b7-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="155b7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="155b7-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="155b7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="155b7-111">属性</span><span class="sxs-lookup"><span data-stu-id="155b7-111">Attributes</span></span>  
  
|<span data-ttu-id="155b7-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="155b7-112">**Attribute**</span></span>|<span data-ttu-id="155b7-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="155b7-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`enabled`|<span data-ttu-id="155b7-114"><xref:System.Net.Dns>クラスのメンバーがインターネットプロトコルバージョン 6 (IPv6) アドレスを返すかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="155b7-114">Specifies whether members of the <xref:System.Net.Dns> class return Internet Protocol version 6 (IPv6) addresses.</span></span> <span data-ttu-id="155b7-115">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="155b7-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="155b7-116">子要素</span><span class="sxs-lookup"><span data-stu-id="155b7-116">Child Elements</span></span>  
 <span data-ttu-id="155b7-117">なし。</span><span class="sxs-lookup"><span data-stu-id="155b7-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="155b7-118">親要素</span><span class="sxs-lookup"><span data-stu-id="155b7-118">Parent Elements</span></span>  
  
|<span data-ttu-id="155b7-119">**要素**</span><span class="sxs-lookup"><span data-stu-id="155b7-119">**Element**</span></span>|<span data-ttu-id="155b7-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="155b7-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="155b7-121">settings</span><span class="sxs-lookup"><span data-stu-id="155b7-121">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="155b7-122"><xref:System.Net> 名前空間の基本的なネットワーク オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="155b7-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="155b7-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="155b7-123">Remarks</span></span>  
 <span data-ttu-id="155b7-124"><xref:System.Net.Dns>この設定により、 <xref:System.Net.Dns.BeginGetHostByName%2A>クラスの廃止されたメンバー ( <xref:System.Net.Dns.GetHostByName%2A>、 <xref:System.Net.Dns.BeginResolve%2A> <xref:System.Net.Dns.EndGetHostByName%2A>、、 <xref:System.Net.Dns.EndResolve%2A> <xref:System.Net.Dns.GetHostByAddress%2A>、、、および<xref:System.Net.Dns.Resolve%2A>) の IPv6 サポートが有効になります。</span><span class="sxs-lookup"><span data-stu-id="155b7-124">This setting enables IPv6 support for the obsolete members of the <xref:System.Net.Dns> class: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, and <xref:System.Net.Dns.Resolve%2A>.</span></span> <span data-ttu-id="155b7-125"><xref:System.Net?displayProperty=nameWithType>名前空間のその他のメンバーについては、オペレーティングシステムで ipv6 が有効になっている場合、ipv6 アドレスが返されることがあります。</span><span class="sxs-lookup"><span data-stu-id="155b7-125">For other members of the <xref:System.Net?displayProperty=nameWithType> namespace, IPv6 addresses may be returned if IPv6 is enabled in the operating system.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="155b7-126">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="155b7-126">Configuration Files</span></span>  
 <span data-ttu-id="155b7-127">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="155b7-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="155b7-128">例</span><span class="sxs-lookup"><span data-stu-id="155b7-128">Example</span></span>  
 <span data-ttu-id="155b7-129">次の例では、 <xref:System.Net.Dns>クラスの IPv6 サポートを有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="155b7-129">The following example shows how to enable IPv6 support for the <xref:System.Net.Dns> class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="155b7-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="155b7-130">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Dns?displayProperty=nameWithType>
- <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType>
- [<span data-ttu-id="155b7-131">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="155b7-131">Network Settings Schema</span></span>](index.md)
