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
ms.openlocfilehash: c16949171d082bd02abb0a02db83c2e71c2f17df
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088133"
---
# <a name="ipv6-element-network-settings"></a><span data-ttu-id="2e999-102">\<ipv6> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="2e999-102">\<ipv6> Element (Network Settings)</span></span>
<span data-ttu-id="2e999-103"><xref:System.Net.Dns> クラスの互換性のために残されているメンバーからのインターネットプロトコルバージョン 6 (IPv6) 応答を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2e999-103">Enables Internet Protocol version 6 (IPv6) responses from obsolete members of the <xref:System.Net.Dns> class.</span></span>  

<span data-ttu-id="2e999-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2e999-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2e999-105">&nbsp;&nbsp;[ **\<system.net>** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="2e999-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="2e999-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<settings>** ](settings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="2e999-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>\
<span data-ttu-id="2e999-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<ipv6>**</span><span class="sxs-lookup"><span data-stu-id="2e999-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ipv6>**</span></span>

## <a name="syntax"></a><span data-ttu-id="2e999-108">構文</span><span class="sxs-lookup"><span data-stu-id="2e999-108">Syntax</span></span>  
  
```xml  
<ipv6  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2e999-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2e999-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2e999-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2e999-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2e999-111">属性</span><span class="sxs-lookup"><span data-stu-id="2e999-111">Attributes</span></span>  
  
|<span data-ttu-id="2e999-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="2e999-112">**Attribute**</span></span>|<span data-ttu-id="2e999-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="2e999-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`enabled`|<span data-ttu-id="2e999-114"><xref:System.Net.Dns> クラスのメンバーがインターネットプロトコルバージョン 6 (IPv6) アドレスを返すかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="2e999-114">Specifies whether members of the <xref:System.Net.Dns> class return Internet Protocol version 6 (IPv6) addresses.</span></span> <span data-ttu-id="2e999-115">既定値は `false`です。</span><span class="sxs-lookup"><span data-stu-id="2e999-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2e999-116">子要素</span><span class="sxs-lookup"><span data-stu-id="2e999-116">Child Elements</span></span>  
 <span data-ttu-id="2e999-117">なし。</span><span class="sxs-lookup"><span data-stu-id="2e999-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2e999-118">親要素</span><span class="sxs-lookup"><span data-stu-id="2e999-118">Parent Elements</span></span>  
  
|<span data-ttu-id="2e999-119">**要素**</span><span class="sxs-lookup"><span data-stu-id="2e999-119">**Element**</span></span>|<span data-ttu-id="2e999-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="2e999-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2e999-121">settings</span><span class="sxs-lookup"><span data-stu-id="2e999-121">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="2e999-122"><xref:System.Net> 名前空間の基本的なネットワーク オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="2e999-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e999-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="2e999-123">Remarks</span></span>  
 <span data-ttu-id="2e999-124">この設定により、<xref:System.Net.Dns> クラスの古いメンバー (<xref:System.Net.Dns.BeginGetHostByName%2A>、<xref:System.Net.Dns.BeginResolve%2A>、<xref:System.Net.Dns.EndGetHostByName%2A>、<xref:System.Net.Dns.EndResolve%2A>、<xref:System.Net.Dns.GetHostByAddress%2A>、<xref:System.Net.Dns.GetHostByName%2A>、<xref:System.Net.Dns.Resolve%2A>) の IPv6 サポートが有効になります。</span><span class="sxs-lookup"><span data-stu-id="2e999-124">This setting enables IPv6 support for the obsolete members of the <xref:System.Net.Dns> class: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, and <xref:System.Net.Dns.Resolve%2A>.</span></span> <span data-ttu-id="2e999-125"><xref:System.Net?displayProperty=nameWithType> 名前空間のその他のメンバーについては、オペレーティングシステムで IPv6 が有効になっている場合、IPv6 アドレスが返されることがあります。</span><span class="sxs-lookup"><span data-stu-id="2e999-125">For other members of the <xref:System.Net?displayProperty=nameWithType> namespace, IPv6 addresses may be returned if IPv6 is enabled in the operating system.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="2e999-126">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="2e999-126">Configuration Files</span></span>  
 <span data-ttu-id="2e999-127">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="2e999-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e999-128">例</span><span class="sxs-lookup"><span data-stu-id="2e999-128">Example</span></span>  
 <span data-ttu-id="2e999-129">次の例は、<xref:System.Net.Dns> クラスの IPv6 サポートを有効にする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2e999-129">The following example shows how to enable IPv6 support for the <xref:System.Net.Dns> class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2e999-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e999-130">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Dns?displayProperty=nameWithType>
- <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType>
- [<span data-ttu-id="2e999-131">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="2e999-131">Network Settings Schema</span></span>](index.md)
