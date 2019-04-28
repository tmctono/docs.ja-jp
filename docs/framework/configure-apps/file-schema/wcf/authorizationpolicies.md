---
title: <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 5b367489-54d7-408b-8f56-cb157dd68eaf
ms.openlocfilehash: 2910f47b85ee67694cae0c3a725c3c7c7b3803c0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701724"
---
# <a name="authorizationpolicies"></a><span data-ttu-id="c28ee-101">\<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="c28ee-101">\<authorizationPolicies></span></span>
<span data-ttu-id="c28ee-102">この構成セクションには、`add` キーワードを使用して追加できる承認ポリシーの種類のコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c28ee-102">This configuration section contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="c28ee-103">各承認ポリシーは、文字列の単一の必須属性 `policyType` を含みます。</span><span class="sxs-lookup"><span data-stu-id="c28ee-103">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="c28ee-104">この属性は、入力クレームのセットをクレームの別のセットに変換することを可能にする承認ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="c28ee-104">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="c28ee-105">アクセス制御は、それに基づいて許可または拒否されます。</span><span class="sxs-lookup"><span data-stu-id="c28ee-105">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="c28ee-106">承認ポリシーのしくみの詳細については、次を参照してください。<xref:System.IdentityModel.Policy.IAuthorizationPolicy>と[承認ポリシー](../../../../../docs/framework/wcf/samples/authorization-policy.md)します。</span><span class="sxs-lookup"><span data-stu-id="c28ee-106">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c28ee-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="c28ee-107">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="c28ee-108">サービス操作へのアクセスの承認</span><span class="sxs-lookup"><span data-stu-id="c28ee-108">Authorizing Access to Service Operations</span></span>](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="c28ee-109">方法: サービスのカスタム承認マネージャーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c28ee-109">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="c28ee-110">\<add></span><span class="sxs-lookup"><span data-stu-id="c28ee-110">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-authorizationpolicies.md)
- [<span data-ttu-id="c28ee-111">承認ポリシー</span><span class="sxs-lookup"><span data-stu-id="c28ee-111">Authorization Policy</span></span>](../../../../../docs/framework/wcf/samples/authorization-policy.md)
