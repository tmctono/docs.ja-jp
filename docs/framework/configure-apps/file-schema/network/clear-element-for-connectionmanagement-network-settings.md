---
title: connectionManagement の <clear> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, connectionManagement
- connectionManagement, clear element
- clear element, connectionManagement
- <connectionManagement>, clear element
ms.assetid: fb259282-84c4-4dc4-a226-78d904a6edc3
ms.openlocfilehash: 733c70b0575de7e2635afaab58ad48591f035fc0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705246"
---
# <a name="clear-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="cde3a-102">connectionManagement の \<clear> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="cde3a-102">\<clear> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="cde3a-103">接続の管理の一覧をクリアします。</span><span class="sxs-lookup"><span data-stu-id="cde3a-103">Clears the connection management list.</span></span>  
  
 <span data-ttu-id="cde3a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="cde3a-104">\<configuration></span></span>  
<span data-ttu-id="cde3a-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="cde3a-105">\<system.net></span></span>  
<span data-ttu-id="cde3a-106">\<connectionManagement></span><span class="sxs-lookup"><span data-stu-id="cde3a-106">\<connectionManagement></span></span>  
<span data-ttu-id="cde3a-107">\<clear></span><span class="sxs-lookup"><span data-stu-id="cde3a-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cde3a-108">構文</span><span class="sxs-lookup"><span data-stu-id="cde3a-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cde3a-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cde3a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="cde3a-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="cde3a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cde3a-111">属性</span><span class="sxs-lookup"><span data-stu-id="cde3a-111">Attributes</span></span>  
 <span data-ttu-id="cde3a-112">なし。</span><span class="sxs-lookup"><span data-stu-id="cde3a-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cde3a-113">子要素</span><span class="sxs-lookup"><span data-stu-id="cde3a-113">Child Elements</span></span>  
 <span data-ttu-id="cde3a-114">なし。</span><span class="sxs-lookup"><span data-stu-id="cde3a-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cde3a-115">親要素</span><span class="sxs-lookup"><span data-stu-id="cde3a-115">Parent Elements</span></span>  
  
|<span data-ttu-id="cde3a-116">**要素**</span><span class="sxs-lookup"><span data-stu-id="cde3a-116">**Element**</span></span>|<span data-ttu-id="cde3a-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="cde3a-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="cde3a-118">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="cde3a-118">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="cde3a-119">ネットワーク ホストへの接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="cde3a-119">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cde3a-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="cde3a-120">Remarks</span></span>  
 <span data-ttu-id="cde3a-121">`clear`要素の接続管理の一覧からすべてのエントリをクリアします。</span><span class="sxs-lookup"><span data-stu-id="cde3a-121">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="cde3a-122">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="cde3a-122">Configuration Files</span></span>  
 <span data-ttu-id="cde3a-123">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="cde3a-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cde3a-124">例</span><span class="sxs-lookup"><span data-stu-id="cde3a-124">Example</span></span>  
 <span data-ttu-id="cde3a-125">次の例は、接続管理の一覧をクリアし、サーバーの接続管理エントリを追加し、`www.contoso.com`およびその他のすべてのネットワーク ホスト。</span><span class="sxs-lookup"><span data-stu-id="cde3a-125">The following example clears the connection management list and then adds new connection management entries for the server `www.contoso.com` and all other network hosts.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <clear/>  
      <add address = "http://www.contoso.com" maxconnection = "4" />  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cde3a-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="cde3a-126">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="cde3a-127">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="cde3a-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
