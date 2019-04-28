---
title: <claimTypeRequirements> 要素
ms.date: 03/30/2017
ms.assetid: a26efe73-4bad-4731-8cad-27f00d54354b
ms.openlocfilehash: 236ae880fff24f7ccbf5d6c9c03c0208d446688f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704415"
---
# <a name="claimtyperequirements-element"></a><span data-ttu-id="f8cc0-102">\<claimTypeRequirements > 要素</span><span class="sxs-lookup"><span data-stu-id="f8cc0-102">\<claimTypeRequirements> element</span></span>
<span data-ttu-id="f8cc0-103">必須のクレームの種類のコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="f8cc0-103">Specifies a collection of required claim types.</span></span>  
  
 <span data-ttu-id="f8cc0-104">フェデレーション シナリオでは、サービスが受信資格情報についての要件を記述します。</span><span class="sxs-lookup"><span data-stu-id="f8cc0-104">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="f8cc0-105">たとえば、受信資格情報は、特定のクレーム タイプのセットを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8cc0-105">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="f8cc0-106">このコレクションの子要素はそれぞれ、フェデレーション資格情報に表示されると予想される必須のクレームおよび省略可能なクレームの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="f8cc0-106">Each child element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>  
  
 <span data-ttu-id="f8cc0-107">クレームの種類の要件は、発行されるトークンで要求されているクレームの種類の URI と、発行されるトークンでそのクレームの種類が必須かまたは省略可能かを示すブール型のパラメーターで構成されます。</span><span class="sxs-lookup"><span data-stu-id="f8cc0-107">A claim type requirement consists of the URI of the claim type requested in the issued token along with a Boolean parameter that indicates whether that claim type is required in the issued token, or is optional.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8cc0-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8cc0-108">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="f8cc0-109">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="f8cc0-109">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="f8cc0-110">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="f8cc0-110">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="f8cc0-111">カスタム バインドを使用したセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="f8cc0-111">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="f8cc0-112">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="f8cc0-112">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="f8cc0-113">\<add></span><span class="sxs-lookup"><span data-stu-id="f8cc0-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-claimtyperequirements.md)
- [<span data-ttu-id="f8cc0-114">バインディング</span><span class="sxs-lookup"><span data-stu-id="f8cc0-114">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="f8cc0-115">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="f8cc0-115">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="f8cc0-116">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="f8cc0-116">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="f8cc0-117">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="f8cc0-117">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="f8cc0-118">方法: SecurityBindingElement を使用してカスタム バインディングを作成します。</span><span class="sxs-lookup"><span data-stu-id="f8cc0-118">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="f8cc0-119">カスタム バインド セキュリティ</span><span class="sxs-lookup"><span data-stu-id="f8cc0-119">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
