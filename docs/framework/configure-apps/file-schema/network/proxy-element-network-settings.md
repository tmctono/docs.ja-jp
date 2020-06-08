---
title: <proxy> 要素 (ネットワーク設定)
description: <proxy>ネットワーク設定要素は、.NET Framework のプロキシサーバーオプションを定義します。 この記事には例が含まれています。
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
ms.openlocfilehash: 0d462fcc92fc1be5ddbc2e76237d8436219c7295
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504538"
---
# <a name="proxy-element-network-settings"></a><span data-ttu-id="a587f-104">\<proxy> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="a587f-104">\<proxy> Element (Network Settings)</span></span>
<span data-ttu-id="a587f-105">プロキシ サーバーを定義します。</span><span class="sxs-lookup"><span data-stu-id="a587f-105">Defines a proxy server.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<proxy>**

## <a name="syntax"></a><span data-ttu-id="a587f-106">構文</span><span class="sxs-lookup"><span data-stu-id="a587f-106">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="true|false|unspecified"
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a587f-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a587f-107">Attributes and Elements</span></span>  
 <span data-ttu-id="a587f-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a587f-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a587f-109">属性</span><span class="sxs-lookup"><span data-stu-id="a587f-109">Attributes</span></span>  
  
|<span data-ttu-id="a587f-110">**属性**</span><span class="sxs-lookup"><span data-stu-id="a587f-110">**Attribute**</span></span>|<span data-ttu-id="a587f-111">**説明**</span><span class="sxs-lookup"><span data-stu-id="a587f-111">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="a587f-112">プロキシを自動的に検出するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a587f-112">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="a587f-113">既定値は `unspecified` です。</span><span class="sxs-lookup"><span data-stu-id="a587f-113">The default value is `unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="a587f-114">ローカル リソースの場合に、プロキシがバイパスされるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a587f-114">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="a587f-115">ローカルリソースには、ローカルサーバー ( `http://localhost` 、 `http://loopback` 、または `http://127.0.0.1` ) と、ピリオドなしの URI () が含ま `http://webserver` れます。</span><span class="sxs-lookup"><span data-stu-id="a587f-115">Local resources include the local server (`http://localhost`, `http://loopback`, or `http://127.0.0.1`) and a URI without a period (`http://webserver`).</span></span> <span data-ttu-id="a587f-116">既定値は `unspecified` です。</span><span class="sxs-lookup"><span data-stu-id="a587f-116">The default value is `unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="a587f-117">使用するプロキシ URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="a587f-117">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="a587f-118">構成スクリプトの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="a587f-118">Specifies the location of the configuration script.</span></span> <span data-ttu-id="a587f-119">この属性には属性を使用しない `bypassonlocal` でください。</span><span class="sxs-lookup"><span data-stu-id="a587f-119">Do not use the `bypassonlocal` attribute with this attribute.</span></span> |  
|`usesystemdefault`|<span data-ttu-id="a587f-120">Internet Explorer のプロキシ設定を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a587f-120">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="a587f-121">に設定する `true` と、それ以降の属性は Internet Explorer のプロキシ設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="a587f-121">If set to `true`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="a587f-122">既定値は `unspecified` です。</span><span class="sxs-lookup"><span data-stu-id="a587f-122">The default value is `unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a587f-123">子要素</span><span class="sxs-lookup"><span data-stu-id="a587f-123">Child Elements</span></span>  
 <span data-ttu-id="a587f-124">なし。</span><span class="sxs-lookup"><span data-stu-id="a587f-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a587f-125">親要素</span><span class="sxs-lookup"><span data-stu-id="a587f-125">Parent Elements</span></span>  
  
|<span data-ttu-id="a587f-126">**要素**</span><span class="sxs-lookup"><span data-stu-id="a587f-126">**Element**</span></span>|<span data-ttu-id="a587f-127">**説明**</span><span class="sxs-lookup"><span data-stu-id="a587f-127">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a587f-128">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="a587f-128">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="a587f-129">ハイパーテキスト転送プロトコル (HTTP: Hypertext Transfer Protocol) プロキシ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="a587f-129">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="a587f-130">テキスト値</span><span class="sxs-lookup"><span data-stu-id="a587f-130">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a587f-131">解説</span><span class="sxs-lookup"><span data-stu-id="a587f-131">Remarks</span></span>  
 <span data-ttu-id="a587f-132">要素は、 `proxy` アプリケーションのプロキシサーバーを定義します。</span><span class="sxs-lookup"><span data-stu-id="a587f-132">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="a587f-133">この要素が構成ファイルにない場合、.NET Framework は Internet Explorer のプロキシ設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="a587f-133">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="a587f-134">属性の値は、整形 `proxyaddress` 式の Uniform Resource Indicator (URI) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a587f-134">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="a587f-135">属性は、 `scriptLocation` プロキシ構成スクリプトの自動検出を参照します。</span><span class="sxs-lookup"><span data-stu-id="a587f-135">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="a587f-136"><xref:System.Net.WebProxy>Internet Explorer で [**自動構成スクリプトを使用する**] オプションが選択されている場合、クラスは、(通常は wpad.dat という名前の) 構成スクリプトの検索を試みます。</span><span class="sxs-lookup"><span data-stu-id="a587f-136">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span> <span data-ttu-id="a587f-137">が任意の値に設定されている場合 `bypassonlocal` 、 `scriptLocation` は無視されます。</span><span class="sxs-lookup"><span data-stu-id="a587f-137">If `bypassonlocal` is set to any value, `scriptLocation` is ignored.</span></span>
  
 <span data-ttu-id="a587f-138">`usesystemdefault`バージョン2.0 に移行する .NET Framework バージョン1.1 アプリケーションの場合は、属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="a587f-138">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="a587f-139">`proxyaddress`属性が無効な既定のプロキシを指定している場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="a587f-139">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="a587f-140">例外の <xref:System.Exception.InnerException%2A> プロパティに、このエラーの根本原因に関する詳細情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a587f-140">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a587f-141">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="a587f-141">Configuration Files</span></span>  
 <span data-ttu-id="a587f-142">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="a587f-142">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a587f-143">例</span><span class="sxs-lookup"><span data-stu-id="a587f-143">Example</span></span>  
 <span data-ttu-id="a587f-144">次の例では、Internet Explorer プロキシの既定値を使用して、プロキシアドレスを指定し、ローカルアクセスのためにプロキシをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="a587f-144">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a587f-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="a587f-145">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="a587f-146">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="a587f-146">Network Settings Schema</span></span>](index.md)
