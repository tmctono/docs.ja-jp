---
title: セキュリティの拡張
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
ms.openlocfilehash: 95dacf3ef975be1ddd56db747936cca35db50625
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099639"
---
# <a name="extending-security"></a><span data-ttu-id="846e0-102">セキュリティの拡張</span><span class="sxs-lookup"><span data-stu-id="846e0-102">Extending Security</span></span>
<span data-ttu-id="846e0-103">新しいクレームの種類とカスタム トークンに対応するためには、Windows Communication Foundation (WCF) のセキュリティ インフラストラクチャを拡張できます。</span><span class="sxs-lookup"><span data-stu-id="846e0-103">To accommodate new claim types and custom tokens, you can extend the security infrastructure of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="846e0-104">このセクションの各トピックでは、この方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="846e0-104">The topics in this section show you how this is done.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="846e0-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="846e0-105">In This Section</span></span>  
  
 [<span data-ttu-id="846e0-106">カスタム資格情報と資格情報の検証</span><span class="sxs-lookup"><span data-stu-id="846e0-106">Custom Credential and Credential Validation</span></span>](../../../../docs/framework/wcf/extending/custom-credential-and-credential-validation.md)  
 <span data-ttu-id="846e0-107">カスタム資格情報の検証中に ID モデルを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="846e0-107">Explains how the Identity Model is used when validating custom credentials.</span></span>  
  
 [<span data-ttu-id="846e0-108">カスタム トークン</span><span class="sxs-lookup"><span data-stu-id="846e0-108">Custom Tokens</span></span>](../../../../docs/framework/wcf/extending/custom-tokens.md)  
 <span data-ttu-id="846e0-109">通常、セキュリティ トークン サービス (STS) から発行されるトークンは SAML トークンです。</span><span class="sxs-lookup"><span data-stu-id="846e0-109">Issued tokens from a Security Token Service (STS) are typically SAML tokens.</span></span> <span data-ttu-id="846e0-110">ここでは、カスタムのトークンの種類を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="846e0-110">This topic explains how to create a custom token type.</span></span>  
  
 [<span data-ttu-id="846e0-111">カスタム承認</span><span class="sxs-lookup"><span data-stu-id="846e0-111">Custom Authorization</span></span>](../../../../docs/framework/wcf/extending/custom-authorization.md)  
 <span data-ttu-id="846e0-112">カスタム承認を実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="846e0-112">Explains how to implement custom authorization.</span></span>  
  
 [<span data-ttu-id="846e0-113">認証のためのサービスの ID のオーバーライド</span><span class="sxs-lookup"><span data-stu-id="846e0-113">Overriding the Identity of a Service for Authentication</span></span>](../../../../docs/framework/wcf/extending/overriding-the-identity-of-a-service-for-authentication.md)  
 <span data-ttu-id="846e0-114">認証のためにサービスの ID をオーバーライドする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="846e0-114">Describes how to override the identity of a service for authentication.</span></span>  
  
 [<span data-ttu-id="846e0-115">方法: カスタム クライアント ID 検証機能を作成する</span><span class="sxs-lookup"><span data-stu-id="846e0-115">How to: Create a Custom Client Identity Verifier</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md)  
 <span data-ttu-id="846e0-116">カスタム エンドポイント ID を検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="846e0-116">Demonstrates how to validate a custom endpoint identity.</span></span>  
  
 [<span data-ttu-id="846e0-117">方法: 署名および暗号化に個別の X.509 証明書を使用する</span><span class="sxs-lookup"><span data-stu-id="846e0-117">How to: Use Separate X.509 Certificates for Signing and Encryption</span></span>](../../../../docs/framework/wcf/extending/how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 <span data-ttu-id="846e0-118">通常、メッセージの署名および暗号化は 1 つの証明書を使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="846e0-118">Messages are typically signed and encrypted with a single certificate.</span></span> <span data-ttu-id="846e0-119">ここでは、必要に応じて 2 つの証明書を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="846e0-119">This topic explains how two certificates can be used, when required.</span></span>  
  
 [<span data-ttu-id="846e0-120">方法: X.509 証明書の秘密キーの暗号化プロバイダーを変更する</span><span class="sxs-lookup"><span data-stu-id="846e0-120">How to: Change the Cryptographic Provider for an X.509 Certificate's Private Key</span></span>](../../../../docs/framework/wcf/extending/change-cryptographic-provider-x509-certificate-private-key.md)  
 <span data-ttu-id="846e0-121">X.509 証明書の秘密キーを提供するために使用する暗号化サービス プロバイダーを変更する方法と、Windows Communication Foundation (WCF) フレームワークにプロバイダーを統合する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="846e0-121">Explains how to change the cryptographic provider used to provide an X.509 certificate's private key and how to integrate the provider into the Windows Communication Foundation (WCF) framework.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="846e0-122">参照</span><span class="sxs-lookup"><span data-stu-id="846e0-122">Reference</span></span>  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## <a name="related-sections"></a><span data-ttu-id="846e0-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="846e0-123">Related Sections</span></span>  
 [<span data-ttu-id="846e0-124">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="846e0-124">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [<span data-ttu-id="846e0-125">基本的な WCF プログラミング</span><span class="sxs-lookup"><span data-stu-id="846e0-125">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
## <a name="see-also"></a><span data-ttu-id="846e0-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="846e0-126">See also</span></span>

- [<span data-ttu-id="846e0-127">セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="846e0-127">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
