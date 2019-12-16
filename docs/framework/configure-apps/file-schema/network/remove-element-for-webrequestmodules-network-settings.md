---
title: webRequestModules の <remove> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, webRequestModules
- webRequestModules, remove element
- <remove> element, webRequestModules
- <webRequestModules>, remove element
ms.assetid: dd84d2fe-2f4f-457a-9d3c-441d0d21cc10
ms.openlocfilehash: ca3a78a491c61b6e23dab0f96eebceb3157706ae
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089142"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="c0a68-102">webRequestModules の \<remove> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="c0a68-102">\<remove> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="c0a68-103">アプリケーションからカスタム Web 要求モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="c0a68-103">Removes a custom Web request module from the application.</span></span>  
  
<span data-ttu-id="c0a68-104">[**\<configuration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c0a68-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c0a68-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c0a68-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="c0a68-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c0a68-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="c0a68-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span><span class="sxs-lookup"><span data-stu-id="c0a68-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="c0a68-108">構文</span><span class="sxs-lookup"><span data-stu-id="c0a68-108">Syntax</span></span>  
  
```xml  
<remove   
  prefix="URI prefix"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0a68-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c0a68-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c0a68-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c0a68-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0a68-111">属性</span><span class="sxs-lookup"><span data-stu-id="c0a68-111">Attributes</span></span>  
  
|<span data-ttu-id="c0a68-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="c0a68-112">**Attribute**</span></span>|<span data-ttu-id="c0a68-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="c0a68-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="c0a68-114">この Web 要求モジュールによって処理される要求の URI プレフィックス。</span><span class="sxs-lookup"><span data-stu-id="c0a68-114">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c0a68-115">子要素</span><span class="sxs-lookup"><span data-stu-id="c0a68-115">Child Elements</span></span>  
 <span data-ttu-id="c0a68-116">なし。</span><span class="sxs-lookup"><span data-stu-id="c0a68-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c0a68-117">親要素</span><span class="sxs-lookup"><span data-stu-id="c0a68-117">Parent Elements</span></span>  
  
|<span data-ttu-id="c0a68-118">**要素**</span><span class="sxs-lookup"><span data-stu-id="c0a68-118">**Element**</span></span>|<span data-ttu-id="c0a68-119">**説明**</span><span class="sxs-lookup"><span data-stu-id="c0a68-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c0a68-120">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="c0a68-120">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="c0a68-121">ネットワークホストから情報を要求するために使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="c0a68-121">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0a68-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="c0a68-122">Remarks</span></span>  
 <span data-ttu-id="c0a68-123">`remove` 要素は、指定された URI プレフィックスの登録済み Web 要求モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="c0a68-123">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="c0a68-124">`prefix` 属性の値は、有効な URI の先頭の文字 ("`http`"、"`http://www.contoso.com`" など) にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0a68-124">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "`http`", or "`http://www.contoso.com`".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c0a68-125">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="c0a68-125">Configuration Files</span></span>  
 <span data-ttu-id="c0a68-126">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="c0a68-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0a68-127">例</span><span class="sxs-lookup"><span data-stu-id="c0a68-127">Example</span></span>  

<span data-ttu-id="c0a68-128">次の例では、HTTP 用の既存の Web 要求モジュールを削除し、HTTP 要求用の新しいカスタム Web 要求モジュールを `www.contoso.com`に登録します。</span><span class="sxs-lookup"><span data-stu-id="c0a68-128">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to `www.contoso.com`.</span></span>
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <remove prefix="http">  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c0a68-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0a68-129">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="c0a68-130">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="c0a68-130">Network Settings Schema</span></span>](index.md)
