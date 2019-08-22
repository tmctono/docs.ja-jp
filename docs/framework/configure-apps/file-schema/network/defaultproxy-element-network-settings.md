---
title: <defaultProxy> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultProxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy
helpviewer_keywords:
- defaultProxy element
- <defaultProxy> element
ms.assetid: 9d663c4b-07b4-4f6f-9b12-efbd3630354f
ms.openlocfilehash: 7e49762ee017564734bfb2b2f7074d94b7eabe11
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659393"
---
# <a name="defaultproxy-element-network-settings"></a><span data-ttu-id="9b1a4-102">\<defaultProxy> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="9b1a4-102">\<defaultProxy> Element (Network Settings)</span></span>
<span data-ttu-id="9b1a4-103">ハイパーテキスト転送プロトコル (HTTP: Hypertext Transfer Protocol) プロキシ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="9b1a4-103">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>  
  
 <span data-ttu-id="9b1a4-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9b1a4-104">\<configuration></span></span>  
<span data-ttu-id="9b1a4-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="9b1a4-105">\<system.net></span></span>  
<span data-ttu-id="9b1a4-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="9b1a4-106">\<defaultProxy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b1a4-107">構文</span><span class="sxs-lookup"><span data-stu-id="9b1a4-107">Syntax</span></span>  
  
```xml  
<defaultProxy  
  enabled="true|false"  
  useDefaultCredentials="true|false">  
    <bypasslist>...</bypasslist>  
    <proxy>...</proxy>  
    <module>...</module>  
</defaultProxy>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b1a4-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9b1a4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9b1a4-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9b1a4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b1a4-110">属性</span><span class="sxs-lookup"><span data-stu-id="9b1a4-110">Attributes</span></span>  
  
|<span data-ttu-id="9b1a4-111">**要素**</span><span class="sxs-lookup"><span data-stu-id="9b1a4-111">**Element**</span></span>|<span data-ttu-id="9b1a4-112">**説明**</span><span class="sxs-lookup"><span data-stu-id="9b1a4-112">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="9b1a4-113">Web プロキシが使用されているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9b1a4-113">Specifies whether a web proxy is used.</span></span> <span data-ttu-id="9b1a4-114">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="9b1a4-114">The default value is `true`.</span></span>|  
|`useDefaultCredentials`|<span data-ttu-id="9b1a4-115">このホストに対する既定の資格情報が Web プロキシにアクセスするために使用されるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9b1a4-115">Specifies whether the default credentials for this host are used to access the web proxy.</span></span> <span data-ttu-id="9b1a4-116">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="9b1a4-116">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b1a4-117">子要素</span><span class="sxs-lookup"><span data-stu-id="9b1a4-117">Child Elements</span></span>  
  
|<span data-ttu-id="9b1a4-118">**要素**</span><span class="sxs-lookup"><span data-stu-id="9b1a4-118">**Element**</span></span>|<span data-ttu-id="9b1a4-119">**説明**</span><span class="sxs-lookup"><span data-stu-id="9b1a4-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="9b1a4-120">bypasslist</span><span class="sxs-lookup"><span data-stu-id="9b1a4-120">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="9b1a4-121">プロキシを使用しないアドレスを記述する一連の正規表現を提供します。</span><span class="sxs-lookup"><span data-stu-id="9b1a4-121">Provides a set of regular expressions that describe addresses that do not use the proxy.</span></span>|  
|[<span data-ttu-id="9b1a4-122">module</span><span class="sxs-lookup"><span data-stu-id="9b1a4-122">module</span></span>](module-element-network-settings.md)|<span data-ttu-id="9b1a4-123">新しいプロキシ モジュールをアプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="9b1a4-123">Adds a new proxy module to the application.</span></span>|  
|[<span data-ttu-id="9b1a4-124">proxy</span><span class="sxs-lookup"><span data-stu-id="9b1a4-124">proxy</span></span>](proxy-element-network-settings.md)|<span data-ttu-id="9b1a4-125">プロキシ サーバーを定義します。</span><span class="sxs-lookup"><span data-stu-id="9b1a4-125">Defines a proxy server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9b1a4-126">親要素</span><span class="sxs-lookup"><span data-stu-id="9b1a4-126">Parent Elements</span></span>  
  
|<span data-ttu-id="9b1a4-127">**要素**</span><span class="sxs-lookup"><span data-stu-id="9b1a4-127">**Element**</span></span>|<span data-ttu-id="9b1a4-128">**説明**</span><span class="sxs-lookup"><span data-stu-id="9b1a4-128">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="9b1a4-129">system.net</span><span class="sxs-lookup"><span data-stu-id="9b1a4-129">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="9b1a4-130">.NET Framework がネットワークに接続する方法を指定するための設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9b1a4-130">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b1a4-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="9b1a4-131">Remarks</span></span>  
 <span data-ttu-id="9b1a4-132">defaultProxy 要素が空の場合、Internet Explorer のプロキシ設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="9b1a4-132">If the defaultProxy element is empty, the proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="9b1a4-133">この動作は、.NET Framework Version 1.1 とは異なります。</span><span class="sxs-lookup"><span data-stu-id="9b1a4-133">This behavior is different from version 1.1 of the .NET Framework.</span></span>  
  
 <span data-ttu-id="9b1a4-134">例外がスローされるのは、 [module](module-element-network-settings.md)要素で非パブリック型が指定されている場合、 <xref:System.Net.IWebProxy>型がクラスから派生していない場合、このオブジェクトのパラメーターなしのコンストラクターの例外が発生した場合、またはを取得しているときに例外が発生した場合です。システム指定の既定のプロキシ。</span><span class="sxs-lookup"><span data-stu-id="9b1a4-134">An exception is thrown if the [module](module-element-network-settings.md) element specifies a non-public type, the type is not deriving from the <xref:System.Net.IWebProxy> class, an exception from the parameterless constructor of this object occurred, or an exception occurred while retrieving the system-specified default proxy.</span></span> <span data-ttu-id="9b1a4-135">例外の <xref:System.Exception.InnerException%2A> プロパティに、このエラーの根本原因に関する詳細情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9b1a4-135">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="9b1a4-136">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="9b1a4-136">Configuration Files</span></span>  
 <span data-ttu-id="9b1a4-137">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="9b1a4-137">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b1a4-138">例</span><span class="sxs-lookup"><span data-stu-id="9b1a4-138">Example</span></span>  
 <span data-ttu-id="9b1a4-139">次の例では、Internet Explorer プロキシの既定値を使用して、プロキシアドレスを指定し、ローカルアクセスと contoso.com に対してプロキシをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="9b1a4-139">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access and contoso.com.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9b1a4-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b1a4-140">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="9b1a4-141">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="9b1a4-141">Network Settings Schema</span></span>](index.md)
