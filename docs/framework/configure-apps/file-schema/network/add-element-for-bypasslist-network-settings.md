---
title: <add> Bypasslist (ネットワーク設定) の要素
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
ms.openlocfilehash: 904c8e23f7a09a975a6f3b9322ed6bc4148d9ba4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59098287"
---
# <a name="add-element-for-bypasslist-network-settings"></a><span data-ttu-id="1907d-102">\<追加 > bypasslist (ネットワーク設定) の要素</span><span class="sxs-lookup"><span data-stu-id="1907d-102">\<add> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="1907d-103">プロキシ バイ パスの一覧には、IP アドレスまたは DNS 名を追加します。</span><span class="sxs-lookup"><span data-stu-id="1907d-103">Adds an IP address or DNS name to the proxy bypass list.</span></span>  
  
 <span data-ttu-id="1907d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1907d-104">\<configuration></span></span>  
<span data-ttu-id="1907d-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="1907d-105">\<system.net></span></span>  
<span data-ttu-id="1907d-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="1907d-106">\<defaultProxy></span></span>  
<span data-ttu-id="1907d-107">\<bypasslist></span><span class="sxs-lookup"><span data-stu-id="1907d-107">\<bypasslist></span></span>  
<span data-ttu-id="1907d-108">\<add></span><span class="sxs-lookup"><span data-stu-id="1907d-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1907d-109">構文</span><span class="sxs-lookup"><span data-stu-id="1907d-109">Syntax</span></span>  
  
```xml  
<add   
  address="regular expression"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1907d-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1907d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1907d-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1907d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1907d-112">属性</span><span class="sxs-lookup"><span data-stu-id="1907d-112">Attributes</span></span>  
  
|**<span data-ttu-id="1907d-113">属性</span><span class="sxs-lookup"><span data-stu-id="1907d-113">Attribute</span></span>**|**<span data-ttu-id="1907d-114">説明</span><span class="sxs-lookup"><span data-stu-id="1907d-114">Description</span></span>**|  
|-------------------|---------------------|  
|**<span data-ttu-id="1907d-115">アドレス</span><span class="sxs-lookup"><span data-stu-id="1907d-115">address</span></span>**|<span data-ttu-id="1907d-116">IP アドレスまたは DNS 名を記述する正規表現。</span><span class="sxs-lookup"><span data-stu-id="1907d-116">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1907d-117">子要素</span><span class="sxs-lookup"><span data-stu-id="1907d-117">Child Elements</span></span>  
 <span data-ttu-id="1907d-118">なし。</span><span class="sxs-lookup"><span data-stu-id="1907d-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1907d-119">親要素</span><span class="sxs-lookup"><span data-stu-id="1907d-119">Parent Elements</span></span>  
  
|**<span data-ttu-id="1907d-120">要素</span><span class="sxs-lookup"><span data-stu-id="1907d-120">Element</span></span>**|**<span data-ttu-id="1907d-121">説明</span><span class="sxs-lookup"><span data-stu-id="1907d-121">Description</span></span>**|  
|-----------------|---------------------|  
|[<span data-ttu-id="1907d-122">bypasslist</span><span class="sxs-lookup"><span data-stu-id="1907d-122">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="1907d-123">一連のプロキシを使用しないアドレスを記述する正規表現を提供します。</span><span class="sxs-lookup"><span data-stu-id="1907d-123">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1907d-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="1907d-124">Remarks</span></span>  
 <span data-ttu-id="1907d-125">`add`要素は IP アドレスまたはプロキシ サーバーをバイパスするアドレスのリストに DNS サーバー名を記述する正規表現を挿入します。</span><span class="sxs-lookup"><span data-stu-id="1907d-125">The `add` element inserts regular expressions describing IP addresses or DNS server names to the list of addresses that bypass a proxy server.</span></span>  
  
 <span data-ttu-id="1907d-126">値、`address`属性は、一連の IP アドレスまたはホスト名を記述する正規表現をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1907d-126">The value of the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="1907d-127">この要素の正規表現を指定するときに注意を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1907d-127">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="1907d-128">正規表現"[a ~ z] +\\.contoso\\.com"contoso.com.cpandl.com ドメイン内の任意のホストと一致させる任意のホストが、contoso.com ドメインに一致します。</span><span class="sxs-lookup"><span data-stu-id="1907d-128">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="1907d-129">Contoso.com ドメイン内のホストのみが一致するアンカー (「$」) を使用します:"[a ~ z] +\\.contoso\\.com$"です。</span><span class="sxs-lookup"><span data-stu-id="1907d-129">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="1907d-130">正規表現の詳細についてを参照してください。[.NET framework の正規表現](../../../../../docs/standard/base-types/regular-expressions.md)します。</span><span class="sxs-lookup"><span data-stu-id="1907d-130">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="1907d-131">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="1907d-131">Configuration Files</span></span>  
 <span data-ttu-id="1907d-132">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="1907d-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1907d-133">例</span><span class="sxs-lookup"><span data-stu-id="1907d-133">Example</span></span>  
 <span data-ttu-id="1907d-134">次の例では、2 つのアドレスをバイパス リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="1907d-134">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="1907d-135">1 つ目は、contoso.com ドメイン内のすべてのサーバーでプロキシをバイパスします。2 つ目は、192.168 で IP アドレスが始まるすべてのサーバーでプロキシをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="1907d-135">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1907d-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="1907d-136">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="1907d-137">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="1907d-137">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
