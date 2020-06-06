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
ms.openlocfilehash: 0945629c1395917bc1cf825f2ba84d20afa99957
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "71698209"
---
# <a name="defaultproxy-element-network-settings"></a><span data-ttu-id="cffbe-102">\<defaultProxy> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="cffbe-102">\<defaultProxy> Element (Network Settings)</span></span>
<span data-ttu-id="cffbe-103">ハイパーテキスト転送プロトコル (HTTP: Hypertext Transfer Protocol) プロキシ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="cffbe-103">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultProxy>**  
  
## <a name="syntax"></a><span data-ttu-id="cffbe-104">構文</span><span class="sxs-lookup"><span data-stu-id="cffbe-104">Syntax</span></span>  
  
```xml  
<defaultProxy  
  enabled="true|false"  
  useDefaultCredentials="true|false">  
    <bypasslist>...</bypasslist>  
    <proxy>...</proxy>  
    <module>...</module>  
</defaultProxy>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cffbe-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cffbe-105">Attributes and Elements</span></span>  
 <span data-ttu-id="cffbe-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="cffbe-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cffbe-107">属性</span><span class="sxs-lookup"><span data-stu-id="cffbe-107">Attributes</span></span>  
  
|<span data-ttu-id="cffbe-108">**要素**</span><span class="sxs-lookup"><span data-stu-id="cffbe-108">**Element**</span></span>|<span data-ttu-id="cffbe-109">**説明**</span><span class="sxs-lookup"><span data-stu-id="cffbe-109">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="cffbe-110">Web プロキシが使用されているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="cffbe-110">Specifies whether a web proxy is used.</span></span> <span data-ttu-id="cffbe-111">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="cffbe-111">The default value is `true`.</span></span>|  
|`useDefaultCredentials`|<span data-ttu-id="cffbe-112">このホストに対する既定の資格情報が Web プロキシにアクセスするために使用されるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="cffbe-112">Specifies whether the default credentials for this host are used to access the web proxy.</span></span> <span data-ttu-id="cffbe-113">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="cffbe-113">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cffbe-114">子要素</span><span class="sxs-lookup"><span data-stu-id="cffbe-114">Child Elements</span></span>  
  
|<span data-ttu-id="cffbe-115">**要素**</span><span class="sxs-lookup"><span data-stu-id="cffbe-115">**Element**</span></span>|<span data-ttu-id="cffbe-116">**説明**</span><span class="sxs-lookup"><span data-stu-id="cffbe-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="cffbe-117">bypasslist</span><span class="sxs-lookup"><span data-stu-id="cffbe-117">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="cffbe-118">プロキシを使用しないアドレスを記述する一連の正規表現を提供します。</span><span class="sxs-lookup"><span data-stu-id="cffbe-118">Provides a set of regular expressions that describe addresses that do not use the proxy.</span></span>|  
|[<span data-ttu-id="cffbe-119">第</span><span class="sxs-lookup"><span data-stu-id="cffbe-119">module</span></span>](module-element-network-settings.md)|<span data-ttu-id="cffbe-120">新しいプロキシ モジュールをアプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="cffbe-120">Adds a new proxy module to the application.</span></span>|  
|[<span data-ttu-id="cffbe-121">rpcproxy</span><span class="sxs-lookup"><span data-stu-id="cffbe-121">proxy</span></span>](proxy-element-network-settings.md)|<span data-ttu-id="cffbe-122">プロキシ サーバーを定義します。</span><span class="sxs-lookup"><span data-stu-id="cffbe-122">Defines a proxy server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cffbe-123">親要素</span><span class="sxs-lookup"><span data-stu-id="cffbe-123">Parent Elements</span></span>  
  
|<span data-ttu-id="cffbe-124">**要素**</span><span class="sxs-lookup"><span data-stu-id="cffbe-124">**Element**</span></span>|<span data-ttu-id="cffbe-125">**説明**</span><span class="sxs-lookup"><span data-stu-id="cffbe-125">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="cffbe-126">system.net</span><span class="sxs-lookup"><span data-stu-id="cffbe-126">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="cffbe-127">.NET Framework がネットワークに接続する方法を指定するための設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cffbe-127">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cffbe-128">解説</span><span class="sxs-lookup"><span data-stu-id="cffbe-128">Remarks</span></span>  
 <span data-ttu-id="cffbe-129">defaultProxy 要素が空の場合、Internet Explorer のプロキシ設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="cffbe-129">If the defaultProxy element is empty, the proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="cffbe-130">この動作は、.NET Framework Version 1.1 とは異なります。</span><span class="sxs-lookup"><span data-stu-id="cffbe-130">This behavior is different from version 1.1 of the .NET Framework.</span></span>  
  
 <span data-ttu-id="cffbe-131">[モジュール](module-element-network-settings.md)要素で非パブリック型が指定されている場合、型がクラスから派生していない場合、 <xref:System.Net.IWebProxy> このオブジェクトのパラメーターなしのコンストラクターの例外が発生した場合、またはシステム指定の既定のプロキシを取得中に例外が発生した場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="cffbe-131">An exception is thrown if the [module](module-element-network-settings.md) element specifies a non-public type, the type is not deriving from the <xref:System.Net.IWebProxy> class, an exception from the parameterless constructor of this object occurred, or an exception occurred while retrieving the system-specified default proxy.</span></span> <span data-ttu-id="cffbe-132">例外の <xref:System.Exception.InnerException%2A> プロパティに、このエラーの根本原因に関する詳細情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cffbe-132">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="cffbe-133">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="cffbe-133">Configuration Files</span></span>  
 <span data-ttu-id="cffbe-134">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="cffbe-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cffbe-135">例</span><span class="sxs-lookup"><span data-stu-id="cffbe-135">Example</span></span>  
 <span data-ttu-id="cffbe-136">次の例では、Internet Explorer プロキシの既定値を使用して、プロキシアドレスを指定し、ローカルアクセスと contoso.com に対してプロキシをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="cffbe-136">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access and contoso.com.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cffbe-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="cffbe-137">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="cffbe-138">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="cffbe-138">Network Settings Schema</span></span>](index.md)
