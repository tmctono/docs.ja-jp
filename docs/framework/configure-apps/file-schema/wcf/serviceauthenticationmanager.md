---
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: cc5ebcf36a10e88d48ed14f1f10dac6396d7b242
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399707"
---
# \<serviceAuthenticationManager>
<span data-ttu-id="ca4fe-101">サービス レベルで転送、メッセージ、または送信元の有効性を確立するワークフロー構成要素を提供します。</span><span class="sxs-lookup"><span data-stu-id="ca4fe-101">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthenticationManager>**  
  
## <a name="syntax"></a><span data-ttu-id="ca4fe-102">構文</span><span class="sxs-lookup"><span data-stu-id="ca4fe-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca4fe-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ca4fe-103">Attributes and Elements</span></span>  
 <span data-ttu-id="ca4fe-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca4fe-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca4fe-105">属性</span><span class="sxs-lookup"><span data-stu-id="ca4fe-105">Attributes</span></span>  
  
|<span data-ttu-id="ca4fe-106">属性</span><span class="sxs-lookup"><span data-stu-id="ca4fe-106">Attribute</span></span>|<span data-ttu-id="ca4fe-107">説明</span><span class="sxs-lookup"><span data-stu-id="ca4fe-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ca4fe-108">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="ca4fe-108">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="ca4fe-109">現在の動作の認証ポリシーの種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="ca4fe-109">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ca4fe-110">子要素</span><span class="sxs-lookup"><span data-stu-id="ca4fe-110">Child Elements</span></span>  
 <span data-ttu-id="ca4fe-111">なし。</span><span class="sxs-lookup"><span data-stu-id="ca4fe-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ca4fe-112">親要素</span><span class="sxs-lookup"><span data-stu-id="ca4fe-112">Parent Elements</span></span>  
  
|<span data-ttu-id="ca4fe-113">要素</span><span class="sxs-lookup"><span data-stu-id="ca4fe-113">Element</span></span>|<span data-ttu-id="ca4fe-114">Description</span><span class="sxs-lookup"><span data-stu-id="ca4fe-114">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="ca4fe-115">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="ca4fe-115">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ca4fe-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca4fe-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
