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
ms.openlocfilehash: 1dda43be8c0e0c94bdf7b57b67aa4d403b547f97
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699543"
---
# <a name="bypasslist-element-network-settings"></a><span data-ttu-id="83ff6-102">\<bypasslist> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="83ff6-102">\<bypasslist> Element (Network Settings)</span></span>
<span data-ttu-id="83ff6-103">プロキシを使用しないアドレスを記述する一連の正規表現を提供します。</span><span class="sxs-lookup"><span data-stu-id="83ff6-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  
  
[<span data-ttu-id="83ff6-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="83ff6-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="83ff6-105">&nbsp; @ no__t-1[ **@no__t 47 >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="83ff6-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="83ff6-106">&nbsp; @ no__t-1 @ no__t @ no__t-3[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="83ff6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>  
<span data-ttu-id="83ff6-107">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5 **\<bypasslist >** を行います。</span><span class="sxs-lookup"><span data-stu-id="83ff6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bypasslist>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83ff6-108">構文</span><span class="sxs-lookup"><span data-stu-id="83ff6-108">Syntax</span></span>  
  
```xml  
<bypasslist>   
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83ff6-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="83ff6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="83ff6-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="83ff6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83ff6-111">属性</span><span class="sxs-lookup"><span data-stu-id="83ff6-111">Attributes</span></span>  
 <span data-ttu-id="83ff6-112">[なし] :</span><span class="sxs-lookup"><span data-stu-id="83ff6-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="83ff6-113">子要素</span><span class="sxs-lookup"><span data-stu-id="83ff6-113">Child Elements</span></span>  
  
|<span data-ttu-id="83ff6-114">**要素**</span><span class="sxs-lookup"><span data-stu-id="83ff6-114">**Element**</span></span>|<span data-ttu-id="83ff6-115">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="83ff6-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="83ff6-116">add</span><span class="sxs-lookup"><span data-stu-id="83ff6-116">add</span></span>](add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="83ff6-117">プロキシバイパス一覧に IP アドレスまたは DNS 名を追加します。</span><span class="sxs-lookup"><span data-stu-id="83ff6-117">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="83ff6-118">clear</span><span class="sxs-lookup"><span data-stu-id="83ff6-118">clear</span></span>](clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="83ff6-119">バイパスリストをクリアします。</span><span class="sxs-lookup"><span data-stu-id="83ff6-119">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="83ff6-120">remove</span><span class="sxs-lookup"><span data-stu-id="83ff6-120">remove</span></span>](remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="83ff6-121">プロキシバイパスリストから IP アドレスまたは DNS 名を削除します。</span><span class="sxs-lookup"><span data-stu-id="83ff6-121">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="83ff6-122">親要素</span><span class="sxs-lookup"><span data-stu-id="83ff6-122">Parent Elements</span></span>  
  
|<span data-ttu-id="83ff6-123">**要素**</span><span class="sxs-lookup"><span data-stu-id="83ff6-123">**Element**</span></span>|<span data-ttu-id="83ff6-124">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="83ff6-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="83ff6-125">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="83ff6-125">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="83ff6-126">ハイパーテキスト転送プロトコル (HTTP: Hypertext Transfer Protocol) プロキシ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="83ff6-126">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83ff6-127">コメント</span><span class="sxs-lookup"><span data-stu-id="83ff6-127">Remarks</span></span>  
 <span data-ttu-id="83ff6-128">バイパスリストには、@no__t 0 のインスタンスがプロキシサーバーを経由せずに直接アクセスする Uri を記述する正規表現が含まれています。</span><span class="sxs-lookup"><span data-stu-id="83ff6-128">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="83ff6-129">この要素に正規表現を指定する場合は、注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="83ff6-129">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="83ff6-130">正規表現 "[a-z] + \\.contoso\\.com" は、contoso.com ドメイン内の任意のホストと一致しますが、contoso.com.cpandl.com ドメイン内の任意のホストとも一致します。</span><span class="sxs-lookup"><span data-stu-id="83ff6-130">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="83ff6-131">Contoso.com ドメイン内のホストのみを一致させるには、アンカー ("$"): "[a-z] + \\.contoso\\.com $" を使用します。</span><span class="sxs-lookup"><span data-stu-id="83ff6-131">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="83ff6-132">正規表現の詳細については、「」を参照してください。[正規表現を .NET Framework](../../../../standard/base-types/regular-expressions.md)します。</span><span class="sxs-lookup"><span data-stu-id="83ff6-132">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="83ff6-133">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="83ff6-133">Configuration Files</span></span>  
 <span data-ttu-id="83ff6-134">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="83ff6-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="83ff6-135">例</span><span class="sxs-lookup"><span data-stu-id="83ff6-135">Example</span></span>  
 <span data-ttu-id="83ff6-136">次の例では、バイパスリストに2つのアドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="83ff6-136">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="83ff6-137">最初のは、contoso.com ドメイン内のすべてのサーバーのプロキシをバイパスします。2つ目は、IP アドレスが192.168 で始まるすべてのサーバーのプロキシをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="83ff6-137">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="83ff6-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="83ff6-138">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="83ff6-139">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="83ff6-139">Network Settings Schema</span></span>](index.md)
