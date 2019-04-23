---
title: <bypasslist> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
ms.openlocfilehash: d3d986dae478f49504dae21b9f39574b7887b4d2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59202223"
---
# <a name="bypasslist-element-network-settings"></a><span data-ttu-id="314ea-102">\<bypasslist > 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="314ea-102">\<bypasslist> Element (Network Settings)</span></span>
<span data-ttu-id="314ea-103">一連のプロキシを使用しないアドレスを記述する正規表現を提供します。</span><span class="sxs-lookup"><span data-stu-id="314ea-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  
  
 <span data-ttu-id="314ea-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="314ea-104">\<configuration></span></span>  
<span data-ttu-id="314ea-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="314ea-105">\<system.net></span></span>  
<span data-ttu-id="314ea-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="314ea-106">\<defaultProxy></span></span>  
<span data-ttu-id="314ea-107">\<bypasslist></span><span class="sxs-lookup"><span data-stu-id="314ea-107">\<bypasslist></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="314ea-108">構文</span><span class="sxs-lookup"><span data-stu-id="314ea-108">Syntax</span></span>  
  
```xml  
<bypasslist>   
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="314ea-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="314ea-109">Attributes and Elements</span></span>  
 <span data-ttu-id="314ea-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="314ea-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="314ea-111">属性</span><span class="sxs-lookup"><span data-stu-id="314ea-111">Attributes</span></span>  
 <span data-ttu-id="314ea-112">なし。</span><span class="sxs-lookup"><span data-stu-id="314ea-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="314ea-113">子要素</span><span class="sxs-lookup"><span data-stu-id="314ea-113">Child Elements</span></span>  
  
|<span data-ttu-id="314ea-114">**要素**</span><span class="sxs-lookup"><span data-stu-id="314ea-114">**Element**</span></span>|<span data-ttu-id="314ea-115">**説明**</span><span class="sxs-lookup"><span data-stu-id="314ea-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="314ea-116">add</span><span class="sxs-lookup"><span data-stu-id="314ea-116">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="314ea-117">プロキシ バイ パスの一覧には、IP アドレスまたは DNS 名を追加します。</span><span class="sxs-lookup"><span data-stu-id="314ea-117">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="314ea-118">clear</span><span class="sxs-lookup"><span data-stu-id="314ea-118">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="314ea-119">バイパス リストをクリアします。</span><span class="sxs-lookup"><span data-stu-id="314ea-119">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="314ea-120">remove</span><span class="sxs-lookup"><span data-stu-id="314ea-120">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="314ea-121">プロキシ バイ パスの一覧から IP アドレスまたは DNS 名を削除します。</span><span class="sxs-lookup"><span data-stu-id="314ea-121">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="314ea-122">親要素</span><span class="sxs-lookup"><span data-stu-id="314ea-122">Parent Elements</span></span>  
  
|<span data-ttu-id="314ea-123">**要素**</span><span class="sxs-lookup"><span data-stu-id="314ea-123">**Element**</span></span>|<span data-ttu-id="314ea-124">**説明**</span><span class="sxs-lookup"><span data-stu-id="314ea-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="314ea-125">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="314ea-125">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="314ea-126">ハイパーテキスト転送プロトコル (HTTP: Hypertext Transfer Protocol) プロキシ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="314ea-126">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="314ea-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="314ea-127">Remarks</span></span>  
 <span data-ttu-id="314ea-128">バイパス リストには、Uri を記述する正規表現が含まれています。 を<xref:System.Net.WebRequest>インスタンスがプロキシ サーバーではなく直接アクセスします。</span><span class="sxs-lookup"><span data-stu-id="314ea-128">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="314ea-129">この要素の正規表現を指定するときに注意を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="314ea-129">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="314ea-130">正規表現"[a ~ z] +\\.contoso\\.com"contoso.com.cpandl.com ドメイン内の任意のホストと一致させる任意のホストが、contoso.com ドメインに一致します。</span><span class="sxs-lookup"><span data-stu-id="314ea-130">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="314ea-131">Contoso.com ドメイン内のホストのみが一致するアンカー (「$」) を使用します:"[a ~ z] +\\.contoso\\.com$"です。</span><span class="sxs-lookup"><span data-stu-id="314ea-131">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="314ea-132">正規表現の詳細についてを参照してください。[.NET framework の正規表現](../../../../../docs/standard/base-types/regular-expressions.md)します。</span><span class="sxs-lookup"><span data-stu-id="314ea-132">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="314ea-133">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="314ea-133">Configuration Files</span></span>  
 <span data-ttu-id="314ea-134">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="314ea-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="314ea-135">例</span><span class="sxs-lookup"><span data-stu-id="314ea-135">Example</span></span>  
 <span data-ttu-id="314ea-136">次の例では、2 つのアドレスをバイパス リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="314ea-136">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="314ea-137">1 つ目は、contoso.com ドメイン内のすべてのサーバーでプロキシをバイパスします。2 つ目は、192.168 で開始の IP アドレスを持つすべてのサーバーでプロキシをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="314ea-137">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="314ea-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="314ea-138">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="314ea-139">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="314ea-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
