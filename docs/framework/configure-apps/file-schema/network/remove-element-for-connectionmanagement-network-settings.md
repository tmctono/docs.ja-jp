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
ms.openlocfilehash: d9c584fb2faa971e7ce1ca287a94c8c6129820fd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705195"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="0f1b0-102">\<削除 > connectionManagement (ネットワーク設定) の要素</span><span class="sxs-lookup"><span data-stu-id="0f1b0-102">\<remove> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="0f1b0-103">接続管理リストから IP アドレスまたは DNS 名を削除します。</span><span class="sxs-lookup"><span data-stu-id="0f1b0-103">Removes an IP address or DNS name from the connection management list.</span></span>  
  
 <span data-ttu-id="0f1b0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="0f1b0-104">\<configuration></span></span>  
<span data-ttu-id="0f1b0-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="0f1b0-105">\<system.net></span></span>  
<span data-ttu-id="0f1b0-106">\<connectionManagement></span><span class="sxs-lookup"><span data-stu-id="0f1b0-106">\<connectionManagement></span></span>  
<span data-ttu-id="0f1b0-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="0f1b0-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f1b0-108">構文</span><span class="sxs-lookup"><span data-stu-id="0f1b0-108">Syntax</span></span>  
  
```xml  
<remove   
  address="server name or IP address"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0f1b0-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0f1b0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0f1b0-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0f1b0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0f1b0-111">属性</span><span class="sxs-lookup"><span data-stu-id="0f1b0-111">Attributes</span></span>  
  
|<span data-ttu-id="0f1b0-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="0f1b0-112">**Attribute**</span></span>|<span data-ttu-id="0f1b0-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="0f1b0-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="0f1b0-114">IP アドレスまたは DNS 名。</span><span class="sxs-lookup"><span data-stu-id="0f1b0-114">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0f1b0-115">子要素</span><span class="sxs-lookup"><span data-stu-id="0f1b0-115">Child Elements</span></span>  
 <span data-ttu-id="0f1b0-116">なし。</span><span class="sxs-lookup"><span data-stu-id="0f1b0-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0f1b0-117">親要素</span><span class="sxs-lookup"><span data-stu-id="0f1b0-117">Parent Elements</span></span>  
  
|<span data-ttu-id="0f1b0-118">**要素**</span><span class="sxs-lookup"><span data-stu-id="0f1b0-118">**Element**</span></span>|<span data-ttu-id="0f1b0-119">**説明**</span><span class="sxs-lookup"><span data-stu-id="0f1b0-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="0f1b0-120">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="0f1b0-120">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="0f1b0-121">ネットワーク ホストへの接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="0f1b0-121">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f1b0-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="0f1b0-122">Remarks</span></span>  
 <span data-ttu-id="0f1b0-123">`remove`要素が指定されたサーバーの接続管理リスト エントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="0f1b0-123">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="0f1b0-124">値、`address`属性が有効な IP アドレスまたはホスト名にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f1b0-124">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="0f1b0-125">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="0f1b0-125">Configuration Files</span></span>  
 <span data-ttu-id="0f1b0-126">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="0f1b0-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f1b0-127">例</span><span class="sxs-lookup"><span data-stu-id="0f1b0-127">Example</span></span>  
 <span data-ttu-id="0f1b0-128">次の例は、サーバーの接続管理リスト エントリを削除します。`www.adventure-works.com`され、サーバーに 4 つの接続を使用するアプリケーションを構成して、`www.contoso.com`とその他のすべてのサーバーに 2 つの接続。</span><span class="sxs-lookup"><span data-stu-id="0f1b0-128">The following example removes any connection management list entries for the server `www.adventure-works.com` and then configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0f1b0-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f1b0-129">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="0f1b0-130">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="0f1b0-130">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
