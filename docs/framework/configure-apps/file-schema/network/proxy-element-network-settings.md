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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154791"
---
# <a name="proxy-element-network-settings"></a><span data-ttu-id="f5b9a-102">\<プロキシ>要素(ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="f5b9a-102">\<proxy> Element (Network Settings)</span></span>
<span data-ttu-id="f5b9a-103">プロキシ サーバーを定義します。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-103">Defines a proxy server.</span></span>  

<span data-ttu-id="f5b9a-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f5b9a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f5b9a-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f5b9a-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="f5b9a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<既定のプロキシ>**](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f5b9a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="f5b9a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<プロキシ>**</span><span class="sxs-lookup"><span data-stu-id="f5b9a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<proxy>**</span></span>

## <a name="syntax"></a><span data-ttu-id="f5b9a-108">構文</span><span class="sxs-lookup"><span data-stu-id="f5b9a-108">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="true|false|unspecified"
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5b9a-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f5b9a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f5b9a-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5b9a-111">属性</span><span class="sxs-lookup"><span data-stu-id="f5b9a-111">Attributes</span></span>  
  
|<span data-ttu-id="f5b9a-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="f5b9a-112">**Attribute**</span></span>|<span data-ttu-id="f5b9a-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="f5b9a-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="f5b9a-114">プロキシを自動的に検出するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-114">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="f5b9a-115">既定値は `unspecified` です。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-115">The default value is `unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="f5b9a-116">ローカル リソースの場合に、プロキシがバイパスされるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-116">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="f5b9a-117">ローカル リソースには、ローカル`http://localhost`サーバー `http://loopback`( `http://127.0.0.1`、 、 、 、`http://webserver`) 、およびピリオド ( ) のない URI が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-117">Local resources include the local server (`http://localhost`, `http://loopback`, or `http://127.0.0.1`) and a URI without a period (`http://webserver`).</span></span> <span data-ttu-id="f5b9a-118">既定値は `unspecified` です。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-118">The default value is `unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="f5b9a-119">使用するプロキシ URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-119">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="f5b9a-120">構成スクリプトの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-120">Specifies the location of the configuration script.</span></span> <span data-ttu-id="f5b9a-121">この属性には、`bypassonlocal`この属性を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-121">Do not use the `bypassonlocal` attribute with this attribute.</span></span> |  
|`usesystemdefault`|<span data-ttu-id="f5b9a-122">インターネット エクスプローラのプロキシ設定を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-122">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="f5b9a-123">に設定すると`true`、それ以降の属性は Internet Explorer プロキシ設定より優先されます。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-123">If set to `true`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="f5b9a-124">既定値は `unspecified` です。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-124">The default value is `unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f5b9a-125">子要素</span><span class="sxs-lookup"><span data-stu-id="f5b9a-125">Child Elements</span></span>  
 <span data-ttu-id="f5b9a-126">[なし] :</span><span class="sxs-lookup"><span data-stu-id="f5b9a-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f5b9a-127">親要素</span><span class="sxs-lookup"><span data-stu-id="f5b9a-127">Parent Elements</span></span>  
  
|<span data-ttu-id="f5b9a-128">**Element**</span><span class="sxs-lookup"><span data-stu-id="f5b9a-128">**Element**</span></span>|<span data-ttu-id="f5b9a-129">**説明**</span><span class="sxs-lookup"><span data-stu-id="f5b9a-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f5b9a-130">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="f5b9a-130">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="f5b9a-131">ハイパーテキスト転送プロトコル (HTTP: Hypertext Transfer Protocol) プロキシ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-131">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="f5b9a-132">テキスト値</span><span class="sxs-lookup"><span data-stu-id="f5b9a-132">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5b9a-133">解説</span><span class="sxs-lookup"><span data-stu-id="f5b9a-133">Remarks</span></span>  
 <span data-ttu-id="f5b9a-134">この`proxy`要素は、アプリケーションのプロキシ サーバーを定義します。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-134">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="f5b9a-135">この要素が構成ファイルに存在しない場合、.NET Framework は Internet Explorer のプロキシ設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-135">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="f5b9a-136">属性の`proxyaddress`値は、整形式の統一リソース インジケーター (URI) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-136">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="f5b9a-137">この`scriptLocation`属性は、プロキシ構成スクリプトの自動検出を参照します。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-137">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="f5b9a-138">Internet Explorer で [自動構成スクリプトを使用する] オプションが選択されている場合、このクラスは構成スクリプト (通常は Wpad.dat という名前) を検索しようとします。 **Use automatic configuration script** <xref:System.Net.WebProxy></span><span class="sxs-lookup"><span data-stu-id="f5b9a-138">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span> <span data-ttu-id="f5b9a-139">任意`bypassonlocal`の値に設定されている場合`scriptLocation`は無視されます。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-139">If `bypassonlocal` is set to any value, `scriptLocation` is ignored.</span></span>
  
 <span data-ttu-id="f5b9a-140">バージョン`usesystemdefault`2.0 に移行する .NET Framework バージョン 1.1 アプリケーションの属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-140">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="f5b9a-141">属性が無効な既定プロキシ`proxyaddress`を指定した場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-141">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="f5b9a-142">例外の <xref:System.Exception.InnerException%2A> プロパティに、このエラーの根本原因に関する詳細情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-142">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f5b9a-143">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="f5b9a-143">Configuration Files</span></span>  
 <span data-ttu-id="f5b9a-144">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-144">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5b9a-145">例</span><span class="sxs-lookup"><span data-stu-id="f5b9a-145">Example</span></span>  
 <span data-ttu-id="f5b9a-146">次の例では、Internet Explorer プロキシの既定値を使用し、プロキシ アドレスを指定し、ローカル アクセス用にプロキシをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="f5b9a-146">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f5b9a-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5b9a-147">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="f5b9a-148">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="f5b9a-148">Network Settings Schema</span></span>](index.md)
