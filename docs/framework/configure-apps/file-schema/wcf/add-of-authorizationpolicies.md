---
title: <add> の <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
ms.openlocfilehash: 532f7f1a74cb3af24d7a1bc26046be901f3cf025
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701412"
---
# <a name="add-of-authorizationpolicies"></a><span data-ttu-id="41740-102">\<add> of \<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="41740-102">\<add> of \<authorizationPolicies></span></span>
<span data-ttu-id="41740-103">クレームの変換の承認ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="41740-103">Specifies an authorization policy for claim transformation.</span></span>  
  
 <span data-ttu-id="41740-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="41740-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="41740-105">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="41740-105">\<behaviors></span></span>  
<span data-ttu-id="41740-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="41740-106">\<behavior></span></span>  
<span data-ttu-id="41740-107">\<serviceAuthorization></span><span class="sxs-lookup"><span data-stu-id="41740-107">\<serviceAuthorization></span></span>  
<span data-ttu-id="41740-108">\<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="41740-108">\<authorizationPolicies></span></span>  
<span data-ttu-id="41740-109">\<add></span><span class="sxs-lookup"><span data-stu-id="41740-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41740-110">構文</span><span class="sxs-lookup"><span data-stu-id="41740-110">Syntax</span></span>  
  
```xml  
<authorizationPolicies>
  <add policyType="String" />
</authorizationPolicies>
```  
  
## <a name="type"></a><span data-ttu-id="41740-111">型</span><span class="sxs-lookup"><span data-stu-id="41740-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="41740-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="41740-112">Attributes and Elements</span></span>  
 <span data-ttu-id="41740-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="41740-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="41740-114">属性</span><span class="sxs-lookup"><span data-stu-id="41740-114">Attributes</span></span>  
  
|<span data-ttu-id="41740-115">属性</span><span class="sxs-lookup"><span data-stu-id="41740-115">Attribute</span></span>|<span data-ttu-id="41740-116">説明</span><span class="sxs-lookup"><span data-stu-id="41740-116">Description</span></span>|  
|---------------|-----------------|  
|`policyType`|<span data-ttu-id="41740-117">必須の文字列属性。</span><span class="sxs-lookup"><span data-stu-id="41740-117">A required String attribute.</span></span><br /><br /> <span data-ttu-id="41740-118">Windows Communication Foundation (WCF) のアクセス制御モデルでは、一連の型として承認ポリシーのプロビジョニングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="41740-118">The Windows Communication Foundation (WCF) access control model supports provisioning a set of authorization policies as types.</span></span> <span data-ttu-id="41740-119">この属性は、入力クレームのセットをクレームの別のセットに変換することを可能にする承認ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="41740-119">This attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="41740-120">アクセス制御は、それに基づいて許可または拒否されます。</span><span class="sxs-lookup"><span data-stu-id="41740-120">Access control can be granted or denied based on that.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="41740-121">子要素</span><span class="sxs-lookup"><span data-stu-id="41740-121">Child Elements</span></span>  
 <span data-ttu-id="41740-122">なし。</span><span class="sxs-lookup"><span data-stu-id="41740-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="41740-123">親要素</span><span class="sxs-lookup"><span data-stu-id="41740-123">Parent Elements</span></span>  
  
|<span data-ttu-id="41740-124">要素</span><span class="sxs-lookup"><span data-stu-id="41740-124">Element</span></span>|<span data-ttu-id="41740-125">説明</span><span class="sxs-lookup"><span data-stu-id="41740-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="41740-126">\<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="41740-126">\<authorizationPolicies></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authorizationpolicies.md)|<span data-ttu-id="41740-127">承認ポリシーの種類のコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="41740-127">Specifies a collection of authorization policy types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41740-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="41740-128">Remarks</span></span>  
 <span data-ttu-id="41740-129">各承認ポリシーは、文字列の単一の必須属性 `policyType` を含みます。</span><span class="sxs-lookup"><span data-stu-id="41740-129">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="41740-130">この属性は、入力クレームのセットをクレームの別のセットに変換することを可能にする承認ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="41740-130">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="41740-131">アクセス制御は、それに基づいて許可または拒否されます。</span><span class="sxs-lookup"><span data-stu-id="41740-131">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="41740-132">承認ポリシーのしくみの詳細については、次を参照してください。<xref:System.IdentityModel.Policy.IAuthorizationPolicy>と[承認ポリシー](../../../../../docs/framework/wcf/samples/authorization-policy.md)します。</span><span class="sxs-lookup"><span data-stu-id="41740-132">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41740-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="41740-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="41740-134">サービス操作へのアクセスの承認</span><span class="sxs-lookup"><span data-stu-id="41740-134">Authorizing Access to Service Operations</span></span>](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="41740-135">方法: サービスのカスタム承認マネージャーを作成します。</span><span class="sxs-lookup"><span data-stu-id="41740-135">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="41740-136">\<add></span><span class="sxs-lookup"><span data-stu-id="41740-136">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-authorizationpolicies.md)
- [<span data-ttu-id="41740-137">承認ポリシー</span><span class="sxs-lookup"><span data-stu-id="41740-137">Authorization Policy</span></span>](../../../../../docs/framework/wcf/samples/authorization-policy.md)
