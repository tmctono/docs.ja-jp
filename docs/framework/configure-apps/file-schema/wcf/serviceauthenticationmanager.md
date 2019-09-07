---
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: cc5ebcf36a10e88d48ed14f1f10dac6396d7b242
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399707"
---
# <a name="serviceauthenticationmanager"></a><span data-ttu-id="85a94-101">\<serviceAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="85a94-101">\<serviceAuthenticationManager></span></span>
<span data-ttu-id="85a94-102">サービス レベルで転送、メッセージ、または送信元の有効性を確立するワークフロー構成要素を提供します。</span><span class="sxs-lookup"><span data-stu-id="85a94-102">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
<span data-ttu-id="85a94-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="85a94-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="85a94-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="85a94-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="85a94-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="85a94-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="85a94-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="85a94-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="85a94-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="85a94-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="85a94-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceAuthenticationManager >**</span><span class="sxs-lookup"><span data-stu-id="85a94-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthenticationManager>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85a94-109">構文</span><span class="sxs-lookup"><span data-stu-id="85a94-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85a94-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="85a94-110">Attributes and Elements</span></span>  
 <span data-ttu-id="85a94-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="85a94-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85a94-112">属性</span><span class="sxs-lookup"><span data-stu-id="85a94-112">Attributes</span></span>  
  
|<span data-ttu-id="85a94-113">属性</span><span class="sxs-lookup"><span data-stu-id="85a94-113">Attribute</span></span>|<span data-ttu-id="85a94-114">説明</span><span class="sxs-lookup"><span data-stu-id="85a94-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="85a94-115">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="85a94-115">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="85a94-116">現在の動作の認証ポリシーの種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="85a94-116">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="85a94-117">子要素</span><span class="sxs-lookup"><span data-stu-id="85a94-117">Child Elements</span></span>  
 <span data-ttu-id="85a94-118">なし。</span><span class="sxs-lookup"><span data-stu-id="85a94-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="85a94-119">親要素</span><span class="sxs-lookup"><span data-stu-id="85a94-119">Parent Elements</span></span>  
  
|<span data-ttu-id="85a94-120">要素</span><span class="sxs-lookup"><span data-stu-id="85a94-120">Element</span></span>|<span data-ttu-id="85a94-121">説明</span><span class="sxs-lookup"><span data-stu-id="85a94-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="85a94-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="85a94-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="85a94-123">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="85a94-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="85a94-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="85a94-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
