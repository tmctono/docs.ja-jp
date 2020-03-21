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
ms.openlocfilehash: afa1aef8ea71f43a136987ec5b6e1925c6d9fb40
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154726"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="d093b-102">\<web 要求モジュール (ネットワーク設定) の要素>を削除します。</span><span class="sxs-lookup"><span data-stu-id="d093b-102">\<remove> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="d093b-103">カスタム Web 要求モジュールをアプリケーションから削除します。</span><span class="sxs-lookup"><span data-stu-id="d093b-103">Removes a custom Web request module from the application.</span></span>  
  
<span data-ttu-id="d093b-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d093b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d093b-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d093b-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="d093b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>**](webrequestmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d093b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="d093b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>を削除する**</span><span class="sxs-lookup"><span data-stu-id="d093b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="d093b-108">構文</span><span class="sxs-lookup"><span data-stu-id="d093b-108">Syntax</span></span>  
  
```xml  
<remove
  prefix="URI prefix"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d093b-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d093b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d093b-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d093b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d093b-111">属性</span><span class="sxs-lookup"><span data-stu-id="d093b-111">Attributes</span></span>  
  
|<span data-ttu-id="d093b-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="d093b-112">**Attribute**</span></span>|<span data-ttu-id="d093b-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="d093b-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="d093b-114">この Web 要求モジュールによって処理される要求の URI プレフィックス。</span><span class="sxs-lookup"><span data-stu-id="d093b-114">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d093b-115">子要素</span><span class="sxs-lookup"><span data-stu-id="d093b-115">Child Elements</span></span>  
 <span data-ttu-id="d093b-116">[なし] :</span><span class="sxs-lookup"><span data-stu-id="d093b-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d093b-117">親要素</span><span class="sxs-lookup"><span data-stu-id="d093b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="d093b-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="d093b-118">**Element**</span></span>|<span data-ttu-id="d093b-119">**説明**</span><span class="sxs-lookup"><span data-stu-id="d093b-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d093b-120">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="d093b-120">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="d093b-121">ネットワーク ホストから情報を要求するために使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="d093b-121">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d093b-122">解説</span><span class="sxs-lookup"><span data-stu-id="d093b-122">Remarks</span></span>  
 <span data-ttu-id="d093b-123">要素`remove`は、指定された URI プレフィックスに登録されている Web 要求モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="d093b-123">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="d093b-124">属性の`prefix`値は、有効な URI の先頭文字である必要があります。`http``http://www.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="d093b-124">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "`http`", or "`http://www.contoso.com`".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="d093b-125">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="d093b-125">Configuration Files</span></span>  
 <span data-ttu-id="d093b-126">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="d093b-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d093b-127">例</span><span class="sxs-lookup"><span data-stu-id="d093b-127">Example</span></span>  

<span data-ttu-id="d093b-128">次の例では、HTTP 用の既存の Web 要求モジュールを削除し、HTTP 要求用の新`www.contoso.com`しいカスタム Web 要求モジュールを登録します。</span><span class="sxs-lookup"><span data-stu-id="d093b-128">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to `www.contoso.com`.</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="d093b-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="d093b-129">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="d093b-130">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="d093b-130">Network Settings Schema</span></span>](index.md)
