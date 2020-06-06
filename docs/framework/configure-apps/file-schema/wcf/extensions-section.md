---
title: <extensions>下
ms.date: 03/30/2017
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
ms.openlocfilehash: 35621acaf96a80ffa3ffe4a3c6605143c48995a5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855359"
---
# <a name="extensions-section"></a><span data-ttu-id="6b797-102">\<extensions>下</span><span class="sxs-lookup"><span data-stu-id="6b797-102">\<extensions> section</span></span>
<span data-ttu-id="6b797-103">この構成セクションには、拡張のコレクションが含まれています。この拡張のコレクションによってユーザーは、ユーザー定義のバインディング、動作、およびその他の拡張機能を作成できます。</span><span class="sxs-lookup"><span data-stu-id="6b797-103">This configuration section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<extensions>**  
  
## <a name="syntax"></a><span data-ttu-id="6b797-104">構文</span><span class="sxs-lookup"><span data-stu-id="6b797-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b797-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6b797-105">Attributes and Elements</span></span>  
 <span data-ttu-id="6b797-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6b797-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b797-107">属性</span><span class="sxs-lookup"><span data-stu-id="6b797-107">Attributes</span></span>  
 <span data-ttu-id="6b797-108">なし。</span><span class="sxs-lookup"><span data-stu-id="6b797-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6b797-109">子要素</span><span class="sxs-lookup"><span data-stu-id="6b797-109">Child Elements</span></span>  
  
|<span data-ttu-id="6b797-110">要素</span><span class="sxs-lookup"><span data-stu-id="6b797-110">Element</span></span>|<span data-ttu-id="6b797-111">説明</span><span class="sxs-lookup"><span data-stu-id="6b797-111">Description</span></span>|  
|-------------|-----------------|  
|[\<behaviorExtensions>](behaviorextensions.md)|<span data-ttu-id="6b797-112">このセクションには、動作拡張を指定する子要素が含まれています。この動作拡張により、ユーザーはサービスまたはエンドポイントの動作をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="6b797-112">This section contains child elements that specify behavior extensions, which enable the user to customize service or endpoint behaviors.</span></span>|  
|[\<bindingElementExtensions>](bindingelementextensions.md)|<span data-ttu-id="6b797-113">このセクションは、コンピューターまたはアプリケーションの構成ファイルからカスタム バインディング要素を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6b797-113">This section enables the use of a custom binding element from a machine or application configuration file.</span></span>|  
|[\<bindingExtensions>](bindingextensions.md)|<span data-ttu-id="6b797-114">このセクションには、バインディング拡張を指定する子要素が含まれています。このバインディング拡張によって、ユーザーはバインディングをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="6b797-114">This section contains child elements that specify binding extensions, which enable the user to customize bindings.</span></span>|  
|[\<endpointExtensions>](endpointextensions.md)|<span data-ttu-id="6b797-115">このセクションには、標準エンドポイントを登録する子要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b797-115">This section contains child elements that registers standard endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6b797-116">親要素</span><span class="sxs-lookup"><span data-stu-id="6b797-116">Parent Elements</span></span>  
  
|<span data-ttu-id="6b797-117">要素</span><span class="sxs-lookup"><span data-stu-id="6b797-117">Element</span></span>|<span data-ttu-id="6b797-118">説明</span><span class="sxs-lookup"><span data-stu-id="6b797-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6b797-119">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6b797-119">system.ServiceModel</span></span>|<span data-ttu-id="6b797-120">すべての WCF 構成要素のルート要素です。</span><span class="sxs-lookup"><span data-stu-id="6b797-120">The root element of all WCF configuration elements.</span></span>|
