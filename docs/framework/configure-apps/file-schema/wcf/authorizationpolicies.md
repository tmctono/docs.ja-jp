---
title: <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 5b367489-54d7-408b-8f56-cb157dd68eaf
ms.openlocfilehash: 38d123a53b344ff1e4d781115093d0d1de5ae679
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "69926460"
---
# \<authorizationPolicies>
<span data-ttu-id="28660-101">この構成セクションには、`add` キーワードを使用して追加できる承認ポリシーの種類のコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="28660-101">This configuration section contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="28660-102">各承認ポリシーは、文字列の単一の必須属性 `policyType` を含みます。</span><span class="sxs-lookup"><span data-stu-id="28660-102">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="28660-103">この属性は、入力クレームのセットをクレームの別のセットに変換することを可能にする承認ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="28660-103">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="28660-104">アクセス制御は、それに基づいて許可または拒否されます。</span><span class="sxs-lookup"><span data-stu-id="28660-104">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="28660-105">承認ポリシーのしくみの詳細については、「」 <xref:System.IdentityModel.Policy.IAuthorizationPolicy> および「[承認ポリシー](../../../wcf/samples/authorization-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28660-105">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28660-106">関連項目</span><span class="sxs-lookup"><span data-stu-id="28660-106">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="28660-107">サービス操作へのアクセスの承認</span><span class="sxs-lookup"><span data-stu-id="28660-107">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="28660-108">方法: サービスで使用するカスタム承認マネージャーを作成する</span><span class="sxs-lookup"><span data-stu-id="28660-108">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [\<add>](add-of-authorizationpolicies.md)
- [<span data-ttu-id="28660-109">承認ポリシー</span><span class="sxs-lookup"><span data-stu-id="28660-109">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)
