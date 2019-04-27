---
title: webRequestModules の <clear> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, webRequestModules
- <webRequestModules>, clear element
- webRequestModules, clear element
- clear element, webRequestModules
ms.assetid: 48f38bcb-f30c-4b74-a8f0-1a3caf1aa96f
ms.openlocfilehash: 5dea238629b282776cb45f7b388e655fa557d084
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674598"
---
# <a name="clear-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="b9e5e-102">\<クリア > webRequestModules (ネットワーク設定) の要素</span><span class="sxs-lookup"><span data-stu-id="b9e5e-102">\<clear> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="b9e5e-103">アプリケーションから登録済みのすべての Web 要求モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="b9e5e-103">Removes all registered Web request modules from the application.</span></span>  
  
 <span data-ttu-id="b9e5e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b9e5e-104">\<configuration></span></span>  
<span data-ttu-id="b9e5e-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="b9e5e-105">\<system.net></span></span>  
<span data-ttu-id="b9e5e-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="b9e5e-106">\<webRequestModules></span></span>  
<span data-ttu-id="b9e5e-107">\<clear></span><span class="sxs-lookup"><span data-stu-id="b9e5e-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9e5e-108">構文</span><span class="sxs-lookup"><span data-stu-id="b9e5e-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b9e5e-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b9e5e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b9e5e-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b9e5e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b9e5e-111">属性</span><span class="sxs-lookup"><span data-stu-id="b9e5e-111">Attributes</span></span>  
 <span data-ttu-id="b9e5e-112">なし。</span><span class="sxs-lookup"><span data-stu-id="b9e5e-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b9e5e-113">子要素</span><span class="sxs-lookup"><span data-stu-id="b9e5e-113">Child Elements</span></span>  
 <span data-ttu-id="b9e5e-114">なし。</span><span class="sxs-lookup"><span data-stu-id="b9e5e-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b9e5e-115">親要素</span><span class="sxs-lookup"><span data-stu-id="b9e5e-115">Parent Elements</span></span>  
  
|<span data-ttu-id="b9e5e-116">**要素**</span><span class="sxs-lookup"><span data-stu-id="b9e5e-116">**Element**</span></span>|<span data-ttu-id="b9e5e-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="b9e5e-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b9e5e-118">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="b9e5e-118">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="b9e5e-119">使用してネットワークのホストから情報を要求するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="b9e5e-119">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9e5e-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="b9e5e-120">Remarks</span></span>  
 <span data-ttu-id="b9e5e-121">`clear`要素は、構成ファイルで、または構成階層のより高いレベルで既に定義されているすべての登録済みの Web 要求モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="b9e5e-121">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b9e5e-122">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="b9e5e-122">Configuration Files</span></span>  
 <span data-ttu-id="b9e5e-123">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="b9e5e-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9e5e-124">例</span><span class="sxs-lookup"><span data-stu-id="b9e5e-124">Example</span></span>  
 <span data-ttu-id="b9e5e-125">次の例では、すべての Web 要求モジュールを削除し、http Web 要求モジュールを登録します。</span><span class="sxs-lookup"><span data-stu-id="b9e5e-125">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <clear/>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b9e5e-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9e5e-126">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="b9e5e-127">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="b9e5e-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
