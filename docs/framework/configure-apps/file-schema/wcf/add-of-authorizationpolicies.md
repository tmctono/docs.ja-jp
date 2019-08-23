---
title: <add> の <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
ms.openlocfilehash: 65398c5afa9750f215c95899bb6004cae671123a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920271"
---
# <a name="add-of-authorizationpolicies"></a><span data-ttu-id="7aead-102">\<authorizationpolicies の\<> を追加 ></span><span class="sxs-lookup"><span data-stu-id="7aead-102">\<add> of \<authorizationPolicies></span></span>
<span data-ttu-id="7aead-103">クレームの変換の承認ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="7aead-103">Specifies an authorization policy for claim transformation.</span></span>  
  
 <span data-ttu-id="7aead-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7aead-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7aead-105">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="7aead-105">\<behaviors></span></span>  
<span data-ttu-id="7aead-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="7aead-106">\<behavior></span></span>  
<span data-ttu-id="7aead-107">\<serviceAuthorization ></span><span class="sxs-lookup"><span data-stu-id="7aead-107">\<serviceAuthorization></span></span>  
<span data-ttu-id="7aead-108">\<authorizationPolicies ></span><span class="sxs-lookup"><span data-stu-id="7aead-108">\<authorizationPolicies></span></span>  
<span data-ttu-id="7aead-109">\<add></span><span class="sxs-lookup"><span data-stu-id="7aead-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7aead-110">構文</span><span class="sxs-lookup"><span data-stu-id="7aead-110">Syntax</span></span>  
  
```xml  
<authorizationPolicies>
  <add policyType="String" />
</authorizationPolicies>
```  
  
## <a name="type"></a><span data-ttu-id="7aead-111">型</span><span class="sxs-lookup"><span data-stu-id="7aead-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7aead-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7aead-112">Attributes and Elements</span></span>  
 <span data-ttu-id="7aead-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7aead-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7aead-114">属性</span><span class="sxs-lookup"><span data-stu-id="7aead-114">Attributes</span></span>  
  
|<span data-ttu-id="7aead-115">属性</span><span class="sxs-lookup"><span data-stu-id="7aead-115">Attribute</span></span>|<span data-ttu-id="7aead-116">説明</span><span class="sxs-lookup"><span data-stu-id="7aead-116">Description</span></span>|  
|---------------|-----------------|  
|`policyType`|<span data-ttu-id="7aead-117">必須の文字列属性。</span><span class="sxs-lookup"><span data-stu-id="7aead-117">A required String attribute.</span></span><br /><br /> <span data-ttu-id="7aead-118">Windows Communication Foundation (WCF) アクセス制御モデルは、一連の承認ポリシーを型としてプロビジョニングすることをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="7aead-118">The Windows Communication Foundation (WCF) access control model supports provisioning a set of authorization policies as types.</span></span> <span data-ttu-id="7aead-119">この属性は、入力クレームのセットをクレームの別のセットに変換することを可能にする承認ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="7aead-119">This attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="7aead-120">アクセス制御は、それに基づいて許可または拒否されます。</span><span class="sxs-lookup"><span data-stu-id="7aead-120">Access control can be granted or denied based on that.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7aead-121">子要素</span><span class="sxs-lookup"><span data-stu-id="7aead-121">Child Elements</span></span>  
 <span data-ttu-id="7aead-122">なし。</span><span class="sxs-lookup"><span data-stu-id="7aead-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7aead-123">親要素</span><span class="sxs-lookup"><span data-stu-id="7aead-123">Parent Elements</span></span>  
  
|<span data-ttu-id="7aead-124">要素</span><span class="sxs-lookup"><span data-stu-id="7aead-124">Element</span></span>|<span data-ttu-id="7aead-125">説明</span><span class="sxs-lookup"><span data-stu-id="7aead-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7aead-126">\<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="7aead-126">\<authorizationPolicies></span></span>](authorizationpolicies.md)|<span data-ttu-id="7aead-127">承認ポリシーの種類のコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="7aead-127">Specifies a collection of authorization policy types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7aead-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="7aead-128">Remarks</span></span>  
 <span data-ttu-id="7aead-129">各承認ポリシーは、文字列の単一の必須属性 `policyType` を含みます。</span><span class="sxs-lookup"><span data-stu-id="7aead-129">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="7aead-130">この属性は、入力クレームのセットをクレームの別のセットに変換することを可能にする承認ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="7aead-130">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="7aead-131">アクセス制御は、それに基づいて許可または拒否されます。</span><span class="sxs-lookup"><span data-stu-id="7aead-131">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="7aead-132">承認ポリシーのしくみの詳細については、 <xref:System.IdentityModel.Policy.IAuthorizationPolicy> 「」および「[承認ポリシー](../../../wcf/samples/authorization-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7aead-132">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aead-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="7aead-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="7aead-134">サービス操作へのアクセスの承認</span><span class="sxs-lookup"><span data-stu-id="7aead-134">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="7aead-135">方法: サービスのカスタム承認マネージャーを作成する</span><span class="sxs-lookup"><span data-stu-id="7aead-135">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="7aead-136">\<add></span><span class="sxs-lookup"><span data-stu-id="7aead-136">\<add></span></span>](add-of-authorizationpolicies.md)
- [<span data-ttu-id="7aead-137">承認ポリシー</span><span class="sxs-lookup"><span data-stu-id="7aead-137">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)
