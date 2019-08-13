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
ms.openlocfilehash: 7499d15f1d57887ffc3e78b83ed686c0c0f46cf4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674637"
---
# <a name="clear-element-for-bypasslist-network-settings"></a><span data-ttu-id="eaeb2-102">bypasslist の \<clear> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="eaeb2-102">\<clear> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="eaeb2-103">プロキシ バイ パスの一覧をクリアします。</span><span class="sxs-lookup"><span data-stu-id="eaeb2-103">Clears the proxy bypass list.</span></span>  
  
 <span data-ttu-id="eaeb2-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="eaeb2-104">\<configuration></span></span>  
<span data-ttu-id="eaeb2-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="eaeb2-105">\<system.net></span></span>  
<span data-ttu-id="eaeb2-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="eaeb2-106">\<defaultProxy></span></span>  
<span data-ttu-id="eaeb2-107">\<bypasslist></span><span class="sxs-lookup"><span data-stu-id="eaeb2-107">\<bypasslist></span></span>  
<span data-ttu-id="eaeb2-108">\<clear></span><span class="sxs-lookup"><span data-stu-id="eaeb2-108">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eaeb2-109">構文</span><span class="sxs-lookup"><span data-stu-id="eaeb2-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eaeb2-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="eaeb2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="eaeb2-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="eaeb2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eaeb2-112">属性</span><span class="sxs-lookup"><span data-stu-id="eaeb2-112">Attributes</span></span>  
 <span data-ttu-id="eaeb2-113">なし。</span><span class="sxs-lookup"><span data-stu-id="eaeb2-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="eaeb2-114">子要素</span><span class="sxs-lookup"><span data-stu-id="eaeb2-114">Child Elements</span></span>  
 <span data-ttu-id="eaeb2-115">なし。</span><span class="sxs-lookup"><span data-stu-id="eaeb2-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eaeb2-116">親要素</span><span class="sxs-lookup"><span data-stu-id="eaeb2-116">Parent Elements</span></span>  
  
|<span data-ttu-id="eaeb2-117">**要素**</span><span class="sxs-lookup"><span data-stu-id="eaeb2-117">**Element**</span></span>|<span data-ttu-id="eaeb2-118">**説明**</span><span class="sxs-lookup"><span data-stu-id="eaeb2-118">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="eaeb2-119">bypasslist</span><span class="sxs-lookup"><span data-stu-id="eaeb2-119">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="eaeb2-120">一連のプロキシを使用しないアドレスを記述する正規表現を提供します。</span><span class="sxs-lookup"><span data-stu-id="eaeb2-120">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eaeb2-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="eaeb2-121">Remarks</span></span>  
 <span data-ttu-id="eaeb2-122">`clear`要素がバイパス リストからすべてのエントリをクリアします。</span><span class="sxs-lookup"><span data-stu-id="eaeb2-122">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="eaeb2-123">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="eaeb2-123">Configuration Files</span></span>  
 <span data-ttu-id="eaeb2-124">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="eaeb2-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="eaeb2-125">例</span><span class="sxs-lookup"><span data-stu-id="eaeb2-125">Example</span></span>  
 <span data-ttu-id="eaeb2-126">次の例では、バイパス一覧をクリアし、バイパス リストに 2 つのアドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="eaeb2-126">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="eaeb2-127">1 つ目は、contoso.com ドメイン内のすべてのサーバーでプロキシをバイパスします。2 つ目は、192.168 で IP アドレスが始まるすべてのサーバーでプロキシをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="eaeb2-127">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="eaeb2-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="eaeb2-128">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="eaeb2-129">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="eaeb2-129">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
