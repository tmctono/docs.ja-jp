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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088133"
---
# <a name="ipv6-element-network-settings"></a><span data-ttu-id="8fe60-102">\<ipv6> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="8fe60-102">\<ipv6> Element (Network Settings)</span></span>
<span data-ttu-id="8fe60-103">クラスの互換性のために残されているメンバーからのインターネットプロトコルバージョン 6 (IPv6) 応答を有効に <xref:System.Net.Dns> します。</span><span class="sxs-lookup"><span data-stu-id="8fe60-103">Enables Internet Protocol version 6 (IPv6) responses from obsolete members of the <xref:System.Net.Dns> class.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ipv6>**

## <a name="syntax"></a><span data-ttu-id="8fe60-104">構文</span><span class="sxs-lookup"><span data-stu-id="8fe60-104">Syntax</span></span>  
  
```xml  
<ipv6  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8fe60-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8fe60-105">Attributes and Elements</span></span>  
 <span data-ttu-id="8fe60-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8fe60-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8fe60-107">属性</span><span class="sxs-lookup"><span data-stu-id="8fe60-107">Attributes</span></span>  
  
|<span data-ttu-id="8fe60-108">**属性**</span><span class="sxs-lookup"><span data-stu-id="8fe60-108">**Attribute**</span></span>|<span data-ttu-id="8fe60-109">**説明**</span><span class="sxs-lookup"><span data-stu-id="8fe60-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`enabled`|<span data-ttu-id="8fe60-110">クラスのメンバーが <xref:System.Net.Dns> インターネットプロトコルバージョン 6 (IPv6) アドレスを返すかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="8fe60-110">Specifies whether members of the <xref:System.Net.Dns> class return Internet Protocol version 6 (IPv6) addresses.</span></span> <span data-ttu-id="8fe60-111">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="8fe60-111">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8fe60-112">子要素</span><span class="sxs-lookup"><span data-stu-id="8fe60-112">Child Elements</span></span>  
 <span data-ttu-id="8fe60-113">なし。</span><span class="sxs-lookup"><span data-stu-id="8fe60-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8fe60-114">親要素</span><span class="sxs-lookup"><span data-stu-id="8fe60-114">Parent Elements</span></span>  
  
|<span data-ttu-id="8fe60-115">**要素**</span><span class="sxs-lookup"><span data-stu-id="8fe60-115">**Element**</span></span>|<span data-ttu-id="8fe60-116">**説明**</span><span class="sxs-lookup"><span data-stu-id="8fe60-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8fe60-117">設定</span><span class="sxs-lookup"><span data-stu-id="8fe60-117">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="8fe60-118"><xref:System.Net> 名前空間の基本的なネットワーク オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="8fe60-118">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8fe60-119">解説</span><span class="sxs-lookup"><span data-stu-id="8fe60-119">Remarks</span></span>  
 <span data-ttu-id="8fe60-120">この設定により、クラスの廃止されたメンバー (、、、、、 <xref:System.Net.Dns> <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.Net.Dns.BeginResolve%2A> <xref:System.Net.Dns.EndGetHostByName%2A> <xref:System.Net.Dns.EndResolve%2A> <xref:System.Net.Dns.GetHostByAddress%2A> <xref:System.Net.Dns.GetHostByName%2A> 、および <xref:System.Net.Dns.Resolve%2A> ) の IPv6 サポートが有効になります。</span><span class="sxs-lookup"><span data-stu-id="8fe60-120">This setting enables IPv6 support for the obsolete members of the <xref:System.Net.Dns> class: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, and <xref:System.Net.Dns.Resolve%2A>.</span></span> <span data-ttu-id="8fe60-121">名前空間のその他のメンバーについては <xref:System.Net?displayProperty=nameWithType> 、オペレーティングシステムで ipv6 が有効になっている場合、ipv6 アドレスが返されることがあります。</span><span class="sxs-lookup"><span data-stu-id="8fe60-121">For other members of the <xref:System.Net?displayProperty=nameWithType> namespace, IPv6 addresses may be returned if IPv6 is enabled in the operating system.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="8fe60-122">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="8fe60-122">Configuration Files</span></span>  
 <span data-ttu-id="8fe60-123">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8fe60-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fe60-124">例</span><span class="sxs-lookup"><span data-stu-id="8fe60-124">Example</span></span>  
 <span data-ttu-id="8fe60-125">次の例では、クラスの IPv6 サポートを有効にする方法を示し <xref:System.Net.Dns> ます。</span><span class="sxs-lookup"><span data-stu-id="8fe60-125">The following example shows how to enable IPv6 support for the <xref:System.Net.Dns> class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8fe60-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="8fe60-126">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Dns?displayProperty=nameWithType>
- <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType>
- [<span data-ttu-id="8fe60-127">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="8fe60-127">Network Settings Schema</span></span>](index.md)
