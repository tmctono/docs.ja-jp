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
ms.openlocfilehash: 5f327a2bb4fe316497614f14669907d514c20654
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089190"
---
# <a name="proxy-element-network-settings"></a><span data-ttu-id="5b8b4-102">\<proxy > 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="5b8b4-102">\<proxy> Element (Network Settings)</span></span>
<span data-ttu-id="5b8b4-103">プロキシ サーバーを定義します。</span><span class="sxs-lookup"><span data-stu-id="5b8b4-103">Defines a proxy server.</span></span>  

<span data-ttu-id="5b8b4-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5b8b4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5b8b4-105">&nbsp;&nbsp;[ **\<system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="5b8b4-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="5b8b4-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**defaultProxy >** ](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="5b8b4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="5b8b4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**プロキシ >**</span><span class="sxs-lookup"><span data-stu-id="5b8b4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<proxy>**</span></span>

## <a name="syntax"></a><span data-ttu-id="5b8b4-108">構文</span><span class="sxs-lookup"><span data-stu-id="5b8b4-108">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="true|false|unspecified" 
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5b8b4-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5b8b4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5b8b4-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5b8b4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5b8b4-111">属性</span><span class="sxs-lookup"><span data-stu-id="5b8b4-111">Attributes</span></span>  
  
|<span data-ttu-id="5b8b4-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="5b8b4-112">**Attribute**</span></span>|<span data-ttu-id="5b8b4-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="5b8b4-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="5b8b4-114">プロキシが自動的に検出されるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5b8b4-114">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="5b8b4-115">既定値は `unspecified`です。</span><span class="sxs-lookup"><span data-stu-id="5b8b4-115">The default value is `unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="5b8b4-116">ローカルリソースに対してプロキシをバイパスするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5b8b4-116">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="5b8b4-117">ローカルリソースには、ローカルサーバー (`http://localhost`、`http://loopback`、または `http://127.0.0.1`) と、ピリオドなしの URI (`http://webserver`) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5b8b4-117">Local resources include the local server (`http://localhost`, `http://loopback`, or `http://127.0.0.1`) and a URI without a period (`http://webserver`).</span></span> <span data-ttu-id="5b8b4-118">既定値は `unspecified`です。</span><span class="sxs-lookup"><span data-stu-id="5b8b4-118">The default value is `unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="5b8b4-119">使用するプロキシ URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="5b8b4-119">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="5b8b4-120">構成スクリプトの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="5b8b4-120">Specifies the location of the configuration script.</span></span> <span data-ttu-id="5b8b4-121">この属性には、`bypassonlocal` 属性を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="5b8b4-121">Do not use the `bypassonlocal` attribute with this attribute.</span></span> |  
|`usesystemdefault`|<span data-ttu-id="5b8b4-122">Internet Explorer のプロキシ設定を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5b8b4-122">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="5b8b4-123">`true`に設定すると、それ以降の属性は Internet Explorer のプロキシ設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="5b8b4-123">If set to `true`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="5b8b4-124">既定値は `unspecified`です。</span><span class="sxs-lookup"><span data-stu-id="5b8b4-124">The default value is `unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5b8b4-125">子要素</span><span class="sxs-lookup"><span data-stu-id="5b8b4-125">Child Elements</span></span>  
 <span data-ttu-id="5b8b4-126">なし。</span><span class="sxs-lookup"><span data-stu-id="5b8b4-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5b8b4-127">親要素</span><span class="sxs-lookup"><span data-stu-id="5b8b4-127">Parent Elements</span></span>  
  
|<span data-ttu-id="5b8b4-128">**要素**</span><span class="sxs-lookup"><span data-stu-id="5b8b4-128">**Element**</span></span>|<span data-ttu-id="5b8b4-129">**説明**</span><span class="sxs-lookup"><span data-stu-id="5b8b4-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="5b8b4-130">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="5b8b4-130">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="5b8b4-131">ハイパーテキスト転送プロトコル (HTTP: Hypertext Transfer Protocol) プロキシ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="5b8b4-131">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="5b8b4-132">テキスト値</span><span class="sxs-lookup"><span data-stu-id="5b8b4-132">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b8b4-133">Remarks</span><span class="sxs-lookup"><span data-stu-id="5b8b4-133">Remarks</span></span>  
 <span data-ttu-id="5b8b4-134">`proxy` 要素は、アプリケーションのプロキシサーバーを定義します。</span><span class="sxs-lookup"><span data-stu-id="5b8b4-134">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="5b8b4-135">この要素が構成ファイルにない場合、.NET Framework は Internet Explorer のプロキシ設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="5b8b4-135">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="5b8b4-136">`proxyaddress` 属性の値は、整形式の Uniform Resource Indicator (URI) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b8b4-136">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="5b8b4-137">`scriptLocation` 属性は、プロキシ構成スクリプトの自動検出を参照します。</span><span class="sxs-lookup"><span data-stu-id="5b8b4-137">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="5b8b4-138">Internet Explorer で **[自動構成スクリプトを使用する]** オプションが選択されている場合、<xref:System.Net.WebProxy> クラスは、通常は wpad.dat という名前の構成スクリプトを見つけようとします。</span><span class="sxs-lookup"><span data-stu-id="5b8b4-138">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span> <span data-ttu-id="5b8b4-139">`bypassonlocal` が任意の値に設定されている場合、`scriptLocation` は無視されます。</span><span class="sxs-lookup"><span data-stu-id="5b8b4-139">If `bypassonlocal` is set to any value, `scriptLocation` is ignored.</span></span>
  
 <span data-ttu-id="5b8b4-140">バージョン2.0 に移行する .NET Framework バージョン1.1 アプリケーションの場合は、`usesystemdefault` 属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="5b8b4-140">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="5b8b4-141">`proxyaddress` 属性が無効な既定のプロキシを指定している場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="5b8b4-141">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="5b8b4-142">例外の <xref:System.Exception.InnerException%2A> プロパティに、このエラーの根本原因に関する詳細情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5b8b4-142">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="5b8b4-143">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="5b8b4-143">Configuration Files</span></span>  
 <span data-ttu-id="5b8b4-144">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="5b8b4-144">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b8b4-145">例</span><span class="sxs-lookup"><span data-stu-id="5b8b4-145">Example</span></span>  
 <span data-ttu-id="5b8b4-146">次の例では、Internet Explorer プロキシの既定値を使用して、プロキシアドレスを指定し、ローカルアクセスのためにプロキシをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="5b8b4-146">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5b8b4-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b8b4-147">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="5b8b4-148">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="5b8b4-148">Network Settings Schema</span></span>](index.md)
