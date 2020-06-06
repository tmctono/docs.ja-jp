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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088501"
---
# <a name="clear-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="65aac-102">webRequestModules の \<clear> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="65aac-102">\<clear> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="65aac-103">アプリケーションから、登録されているすべての Web 要求モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="65aac-103">Removes all registered Web request modules from the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="65aac-104">構文</span><span class="sxs-lookup"><span data-stu-id="65aac-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="65aac-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="65aac-105">Attributes and Elements</span></span>  
 <span data-ttu-id="65aac-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="65aac-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="65aac-107">属性</span><span class="sxs-lookup"><span data-stu-id="65aac-107">Attributes</span></span>  
 <span data-ttu-id="65aac-108">なし。</span><span class="sxs-lookup"><span data-stu-id="65aac-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="65aac-109">子要素</span><span class="sxs-lookup"><span data-stu-id="65aac-109">Child Elements</span></span>  
 <span data-ttu-id="65aac-110">[なし] :</span><span class="sxs-lookup"><span data-stu-id="65aac-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="65aac-111">親要素</span><span class="sxs-lookup"><span data-stu-id="65aac-111">Parent Elements</span></span>  
  
|<span data-ttu-id="65aac-112">**要素**</span><span class="sxs-lookup"><span data-stu-id="65aac-112">**Element**</span></span>|<span data-ttu-id="65aac-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="65aac-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="65aac-114">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="65aac-114">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="65aac-115">ネットワークホストから情報を要求するために使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="65aac-115">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65aac-116">解説</span><span class="sxs-lookup"><span data-stu-id="65aac-116">Remarks</span></span>  
 <span data-ttu-id="65aac-117">要素は、構成 `clear` ファイルで既に定義されている、または構成階層の上位レベルに定義されている、登録済みのすべての Web 要求モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="65aac-117">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="65aac-118">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="65aac-118">Configuration Files</span></span>  
 <span data-ttu-id="65aac-119">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="65aac-119">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="65aac-120">例</span><span class="sxs-lookup"><span data-stu-id="65aac-120">Example</span></span>  
 <span data-ttu-id="65aac-121">次の例では、すべての Web 要求モジュールをクリアし、Web 要求モジュールを HTTP に登録します。</span><span class="sxs-lookup"><span data-stu-id="65aac-121">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="65aac-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="65aac-122">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="65aac-123">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="65aac-123">Network Settings Schema</span></span>](index.md)
