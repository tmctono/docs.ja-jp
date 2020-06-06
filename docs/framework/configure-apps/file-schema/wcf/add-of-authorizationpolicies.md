---
title: <add> の <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
ms.openlocfilehash: e2597bc51e788c919bfe3ce3422ae2911cc6b33b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400696"
---
# <a name="add-of-authorizationpolicies"></a><span data-ttu-id="75306-102">\<add> の \<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="75306-102">\<add> of \<authorizationPolicies></span></span>
<span data-ttu-id="75306-103">クレームの変換の承認ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="75306-103">Specifies an authorization policy for claim transformation.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceAuthorization>**](serviceauthorization-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<authorizationPolicies>**](authorizationpolicies.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="75306-104">構文</span><span class="sxs-lookup"><span data-stu-id="75306-104">Syntax</span></span>  
  
```xml  
<authorizationPolicies>
  <add policyType="String" />
</authorizationPolicies>
```  
  
## <a name="type"></a><span data-ttu-id="75306-105">Type</span><span class="sxs-lookup"><span data-stu-id="75306-105">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75306-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="75306-106">Attributes and Elements</span></span>  
 <span data-ttu-id="75306-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="75306-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75306-108">属性</span><span class="sxs-lookup"><span data-stu-id="75306-108">Attributes</span></span>  
  
|<span data-ttu-id="75306-109">属性</span><span class="sxs-lookup"><span data-stu-id="75306-109">Attribute</span></span>|<span data-ttu-id="75306-110">説明</span><span class="sxs-lookup"><span data-stu-id="75306-110">Description</span></span>|  
|---------------|-----------------|  
|`policyType`|<span data-ttu-id="75306-111">必須の文字列属性。</span><span class="sxs-lookup"><span data-stu-id="75306-111">A required String attribute.</span></span><br /><br /> <span data-ttu-id="75306-112">Windows Communication Foundation (WCF) アクセス制御モデルは、一連の承認ポリシーを型としてプロビジョニングすることをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="75306-112">The Windows Communication Foundation (WCF) access control model supports provisioning a set of authorization policies as types.</span></span> <span data-ttu-id="75306-113">この属性は、入力クレームのセットをクレームの別のセットに変換することを可能にする承認ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="75306-113">This attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="75306-114">アクセス制御は、それに基づいて許可または拒否されます。</span><span class="sxs-lookup"><span data-stu-id="75306-114">Access control can be granted or denied based on that.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="75306-115">子要素</span><span class="sxs-lookup"><span data-stu-id="75306-115">Child Elements</span></span>  
 <span data-ttu-id="75306-116">なし。</span><span class="sxs-lookup"><span data-stu-id="75306-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="75306-117">親要素</span><span class="sxs-lookup"><span data-stu-id="75306-117">Parent Elements</span></span>  
  
|<span data-ttu-id="75306-118">要素</span><span class="sxs-lookup"><span data-stu-id="75306-118">Element</span></span>|<span data-ttu-id="75306-119">Description</span><span class="sxs-lookup"><span data-stu-id="75306-119">Description</span></span>|  
|-------------|-----------------|  
|[\<authorizationPolicies>](authorizationpolicies.md)|<span data-ttu-id="75306-120">承認ポリシーの種類のコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="75306-120">Specifies a collection of authorization policy types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75306-121">解説</span><span class="sxs-lookup"><span data-stu-id="75306-121">Remarks</span></span>  
 <span data-ttu-id="75306-122">各承認ポリシーは、文字列の単一の必須属性 `policyType` を含みます。</span><span class="sxs-lookup"><span data-stu-id="75306-122">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="75306-123">この属性は、入力クレームのセットをクレームの別のセットに変換することを可能にする承認ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="75306-123">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="75306-124">アクセス制御は、それに基づいて許可または拒否されます。</span><span class="sxs-lookup"><span data-stu-id="75306-124">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="75306-125">承認ポリシーのしくみの詳細については、「」 <xref:System.IdentityModel.Policy.IAuthorizationPolicy> および「[承認ポリシー](../../../wcf/samples/authorization-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75306-125">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75306-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="75306-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="75306-127">サービス操作へのアクセスの承認</span><span class="sxs-lookup"><span data-stu-id="75306-127">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="75306-128">方法: サービスで使用するカスタム承認マネージャーを作成する</span><span class="sxs-lookup"><span data-stu-id="75306-128">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [\<add>](add-of-authorizationpolicies.md)
- [<span data-ttu-id="75306-129">承認ポリシー</span><span class="sxs-lookup"><span data-stu-id="75306-129">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)
