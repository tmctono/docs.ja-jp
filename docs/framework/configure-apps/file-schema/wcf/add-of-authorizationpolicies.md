---
title: <add> の <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
ms.openlocfilehash: e2597bc51e788c919bfe3ce3422ae2911cc6b33b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400696"
---
# <a name="add-of-authorizationpolicies"></a><span data-ttu-id="21a94-102">\<authorizationpolicies の\<> を追加 ></span><span class="sxs-lookup"><span data-stu-id="21a94-102">\<add> of \<authorizationPolicies></span></span>
<span data-ttu-id="21a94-103">クレームの変換の承認ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="21a94-103">Specifies an authorization policy for claim transformation.</span></span>  
  
<span data-ttu-id="21a94-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="21a94-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="21a94-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="21a94-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="21a94-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="21a94-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="21a94-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="21a94-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="21a94-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="21a94-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="21a94-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceAuthorization >** ](serviceauthorization-element.md)</span><span class="sxs-lookup"><span data-stu-id="21a94-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceAuthorization>**](serviceauthorization-element.md)</span></span>\
<span data-ttu-id="21a94-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<authorizationPolicies >** ](authorizationpolicies.md)</span><span class="sxs-lookup"><span data-stu-id="21a94-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<authorizationPolicies>**](authorizationpolicies.md)</span></span>\
<span data-ttu-id="21a94-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> の追加**</span><span class="sxs-lookup"><span data-stu-id="21a94-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21a94-112">構文</span><span class="sxs-lookup"><span data-stu-id="21a94-112">Syntax</span></span>  
  
```xml  
<authorizationPolicies>
  <add policyType="String" />
</authorizationPolicies>
```  
  
## <a name="type"></a><span data-ttu-id="21a94-113">型</span><span class="sxs-lookup"><span data-stu-id="21a94-113">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="21a94-114">属性および要素</span><span class="sxs-lookup"><span data-stu-id="21a94-114">Attributes and Elements</span></span>  
 <span data-ttu-id="21a94-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="21a94-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="21a94-116">属性</span><span class="sxs-lookup"><span data-stu-id="21a94-116">Attributes</span></span>  
  
|<span data-ttu-id="21a94-117">属性</span><span class="sxs-lookup"><span data-stu-id="21a94-117">Attribute</span></span>|<span data-ttu-id="21a94-118">説明</span><span class="sxs-lookup"><span data-stu-id="21a94-118">Description</span></span>|  
|---------------|-----------------|  
|`policyType`|<span data-ttu-id="21a94-119">必須の文字列属性。</span><span class="sxs-lookup"><span data-stu-id="21a94-119">A required String attribute.</span></span><br /><br /> <span data-ttu-id="21a94-120">Windows Communication Foundation (WCF) アクセス制御モデルは、一連の承認ポリシーを型としてプロビジョニングすることをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="21a94-120">The Windows Communication Foundation (WCF) access control model supports provisioning a set of authorization policies as types.</span></span> <span data-ttu-id="21a94-121">この属性は、入力クレームのセットをクレームの別のセットに変換することを可能にする承認ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="21a94-121">This attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="21a94-122">アクセス制御は、それに基づいて許可または拒否されます。</span><span class="sxs-lookup"><span data-stu-id="21a94-122">Access control can be granted or denied based on that.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="21a94-123">子要素</span><span class="sxs-lookup"><span data-stu-id="21a94-123">Child Elements</span></span>  
 <span data-ttu-id="21a94-124">なし。</span><span class="sxs-lookup"><span data-stu-id="21a94-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="21a94-125">親要素</span><span class="sxs-lookup"><span data-stu-id="21a94-125">Parent Elements</span></span>  
  
|<span data-ttu-id="21a94-126">要素</span><span class="sxs-lookup"><span data-stu-id="21a94-126">Element</span></span>|<span data-ttu-id="21a94-127">説明</span><span class="sxs-lookup"><span data-stu-id="21a94-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21a94-128">\<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="21a94-128">\<authorizationPolicies></span></span>](authorizationpolicies.md)|<span data-ttu-id="21a94-129">承認ポリシーの種類のコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="21a94-129">Specifies a collection of authorization policy types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21a94-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="21a94-130">Remarks</span></span>  
 <span data-ttu-id="21a94-131">各承認ポリシーは、文字列の単一の必須属性 `policyType` を含みます。</span><span class="sxs-lookup"><span data-stu-id="21a94-131">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="21a94-132">この属性は、入力クレームのセットをクレームの別のセットに変換することを可能にする承認ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="21a94-132">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="21a94-133">アクセス制御は、それに基づいて許可または拒否されます。</span><span class="sxs-lookup"><span data-stu-id="21a94-133">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="21a94-134">承認ポリシーのしくみの詳細については、 <xref:System.IdentityModel.Policy.IAuthorizationPolicy> 「」および「[承認ポリシー](../../../wcf/samples/authorization-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21a94-134">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21a94-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="21a94-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="21a94-136">サービス操作へのアクセスの承認</span><span class="sxs-lookup"><span data-stu-id="21a94-136">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="21a94-137">方法: サービスのカスタム承認マネージャーを作成する</span><span class="sxs-lookup"><span data-stu-id="21a94-137">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="21a94-138">\<add></span><span class="sxs-lookup"><span data-stu-id="21a94-138">\<add></span></span>](add-of-authorizationpolicies.md)
- [<span data-ttu-id="21a94-139">承認ポリシー</span><span class="sxs-lookup"><span data-stu-id="21a94-139">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)
