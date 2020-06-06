---
title: bypasslist の <add> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <bypasslist>, add element
- bypasslist, add element
- <add> element, bypasslist
- add element, bypasslist
ms.assetid: a0b86e28-86b4-4497-abe8-d5fd614c7926
ms.openlocfilehash: 652b8738a201aaa98fa2c5c435fee1a6da91673b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155078"
---
# <a name="add-element-for-bypasslist-network-settings"></a><span data-ttu-id="e84dc-102">bypasslist の \<add> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="e84dc-102">\<add> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="e84dc-103">プロキシバイパス一覧に IP アドレスまたは DNS 名を追加します。</span><span class="sxs-lookup"><span data-stu-id="e84dc-103">Adds an IP address or DNS name to the proxy bypass list.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="e84dc-104">構文</span><span class="sxs-lookup"><span data-stu-id="e84dc-104">Syntax</span></span>  
  
```xml  
<add
  address="regular expression"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e84dc-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e84dc-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e84dc-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e84dc-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e84dc-107">属性</span><span class="sxs-lookup"><span data-stu-id="e84dc-107">Attributes</span></span>  
  
|<span data-ttu-id="e84dc-108">**属性**</span><span class="sxs-lookup"><span data-stu-id="e84dc-108">**Attribute**</span></span>|<span data-ttu-id="e84dc-109">**説明**</span><span class="sxs-lookup"><span data-stu-id="e84dc-109">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="e84dc-110">**address**</span><span class="sxs-lookup"><span data-stu-id="e84dc-110">**address**</span></span>|<span data-ttu-id="e84dc-111">IP アドレスまたは DNS 名を記述する正規表現。</span><span class="sxs-lookup"><span data-stu-id="e84dc-111">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e84dc-112">子要素</span><span class="sxs-lookup"><span data-stu-id="e84dc-112">Child Elements</span></span>  
 <span data-ttu-id="e84dc-113">なし。</span><span class="sxs-lookup"><span data-stu-id="e84dc-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e84dc-114">親要素</span><span class="sxs-lookup"><span data-stu-id="e84dc-114">Parent Elements</span></span>  
  
|<span data-ttu-id="e84dc-115">**要素**</span><span class="sxs-lookup"><span data-stu-id="e84dc-115">**Element**</span></span>|<span data-ttu-id="e84dc-116">**説明**</span><span class="sxs-lookup"><span data-stu-id="e84dc-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e84dc-117">bypasslist</span><span class="sxs-lookup"><span data-stu-id="e84dc-117">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="e84dc-118">プロキシを使用しないアドレスを記述する一連の正規表現を提供します。</span><span class="sxs-lookup"><span data-stu-id="e84dc-118">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e84dc-119">解説</span><span class="sxs-lookup"><span data-stu-id="e84dc-119">Remarks</span></span>  
 <span data-ttu-id="e84dc-120">要素は、 `add` IP アドレスまたは DNS サーバー名を記述する正規表現を、プロキシサーバーをバイパスするアドレスの一覧に挿入します。</span><span class="sxs-lookup"><span data-stu-id="e84dc-120">The `add` element inserts regular expressions describing IP addresses or DNS server names to the list of addresses that bypass a proxy server.</span></span>  
  
 <span data-ttu-id="e84dc-121">属性の値は、 `address` 一連の IP アドレスまたはホスト名を表す正規表現である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e84dc-121">The value of the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="e84dc-122">この要素に正規表現を指定する場合は、注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="e84dc-122">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="e84dc-123">正規表現 "[a-z] + \\ . contoso \\ .com" は、contoso.com ドメイン内の任意のホストと一致しますが、contoso.com.cpandl.com ドメイン内の任意のホストとも一致します。</span><span class="sxs-lookup"><span data-stu-id="e84dc-123">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="e84dc-124">Contoso.com ドメイン内のホストのみを一致させるには、アンカー ("$"): "[a-z] + \\ . contoso \\ .com $" を使用します。</span><span class="sxs-lookup"><span data-stu-id="e84dc-124">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="e84dc-125">正規表現の詳細については、「」を参照してください。[正規表現を .NET Framework](../../../../standard/base-types/regular-expressions.md)します。</span><span class="sxs-lookup"><span data-stu-id="e84dc-125">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e84dc-126">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="e84dc-126">Configuration Files</span></span>  
 <span data-ttu-id="e84dc-127">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="e84dc-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e84dc-128">例</span><span class="sxs-lookup"><span data-stu-id="e84dc-128">Example</span></span>  
 <span data-ttu-id="e84dc-129">次の例では、バイパスリストに2つのアドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="e84dc-129">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="e84dc-130">最初のは、contoso.com ドメイン内のすべてのサーバーのプロキシをバイパスします。2つ目は、IP アドレスが192.168 で始まるすべてのサーバーのプロキシをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="e84dc-130">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e84dc-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="e84dc-131">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="e84dc-132">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="e84dc-132">Network Settings Schema</span></span>](index.md)
