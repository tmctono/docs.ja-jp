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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155078"
---
# <a name="add-element-for-bypasslist-network-settings"></a><span data-ttu-id="fff96-102">\<バイパスリスト>要素を追加する(ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="fff96-102">\<add> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="fff96-103">IP アドレスまたは DNS 名をプロキシ バイパス リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="fff96-103">Adds an IP address or DNS name to the proxy bypass list.</span></span>  
  
[<span data-ttu-id="fff96-104">**\<構成>**</span><span class="sxs-lookup"><span data-stu-id="fff96-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="fff96-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="fff96-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="fff96-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<既定のプロキシ>**](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="fff96-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>  
<span data-ttu-id="fff96-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<バイパスリスト>**](bypasslist-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="fff96-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)</span></span>  
<span data-ttu-id="fff96-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>を追加する**</span><span class="sxs-lookup"><span data-stu-id="fff96-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fff96-109">構文</span><span class="sxs-lookup"><span data-stu-id="fff96-109">Syntax</span></span>  
  
```xml  
<add
  address="regular expression"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fff96-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="fff96-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fff96-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="fff96-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fff96-112">属性</span><span class="sxs-lookup"><span data-stu-id="fff96-112">Attributes</span></span>  
  
|<span data-ttu-id="fff96-113">**属性**</span><span class="sxs-lookup"><span data-stu-id="fff96-113">**Attribute**</span></span>|<span data-ttu-id="fff96-114">**説明**</span><span class="sxs-lookup"><span data-stu-id="fff96-114">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="fff96-115">**アドレス**</span><span class="sxs-lookup"><span data-stu-id="fff96-115">**address**</span></span>|<span data-ttu-id="fff96-116">IP アドレスまたは DNS 名を記述する正規表現。</span><span class="sxs-lookup"><span data-stu-id="fff96-116">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fff96-117">子要素</span><span class="sxs-lookup"><span data-stu-id="fff96-117">Child Elements</span></span>  
 <span data-ttu-id="fff96-118">[なし] :</span><span class="sxs-lookup"><span data-stu-id="fff96-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fff96-119">親要素</span><span class="sxs-lookup"><span data-stu-id="fff96-119">Parent Elements</span></span>  
  
|<span data-ttu-id="fff96-120">**Element**</span><span class="sxs-lookup"><span data-stu-id="fff96-120">**Element**</span></span>|<span data-ttu-id="fff96-121">**説明**</span><span class="sxs-lookup"><span data-stu-id="fff96-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="fff96-122">bypasslist</span><span class="sxs-lookup"><span data-stu-id="fff96-122">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="fff96-123">プロキシを使用しないアドレスを記述する正規表現のセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="fff96-123">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fff96-124">解説</span><span class="sxs-lookup"><span data-stu-id="fff96-124">Remarks</span></span>  
 <span data-ttu-id="fff96-125">この`add`要素は、IP アドレスまたは DNS サーバー名を記述した正規表現を、プロキシ サーバーをバイパスするアドレスの一覧に挿入します。</span><span class="sxs-lookup"><span data-stu-id="fff96-125">The `add` element inserts regular expressions describing IP addresses or DNS server names to the list of addresses that bypass a proxy server.</span></span>  
  
 <span data-ttu-id="fff96-126">属性の`address`値は、IP アドレスまたはホスト名のセットを記述する正規表現である必要があります。</span><span class="sxs-lookup"><span data-stu-id="fff96-126">The value of the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="fff96-127">この要素の正規表現を指定する場合は注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="fff96-127">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="fff96-128">正規表現 "[a-z]+\\.contoso\\.com" は、contoso.com ドメイン内の任意のホストと一致しますが、contoso.com.cpandl.com ドメイン内の任意のホストとも一致します。</span><span class="sxs-lookup"><span data-stu-id="fff96-128">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="fff96-129">contoso.com ドメイン内のホストのみを照合するには、アンカー ("$") "[a-z]+\\.contoso\\.com$" を使用します。</span><span class="sxs-lookup"><span data-stu-id="fff96-129">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="fff96-130">正規表現の詳細については、を参照してください。[.NET フレームワークの正規表現](../../../../standard/base-types/regular-expressions.md):</span><span class="sxs-lookup"><span data-stu-id="fff96-130">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="fff96-131">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="fff96-131">Configuration Files</span></span>  
 <span data-ttu-id="fff96-132">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="fff96-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fff96-133">例</span><span class="sxs-lookup"><span data-stu-id="fff96-133">Example</span></span>  
 <span data-ttu-id="fff96-134">次の例では、バイパス リストに 2 つのアドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="fff96-134">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="fff96-135">最初の手順では、contoso.com ドメイン内のすべてのサーバーのプロキシをバイパスします。2 番目のサーバーは、IP アドレスが 192.168 で始まるすべてのサーバーのプロキシをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="fff96-135">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fff96-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="fff96-136">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="fff96-137">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="fff96-137">Network Settings Schema</span></span>](index.md)
