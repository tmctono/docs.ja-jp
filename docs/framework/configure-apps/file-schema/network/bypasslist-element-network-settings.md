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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154947"
---
# <a name="bypasslist-element-network-settings"></a><span data-ttu-id="a8da7-102">\<bypasslist> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="a8da7-102">\<bypasslist> Element (Network Settings)</span></span>
<span data-ttu-id="a8da7-103">プロキシを使用しないアドレスを記述する一連の正規表現を提供します。</span><span class="sxs-lookup"><span data-stu-id="a8da7-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bypasslist>**

## <a name="syntax"></a><span data-ttu-id="a8da7-104">構文</span><span class="sxs-lookup"><span data-stu-id="a8da7-104">Syntax</span></span>  
  
```xml  
<bypasslist>
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a8da7-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a8da7-105">Attributes and Elements</span></span>  
 <span data-ttu-id="a8da7-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a8da7-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a8da7-107">属性</span><span class="sxs-lookup"><span data-stu-id="a8da7-107">Attributes</span></span>  
 <span data-ttu-id="a8da7-108">なし。</span><span class="sxs-lookup"><span data-stu-id="a8da7-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a8da7-109">子要素</span><span class="sxs-lookup"><span data-stu-id="a8da7-109">Child Elements</span></span>  
  
|<span data-ttu-id="a8da7-110">**要素**</span><span class="sxs-lookup"><span data-stu-id="a8da7-110">**Element**</span></span>|<span data-ttu-id="a8da7-111">**説明**</span><span class="sxs-lookup"><span data-stu-id="a8da7-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a8da7-112">add</span><span class="sxs-lookup"><span data-stu-id="a8da7-112">add</span></span>](add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="a8da7-113">プロキシバイパス一覧に IP アドレスまたは DNS 名を追加します。</span><span class="sxs-lookup"><span data-stu-id="a8da7-113">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="a8da7-114">オフ</span><span class="sxs-lookup"><span data-stu-id="a8da7-114">clear</span></span>](clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="a8da7-115">バイパスリストをクリアします。</span><span class="sxs-lookup"><span data-stu-id="a8da7-115">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="a8da7-116">remove</span><span class="sxs-lookup"><span data-stu-id="a8da7-116">remove</span></span>](remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="a8da7-117">プロキシバイパスリストから IP アドレスまたは DNS 名を削除します。</span><span class="sxs-lookup"><span data-stu-id="a8da7-117">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a8da7-118">親要素</span><span class="sxs-lookup"><span data-stu-id="a8da7-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a8da7-119">**要素**</span><span class="sxs-lookup"><span data-stu-id="a8da7-119">**Element**</span></span>|<span data-ttu-id="a8da7-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="a8da7-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a8da7-121">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="a8da7-121">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="a8da7-122">ハイパーテキスト転送プロトコル (HTTP: Hypertext Transfer Protocol) プロキシ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="a8da7-122">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8da7-123">解説</span><span class="sxs-lookup"><span data-stu-id="a8da7-123">Remarks</span></span>  
 <span data-ttu-id="a8da7-124">バイパスリストには、 <xref:System.Net.WebRequest> インスタンスがプロキシサーバー経由ではなく直接アクセスする uri を記述する正規表現が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a8da7-124">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="a8da7-125">この要素に正規表現を指定する場合は、注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="a8da7-125">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="a8da7-126">正規表現 "[a-z] + \\ . contoso \\ .com" は、contoso.com ドメイン内の任意のホストと一致しますが、contoso.com.cpandl.com ドメイン内の任意のホストとも一致します。</span><span class="sxs-lookup"><span data-stu-id="a8da7-126">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="a8da7-127">Contoso.com ドメイン内のホストのみを一致させるには、アンカー ("$"): "[a-z] + \\ . contoso \\ .com $" を使用します。</span><span class="sxs-lookup"><span data-stu-id="a8da7-127">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="a8da7-128">正規表現の詳細については、「」を参照してください。[正規表現を .NET Framework](../../../../standard/base-types/regular-expressions.md)します。</span><span class="sxs-lookup"><span data-stu-id="a8da7-128">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a8da7-129">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="a8da7-129">Configuration Files</span></span>  
 <span data-ttu-id="a8da7-130">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="a8da7-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8da7-131">例</span><span class="sxs-lookup"><span data-stu-id="a8da7-131">Example</span></span>  
 <span data-ttu-id="a8da7-132">次の例では、バイパスリストに2つのアドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="a8da7-132">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="a8da7-133">最初のは、contoso.com ドメイン内のすべてのサーバーのプロキシをバイパスします。2つ目は、IP アドレスが192.168 で始まるすべてのサーバーのプロキシをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="a8da7-133">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a8da7-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8da7-134">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="a8da7-135">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="a8da7-135">Network Settings Schema</span></span>](index.md)
