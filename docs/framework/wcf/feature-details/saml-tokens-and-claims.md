---
title: SAML トークンとクレーム
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
- issued tokens
- SAML token
ms.assetid: 930b6e34-9eab-4e95-826c-4e06659bb977
ms.openlocfilehash: 7037daf299d7c750ab398c21c1d7ccb541620701
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943072"
---
# <a name="saml-tokens-and-claims"></a><span data-ttu-id="9c24a-102">SAML トークンとクレーム</span><span class="sxs-lookup"><span data-stu-id="9c24a-102">SAML Tokens and Claims</span></span>
<span data-ttu-id="9c24a-103">セキュリティアサーションマークアップ言語 (SAML)*トークン*は、クレームの XML 表現です。</span><span class="sxs-lookup"><span data-stu-id="9c24a-103">Security Assertions Markup Language (SAML) *tokens* are XML representations of claims.</span></span> <span data-ttu-id="9c24a-104">既定では、フェデレーションセキュリティシナリオで使用される SAML トークン Windows Communication Foundation (WCF) では、*トークンが発行*されます。</span><span class="sxs-lookup"><span data-stu-id="9c24a-104">By default, SAML tokens Windows Communication Foundation (WCF) uses in federated security scenarios are *issued tokens*.</span></span>  
  
 <span data-ttu-id="9c24a-105">SAML トークンは、ステートメント (特定のエンティティによって他のエンティティに関して作成されるクレームのセット) を伝達します。</span><span class="sxs-lookup"><span data-stu-id="9c24a-105">SAML tokens carry statements that are sets of claims made by one entity about another entity.</span></span> <span data-ttu-id="9c24a-106">たとえば、フェデレーション セキュリティ シナリオでは、ステートメントがセキュリティ トークン サービスによって、システム内の特定のユーザーに関して作成されます。</span><span class="sxs-lookup"><span data-stu-id="9c24a-106">For example, in federated security scenarios, the statements are made by a security token service about a user in the system.</span></span> <span data-ttu-id="9c24a-107">セキュリティ トークン サービスは、トークンに含まれるステートメントの信憑性を示すために SAML トークンに署名します。</span><span class="sxs-lookup"><span data-stu-id="9c24a-107">The security token service signs the SAML token to indicate the veracity of the statements contained in the token.</span></span> <span data-ttu-id="9c24a-108">また、SAML トークンは、SAML トークンのユーザーが証明として提示する暗号化キー マテリアルに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="9c24a-108">In addition, the SAML token is associated with cryptographic key material that the user of the SAML token proves knowledge of.</span></span> <span data-ttu-id="9c24a-109">これが証拠となり、証明書利用者は、SAML トークンが実際にそのユーザーに対して発行されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="9c24a-109">This proof satisfies the relying party that the SAML token was, in fact, issued to that user.</span></span> <span data-ttu-id="9c24a-110">一般的なシナリオでの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9c24a-110">For example, in a typical scenario:</span></span>  
  
1. <span data-ttu-id="9c24a-111">クライアントは、セキュリティ トークン サービスから SAML トークンを要求し、Windows 資格情報を使用して、そのセキュリティ トークン サービスに対して認証を行います。</span><span class="sxs-lookup"><span data-stu-id="9c24a-111">A client requests a SAML token from a security token service, authenticating to that security token service by using Windows credentials.</span></span>  
  
2. <span data-ttu-id="9c24a-112">セキュリティ トークン サービスは、SAML トークンをクライアントに発行します。</span><span class="sxs-lookup"><span data-stu-id="9c24a-112">The security token service issues a SAML token to the client.</span></span> <span data-ttu-id="9c24a-113">SAML トークンは、セキュリティ トークン サービスに関連付けられた証明書を使用して署名され、ターゲット サービス用に暗号化された証明キーを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="9c24a-113">The SAML token is signed with a certificate associated with the security token service and contains a proof key encrypted for the target service.</span></span>  
  
3. <span data-ttu-id="9c24a-114">クライアントは、*証明キー*のコピーも受け取ります。</span><span class="sxs-lookup"><span data-stu-id="9c24a-114">The client also receives a copy of the *proof key*.</span></span> <span data-ttu-id="9c24a-115">次に、クライアントは SAML トークンをアプリケーションサービス (*証明書利用者*) に提示し、その証明キーを使用してメッセージに署名します。</span><span class="sxs-lookup"><span data-stu-id="9c24a-115">The client then presents the SAML token to the application service (the *relying party*) and signs the message with that proof key.</span></span>  
  
4. <span data-ttu-id="9c24a-116">SAML トークンの署名は、そのトークンがセキュリティ トークン サービスによって発行されたことを証明書利用者に示します。</span><span class="sxs-lookup"><span data-stu-id="9c24a-116">The signature over the SAML token tells the relying party that the security token service issued the token.</span></span> <span data-ttu-id="9c24a-117">また、証明キーを使用して作成されたメッセージ署名は、トークンがそのクライアントに対して発行されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="9c24a-117">The message signature created with the proof key tells the relying party that the token was issued to the client.</span></span>  
  
## <a name="from-claims-to-samlattributes"></a><span data-ttu-id="9c24a-118">クレームから SamlAttributes</span><span class="sxs-lookup"><span data-stu-id="9c24a-118">From Claims to SamlAttributes</span></span>  
 <span data-ttu-id="9c24a-119">WCF では、SAML トークン内のステートメントは<xref:System.IdentityModel.Tokens.SamlAttribute>オブジェクトとしてモデル化され<xref:System.IdentityModel.Claims.Claim>ます。オブジェクトの<xref:System.IdentityModel.Claims.Claim> <xref:System.IdentityModel.Claims.Claim.Right%2A>プロパティ<xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> <xref:System.IdentityModel.Claims.Claim.Resource%2A>がで、プロパティがである場合は、オブジェクトから直接データを設定できます。「 <xref:System.String>」と入力します。</span><span class="sxs-lookup"><span data-stu-id="9c24a-119">In WCF, statements in SAML tokens are modeled as <xref:System.IdentityModel.Tokens.SamlAttribute> objects, which can be populated directly from <xref:System.IdentityModel.Claims.Claim> objects, provided the <xref:System.IdentityModel.Claims.Claim> object has a <xref:System.IdentityModel.Claims.Claim.Right%2A> property of <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> and the <xref:System.IdentityModel.Claims.Claim.Resource%2A> property is of type <xref:System.String>.</span></span> <span data-ttu-id="9c24a-120">例:</span><span class="sxs-lookup"><span data-stu-id="9c24a-120">For example:</span></span>  
  
 [!code-csharp[c_CreateSTS#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#8)]
 [!code-vb[c_CreateSTS#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#8)]  
  
> [!NOTE]
> <span data-ttu-id="9c24a-121">セキュリティ トークン サービスによって発行されたか、または認証の一部としてクライアントからサービスに提示されたときに、SAML トークンがメッセージ内にシリアル化される場合、メッセージの最大クォータ サイズが、SAML トークンおよびメッセージの他の部分を格納できるだけの大きさである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c24a-121">When SAML tokens are serialized in messages, either when they are issued by a security token service or when they are presented by clients to services as part of authentication, the maximum message size quota must be sufficiently large to accommodate the SAML token and the other message parts.</span></span> <span data-ttu-id="9c24a-122">通常は、既定のメッセージ クォータ サイズで十分です。</span><span class="sxs-lookup"><span data-stu-id="9c24a-122">In normal cases, the default message size quotas are sufficient.</span></span> <span data-ttu-id="9c24a-123">ただし、何百ものクレームを含んでいるために SAML トークンのサイズが大きい場合には、シリアル化されたトークンを格納できるように、クォータを増やす必要が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="9c24a-123">However, in cases where a SAML token is large because it contains hundreds of claims, you may need to increase the quotas to accommodate the serialized token.</span></span> <span data-ttu-id="9c24a-124">詳細については、「[データのセキュリティに関する考慮事項](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c24a-124">For more information, see [Security Considerations for Data](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md).</span></span>  
  
## <a name="from-samlattributes-to-claims"></a><span data-ttu-id="9c24a-125">SamlAttributes からクレーム</span><span class="sxs-lookup"><span data-stu-id="9c24a-125">From SamlAttributes to Claims</span></span>  
 <span data-ttu-id="9c24a-126">SAML トークンがメッセージで受信されると、SAML トークン内のさまざまなステートメントは、 <xref:System.IdentityModel.Policy.IAuthorizationPolicy> オブジェクトに変換され、<xref:System.IdentityModel.Policy.AuthorizationContext> に配置されます。</span><span class="sxs-lookup"><span data-stu-id="9c24a-126">When SAML tokens are received in messages, the various statements in the SAML token are turned into <xref:System.IdentityModel.Policy.IAuthorizationPolicy> objects that are placed into the <xref:System.IdentityModel.Policy.AuthorizationContext>.</span></span> <span data-ttu-id="9c24a-127">各 SAML ステートメントのクレームは <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> の <xref:System.IdentityModel.Policy.AuthorizationContext> プロパティによって返され、これを調べることによってユーザーの認証と承認を行うかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="9c24a-127">The claims from each SAML statement are returned by the <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> property of the <xref:System.IdentityModel.Policy.AuthorizationContext> and can be examined to determine whether to authenticate and authorize the user.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c24a-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c24a-128">See also</span></span>

- <xref:System.IdentityModel.Policy.AuthorizationContext>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- <xref:System.IdentityModel.Claims.ClaimSet>
- [<span data-ttu-id="9c24a-129">フェデレーション</span><span class="sxs-lookup"><span data-stu-id="9c24a-129">Federation</span></span>](../../../../docs/framework/wcf/feature-details/federation.md)
- [<span data-ttu-id="9c24a-130">方法: フェデレーションクライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="9c24a-130">How to: Create a Federated Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="9c24a-131">方法: フェデレーションサービスで資格情報を構成する</span><span class="sxs-lookup"><span data-stu-id="9c24a-131">How to: Configure Credentials on a Federation Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="9c24a-132">ID モデルを使用したクレームと承認の管理</span><span class="sxs-lookup"><span data-stu-id="9c24a-132">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
- [<span data-ttu-id="9c24a-133">クレームとトークン</span><span class="sxs-lookup"><span data-stu-id="9c24a-133">Claims and Tokens</span></span>](../../../../docs/framework/wcf/feature-details/claims-and-tokens.md)
- [<span data-ttu-id="9c24a-134">クレームの作成とリソース値</span><span class="sxs-lookup"><span data-stu-id="9c24a-134">Claim Creation and Resource Values</span></span>](../../../../docs/framework/wcf/feature-details/claim-creation-and-resource-values.md)
- [<span data-ttu-id="9c24a-135">方法: カスタム要求の作成</span><span class="sxs-lookup"><span data-stu-id="9c24a-135">How to: Create a Custom Claim</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-claim.md)
