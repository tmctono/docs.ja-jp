---
title: bypasslist の <clear> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- clear element, bypasslist
- <clear> element, bypasslist
- <bypasslist>, clear element
- bypasslist, clear element
ms.assetid: 301584ca-a914-4100-b180-3b288d3b099e
ms.openlocfilehash: e5305d9aed09b6c4d1ad4201e5e08e007a14c7c0
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664186"
---
# <a name="clear-element-for-bypasslist-network-settings"></a><span data-ttu-id="3fd69-102">bypasslist の \<clear> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="3fd69-102">\<clear> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="3fd69-103">プロキシバイパスリストをクリアします。</span><span class="sxs-lookup"><span data-stu-id="3fd69-103">Clears the proxy bypass list.</span></span>  
  
 <span data-ttu-id="3fd69-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3fd69-104">\<configuration></span></span>  
<span data-ttu-id="3fd69-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="3fd69-105">\<system.net></span></span>  
<span data-ttu-id="3fd69-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="3fd69-106">\<defaultProxy></span></span>  
<span data-ttu-id="3fd69-107">\<bypasslist></span><span class="sxs-lookup"><span data-stu-id="3fd69-107">\<bypasslist></span></span>  
<span data-ttu-id="3fd69-108">\<clear></span><span class="sxs-lookup"><span data-stu-id="3fd69-108">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fd69-109">構文</span><span class="sxs-lookup"><span data-stu-id="3fd69-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3fd69-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3fd69-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3fd69-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3fd69-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3fd69-112">属性</span><span class="sxs-lookup"><span data-stu-id="3fd69-112">Attributes</span></span>  
 <span data-ttu-id="3fd69-113">なし。</span><span class="sxs-lookup"><span data-stu-id="3fd69-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3fd69-114">子要素</span><span class="sxs-lookup"><span data-stu-id="3fd69-114">Child Elements</span></span>  
 <span data-ttu-id="3fd69-115">なし。</span><span class="sxs-lookup"><span data-stu-id="3fd69-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3fd69-116">親要素</span><span class="sxs-lookup"><span data-stu-id="3fd69-116">Parent Elements</span></span>  
  
|<span data-ttu-id="3fd69-117">**要素**</span><span class="sxs-lookup"><span data-stu-id="3fd69-117">**Element**</span></span>|<span data-ttu-id="3fd69-118">**説明**</span><span class="sxs-lookup"><span data-stu-id="3fd69-118">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="3fd69-119">bypasslist</span><span class="sxs-lookup"><span data-stu-id="3fd69-119">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="3fd69-120">プロキシを使用しないアドレスを記述する一連の正規表現を提供します。</span><span class="sxs-lookup"><span data-stu-id="3fd69-120">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3fd69-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="3fd69-121">Remarks</span></span>  
 <span data-ttu-id="3fd69-122">要素`clear`は、バイパスリストからすべてのエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="3fd69-122">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="3fd69-123">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="3fd69-123">Configuration Files</span></span>  
 <span data-ttu-id="3fd69-124">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="3fd69-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fd69-125">例</span><span class="sxs-lookup"><span data-stu-id="3fd69-125">Example</span></span>  
 <span data-ttu-id="3fd69-126">次の例では、バイパスリストをクリアし、2つのアドレスをバイパスリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="3fd69-126">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="3fd69-127">最初のは、contoso.com ドメイン内のすべてのサーバーのプロキシをバイパスします。2つ目は、IP アドレスが192.168 で始まるすべてのサーバーのプロキシをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="3fd69-127">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
         <clear/>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="3fd69-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="3fd69-128">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="3fd69-129">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="3fd69-129">Network Settings Schema</span></span>](index.md)
