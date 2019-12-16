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
ms.openlocfilehash: 5832d120824df75d374fc94cb0aa4e08189cb965
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088501"
---
# <a name="clear-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="30742-102">webRequestModules の \<clear> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="30742-102">\<clear> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="30742-103">アプリケーションから、登録されているすべての Web 要求モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="30742-103">Removes all registered Web request modules from the application.</span></span>  

<span data-ttu-id="30742-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="30742-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="30742-105">&nbsp;&nbsp;[ **\<system.net>** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="30742-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="30742-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<webRequestModules>** ](webrequestmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="30742-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="30742-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**clear>**</span><span class="sxs-lookup"><span data-stu-id="30742-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="30742-108">構文</span><span class="sxs-lookup"><span data-stu-id="30742-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="30742-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="30742-109">Attributes and Elements</span></span>  
 <span data-ttu-id="30742-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="30742-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="30742-111">属性</span><span class="sxs-lookup"><span data-stu-id="30742-111">Attributes</span></span>  
 <span data-ttu-id="30742-112">なし。</span><span class="sxs-lookup"><span data-stu-id="30742-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="30742-113">子要素</span><span class="sxs-lookup"><span data-stu-id="30742-113">Child Elements</span></span>  
 <span data-ttu-id="30742-114">なし。</span><span class="sxs-lookup"><span data-stu-id="30742-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="30742-115">親要素</span><span class="sxs-lookup"><span data-stu-id="30742-115">Parent Elements</span></span>  
  
|<span data-ttu-id="30742-116">**要素**</span><span class="sxs-lookup"><span data-stu-id="30742-116">**Element**</span></span>|<span data-ttu-id="30742-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="30742-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="30742-118">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="30742-118">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="30742-119">ネットワークホストから情報を要求するために使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="30742-119">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30742-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="30742-120">Remarks</span></span>  
 <span data-ttu-id="30742-121">`clear` 要素は、構成ファイルで既に定義されている、または構成階層内の上位レベルのすべての登録済み Web 要求モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="30742-121">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="30742-122">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="30742-122">Configuration Files</span></span>  
 <span data-ttu-id="30742-123">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="30742-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="30742-124">例</span><span class="sxs-lookup"><span data-stu-id="30742-124">Example</span></span>  
 <span data-ttu-id="30742-125">次の例では、すべての Web 要求モジュールをクリアし、Web 要求モジュールを HTTP に登録します。</span><span class="sxs-lookup"><span data-stu-id="30742-125">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="30742-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="30742-126">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="30742-127">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="30742-127">Network Settings Schema</span></span>](index.md)
