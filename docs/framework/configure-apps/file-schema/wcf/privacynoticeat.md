---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: 2ff70d3a8636970434582e417e4549ab6b433fc1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738764"
---
# \<privacyNoticeAt>
<span data-ttu-id="6027c-101">`wsFederationHttp` バインディングで使用されるプライバシーに関する声明を指定する構成要素を表します。</span><span class="sxs-lookup"><span data-stu-id="6027c-101">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<privacyNotice>**  
  
## <a name="syntax"></a><span data-ttu-id="6027c-102">構文</span><span class="sxs-lookup"><span data-stu-id="6027c-102">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="6027c-103">Type</span><span class="sxs-lookup"><span data-stu-id="6027c-103">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6027c-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6027c-104">Attributes and Elements</span></span>  
 <span data-ttu-id="6027c-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6027c-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6027c-106">属性</span><span class="sxs-lookup"><span data-stu-id="6027c-106">Attributes</span></span>  
  
|<span data-ttu-id="6027c-107">属性</span><span class="sxs-lookup"><span data-stu-id="6027c-107">Attribute</span></span>|<span data-ttu-id="6027c-108">説明</span><span class="sxs-lookup"><span data-stu-id="6027c-108">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="6027c-109">プライバシーに関する声明の場所を示す URI を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="6027c-109">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="6027c-110">このプライバシーに関する声明のバージョンを指定する整数。</span><span class="sxs-lookup"><span data-stu-id="6027c-110">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6027c-111">子要素</span><span class="sxs-lookup"><span data-stu-id="6027c-111">Child Elements</span></span>  
 <span data-ttu-id="6027c-112">なし。</span><span class="sxs-lookup"><span data-stu-id="6027c-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6027c-113">親要素</span><span class="sxs-lookup"><span data-stu-id="6027c-113">Parent Elements</span></span>  
  
|<span data-ttu-id="6027c-114">要素</span><span class="sxs-lookup"><span data-stu-id="6027c-114">Element</span></span>|<span data-ttu-id="6027c-115">Description</span><span class="sxs-lookup"><span data-stu-id="6027c-115">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="6027c-116">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="6027c-116">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6027c-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="6027c-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="6027c-118">バインド</span><span class="sxs-lookup"><span data-stu-id="6027c-118">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="6027c-119">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="6027c-119">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="6027c-120">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="6027c-120">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
