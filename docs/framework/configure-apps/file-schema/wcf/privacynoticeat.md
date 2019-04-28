---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: e2ce2111e4bb26cc6a51b4a772b1d8a4d3238c70
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783163"
---
# <a name="privacynoticeat"></a><span data-ttu-id="a729d-101">\<privacyNoticeAt></span><span class="sxs-lookup"><span data-stu-id="a729d-101">\<privacyNoticeAt></span></span>
<span data-ttu-id="a729d-102">`wsFederationHttp` バインディングで使用されるプライバシーに関する声明を指定する構成要素を表します。</span><span class="sxs-lookup"><span data-stu-id="a729d-102">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
 <span data-ttu-id="a729d-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a729d-103">\<system.serviceModel></span></span>  
<span data-ttu-id="a729d-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="a729d-104">\<bindings></span></span>  
<span data-ttu-id="a729d-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="a729d-105">\<customBinding></span></span>  
<span data-ttu-id="a729d-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="a729d-106">\<binding></span></span>  
<span data-ttu-id="a729d-107">\<privacyNotice></span><span class="sxs-lookup"><span data-stu-id="a729d-107">\<privacyNotice></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a729d-108">構文</span><span class="sxs-lookup"><span data-stu-id="a729d-108">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="a729d-109">型</span><span class="sxs-lookup"><span data-stu-id="a729d-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a729d-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a729d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a729d-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a729d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a729d-112">属性</span><span class="sxs-lookup"><span data-stu-id="a729d-112">Attributes</span></span>  
  
|<span data-ttu-id="a729d-113">属性</span><span class="sxs-lookup"><span data-stu-id="a729d-113">Attribute</span></span>|<span data-ttu-id="a729d-114">説明</span><span class="sxs-lookup"><span data-stu-id="a729d-114">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="a729d-115">プライバシーに関する声明の場所を示す URI を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="a729d-115">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="a729d-116">このプライバシーに関する声明のバージョンを指定する整数。</span><span class="sxs-lookup"><span data-stu-id="a729d-116">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a729d-117">子要素</span><span class="sxs-lookup"><span data-stu-id="a729d-117">Child Elements</span></span>  
 <span data-ttu-id="a729d-118">なし。</span><span class="sxs-lookup"><span data-stu-id="a729d-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a729d-119">親要素</span><span class="sxs-lookup"><span data-stu-id="a729d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="a729d-120">要素</span><span class="sxs-lookup"><span data-stu-id="a729d-120">Element</span></span>|<span data-ttu-id="a729d-121">説明</span><span class="sxs-lookup"><span data-stu-id="a729d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a729d-122">\<binding></span><span class="sxs-lookup"><span data-stu-id="a729d-122">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="a729d-123">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="a729d-123">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a729d-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="a729d-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="a729d-125">バインディング</span><span class="sxs-lookup"><span data-stu-id="a729d-125">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="a729d-126">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="a729d-126">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="a729d-127">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="a729d-127">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="a729d-128">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="a729d-128">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
