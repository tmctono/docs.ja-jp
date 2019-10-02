---
title: connectionManagement の <remove> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- connectionManagement, remove element
- <remove> element, connectionManagement
- <connectionManagement>, remove element
- remove element, connectionManagement
ms.assetid: 94b81775-5a22-4975-8c47-8620c40c3f35
ms.openlocfilehash: cbafd29be6855cbb95d17388791ba152230295cc
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697839"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="27ec1-102">\<remove > connectionManagement の要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="27ec1-102">\<remove> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="27ec1-103">接続管理リストから IP アドレスまたは DNS 名を削除します。</span><span class="sxs-lookup"><span data-stu-id="27ec1-103">Removes an IP address or DNS name from the connection management list.</span></span>  
  
[<span data-ttu-id="27ec1-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="27ec1-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="27ec1-105">&nbsp; @ no__t-1[ **@no__t 47 >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="27ec1-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="27ec1-106">&nbsp; @ no__t @ no__t-2 @ no__t-3[ **\<connectionManagement >** ](connectionmanagement-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="27ec1-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)</span></span>  
<span data-ttu-id="27ec1-107">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5 **\<remove を削除**します。</span><span class="sxs-lookup"><span data-stu-id="27ec1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27ec1-108">構文</span><span class="sxs-lookup"><span data-stu-id="27ec1-108">Syntax</span></span>  
  
```xml  
<remove   
  address="server name or IP address"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="27ec1-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="27ec1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="27ec1-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="27ec1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="27ec1-111">属性</span><span class="sxs-lookup"><span data-stu-id="27ec1-111">Attributes</span></span>  
  
|<span data-ttu-id="27ec1-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="27ec1-112">**Attribute**</span></span>|<span data-ttu-id="27ec1-113">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="27ec1-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="27ec1-114">IP アドレスまたは DNS 名。</span><span class="sxs-lookup"><span data-stu-id="27ec1-114">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="27ec1-115">子要素</span><span class="sxs-lookup"><span data-stu-id="27ec1-115">Child Elements</span></span>  
 <span data-ttu-id="27ec1-116">なし。</span><span class="sxs-lookup"><span data-stu-id="27ec1-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="27ec1-117">親要素</span><span class="sxs-lookup"><span data-stu-id="27ec1-117">Parent Elements</span></span>  
  
|<span data-ttu-id="27ec1-118">**要素**</span><span class="sxs-lookup"><span data-stu-id="27ec1-118">**Element**</span></span>|<span data-ttu-id="27ec1-119">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="27ec1-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="27ec1-120">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="27ec1-120">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="27ec1-121">ネットワーク ホストへの接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="27ec1-121">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27ec1-122">コメント</span><span class="sxs-lookup"><span data-stu-id="27ec1-122">Remarks</span></span>  
 <span data-ttu-id="27ec1-123">@No__t-0 要素は、指定されたサーバーの接続管理リストのエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="27ec1-123">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="27ec1-124">@No__t-0 属性の値には、有効な IP アドレスまたはホスト名を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27ec1-124">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="27ec1-125">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="27ec1-125">Configuration Files</span></span>  
 <span data-ttu-id="27ec1-126">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="27ec1-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="27ec1-127">例</span><span class="sxs-lookup"><span data-stu-id="27ec1-127">Example</span></span>  
 <span data-ttu-id="27ec1-128">次の例では、@no__t サーバーの接続管理リストのエントリをすべて削除してから、サーバーへの4つの接続を使用するようにアプリケーションを構成してから、他のすべてのサーバーへの接続を2つ @no__t ます。</span><span class="sxs-lookup"><span data-stu-id="27ec1-128">The following example removes any connection management list entries for the server `www.adventure-works.com` and then configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <remove address="http://www.adventure-works.com" />  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="27ec1-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="27ec1-129">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="27ec1-130">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="27ec1-130">Network Settings Schema</span></span>](index.md)
