---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: 624b52c0618362f48063c8f7e7c53c5a68d7de8f
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400036"
---
# <a name="privacynoticeat"></a><span data-ttu-id="938ea-101">\<privacyNoticeAt ></span><span class="sxs-lookup"><span data-stu-id="938ea-101">\<privacyNoticeAt></span></span>
<span data-ttu-id="938ea-102">`wsFederationHttp` バインディングで使用されるプライバシーに関する声明を指定する構成要素を表します。</span><span class="sxs-lookup"><span data-stu-id="938ea-102">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
<span data-ttu-id="938ea-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="938ea-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="938ea-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="938ea-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="938ea-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<バインド >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="938ea-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="938ea-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="938ea-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="938ea-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<バインド >** </span><span class="sxs-lookup"><span data-stu-id="938ea-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="938ea-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<privacyNotice >**</span><span class="sxs-lookup"><span data-stu-id="938ea-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<privacyNotice>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="938ea-109">構文</span><span class="sxs-lookup"><span data-stu-id="938ea-109">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="938ea-110">型</span><span class="sxs-lookup"><span data-stu-id="938ea-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="938ea-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="938ea-111">Attributes and Elements</span></span>  
 <span data-ttu-id="938ea-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="938ea-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="938ea-113">属性</span><span class="sxs-lookup"><span data-stu-id="938ea-113">Attributes</span></span>  
  
|<span data-ttu-id="938ea-114">属性</span><span class="sxs-lookup"><span data-stu-id="938ea-114">Attribute</span></span>|<span data-ttu-id="938ea-115">説明</span><span class="sxs-lookup"><span data-stu-id="938ea-115">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="938ea-116">プライバシーに関する声明の場所を示す URI を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="938ea-116">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="938ea-117">このプライバシーに関する声明のバージョンを指定する整数。</span><span class="sxs-lookup"><span data-stu-id="938ea-117">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="938ea-118">子要素</span><span class="sxs-lookup"><span data-stu-id="938ea-118">Child Elements</span></span>  
 <span data-ttu-id="938ea-119">なし。</span><span class="sxs-lookup"><span data-stu-id="938ea-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="938ea-120">親要素</span><span class="sxs-lookup"><span data-stu-id="938ea-120">Parent Elements</span></span>  
  
|<span data-ttu-id="938ea-121">要素</span><span class="sxs-lookup"><span data-stu-id="938ea-121">Element</span></span>|<span data-ttu-id="938ea-122">説明</span><span class="sxs-lookup"><span data-stu-id="938ea-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="938ea-123">\<binding></span><span class="sxs-lookup"><span data-stu-id="938ea-123">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="938ea-124">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="938ea-124">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="938ea-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="938ea-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="938ea-126">バインディング</span><span class="sxs-lookup"><span data-stu-id="938ea-126">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="938ea-127">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="938ea-127">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="938ea-128">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="938ea-128">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="938ea-129">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="938ea-129">\<customBinding></span></span>](custombinding.md)
