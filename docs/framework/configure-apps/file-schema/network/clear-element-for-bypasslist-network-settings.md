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
ms.openlocfilehash: c25477c2c99be66b34b07e1f7e50115bfa8d14e9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154934"
---
# <a name="clear-element-for-bypasslist-network-settings"></a><span data-ttu-id="0f7fe-102">bypasslist の \<clear> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="0f7fe-102">\<clear> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="0f7fe-103">プロキシバイパスリストをクリアします。</span><span class="sxs-lookup"><span data-stu-id="0f7fe-103">Clears the proxy bypass list.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="0f7fe-104">構文</span><span class="sxs-lookup"><span data-stu-id="0f7fe-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0f7fe-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0f7fe-105">Attributes and Elements</span></span>  
 <span data-ttu-id="0f7fe-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0f7fe-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0f7fe-107">属性</span><span class="sxs-lookup"><span data-stu-id="0f7fe-107">Attributes</span></span>  
 <span data-ttu-id="0f7fe-108">なし。</span><span class="sxs-lookup"><span data-stu-id="0f7fe-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0f7fe-109">子要素</span><span class="sxs-lookup"><span data-stu-id="0f7fe-109">Child Elements</span></span>  
 <span data-ttu-id="0f7fe-110">[なし] :</span><span class="sxs-lookup"><span data-stu-id="0f7fe-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0f7fe-111">親要素</span><span class="sxs-lookup"><span data-stu-id="0f7fe-111">Parent Elements</span></span>  
  
|<span data-ttu-id="0f7fe-112">**要素**</span><span class="sxs-lookup"><span data-stu-id="0f7fe-112">**Element**</span></span>|<span data-ttu-id="0f7fe-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="0f7fe-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="0f7fe-114">bypasslist</span><span class="sxs-lookup"><span data-stu-id="0f7fe-114">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="0f7fe-115">プロキシを使用しないアドレスを記述する一連の正規表現を提供します。</span><span class="sxs-lookup"><span data-stu-id="0f7fe-115">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f7fe-116">解説</span><span class="sxs-lookup"><span data-stu-id="0f7fe-116">Remarks</span></span>  
 <span data-ttu-id="0f7fe-117">要素は、 `clear` バイパスリストからすべてのエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="0f7fe-117">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="0f7fe-118">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="0f7fe-118">Configuration Files</span></span>  
 <span data-ttu-id="0f7fe-119">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="0f7fe-119">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f7fe-120">例</span><span class="sxs-lookup"><span data-stu-id="0f7fe-120">Example</span></span>  
 <span data-ttu-id="0f7fe-121">次の例では、バイパスリストをクリアし、2つのアドレスをバイパスリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="0f7fe-121">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="0f7fe-122">最初のは、contoso.com ドメイン内のすべてのサーバーのプロキシをバイパスします。2つ目は、IP アドレスが192.168 で始まるすべてのサーバーのプロキシをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="0f7fe-122">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0f7fe-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f7fe-123">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="0f7fe-124">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="0f7fe-124">Network Settings Schema</span></span>](index.md)
