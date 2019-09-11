---
title: <extensions>下
ms.date: 03/30/2017
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
ms.openlocfilehash: 35621acaf96a80ffa3ffe4a3c6605143c48995a5
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855359"
---
# <a name="extensions-section"></a><span data-ttu-id="f74f7-102">\<拡張機能 > セクション</span><span class="sxs-lookup"><span data-stu-id="f74f7-102">\<extensions> section</span></span>
<span data-ttu-id="f74f7-103">この構成セクションには、拡張のコレクションが含まれています。この拡張のコレクションによってユーザーは、ユーザー定義のバインディング、動作、およびその他の拡張機能を作成できます。</span><span class="sxs-lookup"><span data-stu-id="f74f7-103">This configuration section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>  
  
<span data-ttu-id="f74f7-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f74f7-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f74f7-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f74f7-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f74f7-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<拡張機能 >**</span><span class="sxs-lookup"><span data-stu-id="f74f7-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<extensions>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f74f7-107">構文</span><span class="sxs-lookup"><span data-stu-id="f74f7-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <extensions>
    <bindingExtensions>
    </bindingExtensions>
    <behaviorExtensions>
    </behaviorExtensions>
    <bindingElementExtensions>
    </bindingElementExtensions>
    <endpointExtensions>
    </endpointExtensions>
  </extensions>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f74f7-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f74f7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f74f7-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f74f7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f74f7-110">属性</span><span class="sxs-lookup"><span data-stu-id="f74f7-110">Attributes</span></span>  
 <span data-ttu-id="f74f7-111">なし。</span><span class="sxs-lookup"><span data-stu-id="f74f7-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f74f7-112">子要素</span><span class="sxs-lookup"><span data-stu-id="f74f7-112">Child Elements</span></span>  
  
|<span data-ttu-id="f74f7-113">要素</span><span class="sxs-lookup"><span data-stu-id="f74f7-113">Element</span></span>|<span data-ttu-id="f74f7-114">説明</span><span class="sxs-lookup"><span data-stu-id="f74f7-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f74f7-115">\<動作拡張機能 ></span><span class="sxs-lookup"><span data-stu-id="f74f7-115">\<behaviorExtensions></span></span>](behaviorextensions.md)|<span data-ttu-id="f74f7-116">このセクションには、動作拡張を指定する子要素が含まれています。この動作拡張により、ユーザーはサービスまたはエンドポイントの動作をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="f74f7-116">This section contains child elements that specify behavior extensions, which enable the user to customize service or endpoint behaviors.</span></span>|  
|[<span data-ttu-id="f74f7-117">\<bindingElementExtensions ></span><span class="sxs-lookup"><span data-stu-id="f74f7-117">\<bindingElementExtensions></span></span>](bindingelementextensions.md)|<span data-ttu-id="f74f7-118">このセクションは、コンピューターまたはアプリケーションの構成ファイルからカスタム バインディング要素を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f74f7-118">This section enables the use of a custom binding element from a machine or application configuration file.</span></span>|  
|[<span data-ttu-id="f74f7-119">\<bindingExtensions ></span><span class="sxs-lookup"><span data-stu-id="f74f7-119">\<bindingExtensions></span></span>](bindingextensions.md)|<span data-ttu-id="f74f7-120">このセクションには、バインディング拡張を指定する子要素が含まれています。このバインディング拡張によって、ユーザーはバインディングをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="f74f7-120">This section contains child elements that specify binding extensions, which enable the user to customize bindings.</span></span>|  
|[<span data-ttu-id="f74f7-121">\<endpointExtensions></span><span class="sxs-lookup"><span data-stu-id="f74f7-121">\<endpointExtensions></span></span>](endpointextensions.md)|<span data-ttu-id="f74f7-122">このセクションには、標準エンドポイントを登録する子要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f74f7-122">This section contains child elements that registers standard endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f74f7-123">親要素</span><span class="sxs-lookup"><span data-stu-id="f74f7-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f74f7-124">要素</span><span class="sxs-lookup"><span data-stu-id="f74f7-124">Element</span></span>|<span data-ttu-id="f74f7-125">説明</span><span class="sxs-lookup"><span data-stu-id="f74f7-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f74f7-126">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f74f7-126">system.ServiceModel</span></span>|<span data-ttu-id="f74f7-127">すべての WCF 構成要素のルート要素です。</span><span class="sxs-lookup"><span data-stu-id="f74f7-127">The root element of all WCF configuration elements.</span></span>|
