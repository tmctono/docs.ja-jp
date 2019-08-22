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
ms.openlocfilehash: 20a586e945a889d1fd8a8d4c5c09c8b790c56fc3
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664017"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="1bceb-102">\<webRequestModules の > 要素の削除 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="1bceb-102">\<remove> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="1bceb-103">アプリケーションからカスタム Web 要求モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="1bceb-103">Removes a custom Web request module from the application.</span></span>  
  
 <span data-ttu-id="1bceb-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1bceb-104">\<configuration></span></span>  
<span data-ttu-id="1bceb-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="1bceb-105">\<system.net></span></span>  
<span data-ttu-id="1bceb-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="1bceb-106">\<webRequestModules></span></span>  
<span data-ttu-id="1bceb-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="1bceb-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bceb-108">構文</span><span class="sxs-lookup"><span data-stu-id="1bceb-108">Syntax</span></span>  
  
```xml  
<remove   
  prefix="URI prefix"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1bceb-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1bceb-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1bceb-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1bceb-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1bceb-111">属性</span><span class="sxs-lookup"><span data-stu-id="1bceb-111">Attributes</span></span>  
  
|<span data-ttu-id="1bceb-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="1bceb-112">**Attribute**</span></span>|<span data-ttu-id="1bceb-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="1bceb-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="1bceb-114">この Web 要求モジュールによって処理される要求の URI プレフィックス。</span><span class="sxs-lookup"><span data-stu-id="1bceb-114">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1bceb-115">子要素</span><span class="sxs-lookup"><span data-stu-id="1bceb-115">Child Elements</span></span>  
 <span data-ttu-id="1bceb-116">なし。</span><span class="sxs-lookup"><span data-stu-id="1bceb-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1bceb-117">親要素</span><span class="sxs-lookup"><span data-stu-id="1bceb-117">Parent Elements</span></span>  
  
|<span data-ttu-id="1bceb-118">**要素**</span><span class="sxs-lookup"><span data-stu-id="1bceb-118">**Element**</span></span>|<span data-ttu-id="1bceb-119">**説明**</span><span class="sxs-lookup"><span data-stu-id="1bceb-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1bceb-120">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="1bceb-120">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="1bceb-121">ネットワークホストから情報を要求するために使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="1bceb-121">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1bceb-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="1bceb-122">Remarks</span></span>  
 <span data-ttu-id="1bceb-123">要素`remove`は、指定された URI プレフィックスの登録済み Web 要求モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="1bceb-123">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="1bceb-124">`prefix`属性の値は、有効な URI の先頭の文字 ("`http`"、`http://www.contoso.com`"" など) にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bceb-124">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "`http`", or "`http://www.contoso.com`".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="1bceb-125">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="1bceb-125">Configuration Files</span></span>  
 <span data-ttu-id="1bceb-126">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="1bceb-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bceb-127">例</span><span class="sxs-lookup"><span data-stu-id="1bceb-127">Example</span></span>  

<span data-ttu-id="1bceb-128">次の例では、HTTP 用の既存の Web 要求モジュールを削除し、HTTP 要求用の新しいカスタム`www.contoso.com`web 要求モジュールをに登録します。</span><span class="sxs-lookup"><span data-stu-id="1bceb-128">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to `www.contoso.com`.</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="1bceb-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="1bceb-129">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="1bceb-130">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="1bceb-130">Network Settings Schema</span></span>](index.md)
