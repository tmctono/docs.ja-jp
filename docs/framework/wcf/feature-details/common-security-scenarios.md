---
title: 一般的なセキュリティ シナリオ
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], scenarios
ms.assetid: 201923b5-5162-4a8a-8d4c-e7bd242748d5
ms.openlocfilehash: cfd29f8cae8ac362a5fa1709864dce4ae11b5af6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558889"
---
# <a name="common-security-scenarios"></a><span data-ttu-id="3bce0-102">一般的なセキュリティ シナリオ</span><span class="sxs-lookup"><span data-stu-id="3bce0-102">Common Security Scenarios</span></span>
<span data-ttu-id="3bce0-103">ここでは、考えられるさまざまなクライアントおよびサービスのセキュリティ構成の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="3bce0-103">The topics in this section catalog a number of possible client and service security configurations.</span></span> <span data-ttu-id="3bce0-104">構成はさまざまな要因により異なります。</span><span class="sxs-lookup"><span data-stu-id="3bce0-104">Configurations vary according to a number of factors.</span></span> <span data-ttu-id="3bce0-105">たとえば、サービスやクライアントがイントラネット上にあるかどうか、また、セキュリティが Windows とトランスポート (HTTPS など) のどちらで提供されるかなどが考えられます。</span><span class="sxs-lookup"><span data-stu-id="3bce0-105">For example, whether a service or client is on an intranet, or whether the security is provided by Windows or transport (such as HTTPS).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3bce0-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3bce0-106">In This Section</span></span>  
 [<span data-ttu-id="3bce0-107">セキュリティで保護されていないインターネット環境のクライアントとサービス</span><span class="sxs-lookup"><span data-stu-id="3bce0-107">Internet Unsecured Client and Service</span></span>](internet-unsecured-client-and-service.md)  
 <span data-ttu-id="3bce0-108">セキュリティで保護されていないパブリックなクライアントとサービスの例です。</span><span class="sxs-lookup"><span data-stu-id="3bce0-108">An example of a public, unsecured client and service.</span></span>  
  
 [<span data-ttu-id="3bce0-109">セキュリティで保護されていないイントラネットのクライアントとサービス</span><span class="sxs-lookup"><span data-stu-id="3bce0-109">Intranet Unsecured Client and Service</span></span>](intranet-unsecured-client-and-service.md)  
 <span data-ttu-id="3bce0-110">セキュリティで保護されたプライベートネットワークに関する情報を WCF アプリケーションに提供するために開発された基本的な Windows Communication Foundation (WCF) サービス。</span><span class="sxs-lookup"><span data-stu-id="3bce0-110">A basic Windows Communication Foundation (WCF) service developed to provide information on a secure private network to a WCF application.</span></span>  
  
 [<span data-ttu-id="3bce0-111">基本認証でのトランスポート セキュリティ</span><span class="sxs-lookup"><span data-stu-id="3bce0-111">Transport Security with Basic Authentication</span></span>](transport-security-with-basic-authentication.md)  
 <span data-ttu-id="3bce0-112">アプリケーションは、カスタム認証を使用して、クライアントにログオンを許可します。</span><span class="sxs-lookup"><span data-stu-id="3bce0-112">The application allows clients to log on using custom authentication.</span></span>  
  
 [<span data-ttu-id="3bce0-113">トランスポート セキュリティと Windows 認証</span><span class="sxs-lookup"><span data-stu-id="3bce0-113">Transport Security with Windows Authentication</span></span>](transport-security-with-windows-authentication.md)  
 <span data-ttu-id="3bce0-114">Windows セキュリティによってセキュリティ保護されたクライアントとサービスを示します。</span><span class="sxs-lookup"><span data-stu-id="3bce0-114">Shows a client and service secured by Windows security.</span></span>  
  
 [<span data-ttu-id="3bce0-115">トランスポート セキュリティと匿名クライアント</span><span class="sxs-lookup"><span data-stu-id="3bce0-115">Transport Security with an Anonymous Client</span></span>](transport-security-with-an-anonymous-client.md)  
 <span data-ttu-id="3bce0-116">このシナリオでは HTTPS などのようなトランスポート セキュリティを使用して、機密性と整合性を強化します。</span><span class="sxs-lookup"><span data-stu-id="3bce0-116">This scenario uses transport security (such as HTTPS) to ensure confidentiality and integrity.</span></span>  
  
 [<span data-ttu-id="3bce0-117">トランスポート セキュリティと証明書認証</span><span class="sxs-lookup"><span data-stu-id="3bce0-117">Transport Security with Certificate Authentication</span></span>](transport-security-with-certificate-authentication.md)  
 <span data-ttu-id="3bce0-118">証明書によってセキュリティ保護されたクライアントとサービスを示します。</span><span class="sxs-lookup"><span data-stu-id="3bce0-118">Shows a client and service secured by a certificate.</span></span>  
  
 [<span data-ttu-id="3bce0-119">メッセージ セキュリティと匿名クライアント</span><span class="sxs-lookup"><span data-stu-id="3bce0-119">Message Security with an Anonymous Client</span></span>](message-security-with-an-anonymous-client.md)  
 <span data-ttu-id="3bce0-120">WCF メッセージセキュリティによってセキュリティ保護されたクライアントとサービスを示します。</span><span class="sxs-lookup"><span data-stu-id="3bce0-120">Shows a client and service secured by WCF message security.</span></span>  
  
 [<span data-ttu-id="3bce0-121">ユーザー名クライアントを使用したメッセージ セキュリティ</span><span class="sxs-lookup"><span data-stu-id="3bce0-121">Message Security with a User Name Client</span></span>](message-security-with-a-user-name-client.md)  
 <span data-ttu-id="3bce0-122">クライアントは、ドメイン ユーザー名とパスワードを使用してクライアントのログオンを許可する Windows フォーム アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="3bce0-122">The client is a Windows Forms application that allows clients to log on using a domain user name and password.</span></span>  
  
 [<span data-ttu-id="3bce0-123">メッセージ セキュリティと証明書クライアント</span><span class="sxs-lookup"><span data-stu-id="3bce0-123">Message Security with a Certificate Client</span></span>](message-security-with-a-certificate-client.md)  
 <span data-ttu-id="3bce0-124">サーバー側の証明書は複数あり、クライアント側の証明書はそれぞれ 1 つです。</span><span class="sxs-lookup"><span data-stu-id="3bce0-124">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="3bce0-125">セキュリティのコンテキストは、トランスポート層セキュリティ (TLS: Transport Layer Security) ネゴシエーションを介して確立されます。</span><span class="sxs-lookup"><span data-stu-id="3bce0-125">A security context is established through Transport Layer Security (TLS) negotiation.</span></span>  
  
 [<span data-ttu-id="3bce0-126">Windows クライアントとのメッセージ セキュリティ</span><span class="sxs-lookup"><span data-stu-id="3bce0-126">Message Security with a Windows Client</span></span>](message-security-with-a-windows-client.md)  
 <span data-ttu-id="3bce0-127">証明書クライアントのバリエーションの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="3bce0-127">A variation of the certificate client.</span></span> <span data-ttu-id="3bce0-128">サーバー側の証明書は複数あり、クライアント側の証明書はそれぞれ 1 つです。</span><span class="sxs-lookup"><span data-stu-id="3bce0-128">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="3bce0-129">セキュリティのコンテキストは TLS ネゴシエーションを介して確立されます。</span><span class="sxs-lookup"><span data-stu-id="3bce0-129">A security context is established through TLS negotiation.</span></span>  
  
 [<span data-ttu-id="3bce0-130">資格情報ネゴシエーションを使用しない Windows クライアントを使用するメッセージ セキュリティ</span><span class="sxs-lookup"><span data-stu-id="3bce0-130">Message Security with a Windows Client without Credential Negotiation</span></span>](message-security-with-a-windows-client-without-credential-negotiation.md)  
 <span data-ttu-id="3bce0-131">Kerberos ドメインによってセキュリティ保護されたクライアントとサービスを示します。</span><span class="sxs-lookup"><span data-stu-id="3bce0-131">Shows a client and service secured by a Kerberos domain.</span></span>  
  
 [<span data-ttu-id="3bce0-132">メッセージ セキュリティと相互の証明書</span><span class="sxs-lookup"><span data-stu-id="3bce0-132">Message Security with Mutual Certificates</span></span>](message-security-with-mutual-certificates.md)  
 <span data-ttu-id="3bce0-133">サーバー側の証明書は複数あり、クライアント側の証明書はそれぞれ 1 つです。</span><span class="sxs-lookup"><span data-stu-id="3bce0-133">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="3bce0-134">サーバーの証明書はアプリケーションと共に配布され、帯域外でも使用可能です。</span><span class="sxs-lookup"><span data-stu-id="3bce0-134">The server certificate is distributed with the application and is available out of band.</span></span>  
  
 [<span data-ttu-id="3bce0-135">発行済みトークンを使用したメッセージ セキュリティ</span><span class="sxs-lookup"><span data-stu-id="3bce0-135">Message Security with Issued Tokens</span></span>](message-security-with-issued-tokens.md)  
 <span data-ttu-id="3bce0-136">フェデレーション セキュリティにより独立したドメイン間で信頼を確立できます。</span><span class="sxs-lookup"><span data-stu-id="3bce0-136">Federated security that enables the establishment of trust between independent domains.</span></span>  
  
 [<span data-ttu-id="3bce0-137">信頼できるサブシステム</span><span class="sxs-lookup"><span data-stu-id="3bce0-137">Trusted Subsystem</span></span>](trusted-subsystem.md)  
 <span data-ttu-id="3bce0-138">クライアントは、ネットワーク全体に分散している 1 つ以上の Web サービスにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="3bce0-138">A client accesses one or more Web services that are distributed across a network.</span></span> <span data-ttu-id="3bce0-139">Web サービスは、セキュリティで保護する必要がある追加のリソース (データベースや他の Web サービスなど) にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="3bce0-139">The Web services access additional resources (such as databases or other Web services) that must be secured.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3bce0-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="3bce0-140">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="3bce0-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="3bce0-141">Related Sections</span></span>  
 [<span data-ttu-id="3bce0-142">承認</span><span class="sxs-lookup"><span data-stu-id="3bce0-142">Authorization</span></span>](authorization-in-wcf.md)  
  
 [<span data-ttu-id="3bce0-143">セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="3bce0-143">Security Overview</span></span>](security-overview.md)  
  
 [<span data-ttu-id="3bce0-144">Security</span><span class="sxs-lookup"><span data-stu-id="3bce0-144">Security</span></span>](security.md)  
  
 [<span data-ttu-id="3bce0-145">バインディングとセキュリティ</span><span class="sxs-lookup"><span data-stu-id="3bce0-145">Bindings and Security</span></span>](bindings-and-security.md)  
  
 [<span data-ttu-id="3bce0-146">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="3bce0-146">Securing Services and Clients</span></span>](securing-services-and-clients.md)  
  
 [<span data-ttu-id="3bce0-147">認証</span><span class="sxs-lookup"><span data-stu-id="3bce0-147">Authentication</span></span>](authentication-in-wcf.md)  
  
 [<span data-ttu-id="3bce0-148">承認</span><span class="sxs-lookup"><span data-stu-id="3bce0-148">Authorization</span></span>](authorization-in-wcf.md)  
  
 [<span data-ttu-id="3bce0-149">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="3bce0-149">Federation and Issued Tokens</span></span>](federation-and-issued-tokens.md)  
  
 [<span data-ttu-id="3bce0-150">監査</span><span class="sxs-lookup"><span data-stu-id="3bce0-150">Auditing</span></span>](auditing-security-events.md)  
  
## <a name="see-also"></a><span data-ttu-id="3bce0-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="3bce0-151">See also</span></span>

- [<span data-ttu-id="3bce0-152">セキュリティ ガイドラインとベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="3bce0-152">Security Guidance and Best Practices</span></span>](security-guidance-and-best-practices.md)
- <span data-ttu-id="3bce0-153">[Windows Server AppFabric のセキュリティ モデル](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="3bce0-153">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
