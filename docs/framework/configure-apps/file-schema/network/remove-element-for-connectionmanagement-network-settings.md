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
ms.openlocfilehash: 8ab7a43fbb3e8df5bb0c99b5947f2fafb362399a
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664030"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="ef710-102">\<connectionManagement の > 要素を削除する (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="ef710-102">\<remove> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="ef710-103">接続管理リストから IP アドレスまたは DNS 名を削除します。</span><span class="sxs-lookup"><span data-stu-id="ef710-103">Removes an IP address or DNS name from the connection management list.</span></span>  
  
 <span data-ttu-id="ef710-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ef710-104">\<configuration></span></span>  
<span data-ttu-id="ef710-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="ef710-105">\<system.net></span></span>  
<span data-ttu-id="ef710-106">\<connectionManagement></span><span class="sxs-lookup"><span data-stu-id="ef710-106">\<connectionManagement></span></span>  
<span data-ttu-id="ef710-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="ef710-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef710-108">構文</span><span class="sxs-lookup"><span data-stu-id="ef710-108">Syntax</span></span>  
  
```xml  
<remove   
  address="server name or IP address"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef710-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ef710-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ef710-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ef710-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef710-111">属性</span><span class="sxs-lookup"><span data-stu-id="ef710-111">Attributes</span></span>  
  
|<span data-ttu-id="ef710-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="ef710-112">**Attribute**</span></span>|<span data-ttu-id="ef710-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="ef710-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="ef710-114">IP アドレスまたは DNS 名。</span><span class="sxs-lookup"><span data-stu-id="ef710-114">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ef710-115">子要素</span><span class="sxs-lookup"><span data-stu-id="ef710-115">Child Elements</span></span>  
 <span data-ttu-id="ef710-116">なし。</span><span class="sxs-lookup"><span data-stu-id="ef710-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ef710-117">親要素</span><span class="sxs-lookup"><span data-stu-id="ef710-117">Parent Elements</span></span>  
  
|<span data-ttu-id="ef710-118">**要素**</span><span class="sxs-lookup"><span data-stu-id="ef710-118">**Element**</span></span>|<span data-ttu-id="ef710-119">**説明**</span><span class="sxs-lookup"><span data-stu-id="ef710-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ef710-120">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="ef710-120">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="ef710-121">ネットワーク ホストへの接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="ef710-121">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef710-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="ef710-122">Remarks</span></span>  
 <span data-ttu-id="ef710-123">要素`remove`は、指定されたサーバーの接続管理リストのエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="ef710-123">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="ef710-124">`address`属性の値は、有効な IP アドレスまたはホスト名である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef710-124">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ef710-125">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="ef710-125">Configuration Files</span></span>  
 <span data-ttu-id="ef710-126">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="ef710-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef710-127">例</span><span class="sxs-lookup"><span data-stu-id="ef710-127">Example</span></span>  
 <span data-ttu-id="ef710-128">次の例では、サーバー `www.adventure-works.com`に対する接続管理の一覧のエントリをすべて削除し、サーバー `www.contoso.com`への接続を4つ、他のすべてのサーバーへの接続を2つ使用するようにアプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="ef710-128">The following example removes any connection management list entries for the server `www.adventure-works.com` and then configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ef710-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef710-129">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="ef710-130">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="ef710-130">Network Settings Schema</span></span>](index.md)
