---
title: '方法: X.509 証明書の秘密キーの暗号化プロバイダーを変更する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptographic provider [WCF], changing
- cryptographic provider [WCF]
ms.assetid: b4254406-272e-4774-bd61-27e39bbb6c12
ms.openlocfilehash: 8101c0d1214eed2c6ea42a4faab774207aab3a79
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70797278"
---
# <a name="how-to-change-the-cryptographic-provider-for-an-x509-certificates-private-key"></a><span data-ttu-id="6b249-102">方法: X.509 証明書の秘密キーの暗号化プロバイダーを変更する</span><span class="sxs-lookup"><span data-stu-id="6b249-102">How to: Change the Cryptographic Provider for an X.509 Certificate's Private Key</span></span>
<span data-ttu-id="6b249-103">このトピックでは、x.509 証明書の秘密キーを提供するために使用する暗号化サービスプロバイダーを変更する方法と、プロバイダーを Windows Communication Foundation (WCF) セキュリティフレームワークに統合する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6b249-103">This topic shows how to change the cryptographic provider used to provide an X.509 certificate's private key and how to integrate the provider into the Windows Communication Foundation (WCF) security framework.</span></span> <span data-ttu-id="6b249-104">証明書の使用方法の詳細については、「[証明書の](../feature-details/working-with-certificates.md)使用」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b249-104">For more information about using certificates, see [Working with Certificates](../feature-details/working-with-certificates.md).</span></span>  
  
 <span data-ttu-id="6b249-105">WCF セキュリティフレームワークには、新しいセキュリティトークンの種類を導入する方法が[用意されています。詳細については、「方法:カスタムトークン](how-to-create-a-custom-token.md)を作成します。</span><span class="sxs-lookup"><span data-stu-id="6b249-105">The WCF security framework provides a way to introduce new security token types as described in [How to: Create a Custom Token](how-to-create-a-custom-token.md).</span></span> <span data-ttu-id="6b249-106">また、カスタム トークンを使用して既存のシステム指定のトークンを置き換えることも可能です。</span><span class="sxs-lookup"><span data-stu-id="6b249-106">It is also possible to use a custom token to replace existing system-provided token types.</span></span>  
  
 <span data-ttu-id="6b249-107">このトピックでは、システム指定の X.509 セキュリティ トークンが、証明書の秘密キーに別の実装を提供するカスタムの X.509 トークンによって置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="6b249-107">In this topic, the system-provided X.509 security token is replaced by a custom X.509 token that provides a different implementation for the certificate private key.</span></span> <span data-ttu-id="6b249-108">これは、実際の秘密キーが、既定の Windows 暗号化プロバイダーとは異なる暗号化プロバイダーから提供されるシナリオで役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6b249-108">This is useful in scenarios where the actual private key is provided by a different cryptographic provider than the default Windows cryptographic provider.</span></span> <span data-ttu-id="6b249-109">別の暗号化プロバイダーの例として、ハードウェア セキュリティ モジュールがあります。このモジュールでは、すべての秘密キー関連の暗号操作を実行し、メモリに秘密キーを格納しないので、システムのセキュリティが向上します。</span><span class="sxs-lookup"><span data-stu-id="6b249-109">One example of an alternative cryptographic provider is a hardware security module that performs all private key related cryptographic operations, and does not store the private keys in memory, thus improving security of the system.</span></span>  
  
 <span data-ttu-id="6b249-110">次の例は、デモンストレーションのためだけに作成されています。</span><span class="sxs-lookup"><span data-stu-id="6b249-110">The following example is for demonstration purposes only.</span></span> <span data-ttu-id="6b249-111">この例では、既定の Windows 暗号化プロバイダーを置き換えていませんが、Windows 暗号化プロバイダーをどこで統合できるかを示します。</span><span class="sxs-lookup"><span data-stu-id="6b249-111">It does not replace the default Windows cryptographic provider, but it shows where such a provider could be integrated.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="6b249-112">手順</span><span class="sxs-lookup"><span data-stu-id="6b249-112">Procedures</span></span>  
 <span data-ttu-id="6b249-113">セキュリティ キーが関連付けられているセキュリティ トークンごとに、セキュリティ トークンのインスタンスからキーのコレクションを返す <xref:System.IdentityModel.Tokens.SecurityToken.SecurityKeys%2A> プロパティを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b249-113">Every security token that has an associated security key or keys must implement the <xref:System.IdentityModel.Tokens.SecurityToken.SecurityKeys%2A> property, which returns a collection of keys from the security token instance.</span></span> <span data-ttu-id="6b249-114">トークンが X.509 セキュリティ トークンの場合、コレクションには、証明書に関連付けられた公開キーと秘密キーの両方を表す <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey> クラスのインスタンスが 1 つ追加されます。</span><span class="sxs-lookup"><span data-stu-id="6b249-114">If the token is an X.509 security token, the collection contains a single instance of the <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey> class that represents both public and private keys associated with the certificate.</span></span> <span data-ttu-id="6b249-115">証明書のキーの提供に使用する既定の暗号化プロバイダーを置き換えるには、このクラスの新しい実装を作成します。</span><span class="sxs-lookup"><span data-stu-id="6b249-115">To replace the default cryptographic provider used to provide the certificate's keys, create a new implementation of this class.</span></span>  
  
#### <a name="to-create-a-custom-x509-asymmetric-key"></a><span data-ttu-id="6b249-116">カスタムの X.509 非対称キーを作成するには</span><span class="sxs-lookup"><span data-stu-id="6b249-116">To create a custom X.509 asymmetric key</span></span>  
  
1. <span data-ttu-id="6b249-117"><xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey> クラスから派生する新しいクラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="6b249-117">Define a new class derived from the <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey> class.</span></span>  
  
2. <span data-ttu-id="6b249-118"><xref:System.IdentityModel.Tokens.SecurityKey.KeySize%2A> 読み取り専用プロパティをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="6b249-118">Override the <xref:System.IdentityModel.Tokens.SecurityKey.KeySize%2A> read-only property.</span></span> <span data-ttu-id="6b249-119">このプロパティは、証明書の公開キーと秘密キーのペアの実際のキー サイズを返します。</span><span class="sxs-lookup"><span data-stu-id="6b249-119">This property returns the actual key size of the certificate's public/private key pair.</span></span>  
  
3. <span data-ttu-id="6b249-120"><xref:System.IdentityModel.Tokens.SecurityKey.DecryptKey%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="6b249-120">Override the <xref:System.IdentityModel.Tokens.SecurityKey.DecryptKey%2A> method.</span></span> <span data-ttu-id="6b249-121">このメソッドは、証明書の秘密キーを使用して対称キーを復号化するために、WCF セキュリティフレームワークによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="6b249-121">This method is called by the WCF security framework to decrypt a symmetric key with the certificate's private key.</span></span> <span data-ttu-id="6b249-122">(このキーは、以前に証明書の公開キーで暗号化されています)。</span><span class="sxs-lookup"><span data-stu-id="6b249-122">(The key was previously encrypted with the certificate's public key.)</span></span>  
  
4. <span data-ttu-id="6b249-123"><xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetAsymmetricAlgorithm%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="6b249-123">Override the <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetAsymmetricAlgorithm%2A> method.</span></span> <span data-ttu-id="6b249-124">このメソッドは、メソッドに渡されたパラメーターに応じて、証明<xref:System.Security.Cryptography.AsymmetricAlgorithm>書の秘密キーまたは公開キーの暗号化サービスプロバイダーを表すクラスのインスタンスを取得するために、WCF セキュリティフレームワークによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="6b249-124">This method is called by the WCF security framework to obtain an instance of the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class that represents the cryptographic provider for either the certificate's private or public key, depending on the parameters passed to the method.</span></span>  
  
5. <span data-ttu-id="6b249-125">任意。</span><span class="sxs-lookup"><span data-stu-id="6b249-125">Optional.</span></span> <span data-ttu-id="6b249-126"><xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetHashAlgorithmForSignature%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="6b249-126">Override the <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetHashAlgorithmForSignature%2A> method.</span></span> <span data-ttu-id="6b249-127"><xref:System.Security.Cryptography.HashAlgorithm> クラスの別の実装が必要な場合は、このメソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="6b249-127">Override this method if a different implementation of the <xref:System.Security.Cryptography.HashAlgorithm> class is required.</span></span>  
  
6. <span data-ttu-id="6b249-128"><xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetSignatureFormatter%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="6b249-128">Override the <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetSignatureFormatter%2A> method.</span></span> <span data-ttu-id="6b249-129">このメソッドは、証明書の秘密キーに関連付けられた <xref:System.Security.Cryptography.AsymmetricSignatureFormatter> クラスのインスタンスを返します。</span><span class="sxs-lookup"><span data-stu-id="6b249-129">This method returns an instance of the <xref:System.Security.Cryptography.AsymmetricSignatureFormatter> class that is associated with the certificate's private key.</span></span>  
  
7. <span data-ttu-id="6b249-130"><xref:System.IdentityModel.Tokens.SecurityKey.IsSupportedAlgorithm%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="6b249-130">Override the <xref:System.IdentityModel.Tokens.SecurityKey.IsSupportedAlgorithm%2A> method.</span></span> <span data-ttu-id="6b249-131">このメソッドを使用して、特定の暗号アルゴリズムがセキュリティ キー実装によってサポートされているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6b249-131">This method is used to indicate whether a particular cryptographic algorithm is supported by the security key implementation.</span></span>  
  
     [!code-csharp[c_CustomX509Token#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#1)]
     [!code-vb[c_CustomX509Token#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#1)]  
  
 <span data-ttu-id="6b249-132">次の手順では、システムによって提供される x.509 セキュリティトークンを置き換えるために、前の手順で作成したカスタムの x.509 非対称セキュリティキーの実装を WCF セキュリティフレームワークに統合する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6b249-132">The following procedure shows how to integrate the custom X.509 asymmetric security key implementation created in the preceding procedure with the WCF security framework in order to replace the system-provided X.509 security token.</span></span>  
  
#### <a name="to-replace-the-system-provided-x509-security-token-with-a-custom-x509-asymmetric-security-key-token"></a><span data-ttu-id="6b249-133">システム指定の X.509 セキュリティ トークンをカスタムの X.509 非対称セキュリティ キー トークンで置き換えるには</span><span class="sxs-lookup"><span data-stu-id="6b249-133">To replace the system-provided X.509 security token with a custom X.509 asymmetric security key token</span></span>  
  
1. <span data-ttu-id="6b249-134">次の例に示すように、システム指定のセキュリティ キーではなく、カスタムの X.509 非対称セキュリティ キーを返すカスタムの X.509 非対称セキュリティ トークンを作成します。</span><span class="sxs-lookup"><span data-stu-id="6b249-134">Create a custom X.509 security token that returns the custom X.509 asymmetric security key instead of the system-provided security key, as shown in the following example.</span></span> <span data-ttu-id="6b249-135">カスタムセキュリティトークンの詳細については[、「」を参照してください。カスタムトークン](how-to-create-a-custom-token.md)を作成します。</span><span class="sxs-lookup"><span data-stu-id="6b249-135">For more information about custom security tokens, see [How to: Create a Custom Token](how-to-create-a-custom-token.md).</span></span>  
  
     [!code-csharp[c_CustomX509Token#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#2)]
     [!code-vb[c_CustomX509Token#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#2)]  
  
2. <span data-ttu-id="6b249-136">次の例に示すように、カスタムの X.509 セキュリティ トークンを返すカスタムのセキュリティ トークン プロバイダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="6b249-136">Create a custom security token provider that returns a custom X.509 security token, as shown in the example.</span></span> <span data-ttu-id="6b249-137">カスタムセキュリティトークンプロバイダーの詳細については[、「」を参照してください。カスタムセキュリティトークンプロバイダー](how-to-create-a-custom-security-token-provider.md)を作成します。</span><span class="sxs-lookup"><span data-stu-id="6b249-137">For more information about custom security token providers, see [How to: Create a Custom Security Token Provider](how-to-create-a-custom-security-token-provider.md).</span></span>  
  
     [!code-csharp[c_CustomX509Token#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#3)]
     [!code-vb[c_CustomX509Token#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#3)]  
  
3. <span data-ttu-id="6b249-138">イニシエーター側でカスタム セキュリティ キーを使用する必要がある場合、次の例に示すように、カスタムのクライアント セキュリティ トークン マネージャーとカスタムのクライアント資格情報クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="6b249-138">If the custom security key needs to be used on the initiator side, create a custom client security token manager and custom client credentials classes, as shown in the following example.</span></span> <span data-ttu-id="6b249-139">カスタムクライアント資格情報とクライアントセキュリティトークンマネージャーの詳細について[は、「チュートリアル:カスタムクライアントおよびサービスの資格](walkthrough-creating-custom-client-and-service-credentials.md)情報を作成しています。</span><span class="sxs-lookup"><span data-stu-id="6b249-139">For more information about custom client credentials and client security token managers, see [Walkthrough: Creating Custom Client and Service Credentials](walkthrough-creating-custom-client-and-service-credentials.md).</span></span>  
  
     [!code-csharp[c_CustomX509Token#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#4)]
     [!code-vb[c_CustomX509Token#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#4)]  
  
     [!code-csharp[c_CustomX509Token#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#6)]
     [!code-vb[c_CustomX509Token#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#6)]  
  
4. <span data-ttu-id="6b249-140">受信側でカスタム セキュリティ キーを使用する必要がある場合、次の例に示すように、カスタムのサービス セキュリティ トークン マネージャーとカスタムのサービス資格情報クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="6b249-140">If the custom security key needs to be used on the recipient side, create a custom service security token manager and custom service credentials, as shown in the following example.</span></span> <span data-ttu-id="6b249-141">カスタムサービス資格情報とサービスセキュリティトークンマネージャーの詳細について[は、「チュートリアル:カスタムクライアントおよびサービスの資格](walkthrough-creating-custom-client-and-service-credentials.md)情報を作成しています。</span><span class="sxs-lookup"><span data-stu-id="6b249-141">For more information about custom service credentials and service security token managers, see [Walkthrough: Creating Custom Client and Service Credentials](walkthrough-creating-custom-client-and-service-credentials.md).</span></span>  
  
     [!code-csharp[c_CustomX509Token#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#5)]
     [!code-vb[c_CustomX509Token#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#5)]  
  
     [!code-csharp[c_CustomX509Token#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#7)]
     [!code-vb[c_CustomX509Token#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="6b249-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b249-142">See also</span></span>

- <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey>
- <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey>
- <xref:System.IdentityModel.Tokens.SecurityKey>
- <xref:System.Security.Cryptography.AsymmetricAlgorithm>
- <xref:System.Security.Cryptography.HashAlgorithm>
- <xref:System.Security.Cryptography.AsymmetricSignatureFormatter>
- [<span data-ttu-id="6b249-143">チュートリアル: カスタムのクライアントおよびサービスの資格情報の作成</span><span class="sxs-lookup"><span data-stu-id="6b249-143">Walkthrough: Creating Custom Client and Service Credentials</span></span>](walkthrough-creating-custom-client-and-service-credentials.md)
- [<span data-ttu-id="6b249-144">カスタムセキュリティトークン認証システムを作成する</span><span class="sxs-lookup"><span data-stu-id="6b249-144">How to: Create a Custom Security Token Authenticator</span></span>](how-to-create-a-custom-security-token-authenticator.md)
- [<span data-ttu-id="6b249-145">カスタムセキュリティトークンプロバイダーを作成する</span><span class="sxs-lookup"><span data-stu-id="6b249-145">How to: Create a Custom Security Token Provider</span></span>](how-to-create-a-custom-security-token-provider.md)
- [<span data-ttu-id="6b249-146">カスタムトークンを作成する</span><span class="sxs-lookup"><span data-stu-id="6b249-146">How to: Create a Custom Token</span></span>](how-to-create-a-custom-token.md)
