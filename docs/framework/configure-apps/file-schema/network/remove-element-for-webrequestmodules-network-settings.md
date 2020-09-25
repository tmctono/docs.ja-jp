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
ms.openlocfilehash: 65e8b1f2088015b86d4f981f07875d236a11a617
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176189"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="ca501-102">webRequestModules の \<remove> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="ca501-102">\<remove> Element for webRequestModules (Network Settings)</span></span>

<span data-ttu-id="ca501-103">アプリケーションからカスタム Web 要求モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="ca501-103">Removes a custom Web request module from the application.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**
  
## <a name="syntax"></a><span data-ttu-id="ca501-104">構文</span><span class="sxs-lookup"><span data-stu-id="ca501-104">Syntax</span></span>  
  
```xml  
<remove
  prefix="URI prefix"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca501-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ca501-105">Attributes and Elements</span></span>  

 <span data-ttu-id="ca501-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca501-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca501-107">属性</span><span class="sxs-lookup"><span data-stu-id="ca501-107">Attributes</span></span>  
  
|<span data-ttu-id="ca501-108">**属性**</span><span class="sxs-lookup"><span data-stu-id="ca501-108">**Attribute**</span></span>|<span data-ttu-id="ca501-109">**説明**</span><span class="sxs-lookup"><span data-stu-id="ca501-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="ca501-110">この Web 要求モジュールによって処理される要求の URI プレフィックス。</span><span class="sxs-lookup"><span data-stu-id="ca501-110">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ca501-111">子要素</span><span class="sxs-lookup"><span data-stu-id="ca501-111">Child Elements</span></span>  

 <span data-ttu-id="ca501-112">なし。</span><span class="sxs-lookup"><span data-stu-id="ca501-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ca501-113">親要素</span><span class="sxs-lookup"><span data-stu-id="ca501-113">Parent Elements</span></span>  
  
|<span data-ttu-id="ca501-114">**要素**</span><span class="sxs-lookup"><span data-stu-id="ca501-114">**Element**</span></span>|<span data-ttu-id="ca501-115">**説明**</span><span class="sxs-lookup"><span data-stu-id="ca501-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ca501-116">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="ca501-116">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="ca501-117">ネットワークホストから情報を要求するために使用するモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="ca501-117">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca501-118">解説</span><span class="sxs-lookup"><span data-stu-id="ca501-118">Remarks</span></span>  

 <span data-ttu-id="ca501-119">要素は、 `remove` 指定された URI プレフィックスの登録済み Web 要求モジュールを削除します。</span><span class="sxs-lookup"><span data-stu-id="ca501-119">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="ca501-120">属性の値は、 `prefix` 有効な URI の先頭の文字 (""、"" など) にする必要があり `http` `http://www.contoso.com` ます。</span><span class="sxs-lookup"><span data-stu-id="ca501-120">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "`http`", or "`http://www.contoso.com`".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ca501-121">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="ca501-121">Configuration Files</span></span>  

 <span data-ttu-id="ca501-122">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="ca501-122">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca501-123">例</span><span class="sxs-lookup"><span data-stu-id="ca501-123">Example</span></span>  

<span data-ttu-id="ca501-124">次の例では、HTTP 用の既存の Web 要求モジュールを削除し、HTTP 要求用の新しいカスタム Web 要求モジュールをに登録し `www.contoso.com` ます。</span><span class="sxs-lookup"><span data-stu-id="ca501-124">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to `www.contoso.com`.</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="ca501-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca501-125">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="ca501-126">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="ca501-126">Network Settings Schema</span></span>](index.md)
