---
title: <clear><claimTypeRequirements>要素の
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: 01f101f7d0dd5da6a834a4ffb2c7e09df0e23cd8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400530"
---
# <a name="clear-of-claimtyperequirements-element"></a><span data-ttu-id="effc0-102">\<clear>\<claimTypeRequirements>要素の</span><span class="sxs-lookup"><span data-stu-id="effc0-102">\<clear> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="effc0-103">すべてのクレームの種類をフェデレーション資格情報から削除するように指定します。</span><span class="sxs-lookup"><span data-stu-id="effc0-103">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="effc0-104">これにより、コレクションの初期値を確実に空にできます。</span><span class="sxs-lookup"><span data-stu-id="effc0-104">This ensures that the collection starts empty.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**  
  
## <a name="syntax"></a><span data-ttu-id="effc0-105">構文</span><span class="sxs-lookup"><span data-stu-id="effc0-105">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="effc0-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="effc0-106">Attributes and Elements</span></span>  
 <span data-ttu-id="effc0-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="effc0-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="effc0-108">属性</span><span class="sxs-lookup"><span data-stu-id="effc0-108">Attributes</span></span>  
 <span data-ttu-id="effc0-109">なし。</span><span class="sxs-lookup"><span data-stu-id="effc0-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="effc0-110">子要素</span><span class="sxs-lookup"><span data-stu-id="effc0-110">Child Elements</span></span>  
 <span data-ttu-id="effc0-111">[なし] :</span><span class="sxs-lookup"><span data-stu-id="effc0-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="effc0-112">親要素</span><span class="sxs-lookup"><span data-stu-id="effc0-112">Parent Elements</span></span>  
  
|<span data-ttu-id="effc0-113">要素</span><span class="sxs-lookup"><span data-stu-id="effc0-113">Element</span></span>|<span data-ttu-id="effc0-114">説明</span><span class="sxs-lookup"><span data-stu-id="effc0-114">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-for-message.md)|<span data-ttu-id="effc0-115">必須のクレームの種類のコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="effc0-115">Specifies a collection of required claim types.</span></span> <span data-ttu-id="effc0-116">各要素は <xref:System.ServiceModel.Configuration.ClaimTypeElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="effc0-116">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="effc0-117">フェデレーション シナリオでは、サービスが受信資格情報についての要件を記述します。</span><span class="sxs-lookup"><span data-stu-id="effc0-117">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="effc0-118">たとえば、受信資格情報は、特定のクレーム タイプのセットを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="effc0-118">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="effc0-119">このコレクションの要素はそれぞれ、フェデレーション資格情報に表示されると予想される必須の要求および省略可能な要求の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="effc0-119">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="effc0-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="effc0-120">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
