---
title: <defaultProxy> 要素 (ネットワーク設定)
description: <defaultProxy>ネットワーク設定要素は、.NET Framework でハイパーテキスト転送プロトコル (HTTP) プロキシサーバーを構成します。
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultProxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy
helpviewer_keywords:
- defaultProxy element
- <defaultProxy> element
ms.assetid: 9d663c4b-07b4-4f6f-9b12-efbd3630354f
ms.openlocfilehash: 915fdc96dbd4d417f9c9e6aa3ff96de3026491ef
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504603"
---
# <a name="defaultproxy-element-network-settings"></a><span data-ttu-id="4a999-103">\<defaultProxy> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="4a999-103">\<defaultProxy> Element (Network Settings)</span></span>
<span data-ttu-id="4a999-104">ハイパーテキスト転送プロトコル (HTTP: Hypertext Transfer Protocol) プロキシ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="4a999-104">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultProxy>**  
  
## <a name="syntax"></a><span data-ttu-id="4a999-105">構文</span><span class="sxs-lookup"><span data-stu-id="4a999-105">Syntax</span></span>  
  
```xml  
<defaultProxy  
  enabled="true|false"  
  useDefaultCredentials="true|false">  
    <bypasslist>...</bypasslist>  
    <proxy>...</proxy>  
    <module>...</module>  
</defaultProxy>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4a999-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4a999-106">Attributes and Elements</span></span>  
 <span data-ttu-id="4a999-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4a999-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4a999-108">属性</span><span class="sxs-lookup"><span data-stu-id="4a999-108">Attributes</span></span>  
  
|<span data-ttu-id="4a999-109">**要素**</span><span class="sxs-lookup"><span data-stu-id="4a999-109">**Element**</span></span>|<span data-ttu-id="4a999-110">**説明**</span><span class="sxs-lookup"><span data-stu-id="4a999-110">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="4a999-111">Web プロキシが使用されているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a999-111">Specifies whether a web proxy is used.</span></span> <span data-ttu-id="4a999-112">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="4a999-112">The default value is `true`.</span></span>|  
|`useDefaultCredentials`|<span data-ttu-id="4a999-113">このホストに対する既定の資格情報が Web プロキシにアクセスするために使用されるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a999-113">Specifies whether the default credentials for this host are used to access the web proxy.</span></span> <span data-ttu-id="4a999-114">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="4a999-114">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4a999-115">子要素</span><span class="sxs-lookup"><span data-stu-id="4a999-115">Child Elements</span></span>  
  
|<span data-ttu-id="4a999-116">**要素**</span><span class="sxs-lookup"><span data-stu-id="4a999-116">**Element**</span></span>|<span data-ttu-id="4a999-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="4a999-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4a999-118">bypasslist</span><span class="sxs-lookup"><span data-stu-id="4a999-118">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="4a999-119">プロキシを使用しないアドレスを記述する一連の正規表現を提供します。</span><span class="sxs-lookup"><span data-stu-id="4a999-119">Provides a set of regular expressions that describe addresses that do not use the proxy.</span></span>|  
|[<span data-ttu-id="4a999-120">第</span><span class="sxs-lookup"><span data-stu-id="4a999-120">module</span></span>](module-element-network-settings.md)|<span data-ttu-id="4a999-121">新しいプロキシ モジュールをアプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="4a999-121">Adds a new proxy module to the application.</span></span>|  
|[<span data-ttu-id="4a999-122">rpcproxy</span><span class="sxs-lookup"><span data-stu-id="4a999-122">proxy</span></span>](proxy-element-network-settings.md)|<span data-ttu-id="4a999-123">プロキシ サーバーを定義します。</span><span class="sxs-lookup"><span data-stu-id="4a999-123">Defines a proxy server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4a999-124">親要素</span><span class="sxs-lookup"><span data-stu-id="4a999-124">Parent Elements</span></span>  
  
|<span data-ttu-id="4a999-125">**要素**</span><span class="sxs-lookup"><span data-stu-id="4a999-125">**Element**</span></span>|<span data-ttu-id="4a999-126">**説明**</span><span class="sxs-lookup"><span data-stu-id="4a999-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4a999-127">system.net</span><span class="sxs-lookup"><span data-stu-id="4a999-127">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="4a999-128">.NET Framework がネットワークに接続する方法を指定するための設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4a999-128">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a999-129">解説</span><span class="sxs-lookup"><span data-stu-id="4a999-129">Remarks</span></span>  
 <span data-ttu-id="4a999-130">defaultProxy 要素が空の場合、Internet Explorer のプロキシ設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="4a999-130">If the defaultProxy element is empty, the proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="4a999-131">この動作は、.NET Framework Version 1.1 とは異なります。</span><span class="sxs-lookup"><span data-stu-id="4a999-131">This behavior is different from version 1.1 of the .NET Framework.</span></span>  
  
 <span data-ttu-id="4a999-132">[モジュール](module-element-network-settings.md)要素で非パブリック型が指定されている場合、型がクラスから派生していない場合、 <xref:System.Net.IWebProxy> このオブジェクトのパラメーターなしのコンストラクターの例外が発生した場合、またはシステム指定の既定のプロキシを取得中に例外が発生した場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="4a999-132">An exception is thrown if the [module](module-element-network-settings.md) element specifies a non-public type, the type is not deriving from the <xref:System.Net.IWebProxy> class, an exception from the parameterless constructor of this object occurred, or an exception occurred while retrieving the system-specified default proxy.</span></span> <span data-ttu-id="4a999-133">例外の <xref:System.Exception.InnerException%2A> プロパティに、このエラーの根本原因に関する詳細情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4a999-133">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4a999-134">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="4a999-134">Configuration Files</span></span>  
 <span data-ttu-id="4a999-135">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="4a999-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a999-136">例</span><span class="sxs-lookup"><span data-stu-id="4a999-136">Example</span></span>  
 <span data-ttu-id="4a999-137">次の例では、Internet Explorer プロキシの既定値を使用して、プロキシアドレスを指定し、ローカルアクセスと contoso.com に対してプロキシをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="4a999-137">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access and contoso.com.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4a999-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a999-138">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="4a999-139">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="4a999-139">Network Settings Schema</span></span>](index.md)
