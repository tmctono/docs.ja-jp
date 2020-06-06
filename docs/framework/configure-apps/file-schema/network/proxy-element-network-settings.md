---
title: <proxy> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
ms.openlocfilehash: 590ea747c2fa9e5e85e5e9d05f6fb80fe60251d3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154791"
---
# <a name="proxy-element-network-settings"></a><span data-ttu-id="10ea8-102">\<proxy> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="10ea8-102">\<proxy> Element (Network Settings)</span></span>
<span data-ttu-id="10ea8-103">プロキシ サーバーを定義します。</span><span class="sxs-lookup"><span data-stu-id="10ea8-103">Defines a proxy server.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<proxy>**

## <a name="syntax"></a><span data-ttu-id="10ea8-104">構文</span><span class="sxs-lookup"><span data-stu-id="10ea8-104">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="true|false|unspecified"
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10ea8-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="10ea8-105">Attributes and Elements</span></span>  
 <span data-ttu-id="10ea8-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="10ea8-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10ea8-107">属性</span><span class="sxs-lookup"><span data-stu-id="10ea8-107">Attributes</span></span>  
  
|<span data-ttu-id="10ea8-108">**属性**</span><span class="sxs-lookup"><span data-stu-id="10ea8-108">**Attribute**</span></span>|<span data-ttu-id="10ea8-109">**説明**</span><span class="sxs-lookup"><span data-stu-id="10ea8-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="10ea8-110">プロキシを自動的に検出するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="10ea8-110">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="10ea8-111">既定値は `unspecified` です。</span><span class="sxs-lookup"><span data-stu-id="10ea8-111">The default value is `unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="10ea8-112">ローカル リソースの場合に、プロキシがバイパスされるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="10ea8-112">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="10ea8-113">ローカルリソースには、ローカルサーバー ( `http://localhost` 、 `http://loopback` 、または `http://127.0.0.1` ) と、ピリオドなしの URI () が含ま `http://webserver` れます。</span><span class="sxs-lookup"><span data-stu-id="10ea8-113">Local resources include the local server (`http://localhost`, `http://loopback`, or `http://127.0.0.1`) and a URI without a period (`http://webserver`).</span></span> <span data-ttu-id="10ea8-114">既定値は `unspecified` です。</span><span class="sxs-lookup"><span data-stu-id="10ea8-114">The default value is `unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="10ea8-115">使用するプロキシ URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="10ea8-115">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="10ea8-116">構成スクリプトの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="10ea8-116">Specifies the location of the configuration script.</span></span> <span data-ttu-id="10ea8-117">この属性には属性を使用しない `bypassonlocal` でください。</span><span class="sxs-lookup"><span data-stu-id="10ea8-117">Do not use the `bypassonlocal` attribute with this attribute.</span></span> |  
|`usesystemdefault`|<span data-ttu-id="10ea8-118">Internet Explorer のプロキシ設定を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="10ea8-118">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="10ea8-119">に設定する `true` と、それ以降の属性は Internet Explorer のプロキシ設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="10ea8-119">If set to `true`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="10ea8-120">既定値は `unspecified` です。</span><span class="sxs-lookup"><span data-stu-id="10ea8-120">The default value is `unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="10ea8-121">子要素</span><span class="sxs-lookup"><span data-stu-id="10ea8-121">Child Elements</span></span>  
 <span data-ttu-id="10ea8-122">なし。</span><span class="sxs-lookup"><span data-stu-id="10ea8-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="10ea8-123">親要素</span><span class="sxs-lookup"><span data-stu-id="10ea8-123">Parent Elements</span></span>  
  
|<span data-ttu-id="10ea8-124">**要素**</span><span class="sxs-lookup"><span data-stu-id="10ea8-124">**Element**</span></span>|<span data-ttu-id="10ea8-125">**説明**</span><span class="sxs-lookup"><span data-stu-id="10ea8-125">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="10ea8-126">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="10ea8-126">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="10ea8-127">ハイパーテキスト転送プロトコル (HTTP: Hypertext Transfer Protocol) プロキシ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="10ea8-127">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="10ea8-128">テキスト値</span><span class="sxs-lookup"><span data-stu-id="10ea8-128">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10ea8-129">解説</span><span class="sxs-lookup"><span data-stu-id="10ea8-129">Remarks</span></span>  
 <span data-ttu-id="10ea8-130">要素は、 `proxy` アプリケーションのプロキシサーバーを定義します。</span><span class="sxs-lookup"><span data-stu-id="10ea8-130">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="10ea8-131">この要素が構成ファイルにない場合、.NET Framework は Internet Explorer のプロキシ設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="10ea8-131">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="10ea8-132">属性の値は、整形 `proxyaddress` 式の Uniform Resource Indicator (URI) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="10ea8-132">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="10ea8-133">属性は、 `scriptLocation` プロキシ構成スクリプトの自動検出を参照します。</span><span class="sxs-lookup"><span data-stu-id="10ea8-133">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="10ea8-134"><xref:System.Net.WebProxy>Internet Explorer で [**自動構成スクリプトを使用する**] オプションが選択されている場合、クラスは、(通常は wpad.dat という名前の) 構成スクリプトの検索を試みます。</span><span class="sxs-lookup"><span data-stu-id="10ea8-134">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span> <span data-ttu-id="10ea8-135">が任意の値に設定されている場合 `bypassonlocal` 、 `scriptLocation` は無視されます。</span><span class="sxs-lookup"><span data-stu-id="10ea8-135">If `bypassonlocal` is set to any value, `scriptLocation` is ignored.</span></span>
  
 <span data-ttu-id="10ea8-136">`usesystemdefault`バージョン2.0 に移行する .NET Framework バージョン1.1 アプリケーションの場合は、属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="10ea8-136">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="10ea8-137">`proxyaddress`属性が無効な既定のプロキシを指定している場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="10ea8-137">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="10ea8-138">例外の <xref:System.Exception.InnerException%2A> プロパティに、このエラーの根本原因に関する詳細情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="10ea8-138">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="10ea8-139">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="10ea8-139">Configuration Files</span></span>  
 <span data-ttu-id="10ea8-140">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="10ea8-140">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="10ea8-141">例</span><span class="sxs-lookup"><span data-stu-id="10ea8-141">Example</span></span>  
 <span data-ttu-id="10ea8-142">次の例では、Internet Explorer プロキシの既定値を使用して、プロキシアドレスを指定し、ローカルアクセスのためにプロキシをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="10ea8-142">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="10ea8-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="10ea8-143">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="10ea8-144">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="10ea8-144">Network Settings Schema</span></span>](index.md)
