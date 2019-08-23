---
title: <extensions>下
ms.date: 03/30/2017
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
ms.openlocfilehash: 4c8b5fe6eef1863ee3f02cb761a3aac61406e446
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918968"
---
# <a name="extensions-section"></a><span data-ttu-id="097a7-102">\<拡張機能 > セクション</span><span class="sxs-lookup"><span data-stu-id="097a7-102">\<extensions> section</span></span>
<span data-ttu-id="097a7-103">この構成セクションには、拡張のコレクションが含まれています。この拡張のコレクションによってユーザーは、ユーザー定義のバインディング、動作、およびその他の拡張機能を作成できます。</span><span class="sxs-lookup"><span data-stu-id="097a7-103">This configuration section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>  
  
<span data-ttu-id="097a7-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="097a7-104">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="097a7-105">構文</span><span class="sxs-lookup"><span data-stu-id="097a7-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="097a7-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="097a7-106">Attributes and Elements</span></span>  
 <span data-ttu-id="097a7-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="097a7-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="097a7-108">属性</span><span class="sxs-lookup"><span data-stu-id="097a7-108">Attributes</span></span>  
 <span data-ttu-id="097a7-109">なし。</span><span class="sxs-lookup"><span data-stu-id="097a7-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="097a7-110">子要素</span><span class="sxs-lookup"><span data-stu-id="097a7-110">Child Elements</span></span>  
  
|<span data-ttu-id="097a7-111">要素</span><span class="sxs-lookup"><span data-stu-id="097a7-111">Element</span></span>|<span data-ttu-id="097a7-112">説明</span><span class="sxs-lookup"><span data-stu-id="097a7-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="097a7-113">\<動作拡張機能 ></span><span class="sxs-lookup"><span data-stu-id="097a7-113">\<behaviorExtensions></span></span>](behaviorextensions.md)|<span data-ttu-id="097a7-114">このセクションには、動作拡張を指定する子要素が含まれています。この動作拡張により、ユーザーはサービスまたはエンドポイントの動作をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="097a7-114">This section contains child elements that specify behavior extensions, which enable the user to customize service or endpoint behaviors.</span></span>|  
|[<span data-ttu-id="097a7-115">\<bindingElementExtensions ></span><span class="sxs-lookup"><span data-stu-id="097a7-115">\<bindingElementExtensions></span></span>](bindingelementextensions.md)|<span data-ttu-id="097a7-116">このセクションは、コンピューターまたはアプリケーションの構成ファイルからカスタム バインディング要素を使用できます。</span><span class="sxs-lookup"><span data-stu-id="097a7-116">This section enables the use of a custom binding element from a machine or application configuration file.</span></span>|  
|[<span data-ttu-id="097a7-117">\<bindingExtensions ></span><span class="sxs-lookup"><span data-stu-id="097a7-117">\<bindingExtensions></span></span>](bindingextensions.md)|<span data-ttu-id="097a7-118">このセクションには、バインディング拡張を指定する子要素が含まれています。このバインディング拡張によって、ユーザーはバインディングをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="097a7-118">This section contains child elements that specify binding extensions, which enable the user to customize bindings.</span></span>|  
|[<span data-ttu-id="097a7-119">\<endpointExtensions></span><span class="sxs-lookup"><span data-stu-id="097a7-119">\<endpointExtensions></span></span>](endpointextensions.md)|<span data-ttu-id="097a7-120">このセクションには、標準エンドポイントを登録する子要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="097a7-120">This section contains child elements that registers standard endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="097a7-121">親要素</span><span class="sxs-lookup"><span data-stu-id="097a7-121">Parent Elements</span></span>  
  
|<span data-ttu-id="097a7-122">要素</span><span class="sxs-lookup"><span data-stu-id="097a7-122">Element</span></span>|<span data-ttu-id="097a7-123">説明</span><span class="sxs-lookup"><span data-stu-id="097a7-123">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="097a7-124">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="097a7-124">system.ServiceModel</span></span>|<span data-ttu-id="097a7-125">すべての WCF 構成要素のルート要素です。</span><span class="sxs-lookup"><span data-stu-id="097a7-125">The root element of all WCF configuration elements.</span></span>|
