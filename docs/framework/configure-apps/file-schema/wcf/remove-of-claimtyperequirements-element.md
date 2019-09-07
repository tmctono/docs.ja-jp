---
title: <remove>要素<claimTypeRequirements>の
ms.date: 03/30/2017
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
ms.openlocfilehash: 84f4208d3f4581cf7e8c4455bf3f5d78f7e13b9f
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399996"
---
# <a name="remove-of-claimtyperequirements-element"></a><span data-ttu-id="9bd32-102">\<claimTypeRequirements > 要素\<の > を削除します</span><span class="sxs-lookup"><span data-stu-id="9bd32-102">\<remove> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="9bd32-103">フェデレーション資格情報から削除するクレームの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="9bd32-103">Specifies the types of claims to be removed in the federated credential.</span></span>  
  
<span data-ttu-id="9bd32-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9bd32-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9bd32-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9bd32-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9bd32-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<バインド >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="9bd32-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="9bd32-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="9bd32-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="9bd32-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<バインド >** </span><span class="sxs-lookup"><span data-stu-id="9bd32-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="9bd32-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<セキュリティ >** ](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="9bd32-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="9bd32-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<メッセージ >** ](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="9bd32-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="9bd32-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<claimTypeRequirements >** ](claimtyperequirements-for-message.md)</span><span class="sxs-lookup"><span data-stu-id="9bd32-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)</span></span>\
<span data-ttu-id="9bd32-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> の削除**</span><span class="sxs-lookup"><span data-stu-id="9bd32-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bd32-113">構文</span><span class="sxs-lookup"><span data-stu-id="9bd32-113">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <remove claimType="URI" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9bd32-114">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9bd32-114">Attributes and Elements</span></span>  
 <span data-ttu-id="9bd32-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9bd32-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9bd32-116">属性</span><span class="sxs-lookup"><span data-stu-id="9bd32-116">Attributes</span></span>  
  
|<span data-ttu-id="9bd32-117">属性</span><span class="sxs-lookup"><span data-stu-id="9bd32-117">Attribute</span></span>|<span data-ttu-id="9bd32-118">説明</span><span class="sxs-lookup"><span data-stu-id="9bd32-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9bd32-119">claimType</span><span class="sxs-lookup"><span data-stu-id="9bd32-119">claimType</span></span>|<span data-ttu-id="9bd32-120">削除するクレームの種類を定義する URI。</span><span class="sxs-lookup"><span data-stu-id="9bd32-120">A URI that defines the type of a claim to be removed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9bd32-121">子要素</span><span class="sxs-lookup"><span data-stu-id="9bd32-121">Child Elements</span></span>  
 <span data-ttu-id="9bd32-122">なし。</span><span class="sxs-lookup"><span data-stu-id="9bd32-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9bd32-123">親要素</span><span class="sxs-lookup"><span data-stu-id="9bd32-123">Parent Elements</span></span>  
  
|<span data-ttu-id="9bd32-124">要素</span><span class="sxs-lookup"><span data-stu-id="9bd32-124">Element</span></span>|<span data-ttu-id="9bd32-125">説明</span><span class="sxs-lookup"><span data-stu-id="9bd32-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9bd32-126">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="9bd32-126">\<claimTypeRequirements></span></span>](claimtyperequirements-for-message.md)|<span data-ttu-id="9bd32-127">必須のクレームの種類のコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="9bd32-127">Specifies a collection of required claim types.</span></span> <span data-ttu-id="9bd32-128">各要素は <xref:System.ServiceModel.Configuration.ClaimTypeElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="9bd32-128">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="9bd32-129">フェデレーション シナリオでは、サービスが受信資格情報についての要件を記述します。</span><span class="sxs-lookup"><span data-stu-id="9bd32-129">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="9bd32-130">たとえば、受信資格情報は、特定のクレーム タイプのセットを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bd32-130">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="9bd32-131">このコレクションの要素はそれぞれ、フェデレーション資格情報に表示されると予想される必須の要求および省略可能な要求の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="9bd32-131">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9bd32-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="9bd32-132">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
