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
ms.openlocfilehash: 97e69a4978aa4700d13a994619a65312cf70aeaa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154947"
---
# <a name="bypasslist-element-network-settings"></a><span data-ttu-id="53fc0-102">\<要素>バイパスリスト (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="53fc0-102">\<bypasslist> Element (Network Settings)</span></span>
<span data-ttu-id="53fc0-103">プロキシを使用しないアドレスを記述する正規表現のセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="53fc0-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  

<span data-ttu-id="53fc0-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="53fc0-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="53fc0-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="53fc0-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="53fc0-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<既定のプロキシ>**](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="53fc0-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="53fc0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<バイパスリスト>**</span><span class="sxs-lookup"><span data-stu-id="53fc0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bypasslist>**</span></span>

## <a name="syntax"></a><span data-ttu-id="53fc0-108">構文</span><span class="sxs-lookup"><span data-stu-id="53fc0-108">Syntax</span></span>  
  
```xml  
<bypasslist>
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53fc0-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="53fc0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="53fc0-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="53fc0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53fc0-111">属性</span><span class="sxs-lookup"><span data-stu-id="53fc0-111">Attributes</span></span>  
 <span data-ttu-id="53fc0-112">[なし] :</span><span class="sxs-lookup"><span data-stu-id="53fc0-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="53fc0-113">子要素</span><span class="sxs-lookup"><span data-stu-id="53fc0-113">Child Elements</span></span>  
  
|<span data-ttu-id="53fc0-114">**Element**</span><span class="sxs-lookup"><span data-stu-id="53fc0-114">**Element**</span></span>|<span data-ttu-id="53fc0-115">**説明**</span><span class="sxs-lookup"><span data-stu-id="53fc0-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="53fc0-116">追加</span><span class="sxs-lookup"><span data-stu-id="53fc0-116">add</span></span>](add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="53fc0-117">IP アドレスまたは DNS 名をプロキシ バイパス リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="53fc0-117">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="53fc0-118">クリア</span><span class="sxs-lookup"><span data-stu-id="53fc0-118">clear</span></span>](clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="53fc0-119">バイパス リストをクリアします。</span><span class="sxs-lookup"><span data-stu-id="53fc0-119">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="53fc0-120">削除</span><span class="sxs-lookup"><span data-stu-id="53fc0-120">remove</span></span>](remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="53fc0-121">プロキシ バイパス リストから IP アドレスまたは DNS 名を削除します。</span><span class="sxs-lookup"><span data-stu-id="53fc0-121">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="53fc0-122">親要素</span><span class="sxs-lookup"><span data-stu-id="53fc0-122">Parent Elements</span></span>  
  
|<span data-ttu-id="53fc0-123">**Element**</span><span class="sxs-lookup"><span data-stu-id="53fc0-123">**Element**</span></span>|<span data-ttu-id="53fc0-124">**説明**</span><span class="sxs-lookup"><span data-stu-id="53fc0-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="53fc0-125">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="53fc0-125">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="53fc0-126">ハイパーテキスト転送プロトコル (HTTP: Hypertext Transfer Protocol) プロキシ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="53fc0-126">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53fc0-127">解説</span><span class="sxs-lookup"><span data-stu-id="53fc0-127">Remarks</span></span>  
 <span data-ttu-id="53fc0-128">バイパス リストには、プロキシ サーバーを介して<xref:System.Net.WebRequest>ではなく、インスタンスが直接アクセスする URI を記述する正規表現が含まれています。</span><span class="sxs-lookup"><span data-stu-id="53fc0-128">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="53fc0-129">この要素の正規表現を指定する場合は注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="53fc0-129">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="53fc0-130">正規表現 "[a-z]+\\.contoso\\.com" は、contoso.com ドメイン内の任意のホストと一致しますが、contoso.com.cpandl.com ドメイン内の任意のホストとも一致します。</span><span class="sxs-lookup"><span data-stu-id="53fc0-130">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="53fc0-131">contoso.com ドメイン内のホストのみを照合するには、アンカー ("$") "[a-z]+\\.contoso\\.com$" を使用します。</span><span class="sxs-lookup"><span data-stu-id="53fc0-131">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="53fc0-132">正規表現の詳細については、を参照してください。[.NET フレームワークの正規表現](../../../../standard/base-types/regular-expressions.md):</span><span class="sxs-lookup"><span data-stu-id="53fc0-132">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="53fc0-133">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="53fc0-133">Configuration Files</span></span>  
 <span data-ttu-id="53fc0-134">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="53fc0-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="53fc0-135">例</span><span class="sxs-lookup"><span data-stu-id="53fc0-135">Example</span></span>  
 <span data-ttu-id="53fc0-136">次の例では、バイパス リストに 2 つのアドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="53fc0-136">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="53fc0-137">最初の手順では、contoso.com ドメイン内のすべてのサーバーのプロキシをバイパスします。2 番目のサーバーは、IP アドレスが 192.168 で始まるすべてのサーバーのプロキシをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="53fc0-137">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="53fc0-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="53fc0-138">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="53fc0-139">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="53fc0-139">Network Settings Schema</span></span>](index.md)
