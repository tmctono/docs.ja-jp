---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: 5e772e23b21c566c906be854e33b924698dcf3e0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158709"
---
# \<privacyNoticeAt>

<span data-ttu-id="db723-101">`wsFederationHttp` バインディングで使用されるプライバシーに関する声明を指定する構成要素を表します。</span><span class="sxs-lookup"><span data-stu-id="db723-101">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<privacyNotice>**  
  
## <a name="syntax"></a><span data-ttu-id="db723-102">構文</span><span class="sxs-lookup"><span data-stu-id="db723-102">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="db723-103">種類</span><span class="sxs-lookup"><span data-stu-id="db723-103">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="db723-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="db723-104">Attributes and Elements</span></span>  

 <span data-ttu-id="db723-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="db723-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="db723-106">属性</span><span class="sxs-lookup"><span data-stu-id="db723-106">Attributes</span></span>  
  
|<span data-ttu-id="db723-107">属性</span><span class="sxs-lookup"><span data-stu-id="db723-107">Attribute</span></span>|<span data-ttu-id="db723-108">[説明]</span><span class="sxs-lookup"><span data-stu-id="db723-108">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="db723-109">プライバシーに関する声明の場所を示す URI を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="db723-109">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="db723-110">このプライバシーに関する声明のバージョンを指定する整数。</span><span class="sxs-lookup"><span data-stu-id="db723-110">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="db723-111">子要素</span><span class="sxs-lookup"><span data-stu-id="db723-111">Child Elements</span></span>  

 <span data-ttu-id="db723-112">なし。</span><span class="sxs-lookup"><span data-stu-id="db723-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="db723-113">親要素</span><span class="sxs-lookup"><span data-stu-id="db723-113">Parent Elements</span></span>  
  
|<span data-ttu-id="db723-114">要素</span><span class="sxs-lookup"><span data-stu-id="db723-114">Element</span></span>|<span data-ttu-id="db723-115">説明</span><span class="sxs-lookup"><span data-stu-id="db723-115">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="db723-116">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="db723-116">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="db723-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="db723-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="db723-118">バインド</span><span class="sxs-lookup"><span data-stu-id="db723-118">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="db723-119">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="db723-119">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="db723-120">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="db723-120">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
