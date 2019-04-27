---
title: セキュリティの拡張
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
ms.openlocfilehash: 95dacf3ef975be1ddd56db747936cca35db50625
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857923"
---
# <a name="extending-security"></a><span data-ttu-id="55e53-102">セキュリティの拡張</span><span class="sxs-lookup"><span data-stu-id="55e53-102">Extending Security</span></span>
<span data-ttu-id="55e53-103">新しいクレームの種類とカスタム トークンに対応するためには、Windows Communication Foundation (WCF) のセキュリティ インフラストラクチャを拡張できます。</span><span class="sxs-lookup"><span data-stu-id="55e53-103">To accommodate new claim types and custom tokens, you can extend the security infrastructure of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="55e53-104">このセクションの各トピックでは、この方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="55e53-104">The topics in this section show you how this is done.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="55e53-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="55e53-105">In This Section</span></span>  
  
 [<span data-ttu-id="55e53-106">カスタム資格情報と資格情報の検証</span><span class="sxs-lookup"><span data-stu-id="55e53-106">Custom Credential and Credential Validation</span></span>](../../../../docs/framework/wcf/extending/custom-credential-and-credential-validation.md)  
 <span data-ttu-id="55e53-107">カスタム資格情報の検証中に ID モデルを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="55e53-107">Explains how the Identity Model is used when validating custom credentials.</span></span>  
  
 [<span data-ttu-id="55e53-108">カスタム トークン</span><span class="sxs-lookup"><span data-stu-id="55e53-108">Custom Tokens</span></span>](../../../../docs/framework/wcf/extending/custom-tokens.md)  
 <span data-ttu-id="55e53-109">通常、セキュリティ トークン サービス (STS) から発行されるトークンは SAML トークンです。</span><span class="sxs-lookup"><span data-stu-id="55e53-109">Issued tokens from a Security Token Service (STS) are typically SAML tokens.</span></span> <span data-ttu-id="55e53-110">ここでは、カスタムのトークンの種類を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="55e53-110">This topic explains how to create a custom token type.</span></span>  
  
 [<span data-ttu-id="55e53-111">カスタム承認</span><span class="sxs-lookup"><span data-stu-id="55e53-111">Custom Authorization</span></span>](../../../../docs/framework/wcf/extending/custom-authorization.md)  
 <span data-ttu-id="55e53-112">カスタム承認を実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="55e53-112">Explains how to implement custom authorization.</span></span>  
  
 [<span data-ttu-id="55e53-113">認証のためのサービスの ID のオーバーライド</span><span class="sxs-lookup"><span data-stu-id="55e53-113">Overriding the Identity of a Service for Authentication</span></span>](../../../../docs/framework/wcf/extending/overriding-the-identity-of-a-service-for-authentication.md)  
 <span data-ttu-id="55e53-114">認証のためにサービスの ID をオーバーライドする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="55e53-114">Describes how to override the identity of a service for authentication.</span></span>  
  
 [<span data-ttu-id="55e53-115">方法: カスタムのクライアント Id 検証機能を作成します。</span><span class="sxs-lookup"><span data-stu-id="55e53-115">How to: Create a Custom Client Identity Verifier</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md)  
 <span data-ttu-id="55e53-116">カスタム エンドポイント ID を検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="55e53-116">Demonstrates how to validate a custom endpoint identity.</span></span>  
  
 [<span data-ttu-id="55e53-117">方法: 個別の X.509 証明書を使用して、署名と暗号化</span><span class="sxs-lookup"><span data-stu-id="55e53-117">How to: Use Separate X.509 Certificates for Signing and Encryption</span></span>](../../../../docs/framework/wcf/extending/how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 <span data-ttu-id="55e53-118">通常、メッセージの署名および暗号化は 1 つの証明書を使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="55e53-118">Messages are typically signed and encrypted with a single certificate.</span></span> <span data-ttu-id="55e53-119">ここでは、必要に応じて 2 つの証明書を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="55e53-119">This topic explains how two certificates can be used, when required.</span></span>  
  
 [<span data-ttu-id="55e53-120">方法: X.509 証明書の秘密キーの暗号化サービス プロバイダーを変更します。</span><span class="sxs-lookup"><span data-stu-id="55e53-120">How to: Change the Cryptographic Provider for an X.509 Certificate's Private Key</span></span>](../../../../docs/framework/wcf/extending/change-cryptographic-provider-x509-certificate-private-key.md)  
 <span data-ttu-id="55e53-121">X.509 証明書の秘密キーを提供するために使用する暗号化サービス プロバイダーを変更する方法と、Windows Communication Foundation (WCF) フレームワークにプロバイダーを統合する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="55e53-121">Explains how to change the cryptographic provider used to provide an X.509 certificate's private key and how to integrate the provider into the Windows Communication Foundation (WCF) framework.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="55e53-122">参照</span><span class="sxs-lookup"><span data-stu-id="55e53-122">Reference</span></span>  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## <a name="related-sections"></a><span data-ttu-id="55e53-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="55e53-123">Related Sections</span></span>  
 [<span data-ttu-id="55e53-124">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="55e53-124">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [<span data-ttu-id="55e53-125">基本的な WCF プログラミング</span><span class="sxs-lookup"><span data-stu-id="55e53-125">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
## <a name="see-also"></a><span data-ttu-id="55e53-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="55e53-126">See also</span></span>

- [<span data-ttu-id="55e53-127">セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="55e53-127">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
