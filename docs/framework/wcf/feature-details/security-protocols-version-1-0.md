---
title: セキュリティ プロトコル バージョン 1.0
ms.date: 03/30/2017
ms.assetid: ee3402d2-1076-410b-a3cb-fae0372bd7af
ms.openlocfilehash: 2014e1f6f8fefa89ed44bd820c3712617ff51470
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184519"
---
# <a name="security-protocols-version-10"></a><span data-ttu-id="a5338-102">セキュリティ プロトコル バージョン 1.0</span><span class="sxs-lookup"><span data-stu-id="a5338-102">Security Protocols version 1.0</span></span>
<span data-ttu-id="a5338-103">Web サービス セキュリティ プロトコルには、既存のエンタープライズ メッセージング セキュリティのあらゆる要件に対応する Web サービス セキュリティ機構が用意されています。</span><span class="sxs-lookup"><span data-stu-id="a5338-103">The Web Services Security Protocols provide Web services security mechanisms that cover all existing enterprise messaging security requirements.</span></span> <span data-ttu-id="a5338-104">このセクションでは、次の Web サービス セキュリティ プロトコルの Windows 通信財団<xref:System.ServiceModel.Channels.SecurityBindingElement>(WCF) バージョン 1.0 の詳細 (で実装) について説明します。</span><span class="sxs-lookup"><span data-stu-id="a5338-104">This section describes the Windows Communication Foundation (WCF) version 1.0 details (implemented in the <xref:System.ServiceModel.Channels.SecurityBindingElement>) for the following Web services security protocols.</span></span>  
  
|<span data-ttu-id="a5338-105">仕様/ドキュメント</span><span class="sxs-lookup"><span data-stu-id="a5338-105">Specification/Document</span></span>|<span data-ttu-id="a5338-106">Link</span><span class="sxs-lookup"><span data-stu-id="a5338-106">Link</span></span>|  
|-|-|  
|<span data-ttu-id="a5338-107">WSS SOAP Message Security 1.0</span><span class="sxs-lookup"><span data-stu-id="a5338-107">WSS: SOAP Message Security 1.0</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf>|
|<span data-ttu-id="a5338-108">WSS: Username Token Profile 1.0</span><span class="sxs-lookup"><span data-stu-id="a5338-108">WSS: Username Token Profile 1.0</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf>|
|<span data-ttu-id="a5338-109">WSS: X509 Token Profile 1.0</span><span class="sxs-lookup"><span data-stu-id="a5338-109">WSS: X509 Token Profile 1.0</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf>|
|<span data-ttu-id="a5338-110">WSS: SAML 1.1 Token Profile 1.0</span><span class="sxs-lookup"><span data-stu-id="a5338-110">WSS: SAML 1.1 Token Profile 1.0</span></span>|<https://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.0.pdf>|
|<span data-ttu-id="a5338-111">WSS SOAP Message Security 1.1</span><span class="sxs-lookup"><span data-stu-id="a5338-111">WSS: SOAP Message Security 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf>|
|<span data-ttu-id="a5338-112">WSS Username Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="a5338-112">WSS Username Token Profile 1.1</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf>|
|<span data-ttu-id="a5338-113">WSS: X.509 Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="a5338-113">WSS: X.509 Token Profile 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf>|
|<span data-ttu-id="a5338-114">WSS: Kerberos Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="a5338-114">WSS: Kerberos Token Profile 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf>|
|<span data-ttu-id="a5338-115">WSS: SAML 1.1 Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="a5338-115">WSS: SAML 1.1 Token Profile 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16768/wss-v1.1-spec-os-SAMLTokenProfile.pdf>|
|<span data-ttu-id="a5338-116">WS-SecureConversation</span><span class="sxs-lookup"><span data-stu-id="a5338-116">WS-Secure Conversation</span></span>|<https://specs.xmlsoap.org/ws/2005/02/sc/WS-SecureConversation.pdf>|
|<span data-ttu-id="a5338-117">WS-Trust</span><span class="sxs-lookup"><span data-stu-id="a5338-117">WS-Trust</span></span>|<https://specs.xmlsoap.org/ws/2005/02/trust/ws-trust.pdf>|
|<span data-ttu-id="a5338-118">Application Note:</span><span class="sxs-lookup"><span data-stu-id="a5338-118">Application Note:</span></span><br /><br /> <span data-ttu-id="a5338-119">Using WS-Trust for TLS Handshake</span><span class="sxs-lookup"><span data-stu-id="a5338-119">Using WS-Trust for TLS Handshake</span></span>|<span data-ttu-id="a5338-120">公開予定</span><span class="sxs-lookup"><span data-stu-id="a5338-120">To be published</span></span>|  
|<span data-ttu-id="a5338-121">Application Note:</span><span class="sxs-lookup"><span data-stu-id="a5338-121">Application Note:</span></span><br /><br /> <span data-ttu-id="a5338-122">Using WS-Trust for SPNEGO</span><span class="sxs-lookup"><span data-stu-id="a5338-122">Using WS-Trust for SPNEGO</span></span>|<span data-ttu-id="a5338-123">公開予定</span><span class="sxs-lookup"><span data-stu-id="a5338-123">To be published</span></span>|  
|<span data-ttu-id="a5338-124">Application Note:</span><span class="sxs-lookup"><span data-stu-id="a5338-124">Application Note:</span></span><br /><br /> <span data-ttu-id="a5338-125">Web Services Addressing Endpoint References And Identity</span><span class="sxs-lookup"><span data-stu-id="a5338-125">Web Services Addressing Endpoint References And Identity</span></span>|<span data-ttu-id="a5338-126">公開予定</span><span class="sxs-lookup"><span data-stu-id="a5338-126">To be published</span></span>|  
|<span data-ttu-id="a5338-127">WS-SecurityPolicy 1.1</span><span class="sxs-lookup"><span data-stu-id="a5338-127">WS-SecurityPolicy 1.1</span></span><br /><br /> <span data-ttu-id="a5338-128">(2005/07)</span><span class="sxs-lookup"><span data-stu-id="a5338-128">(2005/07)</span></span>|<https://specs.xmlsoap.org/ws/2005/07/securitypolicy/ws-securitypolicy.pdf><br /><br /> <span data-ttu-id="a5338-129">OASIS WS-SX技術委員会に提出された[正誤によって](https://lists.oasis-open.org/archives/ws-sx/200512/msg00017.html)修正された</span><span class="sxs-lookup"><span data-stu-id="a5338-129">as amended by [errata](https://lists.oasis-open.org/archives/ws-sx/200512/msg00017.html) submitted to OASIS WS-SX Technical Committee</span></span> |  
  
 <span data-ttu-id="a5338-130">WCF バージョン 1 では、Web サービス セキュリティ構成の基礎として使用できる 17 の認証モードを提供します。</span><span class="sxs-lookup"><span data-stu-id="a5338-130">WCF, version 1, provides 17 authentication modes that can be used as the basis for Web services security configuration.</span></span> <span data-ttu-id="a5338-131">各モードは、次のような一般的な展開要件について最適化されています。</span><span class="sxs-lookup"><span data-stu-id="a5338-131">Each mode is optimized for a common set of deployment requirements, such as:</span></span>  
  
- <span data-ttu-id="a5338-132">クライアントとサービスの認証に使用する資格情報</span><span class="sxs-lookup"><span data-stu-id="a5338-132">Credentials used to authenticate client and service.</span></span>  
  
- <span data-ttu-id="a5338-133">メッセージまたはトランスポートのセキュリティ保護機構</span><span class="sxs-lookup"><span data-stu-id="a5338-133">Message or transport security protection mechanisms.</span></span>  
  
- <span data-ttu-id="a5338-134">メッセージ交換パターン</span><span class="sxs-lookup"><span data-stu-id="a5338-134">Message exchange patterns.</span></span>  
  
|<span data-ttu-id="a5338-135">認証モード</span><span class="sxs-lookup"><span data-stu-id="a5338-135">Authentication Mode</span></span>|<span data-ttu-id="a5338-136">クライアント認証</span><span class="sxs-lookup"><span data-stu-id="a5338-136">Client Authentication</span></span>|<span data-ttu-id="a5338-137">[サーバー認証]</span><span class="sxs-lookup"><span data-stu-id="a5338-137">Server Authentication</span></span>|<span data-ttu-id="a5338-138">モード</span><span class="sxs-lookup"><span data-stu-id="a5338-138">Mode</span></span>|  
|-------------------------|---------------------------|---------------------------|----------|  
|<span data-ttu-id="a5338-139">UserNameOverTransport</span><span class="sxs-lookup"><span data-stu-id="a5338-139">UserNameOverTransport</span></span>|<span data-ttu-id="a5338-140">ユーザー名/パスワード</span><span class="sxs-lookup"><span data-stu-id="a5338-140">User name/password</span></span>|<span data-ttu-id="a5338-141">X509</span><span class="sxs-lookup"><span data-stu-id="a5338-141">X509</span></span>|<span data-ttu-id="a5338-142">トランスポート</span><span class="sxs-lookup"><span data-stu-id="a5338-142">Transport</span></span>|  
|<span data-ttu-id="a5338-143">CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="a5338-143">CertificateOverTransport</span></span>|<span data-ttu-id="a5338-144">X509</span><span class="sxs-lookup"><span data-stu-id="a5338-144">X509</span></span>|<span data-ttu-id="a5338-145">X509</span><span class="sxs-lookup"><span data-stu-id="a5338-145">X509</span></span>|<span data-ttu-id="a5338-146">トランスポート</span><span class="sxs-lookup"><span data-stu-id="a5338-146">Transport</span></span>|  
|<span data-ttu-id="a5338-147">KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="a5338-147">KerberosOverTransport</span></span>|<span data-ttu-id="a5338-148">Windows</span><span class="sxs-lookup"><span data-stu-id="a5338-148">Windows</span></span>|<span data-ttu-id="a5338-149">X509</span><span class="sxs-lookup"><span data-stu-id="a5338-149">X509</span></span>|<span data-ttu-id="a5338-150">トランスポート</span><span class="sxs-lookup"><span data-stu-id="a5338-150">Transport</span></span>|  
|<span data-ttu-id="a5338-151">IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="a5338-151">IssuedTokenOverTransport</span></span>|<span data-ttu-id="a5338-152">フェデレーション</span><span class="sxs-lookup"><span data-stu-id="a5338-152">Federated</span></span>|<span data-ttu-id="a5338-153">X509</span><span class="sxs-lookup"><span data-stu-id="a5338-153">X509</span></span>|<span data-ttu-id="a5338-154">トランスポート</span><span class="sxs-lookup"><span data-stu-id="a5338-154">Transport</span></span>|  
|<span data-ttu-id="a5338-155">SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="a5338-155">SspiNegotiatedOverTransport</span></span>|<span data-ttu-id="a5338-156">Windows SSPI ネゴシエーション</span><span class="sxs-lookup"><span data-stu-id="a5338-156">Windows Sspi Negotiated</span></span>|<span data-ttu-id="a5338-157">Windows SSPI ネゴシエーション</span><span class="sxs-lookup"><span data-stu-id="a5338-157">Windows Sspi Negotiated</span></span>|<span data-ttu-id="a5338-158">トランスポート</span><span class="sxs-lookup"><span data-stu-id="a5338-158">Transport</span></span>|  
|<span data-ttu-id="a5338-159">AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="a5338-159">AnonymousForCertificate</span></span>|<span data-ttu-id="a5338-160">なし</span><span class="sxs-lookup"><span data-stu-id="a5338-160">None</span></span>|<span data-ttu-id="a5338-161">X509</span><span class="sxs-lookup"><span data-stu-id="a5338-161">X509</span></span>|<span data-ttu-id="a5338-162">Message</span><span class="sxs-lookup"><span data-stu-id="a5338-162">Message</span></span>|  
|<span data-ttu-id="a5338-163">UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="a5338-163">UserNameForCertificate</span></span>|<span data-ttu-id="a5338-164">ユーザー名/パスワード</span><span class="sxs-lookup"><span data-stu-id="a5338-164">User name/password</span></span>|<span data-ttu-id="a5338-165">X509</span><span class="sxs-lookup"><span data-stu-id="a5338-165">X509</span></span>|<span data-ttu-id="a5338-166">Message</span><span class="sxs-lookup"><span data-stu-id="a5338-166">Message</span></span>|  
|<span data-ttu-id="a5338-167">MutualCertificate</span><span class="sxs-lookup"><span data-stu-id="a5338-167">MutualCertificate</span></span>|<span data-ttu-id="a5338-168">X509</span><span class="sxs-lookup"><span data-stu-id="a5338-168">X509</span></span>|<span data-ttu-id="a5338-169">X509</span><span class="sxs-lookup"><span data-stu-id="a5338-169">X509</span></span>|<span data-ttu-id="a5338-170">Message</span><span class="sxs-lookup"><span data-stu-id="a5338-170">Message</span></span>|  
|<span data-ttu-id="a5338-171">MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="a5338-171">MutualCertificateDuplex</span></span>|<span data-ttu-id="a5338-172">X509</span><span class="sxs-lookup"><span data-stu-id="a5338-172">X509</span></span>|<span data-ttu-id="a5338-173">X509</span><span class="sxs-lookup"><span data-stu-id="a5338-173">X509</span></span>|<span data-ttu-id="a5338-174">Message</span><span class="sxs-lookup"><span data-stu-id="a5338-174">Message</span></span>|  
|<span data-ttu-id="a5338-175">IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="a5338-175">IssuedTokenForCertificate</span></span>|<span data-ttu-id="a5338-176">フェデレーション</span><span class="sxs-lookup"><span data-stu-id="a5338-176">Federated</span></span>|<span data-ttu-id="a5338-177">X509</span><span class="sxs-lookup"><span data-stu-id="a5338-177">X509</span></span>|<span data-ttu-id="a5338-178">Message</span><span class="sxs-lookup"><span data-stu-id="a5338-178">Message</span></span>|  
|<span data-ttu-id="a5338-179">Kerberos</span><span class="sxs-lookup"><span data-stu-id="a5338-179">Kerberos</span></span>|<span data-ttu-id="a5338-180">Windows</span><span class="sxs-lookup"><span data-stu-id="a5338-180">Windows</span></span>|<span data-ttu-id="a5338-181">Windows</span><span class="sxs-lookup"><span data-stu-id="a5338-181">Windows</span></span>|<span data-ttu-id="a5338-182">Message</span><span class="sxs-lookup"><span data-stu-id="a5338-182">Message</span></span>|  
|<span data-ttu-id="a5338-183">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="a5338-183">IssuedToken</span></span>|<span data-ttu-id="a5338-184">フェデレーション</span><span class="sxs-lookup"><span data-stu-id="a5338-184">Federated</span></span>|<span data-ttu-id="a5338-185">フェデレーション</span><span class="sxs-lookup"><span data-stu-id="a5338-185">Federated</span></span>|<span data-ttu-id="a5338-186">Message</span><span class="sxs-lookup"><span data-stu-id="a5338-186">Message</span></span>|  
|<span data-ttu-id="a5338-187">SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="a5338-187">SspiNegotiated</span></span>|<span data-ttu-id="a5338-188">Windows SSPI ネゴシエーション</span><span class="sxs-lookup"><span data-stu-id="a5338-188">Windows Sspi Negotiated</span></span>|<span data-ttu-id="a5338-189">Windows SSPI ネゴシエーション</span><span class="sxs-lookup"><span data-stu-id="a5338-189">Windows Sspi Negotiated</span></span>|<span data-ttu-id="a5338-190">Message</span><span class="sxs-lookup"><span data-stu-id="a5338-190">Message</span></span>|  
|<span data-ttu-id="a5338-191">AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="a5338-191">AnonymousForSslNegotiated</span></span>|<span data-ttu-id="a5338-192">なし</span><span class="sxs-lookup"><span data-stu-id="a5338-192">None</span></span>|<span data-ttu-id="a5338-193">X509、TLS ネゴシエーション</span><span class="sxs-lookup"><span data-stu-id="a5338-193">X509, TLS-Nego</span></span>|<span data-ttu-id="a5338-194">Message</span><span class="sxs-lookup"><span data-stu-id="a5338-194">Message</span></span>|  
|<span data-ttu-id="a5338-195">UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="a5338-195">UserNameForSslNegotiated</span></span>|<span data-ttu-id="a5338-196">ユーザー名/パスワード</span><span class="sxs-lookup"><span data-stu-id="a5338-196">User name/password</span></span>|<span data-ttu-id="a5338-197">X509、TLS ネゴシエーション</span><span class="sxs-lookup"><span data-stu-id="a5338-197">X509, TLS-Nego</span></span>|<span data-ttu-id="a5338-198">Message</span><span class="sxs-lookup"><span data-stu-id="a5338-198">Message</span></span>|  
|<span data-ttu-id="a5338-199">MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="a5338-199">MutualSslNegotiated</span></span>|<span data-ttu-id="a5338-200">X509</span><span class="sxs-lookup"><span data-stu-id="a5338-200">X509</span></span>|<span data-ttu-id="a5338-201">X509、TLS ネゴシエーション</span><span class="sxs-lookup"><span data-stu-id="a5338-201">X509, TLS-Nego</span></span>|<span data-ttu-id="a5338-202">Message</span><span class="sxs-lookup"><span data-stu-id="a5338-202">Message</span></span>|  
|<span data-ttu-id="a5338-203">IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="a5338-203">IssuedTokenForSslNegotiated</span></span>|<span data-ttu-id="a5338-204">フェデレーション</span><span class="sxs-lookup"><span data-stu-id="a5338-204">Federated</span></span>|<span data-ttu-id="a5338-205">X509、TLS ネゴシエーション</span><span class="sxs-lookup"><span data-stu-id="a5338-205">X509, TLS-Nego</span></span>|<span data-ttu-id="a5338-206">Message</span><span class="sxs-lookup"><span data-stu-id="a5338-206">Message</span></span>|  
  
 <span data-ttu-id="a5338-207">このような認証モードを使用するエンドポイントは、WS-SecurityPolicy (WS-SP) を使用してセキュリティ要件を表現できます。</span><span class="sxs-lookup"><span data-stu-id="a5338-207">Endpoints using such authentication modes can express their security requirements using WS-SecurityPolicy (WS-SP).</span></span> <span data-ttu-id="a5338-208">ここでは、各認証モードのセキュリティ ヘッダーとインフラストラクチャ メッセージの構造について説明します。また、ポリシーとメッセージの例も示します。</span><span class="sxs-lookup"><span data-stu-id="a5338-208">This document describes the structure of security header and infrastructure messages for each authentication mode and provides examples of policies and messages.</span></span>  
  
 <span data-ttu-id="a5338-209">WCF では WS-SecureConversation を利用して、セキュリティで保護されたセッションのサポートを提供し、アプリケーション間の複数メッセージ交換を保護します。</span><span class="sxs-lookup"><span data-stu-id="a5338-209">WCF leverages WS-SecureConversation to provide secure sessions support to protect multi-message exchanges between applications.</span></span>  <span data-ttu-id="a5338-210">実装の詳細については、後述の「セキュリティで保護されたセッション」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5338-210">See "Secure Sessions" below for implementation details.</span></span>  
  
 <span data-ttu-id="a5338-211">認証モードに加えて、WCF は、ほとんどのメッセージ セキュリティ ベースの認証モードに適用される共通の保護メカニズムを制御するための設定を提供します。、および署名の確認。</span><span class="sxs-lookup"><span data-stu-id="a5338-211">In addition to authentication modes, WCF provides settings to control common protection mechanisms that apply to most message security-based authentication modes, for example: order of signature versus encryption operations, algorithm suites, key derivation, and signature confirmation.</span></span>  
  
 <span data-ttu-id="a5338-212">このドキュメントでは、以下のプレフィックスと名前空間を使用します。</span><span class="sxs-lookup"><span data-stu-id="a5338-212">The following prefixes and namespaces are used in this document.</span></span>  
  
|<span data-ttu-id="a5338-213">Prefix</span><span class="sxs-lookup"><span data-stu-id="a5338-213">Prefix</span></span>|<span data-ttu-id="a5338-214">名前空間</span><span class="sxs-lookup"><span data-stu-id="a5338-214">Namespace</span></span>|  
|------------|---------------|  
|<span data-ttu-id="a5338-215">s</span><span class="sxs-lookup"><span data-stu-id="a5338-215">s</span></span>|<http://www.w3.org/2003/05/soap-envelope/>|
|<span data-ttu-id="a5338-216">sp</span><span class="sxs-lookup"><span data-stu-id="a5338-216">sp</span></span>|<http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/>|
|<span data-ttu-id="a5338-217">a</span><span class="sxs-lookup"><span data-stu-id="a5338-217">a</span></span>|<http://www.w3.org/2005/08/addressing>|  
|<span data-ttu-id="a5338-218">wsse</span><span class="sxs-lookup"><span data-stu-id="a5338-218">wsse</span></span>|<span data-ttu-id="a5338-219">未定 - OASIS WSS 1.0 の URI</span><span class="sxs-lookup"><span data-stu-id="a5338-219">TBD – OASIS WSS 1.0 URI</span></span>|  
|<span data-ttu-id="a5338-220">wsse11</span><span class="sxs-lookup"><span data-stu-id="a5338-220">wsse11</span></span>|<span data-ttu-id="a5338-221">未定 - OASIS WSS 1.1 の URI</span><span class="sxs-lookup"><span data-stu-id="a5338-221">TBD – OASIS WSS 1.1 URI</span></span>|  
|<span data-ttu-id="a5338-222">wsu</span><span class="sxs-lookup"><span data-stu-id="a5338-222">wsu</span></span>|<span data-ttu-id="a5338-223">未定 - OASIS WSS 1.0 Utility の URI</span><span class="sxs-lookup"><span data-stu-id="a5338-223">TBD – OASIS WSS 1.0 Utility URI</span></span>|  
|<span data-ttu-id="a5338-224">ds</span><span class="sxs-lookup"><span data-stu-id="a5338-224">ds</span></span>|<span data-ttu-id="a5338-225">未定 - W3C XMLDSig の URI</span><span class="sxs-lookup"><span data-stu-id="a5338-225">TBD – W3C XMLDSig URI</span></span>|  
|<span data-ttu-id="a5338-226">wst</span><span class="sxs-lookup"><span data-stu-id="a5338-226">wst</span></span>|<span data-ttu-id="a5338-227">未定 - WS-Trust 2005/02 の URI</span><span class="sxs-lookup"><span data-stu-id="a5338-227">TBD – WS-Trust 2005/02 URI</span></span>|  
|<span data-ttu-id="a5338-228">wssc</span><span class="sxs-lookup"><span data-stu-id="a5338-228">wssc</span></span>|<span data-ttu-id="a5338-229">未定 - WS-SecureConversation 2005/02 の URI</span><span class="sxs-lookup"><span data-stu-id="a5338-229">TBD – WS-SecureConversation 2005/02 URI</span></span>|  
|<span data-ttu-id="a5338-230">wsaw</span><span class="sxs-lookup"><span data-stu-id="a5338-230">wsaw</span></span>|<span data-ttu-id="a5338-231">未定 - WS-Addressing ポリシーの名前空間</span><span class="sxs-lookup"><span data-stu-id="a5338-231">TBD - WS-Addressing policy namespace</span></span>|  
|<span data-ttu-id="a5338-232">wsp</span><span class="sxs-lookup"><span data-stu-id="a5338-232">wsp</span></span>|<http://schemas.xmlsoap.org/ws/2004/09/policy>|  
|<span data-ttu-id="a5338-233">mssp</span><span class="sxs-lookup"><span data-stu-id="a5338-233">mssp</span></span>|<http://schemas.xmlsoap.org/ws/2005/07/securitypolicy>|
  
## <a name="1-token-profiles"></a><span data-ttu-id="a5338-234">1. トークンプロファイル</span><span class="sxs-lookup"><span data-stu-id="a5338-234">1. Token Profiles</span></span>  
 <span data-ttu-id="a5338-235">Web サービス セキュリティ仕様では、資格情報をセキュリティ トークンとして表します。</span><span class="sxs-lookup"><span data-stu-id="a5338-235">Web Services Security specifications represent credential as security tokens.</span></span> <span data-ttu-id="a5338-236">WCF では、次の種類のトークンをサポートします。</span><span class="sxs-lookup"><span data-stu-id="a5338-236">WCF supports the following token types:</span></span>  
  
### <a name="11-usernametoken"></a><span data-ttu-id="a5338-237">1.1 UsernameToken</span><span class="sxs-lookup"><span data-stu-id="a5338-237">1.1 UsernameToken</span></span>  
 <span data-ttu-id="a5338-238">WCF は、次の制約を持つユーザー名トークン10 およびユーザー名トークン11 プロファイルに従います。</span><span class="sxs-lookup"><span data-stu-id="a5338-238">WCF follows UsernameToken10 and UsernameToken11 profiles with the following constraints:</span></span>  
  
 <span data-ttu-id="a5338-239">R1101 : UsernameToken\Password 要素の PasswordType 属性では、#PasswordText (既定値) を省略するか、指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5338-239">R1101 PasswordType attribute on UsernameToken\Password element MUST be either omitted or have value #PasswordText (default).</span></span>  
  
 <span data-ttu-id="a5338-240">機能拡張を使用すると、#PasswordDigest を実装できます。</span><span class="sxs-lookup"><span data-stu-id="a5338-240">One can implement the #PasswordDigest using extensibility.</span></span> <span data-ttu-id="a5338-241">#PasswordDigest は、十分に安全性の高いパスワード保護機構であると誤解されがちであることが報告されています。</span><span class="sxs-lookup"><span data-stu-id="a5338-241">It has been observed that #PasswordDigest was often mistaken to be a secure enough password protection mechanism.</span></span> <span data-ttu-id="a5338-242">しかし、#PasswordDigest は、UsernameToken の暗号化の代替として使用できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="a5338-242">But #PasswordDigest cannot serve as a substitute for encryption of the UsernameToken.</span></span> <span data-ttu-id="a5338-243">#PasswordDigest の第一の目的は、リプレイ攻撃から保護することです。</span><span class="sxs-lookup"><span data-stu-id="a5338-243">The primary goal of #PasswordDigest is protection against replay attacks.</span></span> <span data-ttu-id="a5338-244">WCF 認証モードでは、リプレイ攻撃の脅威は、メッセージ署名を使用して軽減されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-244">In WCF authentication modes, replay attack threats are mitigated by using message signatures.</span></span>  
  
 <span data-ttu-id="a5338-245">B1102 WCF は、ユーザー名トークンの Nonce および作成済みサブ要素を生成しません。</span><span class="sxs-lookup"><span data-stu-id="a5338-245">B1102 WCF never emits Nonce and Created sub-elements of the UsernameToken.</span></span>  
  
 <span data-ttu-id="a5338-246">これらのサブ要素は、リプレイ検出を支援するためのものです。</span><span class="sxs-lookup"><span data-stu-id="a5338-246">These sub-elements are intended to help replay detection.</span></span> <span data-ttu-id="a5338-247">WCF では、代わりにメッセージ署名が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-247">WCF uses message signatures instead.</span></span>  
  
 <span data-ttu-id="a5338-248">OASIS WSS SOAP Message Security UsernameToken Profile 1.1 (UsernameToken11) では、パスワードからのキー派生機能が導入されています。</span><span class="sxs-lookup"><span data-stu-id="a5338-248">OASIS WSS SOAP Message Security UsernameToken Profile 1.1 (UsernameToken11) introduced key derivation from password feature.</span></span>  
  
 <span data-ttu-id="a5338-249">B1103 : UsernameToken のパスワードをキー派生に使用することはできません。したがって、暗号化操作では使用できません。</span><span class="sxs-lookup"><span data-stu-id="a5338-249">B1103 UsernameToken password MUST not be used for key derivation and therefore for cryptographic operations.</span></span>  
  
 <span data-ttu-id="a5338-250">理由 : パスワードは、一般に暗号化操作に使用するには脆弱すぎると見なされています。</span><span class="sxs-lookup"><span data-stu-id="a5338-250">Rationale: passwords are generally considered too weak to be used for cryptographic operations.</span></span>  
  
### <a name="12-x509-token"></a><span data-ttu-id="a5338-251">1.2 X509 トークン</span><span class="sxs-lookup"><span data-stu-id="a5338-251">1.2 X509 Token</span></span>  
 <span data-ttu-id="a5338-252">WCF は、資格情報の種類として X509v3 証明書をサポートし、次の制約を持つ X509TokenProfile1.0 および X509TokenProfile1.1 に従います。</span><span class="sxs-lookup"><span data-stu-id="a5338-252">WCF supports X509v3 certificates as a credential type and follows X509TokenProfile1.0 and X509TokenProfile1.1 with the following constraints:</span></span>  
  
 <span data-ttu-id="a5338-253">R1201 : BinarySecurityToken 要素に X509v3 証明書が含まれている場合、この要素の ValueType 属性の値は #X509v3 であることが必要です。</span><span class="sxs-lookup"><span data-stu-id="a5338-253">R1201 The ValueType attribute on the BinarySecurityToken element must have value #X509v3 when it contains an X509v3 certificate.</span></span>  
  
 <span data-ttu-id="a5338-254">WSS X509 Token Profile 1.0 および 1.1 では、値の種類として #X509PKIPathv1 と #PKCS7 も定義されています。</span><span class="sxs-lookup"><span data-stu-id="a5338-254">WSS X509 Token Profile 1.0 and 1.1 define also #X509PKIPathv1 and #PKCS7 as value types.</span></span> <span data-ttu-id="a5338-255">WCF では、これらの型をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="a5338-255">WCF does not support these types.</span></span>  
  
 <span data-ttu-id="a5338-256">R1202 : X509 証明書に SubjectKeyIdentifier (SKI) 拡張が含まれている場合、トークンへの外部参照に wsse:KeyIdentifier を使用する必要があります。この場合、ValueType 属性に #X509SubjectKeyIdentifier を指定し、証明書の SKI 拡張の Base64 でエンコードされた値を含めます。</span><span class="sxs-lookup"><span data-stu-id="a5338-256">R1202 If a SubjectKeyIdentifier (SKI) extension is present in an X509 certificate, wsse:KeyIdentifier should be used for external references to the token, with the ValueType attribute as #X509SubjectKeyIdentifier and its content the base64-encoded value of certificate's SKI extension.</span></span>  
  
 <span data-ttu-id="a5338-257">SKI 参照は幅広く実装されており、相互運用性の高い外部参照型であることが証明されています。</span><span class="sxs-lookup"><span data-stu-id="a5338-257">SKI references are widely implemented and proven to be a highly interoperable external reference type.</span></span>  
  
 <span data-ttu-id="a5338-258">R1203 : X509 セキュリティ トークンへの外部参照では、ds:X509IssuerSerial を使用できません。</span><span class="sxs-lookup"><span data-stu-id="a5338-258">R1203 An external Reference to X509 Security Token SHOULD NOT use ds:X509IssuerSerial.</span></span>  
  
 <span data-ttu-id="a5338-259">R1204 : X509TokenProfile1.1 を使用している場合、X509 セキュリティ トークンへの外部参照では、WS-Security 1.1 で導入された拇印を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5338-259">R1204 If X509TokenProfile1.1 is in use, an external reference to X509 Security Token SHOULD use the thumbprint introduced by WS-Security 1.1.</span></span>  
  
 <span data-ttu-id="a5338-260">WCF は、X509 発行者シリアルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a5338-260">WCF supports X509IssuerSerial.</span></span> <span data-ttu-id="a5338-261">ただし、X509IssuerSerial との相互運用性の問題があります: WCF は、X509IssuerSerial の 2 つの値を比較するために文字列を使用します。</span><span class="sxs-lookup"><span data-stu-id="a5338-261">However There are interoperability issues with X509IssuerSerial: WCF uses a string to compare two values of X509IssuerSerial.</span></span> <span data-ttu-id="a5338-262">したがって、サブジェクト名のコンポーネントを並べ替え、WCF サービスに証明書への参照を送信した場合、そのコンポーネントが見つからない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a5338-262">Therefore if one reorders components of the Subject Name and sends to an WCF service a reference to a certificate, it may not be found.</span></span>  
  
### <a name="13-kerberos-token"></a><span data-ttu-id="a5338-263">1.3 Kerberos トークン</span><span class="sxs-lookup"><span data-stu-id="a5338-263">1.3 Kerberos Token</span></span>  
 <span data-ttu-id="a5338-264">WCF は、次の制約を持つ Windows 認証の目的で KerberosTokenProfile1.1 をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a5338-264">WCF supports KerberosTokenProfile1.1 for the purpose of Windows authentication with the following constraints:</span></span>  
  
 <span data-ttu-id="a5338-265">R1301 : GSS_API と Kerberos 仕様で定義されているように、Kerberos トークンは GSS によってラップされた Kerberos v4 AP_REQ の値を伝達する必要があります。また、値 #GSS_Kerberosv5_AP_REQ が指定された ValueType 属性を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5338-265">R1301 A Kerberos Token must carry the value of a GSS wrapped Kerberos v4 AP_REQ as defined in GSS_API and the Kerberos specification, and must have the ValueType attribute with the value #GSS_Kerberosv5_AP_REQ.</span></span>  
  
 <span data-ttu-id="a5338-266">WCF は、ベア AP-REQ ではなく、GSS でラップされた Kerberos AP-REQ を使用します。</span><span class="sxs-lookup"><span data-stu-id="a5338-266">WCF uses GSS wrapped Kerberos AP-REQ, not a bare AP-REQ.</span></span> <span data-ttu-id="a5338-267">これは、セキュリティのベスト プラクティスです。</span><span class="sxs-lookup"><span data-stu-id="a5338-267">This is a security best practice.</span></span>  
  
### <a name="14-saml-v11-token"></a><span data-ttu-id="a5338-268">1.4 SAML v1.1 トークン</span><span class="sxs-lookup"><span data-stu-id="a5338-268">1.4 SAML v1.1 Token</span></span>  
 <span data-ttu-id="a5338-269">WCF は、SAML v1.1 トークンの WSS SAML トークン プロファイル 1.0 および 1.1 をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a5338-269">WCF supports WSS SAML Token profiles 1.0 and 1.1 for SAML v1.1 tokens.</span></span> <span data-ttu-id="a5338-270">SAML トークンの形式のその他のバージョンも実装できます。</span><span class="sxs-lookup"><span data-stu-id="a5338-270">It is possible to implement other versions of SAML token formats.</span></span>  
  
### <a name="15-security-context-token"></a><span data-ttu-id="a5338-271">1.5 セキュリティ コンテキスト トークン</span><span class="sxs-lookup"><span data-stu-id="a5338-271">1.5 Security Context Token</span></span>  
 <span data-ttu-id="a5338-272">WCF は、WS-Secure 会話で導入されたセキュリティ コンテキスト トークン (SCT) をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a5338-272">WCF supports the Security Context Token (SCT) introduced in WS-SecureConversation.</span></span> <span data-ttu-id="a5338-273">SCT は、SecureConversation と、後述する TLS および SSPI の各バイナリ ネゴシエーション プロトコルで確立されたセキュリティ コンテキストを表すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-273">SCT is used to represent a security context established in SecureConversation as well as the binary negotiation protocols TLS and SSPI, described below.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="a5338-274">2. 共通メッセージセキュリティパラメータ</span><span class="sxs-lookup"><span data-stu-id="a5338-274">2. Common Message Security Parameters</span></span>  
  
### <a name="21-timestamp"></a><span data-ttu-id="a5338-275">2.1 タイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="a5338-275">2.1 TimeStamp</span></span>  
 <span data-ttu-id="a5338-276">タイムスタンプの有無は、<xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> クラスの <xref:System.ServiceModel.Channels.SecurityBindingElement> プロパティを使用して制御します。</span><span class="sxs-lookup"><span data-stu-id="a5338-276">Timestamp presence is controlled using the <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> property of the <xref:System.ServiceModel.Channels.SecurityBindingElement> class.</span></span> <span data-ttu-id="a5338-277">WCF は常に wsse:タイムスタンプを wsse:作成し、wsse:Expires フィールドをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="a5338-277">WCF always serializes wsse:TimeStamp with wsse:Created and wsse:Expires fields.</span></span> <span data-ttu-id="a5338-278">署名を使用する場合、wsse:TimeStamp は必ず署名されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-278">The wsse:TimeStamp is always signed when signing is used.</span></span>  
  
### <a name="22-protection-order"></a><span data-ttu-id="a5338-279">2.2 保護の順序</span><span class="sxs-lookup"><span data-stu-id="a5338-279">2.2 Protection Order</span></span>  
 <span data-ttu-id="a5338-280">WCF では、メッセージ保護命令 "暗号化前に署名" と "署名前に暗号化" (セキュリティ ポリシー 1.1) がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a5338-280">WCF supports the message protection order "Sign Before Encrypt" and "Encrypt Before Sign" (Security Policy 1.1).</span></span> <span data-ttu-id="a5338-281">WS-Security 1.1 の SignatureConfirmation 機構を使用していない場合、"署名前に暗号化" を使用して保護されたメッセージを開くと、置き換え攻撃への署名が行われます。また、暗号化された内容に署名すると監査が困難になります。これらの理由から、"暗号化前に署名" を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a5338-281">"Sign Before Encrypt" is recommended for reasons including: messages protected with Encrypt Before Sign are open to signature substitution attacks unless the WS-Security 1.1 SignatureConfirmation mechanism is used, and a signature over encrypted content makes auditing harder.</span></span>  
  
### <a name="23-signature-protection"></a><span data-ttu-id="a5338-282">2.3 署名の保護</span><span class="sxs-lookup"><span data-stu-id="a5338-282">2.3 Signature Protection</span></span>  
 <span data-ttu-id="a5338-283">"署名前に暗号化" を使用する場合、暗号化された内容や署名キー (特に、脆弱なキー マテリアルでカスタム トークンを使用する場合) を推測するブルート フォース攻撃を防ぐために、署名を保護することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a5338-283">When Encrypt Before Sign is used, it is recommended to protect the signature to prevent brute force attacks for guessing the encrypted content or the signing key (especially when a custom token is used with weak key material).</span></span>  
  
### <a name="24-algorithm-suite"></a><span data-ttu-id="a5338-284">2.4 アルゴリズム スイート</span><span class="sxs-lookup"><span data-stu-id="a5338-284">2.4 Algorithm Suite</span></span>  
 <span data-ttu-id="a5338-285">WCF では、セキュリティ ポリシー 1.1 に記載されているすべてのアルゴリズム スイートをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a5338-285">WCF supports all algorithm suites listed in Security Policy 1.1.</span></span>  
  
### <a name="25-key-derivation"></a><span data-ttu-id="a5338-286">2.5 キー派生</span><span class="sxs-lookup"><span data-stu-id="a5338-286">2.5 Key Derivation</span></span>  
 <span data-ttu-id="a5338-287">WCF では、WS-Secure 会話で説明されているように、対称キーのキー派生を使用します。</span><span class="sxs-lookup"><span data-stu-id="a5338-287">WCF uses "Key Derivation for symmetric keys" as described in WS-SecureConversation.</span></span>  
  
### <a name="26-signature-confirmation"></a><span data-ttu-id="a5338-288">2.6 署名確認</span><span class="sxs-lookup"><span data-stu-id="a5338-288">2.6 Signature Confirmation</span></span>  
 <span data-ttu-id="a5338-289">署名確認によって "man-in-the-middle" 攻撃から保護することで、署名セットを保護できます。</span><span class="sxs-lookup"><span data-stu-id="a5338-289">Signature confirmation can be as protection from middle man attacks to protect the set of signatures.</span></span>  
  
### <a name="27-security-header-layout"></a><span data-ttu-id="a5338-290">2.7 セキュリティ ヘッダーのレイアウト</span><span class="sxs-lookup"><span data-stu-id="a5338-290">2.7 Security Header Layout</span></span>  
 <span data-ttu-id="a5338-291">各認証モードでは、セキュリティ ヘッダーの特定のレイアウトが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-291">Each authentication mode describes a certain layout for the security header.</span></span> <span data-ttu-id="a5338-292">セキュリティ ヘッダー内の要素は、部分的に順序付けられています。</span><span class="sxs-lookup"><span data-stu-id="a5338-292">Elements within the security header are semi-ordered.</span></span> <span data-ttu-id="a5338-293">セキュリティ ヘッダーの子要素の順序を定義するために、WS-Security Policy では、以下のセキュリティ ヘッダー レイアウト モードが定義されています。</span><span class="sxs-lookup"><span data-stu-id="a5338-293">To define the order of security header child elements, WS-Security Policy defines the following security header layout modes:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a5338-294">高</span><span class="sxs-lookup"><span data-stu-id="a5338-294">Strict</span></span>|<span data-ttu-id="a5338-295">"使用前に宣言する" という一般的原則に基づき、Security Policy のセクション 7.7.1 に記載された番号付きレイアウト ルールに従って、項目がセキュリティ ヘッダーに追加されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-295">Items are added to the security header following the numbered layout rules described in Security Policy section 7.7.1 according to a general principle of "declare before use".</span></span>|  
|<span data-ttu-id="a5338-296">Lax</span><span class="sxs-lookup"><span data-stu-id="a5338-296">Lax</span></span>|<span data-ttu-id="a5338-297">WSS: SOAP Message Security に準拠した任意の順序で、項目がセキュリティ ヘッダーに追加されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-297">Items are added to the security header in any order that conforms to WSS: SOAP Message Security.</span></span>|  
|<span data-ttu-id="a5338-298">LaxTimestampFirst</span><span class="sxs-lookup"><span data-stu-id="a5338-298">LaxTimestampFirst</span></span>|<span data-ttu-id="a5338-299">セキュリティ ヘッダー内の最初の項目が wsse:Timestamp でなければならないという点を除き、Lax と同じです。</span><span class="sxs-lookup"><span data-stu-id="a5338-299">Same as Lax except that the first item in the security header must be a wsse:Timestamp</span></span>|  
|<span data-ttu-id="a5338-300">LaxTimestampLast</span><span class="sxs-lookup"><span data-stu-id="a5338-300">LaxTimestampLast</span></span>|<span data-ttu-id="a5338-301">セキュリティ ヘッダー内の最後の項目が wsse:Timestamp でなければならないという点を除き、Lax と同じです。</span><span class="sxs-lookup"><span data-stu-id="a5338-301">Same as lax except that the last item in the security header must be a wsse:Timestamp</span></span>|  
  
 <span data-ttu-id="a5338-302">WCF では、セキュリティ ヘッダー レイアウトの 4 つのモードをすべてサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a5338-302">WCF supports all four modes for security header layout.</span></span> <span data-ttu-id="a5338-303">後ほど示す各認証モードのセキュリティ ヘッダーの構造とメッセージの例では、"Strict" モードに従っています。</span><span class="sxs-lookup"><span data-stu-id="a5338-303">Security header structure and message examples for authentication modes below follow the "Strict" mode.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="a5338-304">2. 共通メッセージセキュリティパラメータ</span><span class="sxs-lookup"><span data-stu-id="a5338-304">2. Common Message Security Parameters</span></span>  
 <span data-ttu-id="a5338-305">このセクションでは、各認証モードのポリシーの例、およびクライアントとサービスによって交換されるメッセージのセキュリティ ヘッダーの構造を示す例を紹介します。</span><span class="sxs-lookup"><span data-stu-id="a5338-305">This section provides example policies for each authentication mode along with examples showing security header structure in messages exchanged by client and service.</span></span>  
  
### <a name="61-transport-protection"></a><span data-ttu-id="a5338-306">6.1 トランスポートの保護</span><span class="sxs-lookup"><span data-stu-id="a5338-306">6.1 Transport Protection</span></span>  
 <span data-ttu-id="a5338-307">WCF には、メッセージを保護するためにセキュリティで保護されたトランスポートを使用する 5 つの認証モードが用意されています。ユーザー名オーバートランスポート、証明書オーバートランスポート、KerberosOverトランスポート、発行されたトークンオーバートランスポートとスピーネゴシエートオーバートランスポート。</span><span class="sxs-lookup"><span data-stu-id="a5338-307">WCF provides five authentication modes that use secure transport to protect messages; UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, IssuedTokenOverTransport and SspiNegotiatedOverTransport.</span></span>  
  
 <span data-ttu-id="a5338-308">これらの認証モードは、SecurityPolicy に記載されたトランスポート バインディングを使用して構築されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-308">These authentication modes are constructed using the transport binding described in SecurityPolicy.</span></span> <span data-ttu-id="a5338-309">UserNameOverTransport 認証モードの場合、UsernameToken は署名付きサポート トークンです。</span><span class="sxs-lookup"><span data-stu-id="a5338-309">For the UserNameOverTransport authentication mode the UsernameToken is a signed supporting token.</span></span> <span data-ttu-id="a5338-310">その他の認証モードでは、トークンは署名付き保証トークンとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-310">For the other authentication modes the token appears as a signed endorsing token.</span></span> <span data-ttu-id="a5338-311">SecurityPolicy の Appendix C.1.2 および C.1.3 には、セキュリティ ヘッダーのレイアウトの詳細が記載されています。</span><span class="sxs-lookup"><span data-stu-id="a5338-311">Appendix C.1.2 and C.1.3 of SecurityPolicy describe the security header layout in detail.</span></span> <span data-ttu-id="a5338-312">以降のセキュリティ ヘッダーの例は、指定の認証モードの Strict レイアウトを示しています。</span><span class="sxs-lookup"><span data-stu-id="a5338-312">The following example security headers show the Strict layout for a given authentication mode.</span></span>  
  
 <span data-ttu-id="a5338-313">すべてのケースで、トークンの "派生キー" プロパティの値は "false" です。</span><span class="sxs-lookup"><span data-stu-id="a5338-313">The value of the "Derived Keys" property for the tokens in all cases is "false".</span></span>  
  
 <span data-ttu-id="a5338-314">トランスポート バインディングの各プロパティの値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a5338-314">The values of the various properties of the transport binding are as follows:</span></span>  
  
 <span data-ttu-id="a5338-315">タイムスタンプ : true</span><span class="sxs-lookup"><span data-stu-id="a5338-315">Timestamp: true</span></span>  
  
 <span data-ttu-id="a5338-316">セキュリティ ヘッダーのレイアウト : Strict</span><span class="sxs-lookup"><span data-stu-id="a5338-316">Security Header Layout: Strict</span></span>  
  
 <span data-ttu-id="a5338-317">アルゴリズム スイート : Basic256</span><span class="sxs-lookup"><span data-stu-id="a5338-317">Algorithm Suite: Basic256</span></span>  
  
#### <a name="611-usernameovertransport"></a><span data-ttu-id="a5338-318">6.1.1 UsernameOverTransport</span><span class="sxs-lookup"><span data-stu-id="a5338-318">6.1.1 UsernameOverTransport</span></span>  
 <span data-ttu-id="a5338-319">この認証モードでは、クライアントはユーザー名トークンを使用して認証を行います。ユーザー名トークンは、イニシエーターから受信者に必ず送信される署名付きサポート トークンとして SOAP 層に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-319">With this authentication mode, the client authenticates with a Username Token which appears at the SOAP layer as a signed supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="a5338-320">サービスはトランスポート層で X.509 証明書を使用して認証されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-320">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="a5338-321">使用するバインディングは、トランスポート バインディングです。</span><span class="sxs-lookup"><span data-stu-id="a5338-321">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="a5338-322">ポリシー</span><span class="sxs-lookup"><span data-stu-id="a5338-322">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='UsernameOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:SignedSupportingTokens >  
        <wsp:Policy>  
          <sp:UsernameToken
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy>  
              <sp:WssUsernameToken10 />
            </wsp:Policy>  
          </sp:UsernameToken>  
        </wsp:Policy>  
      </sp:SignedSupportingTokens>  
      <sp:Wss11 >  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10 >  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="a5338-323">セキュリティ ヘッダーのレイアウト</span><span class="sxs-lookup"><span data-stu-id="a5338-323">Security Header Layout</span></span>  
  
 <span data-ttu-id="a5338-324">Request</span><span class="sxs-lookup"><span data-stu-id="a5338-324">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:UsernameToken ... >  
  ...  
  </wsse:UsernameToken>  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-325">Response</span><span class="sxs-lookup"><span data-stu-id="a5338-325">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="612-certificateovertransport"></a><span data-ttu-id="a5338-326">6.1.2 CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="a5338-326">6.1.2 CertificateOverTransport</span></span>  
 <span data-ttu-id="a5338-327">この認証モードでは、クライアントは X.509 証明書を使用して認証を行います。X.509 証明書は、イニシエーターから受信者に必ず送信される保証サポート トークンとして SOAP 層に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-327">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="a5338-328">サービスはトランスポート層で X.509 証明書を使用して認証されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-328">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="a5338-329">使用するバインディングは、トランスポート バインディングです。</span><span class="sxs-lookup"><span data-stu-id="a5338-329">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="a5338-330">ポリシー</span><span class="sxs-lookup"><span data-stu-id="a5338-330">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='CertificateOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding xmlns:sp='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy' >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
             <sp:HttpsToken RequireClientCertificate='false' />
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy>  
              <sp:RequireThumbprintReference />
              <sp:WssX509V3Token10 />
            </wsp:Policy>  
          </sp:X509Token>  
          <sp:SignedParts>  
            <sp:Header Name='To'
Namespace='http://www.w3.org/2005/08/addressing' />
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="a5338-331">セキュリティ ヘッダーのレイアウト</span><span class="sxs-lookup"><span data-stu-id="a5338-331">Security Header Layout</span></span>  
  
 <span data-ttu-id="a5338-332">Request</span><span class="sxs-lookup"><span data-stu-id="a5338-332">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wse:Timestamp u:Id="_0">  
  ...  
  </wse:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-333">Response</span><span class="sxs-lookup"><span data-stu-id="a5338-333">Response</span></span>  
  
```xml  
<o:Security>  
  <u:Timestamp u:Id="_0">  
  ...  
  </u:Timestamp>  
</o:Security>  
```  
  
#### <a name="613-issuedtokenovertransport"></a><span data-ttu-id="a5338-334">6.1.3 IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="a5338-334">6.1.3 IssuedTokenOverTransport</span></span>  
 <span data-ttu-id="a5338-335">この認証モードでは、クライアントはサービスに対する認証を行わず、セキュリティ トークン サービス (STS) により発行されたトークンを示すことで、共有キーの有無を示します。</span><span class="sxs-lookup"><span data-stu-id="a5338-335">With this authentication mode the client does not authenticate to the service, as such, but rather presents a token issued by a Security Token Service (STS) and proves knowledge of a shared key.</span></span> <span data-ttu-id="a5338-336">発行されたトークンは、イニシエーターから受信者に必ず送信される保証サポート トークンとして SOAP 層に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-336">The issued token appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="a5338-337">サービスはトランスポート層で X.509 証明書を使用して認証されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-337">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="a5338-338">バインディングはトランスポート バインディングです。</span><span class="sxs-lookup"><span data-stu-id="a5338-338">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="a5338-339">ポリシー</span><span class="sxs-lookup"><span data-stu-id="a5338-339">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='IssuedTokenOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:IssuedToken
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <sp:RequestSecurityTokenTemplate>  
              <wst:KeyType>  
              http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
              </wst:KeyType>
            </sp:RequestSecurityTokenTemplate>  
            <wsp:Policy>  
              <sp:RequireInternalReference />
            </wsp:Policy>  
          </sp:IssuedToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'
Namespace='http://www.w3.org/2005/08/addressing' />
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="a5338-340">セキュリティ ヘッダーのレイアウト</span><span class="sxs-lookup"><span data-stu-id="a5338-340">Security Header Layout</span></span>  
  
 <span data-ttu-id="a5338-341">Request</span><span class="sxs-lookup"><span data-stu-id="a5338-341">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1" >  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion ...>  
  ...  
  </saml:Assertion>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-342">Response</span><span class="sxs-lookup"><span data-stu-id="a5338-342">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="614-kerberosovertransport"></a><span data-ttu-id="a5338-343">6.1.4 KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="a5338-343">6.1.4 KerberosOverTransport</span></span>  
 <span data-ttu-id="a5338-344">この認証モードを使用すると、クライアントは Kerberos チケットを使用してサービスに対する認証を行います。</span><span class="sxs-lookup"><span data-stu-id="a5338-344">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="a5338-345">Kerberos トークンは、保証サポート トークンとして SOAP 層に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-345">The Kerberos token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="a5338-346">サービスはトランスポート層で X.509 証明書を使用して認証されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-346">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="a5338-347">バインディングはトランスポート バインディングです。</span><span class="sxs-lookup"><span data-stu-id="a5338-347">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="a5338-348">ポリシー</span><span class="sxs-lookup"><span data-stu-id="a5338-348">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='KerberosOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding>  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic128 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:KerberosToken  
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Once' >  
            <wsp:Policy>  
              <sp:WssGssKerberosV5ApReqToken11 />
            </wsp:Policy>  
          </sp:KerberosToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'
Namespace='http://www.w3.org/2005/08/addressing' />
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="a5338-349">セキュリティ ヘッダーのレイアウト</span><span class="sxs-lookup"><span data-stu-id="a5338-349">Security Header Layout</span></span>  
  
 <span data-ttu-id="a5338-350">Request</span><span class="sxs-lookup"><span data-stu-id="a5338-350">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1" >  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken ValueType="...#GSS_Kerberosv5_AP_REQ">  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-351">Response</span><span class="sxs-lookup"><span data-stu-id="a5338-351">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="615-sspinegotiatedovertransport"></a><span data-ttu-id="a5338-352">6.1.5 SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="a5338-352">6.1.5 SspiNegotiatedOverTransport</span></span>  
 <span data-ttu-id="a5338-353">このモードでは、ネゴシエーション プロトコルを使用して、クライアントとサーバーの認証を行います。</span><span class="sxs-lookup"><span data-stu-id="a5338-353">With this mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="a5338-354">Kerberos を使用できる場合は Kerberos が使用され、それ以外の場合は NTLM が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-354">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="a5338-355">発行された SCT は、イニシエーターから受信者に必ず送信される保証サポート トークンとして SOAP 層に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-355">The resulting SCT appears at the SOAP layer as an endorsing supporting token that is always sent from initiator to recipient.</span></span> <span data-ttu-id="a5338-356">サービスは、トランスポート層で X.509 証明書により追加的に認証されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-356">The service is additionally authenticated at the transport layer by an X.509 certificate.</span></span> <span data-ttu-id="a5338-357">使用するバインディングは、トランスポート バインディングです。</span><span class="sxs-lookup"><span data-stu-id="a5338-357">The binding used is a transport binding.</span></span> <span data-ttu-id="a5338-358">"SPNEGO" (ネゴシエーション) では、WCF が WS-Trust で SSPI バイナリ ネゴシエーション プロトコルを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a5338-358">"SPNEGO" (negotiation) describes how WCF uses SSPI binary negotiation protocol with WS-Trust.</span></span> <span data-ttu-id="a5338-359">このセクションで示すセキュリティ ヘッダーの例は、SPNEGO ハンドシェイクによって SCT が確立された後の状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="a5338-359">Security header examples in this section are after the SCT has been established through the SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="a5338-360">ポリシー</span><span class="sxs-lookup"><span data-stu-id="a5338-360">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SspiNegotiatedOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding>  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:SpnegoContextToken
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy />
          </sp:SpnegoContextToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'
Namespace='http://www.w3.org/2005/08/addressing' />
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples"></a><span data-ttu-id="a5338-361">セキュリティ ヘッダーの例</span><span class="sxs-lookup"><span data-stu-id="a5338-361">Security Header Examples</span></span>  
 <span data-ttu-id="a5338-362">WS-Trust バイナリ ネゴシエーションを使用して、SPNEGO ハンドシェイクによってセキュリティ コンテキスト トークンが確立されると、アプリケーション メッセージのセキュリティ ヘッダーは、次のような構造になります。</span><span class="sxs-lookup"><span data-stu-id="a5338-362">Once the Security Context Token is established through SPNEGO handshake using WS-Trust Binary Negotiation, the application messages have security headers with the following structure.</span></span>  
  
 <span data-ttu-id="a5338-363">Request</span><span class="sxs-lookup"><span data-stu-id="a5338-363">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:SecurityContextToken u:Id="uuid-2202746a-7725-453d-8747-809cb718dab0-29" >  
  ...  
  </wssc:SecurityContextToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-364">Response</span><span class="sxs-lookup"><span data-stu-id="a5338-364">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
### <a name="62-using-x509-certificates-for-service-authentication"></a><span data-ttu-id="a5338-365">6.2 X.509 証明書を使用したサービス認証</span><span class="sxs-lookup"><span data-stu-id="a5338-365">6.2 Using X.509 Certificates for Service Authentication</span></span>  
 <span data-ttu-id="a5338-366">このセクションでは、MutualCertificate WSS1.0、Mutual CertificateDuplex、MutualCertificate WSS1.1、AnonymousForCertificate、UserNameForCertificate、および IssuedTokenForCertificate の各認証モードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a5338-366">This section describes the following authentication modes: MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate and IssuedTokenForCertificate.</span></span>  
  
#### <a name="621-mutualcertificate-wss10"></a><span data-ttu-id="a5338-367">6.2.1 MutualCertificate WSS1.0</span><span class="sxs-lookup"><span data-stu-id="a5338-367">6.2.1 MutualCertificate WSS1.0</span></span>  
 <span data-ttu-id="a5338-368">この認証モードでは、クライアントは X.509 証明書を使用して認証を行います。X.509 証明書は、イニシエーター トークンとして SOAP 層に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-368">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="a5338-369">また、サービスは X.509 証明書を使用して認証されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-369">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="a5338-370">使用するバインディングは、次のプロパティ値が設定された非対称バインディングです。</span><span class="sxs-lookup"><span data-stu-id="a5338-370">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="a5338-371">イニシエーター トークン : インクルード モードが .../IncludeToken/AlwaysToRecipient に設定されたクライアントの X.509 証明書</span><span class="sxs-lookup"><span data-stu-id="a5338-371">Initiator Token: the client’s X.509 certificate, with inclusion mode set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="a5338-372">受信者トークン : インクルード モードが …/IncludeToken/Never に設定されたサーバーの X.509 証明書</span><span class="sxs-lookup"><span data-stu-id="a5338-372">Recipient Token: Server’s X.509 Certificate, with inclusion mode is set …/IncludeToken/Never</span></span>  
  
 <span data-ttu-id="a5338-373">トークンの保護 : False</span><span class="sxs-lookup"><span data-stu-id="a5338-373">Token Protection: False</span></span>  
  
 <span data-ttu-id="a5338-374">ヘッダーと本文全体の署名 : True</span><span class="sxs-lookup"><span data-stu-id="a5338-374">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="a5338-375">保護の順序 : SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="a5338-375">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="a5338-376">署名の暗号化 : True</span><span class="sxs-lookup"><span data-stu-id="a5338-376">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="a5338-377">ポリシー</span><span class="sxs-lookup"><span data-stu-id="a5338-377">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='MutualCertificate_WSS10_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:AsymmetricBinding>  
        <wsp:Policy>  
          <sp:InitiatorToken>  
            <wsp:Policy>  
              <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:InitiatorToken>  
          <sp:RecipientToken>  
            <wsp:Policy>  
              <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Never' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:RecipientToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:AsymmetricBinding>  
      <sp:Wss10>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
        </wsp:Policy>  
      </sp:Wss10>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="a5338-378">セキュリティ ヘッダーの例 : SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="a5338-378">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="a5338-379">Request</span><span class="sxs-lookup"><span data-stu-id="a5338-379">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-380">Response</span><span class="sxs-lookup"><span data-stu-id="a5338-380">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-381">セキュリティ ヘッダーの例 : EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="a5338-381">Security Header Examples: EncryptBeforeSign</span></span>  
  
 <span data-ttu-id="a5338-382">Request</span><span class="sxs-lookup"><span data-stu-id="a5338-382">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-383">Response</span><span class="sxs-lookup"><span data-stu-id="a5338-383">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="622-mutualcertificateduplex"></a><span data-ttu-id="a5338-384">6.2.2 MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="a5338-384">6.2.2 MutualCertificateDuplex</span></span>  
 <span data-ttu-id="a5338-385">この認証モードでは、クライアントは X.509 証明書を使用して認証を行います。X.509 証明書は、イニシエーター トークンとして SOAP 層に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-385">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="a5338-386">また、サービスは X.509 証明書を使用して認証されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-386">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="a5338-387">使用するバインディングは、次のプロパティ値が設定された非対称バインディングです。</span><span class="sxs-lookup"><span data-stu-id="a5338-387">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="a5338-388">イニシエーター トークン : インクルード モードが .../IncludeToken/AlwaysToRecipient に設定されたクライアントの X.509 証明書</span><span class="sxs-lookup"><span data-stu-id="a5338-388">Initiator Token: Client’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="a5338-389">受信者トークン : インクルード モードが .../IncludeToken/AlwaysToInitiator に設定されたサーバーの X509 証明書</span><span class="sxs-lookup"><span data-stu-id="a5338-389">Recipient Token: Server’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToInitiator</span></span>  
  
 <span data-ttu-id="a5338-390">トークンの保護 : False</span><span class="sxs-lookup"><span data-stu-id="a5338-390">Token Protection: False</span></span>  
  
 <span data-ttu-id="a5338-391">ヘッダーと本文全体の署名 : True</span><span class="sxs-lookup"><span data-stu-id="a5338-391">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="a5338-392">保護の順序 : SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="a5338-392">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="a5338-393">署名の暗号化 : True</span><span class="sxs-lookup"><span data-stu-id="a5338-393">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="a5338-394">ポリシー</span><span class="sxs-lookup"><span data-stu-id="a5338-394">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='MutualCertificateDuplex_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:AsymmetricBinding>  
        <wsp:Policy>  
          <sp:InitiatorToken>  
            <wsp:Policy>  
              <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:InitiatorToken>  
          <sp:RecipientToken>  
            <wsp:Policy>  
              <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToInitiator' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:RecipientToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:AsymmetricBinding>  
      <sp:Wss10>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
        </wsp:Policy>  
      </sp:Wss10>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="a5338-395">セキュリティ ヘッダーの例 : SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="a5338-395">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="a5338-396">要求と応答</span><span class="sxs-lookup"><span data-stu-id="a5338-396">Request and Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="a5338-397">セキュリティ ヘッダーの例 : EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="a5338-397">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="a5338-398">要求と応答</span><span class="sxs-lookup"><span data-stu-id="a5338-398">Request and Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="623-using-symmetricbinding-with-x509-service-authentication"></a><span data-ttu-id="a5338-399">6.2.3 X.509 サービス認証での SymmetricBinding の使用</span><span class="sxs-lookup"><span data-stu-id="a5338-399">6.2.3 Using SymmetricBinding with X.509 Service Authentication</span></span>  
 <span data-ttu-id="a5338-400">"WSS10" では、X509 トークンを使用するシナリオのサポートが制限されていました。</span><span class="sxs-lookup"><span data-stu-id="a5338-400">"WSS10" provided limited support for scenarios with X509 tokens.</span></span> <span data-ttu-id="a5338-401">たとえば、サービスの X509 トークンだけを使用して、メッセージの署名と暗号化を保護することはできませんでした。</span><span class="sxs-lookup"><span data-stu-id="a5338-401">For example, there was no way to provide signature and encryption protection for messages using only service X509 token.</span></span> <span data-ttu-id="a5338-402">"WSS11" では、EncryptedKey を共通鍵トークンとして使用する方法が導入されています。</span><span class="sxs-lookup"><span data-stu-id="a5338-402">"WSS11" introduced the usage of EncryptedKey as a symmetric token.</span></span> <span data-ttu-id="a5338-403">これにより、サービスの X.509 証明書の暗号化された一時キーを使用して、要求メッセージと応答メッセージの両方を保護できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a5338-403">Now a temporary key encrypted for the service's X.509 certificate could be used for both request and response messages protection.</span></span> <span data-ttu-id="a5338-404">セクション 6.4 で説明する認証モードでは、このパターンを使用します。</span><span class="sxs-lookup"><span data-stu-id="a5338-404">The authentication modes described in the section 6.4 below use this pattern.</span></span>  
  
 <span data-ttu-id="a5338-405">WS-SecurityPolicy には、サービスの X509 トークンを保護トークンとして使用して SymmetricBinding を使用するこのパターンが記載されています。</span><span class="sxs-lookup"><span data-stu-id="a5338-405">WS-SecurityPolicy describes this pattern using SymmetricBinding with Service X509 token as the protection token.</span></span>  
  
 <span data-ttu-id="a5338-406">AnonymousForCertificate、UsernameForCertificate、MutualCertificate WSS11、および IssuedTokenForCertificate の各認証モードはすべて、以下のプロパティ値が設定された sp:SymmetricBinding の同様のインスタンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="a5338-406">Authentication modes AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 and IssuedTokenForCertificate all use a similar instance of sp:SymmetricBinding with the following property values:</span></span>  
  
 <span data-ttu-id="a5338-407">保護トークン: インクルード モードが .../IncludeToken/Never に設定されたサーバーの X509 証明書</span><span class="sxs-lookup"><span data-stu-id="a5338-407">Protection Token: Server’s X509 Certificate, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="a5338-408">トークンの保護 : False</span><span class="sxs-lookup"><span data-stu-id="a5338-408">Token Protection: False</span></span>  
  
 <span data-ttu-id="a5338-409">ヘッダーと本文全体の署名 : True</span><span class="sxs-lookup"><span data-stu-id="a5338-409">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="a5338-410">保護の順序 : SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="a5338-410">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="a5338-411">署名の暗号化 : True</span><span class="sxs-lookup"><span data-stu-id="a5338-411">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="a5338-412">前述の各認証モードは、使用するサポート トークンだけが異なります。</span><span class="sxs-lookup"><span data-stu-id="a5338-412">The above authentication modes only differ by the supporting tokens they use.</span></span> <span data-ttu-id="a5338-413">AnonymousForCertificate はサポート トークンをまったく使用せず、MutualCertificate WSS 1.1 は保証サポート トークンとしてクライアントの X509 証明書を使用します。また、UserNameForCertificate は署名付きサポート トークンとしてユーザー名トークンを使用し、IssuedTokenForCertificate は保証サポート トークンとして発行済みトークンを使用します。</span><span class="sxs-lookup"><span data-stu-id="a5338-413">AnonymousForCertificate does not have any supporting tokens, MutualCertificate WSS 1.1 has the client’s X509 certificate as an endorsing supporting tokens, UserNameForCertificate has a UserName Token as a signed supporting token and IssuedTokenForCertificate has the issued token as an endorsing supporting token.</span></span>  
  
 <span data-ttu-id="a5338-414">ポリシー</span><span class="sxs-lookup"><span data-stu-id="a5338-414">Policy</span></span>  
  
 <span data-ttu-id="a5338-415">対称バインディング</span><span class="sxs-lookup"><span data-stu-id="a5338-415">Symmetric Binding</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SymmetricCert_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Never' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                  <sp:RequireThumbprintReference />
                  <sp:WssX509V3Token10 />
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />  
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <!-- Supporting Token Assertions appear here -->  
      ...  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
          <sp:RequireSignatureConfirmation />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
#### <a name="624-anonymousforcertificate"></a><span data-ttu-id="a5338-416">6.2.4 AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="a5338-416">6.2.4 AnonymousForCertificate</span></span>  
 <span data-ttu-id="a5338-417">この認証モードでは、クライアントは匿名になり、X.509 証明書を使用してサービスが認証されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-417">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="a5338-418">使用するバインディングは、6.4.2 で説明する対称バインディングのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="a5338-418">The binding used is an instance of symmetric binding as described in 6.4.2.</span></span>  
  
 <span data-ttu-id="a5338-419">ポリシー</span><span class="sxs-lookup"><span data-stu-id="a5338-419">Policy</span></span>  
  
 <span data-ttu-id="a5338-420">バインディングの詳細については、前述の 6.2.3 の「ポリシー」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5338-420">See "Policy" in 6.2.3 above for binding details</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="a5338-421">セキュリティ ヘッダーの例 : SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="a5338-421">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="a5338-422">Request</span><span class="sxs-lookup"><span data-stu-id="a5338-422">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-423">Response</span><span class="sxs-lookup"><span data-stu-id="a5338-423">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="a5338-424">セキュリティ ヘッダーの例 : EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="a5338-424">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="a5338-425">Request</span><span class="sxs-lookup"><span data-stu-id="a5338-425">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-426">Response</span><span class="sxs-lookup"><span data-stu-id="a5338-426">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="625-usernameforcertificate"></a><span data-ttu-id="a5338-427">6.2.5 UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="a5338-427">6.2.5 UserNameForCertificate</span></span>  
 <span data-ttu-id="a5338-428">この認証モードでは、クライアントはユーザー名トークンを使用してサーバーに対する認証を行います。ユーザー名トークンは、署名付きサポート トークンとして SOAP 層に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-428">With this authentication mode the client authenticates to the service using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="a5338-429">X.509 証明書を使用したクライアントに対するサービス認証。</span><span class="sxs-lookup"><span data-stu-id="a5338-429">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="a5338-430">使用するバインディングは、クライアントによって生成され、サービスの公開キーで暗号化されたキーを保護トークンとして使用する対称バインディングです。</span><span class="sxs-lookup"><span data-stu-id="a5338-430">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="a5338-431">ポリシー</span><span class="sxs-lookup"><span data-stu-id="a5338-431">Policy</span></span>  
  
 <span data-ttu-id="a5338-432">バインディングの詳細については、前述の 6.2.3 の「ポリシー」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5338-432">See "Policy" in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="a5338-433">署名付きサポート トークン</span><span class="sxs-lookup"><span data-stu-id="a5338-433">Signed Supporting Token</span></span>  
  
```xml  
<sp:SignedSupportingTokens>  
  <wsp:Policy>  
    <sp:UsernameToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:WssUsernameToken10 />
      </wsp:Policy>  
    </sp:UsernameToken>  
  </wsp:Policy>  
</sp:SignedSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="a5338-434">セキュリティ ヘッダーの例 : SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="a5338-434">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="a5338-435">Request</span><span class="sxs-lookup"><span data-stu-id="a5338-435">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-436">Response</span><span class="sxs-lookup"><span data-stu-id="a5338-436">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="a5338-437">セキュリティ ヘッダーの例 : EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="a5338-437">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="a5338-438">Request</span><span class="sxs-lookup"><span data-stu-id="a5338-438">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-439">Response</span><span class="sxs-lookup"><span data-stu-id="a5338-439">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="626-mutualcertificate-wss-11"></a><span data-ttu-id="a5338-440">6.2.6 MutualCertificate (WSS 1.1)</span><span class="sxs-lookup"><span data-stu-id="a5338-440">6.2.6 MutualCertificate (WSS 1.1)</span></span>  
 <span data-ttu-id="a5338-441">この認証モードでは、クライアントは X.509 証明書を使用して認証を行います。X.509 証明書は、保証サポート トークンとして SOAP 層に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-441">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="a5338-442">また、サービスは X.509 証明書を使用して認証されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-442">The service is also authenticated using an X.509 certificate.</span></span> <span data-ttu-id="a5338-443">使用するバインディングは、クライアントによって生成され、サービスの公開キーで暗号化されたキーを保護トークンとして使用する対称バインディングです。</span><span class="sxs-lookup"><span data-stu-id="a5338-443">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="a5338-444">ポリシー</span><span class="sxs-lookup"><span data-stu-id="a5338-444">Policy</span></span>  
  
 <span data-ttu-id="a5338-445">バインディングの詳細については、前述の 6.2.3 の「ポリシー」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5338-445">See Policy in 6.2.3 for binding details</span></span>  
  
 <span data-ttu-id="a5338-446">保証サポート トークン</span><span class="sxs-lookup"><span data-stu-id="a5338-446">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:X509Token sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:RequireThumbprintReference />
        <sp:WssX509V3Token10 />
      </wsp:Policy>  
    </sp:X509Token>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="a5338-447">セキュリティ ヘッダーの例 : SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="a5338-447">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="a5338-448">Request</span><span class="sxs-lookup"><span data-stu-id="a5338-448">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-449">Response</span><span class="sxs-lookup"><span data-stu-id="a5338-449">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="a5338-450">セキュリティ ヘッダーの例 : EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="a5338-450">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="a5338-451">Request</span><span class="sxs-lookup"><span data-stu-id="a5338-451">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-452">Response</span><span class="sxs-lookup"><span data-stu-id="a5338-452">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="627-issuedtokenforcertificate"></a><span data-ttu-id="a5338-453">6.2.7 IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="a5338-453">6.2.7 IssuedTokenForCertificate</span></span>  
 <span data-ttu-id="a5338-454">この認証モードでは、クライアントはサービスに対する認証を行わず、STS により発行されたトークンを示すことで、共有キーの有無を示します。</span><span class="sxs-lookup"><span data-stu-id="a5338-454">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by a STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="a5338-455">発行済みトークンは、保証サポート トークンとして SOAP 層に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-455">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="a5338-456">X.509 証明書を使用したクライアントに対するサービス認証。</span><span class="sxs-lookup"><span data-stu-id="a5338-456">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="a5338-457">使用するバインディングは、クライアントによって生成され、サービスの公開キーで暗号化されたキーを保護トークンとして使用する対称バインディングです。</span><span class="sxs-lookup"><span data-stu-id="a5338-457">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="a5338-458">ポリシー</span><span class="sxs-lookup"><span data-stu-id="a5338-458">Policy</span></span>  
  
 <span data-ttu-id="a5338-459">バインディングの詳細については、前述の 6.2.3 の「ポリシー」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5338-459">See Policy in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="a5338-460">保証サポート トークン</span><span class="sxs-lookup"><span data-stu-id="a5338-460">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <sp:RequestSecurityTokenTemplate>  
        <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
       </wst:KeyType>  
     </sp:RequestSecurityTokenTemplate>  
     <wsp:Policy>  
       <sp:RequireDerivedKeys />
       <sp:RequireInternalReference />
     </wsp:Policy>  
   </sp:IssuedToken>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="a5338-461">セキュリティ ヘッダーの例 : SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="a5338-461">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="a5338-462">Request</span><span class="sxs-lookup"><span data-stu-id="a5338-462">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-463">Response</span><span class="sxs-lookup"><span data-stu-id="a5338-463">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="a5338-464">セキュリティ ヘッダーの例 : EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="a5338-464">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="a5338-465">Request</span><span class="sxs-lookup"><span data-stu-id="a5338-465">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-466">Response</span><span class="sxs-lookup"><span data-stu-id="a5338-466">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
## <a name="63-kerberos"></a><span data-ttu-id="a5338-467">6.3 Kerberos</span><span class="sxs-lookup"><span data-stu-id="a5338-467">6.3 Kerberos</span></span>  
 <span data-ttu-id="a5338-468">この認証モードを使用すると、クライアントは Kerberos チケットを使用してサービスに対する認証を行います。</span><span class="sxs-lookup"><span data-stu-id="a5338-468">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="a5338-469">また、その同じチケットによってサーバーが認証されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-469">That same ticket also provides server authentication.</span></span> <span data-ttu-id="a5338-470">使用するバインディングは、以下のプロパティが設定された対称バインディングです。</span><span class="sxs-lookup"><span data-stu-id="a5338-470">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="a5338-471">保護トークン: インクルード モードが .../IncludeToken/Once に設定された Kerberos チケット</span><span class="sxs-lookup"><span data-stu-id="a5338-471">Protection Token: Kerberos Ticket, inclusion mode is set to .../IncludeToken/Once</span></span>  
<span data-ttu-id="a5338-472">トークンの保護 : False</span><span class="sxs-lookup"><span data-stu-id="a5338-472">Token Protection: False</span></span>  
  
 <span data-ttu-id="a5338-473">ヘッダーと本文全体の署名 : True</span><span class="sxs-lookup"><span data-stu-id="a5338-473">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="a5338-474">保護の順序 : SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="a5338-474">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="a5338-475">署名の暗号化 : True</span><span class="sxs-lookup"><span data-stu-id="a5338-475">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="a5338-476">ポリシー</span><span class="sxs-lookup"><span data-stu-id="a5338-476">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='Kerberos_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:KerberosToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Once' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                  <sp:WssGssKerberosV5ApReqToken11 />
                </wsp:Policy>  
              </sp:KerberosToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic128 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="a5338-477">セキュリティ ヘッダーの例 : SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="a5338-477">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="a5338-478">Request</span><span class="sxs-lookup"><span data-stu-id="a5338-478">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-479">Response</span><span class="sxs-lookup"><span data-stu-id="a5338-479">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="a5338-480">セキュリティ ヘッダーの例 : EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="a5338-480">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="a5338-481">Request</span><span class="sxs-lookup"><span data-stu-id="a5338-481">Request</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-482">Response</span><span class="sxs-lookup"><span data-stu-id="a5338-482">Response</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
#### <a name="64-issuedtoken"></a><span data-ttu-id="a5338-483">6.4 IssuedToken</span><span class="sxs-lookup"><span data-stu-id="a5338-483">6.4 IssuedToken</span></span>  
 <span data-ttu-id="a5338-484">この認証モードでは、クライアントはサービスに対する認証を行わず、STS により発行されたトークンを示すことで、共有キーの有無を示します。</span><span class="sxs-lookup"><span data-stu-id="a5338-484">With this authentication mode the client does not authenticate to the service, as such, rather the client presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="a5338-485">サービスはクライアントに対する認証を行いませんが、そのサービスだけがキーを復号化できるように、STS は発行されたトークンの一部として共有キーを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="a5338-485">The service is not authenticated to the client, as such, instead the STS encrypts the shared key as part of the issued token such that only the service can decrypt the key.</span></span> <span data-ttu-id="a5338-486">使用するバインディングは、以下のプロパティが設定された対称バインディングです。</span><span class="sxs-lookup"><span data-stu-id="a5338-486">The binding used is as symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="a5338-487">保護トークン: インクルード モードが .../IncludeToken/AlwaysToRecipient に設定された発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="a5338-487">Protection Token: Issued Token, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="a5338-488">トークンの保護 : False</span><span class="sxs-lookup"><span data-stu-id="a5338-488">Token Protection: False</span></span>  
  
 <span data-ttu-id="a5338-489">ヘッダーと本文全体の署名 : True</span><span class="sxs-lookup"><span data-stu-id="a5338-489">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="a5338-490">保護の順序 : SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="a5338-490">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="a5338-491">署名の暗号化 : True</span><span class="sxs-lookup"><span data-stu-id="a5338-491">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="a5338-492">ポリシー</span><span class="sxs-lookup"><span data-stu-id="a5338-492">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='CustomBinding_ISimple3_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <sp:RequestSecurityTokenTemplate>  
                  <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
                  </wst:KeyType>
                </sp:RequestSecurityTokenTemplate>  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                  <sp:RequireInternalReference />
                </wsp:Policy>  
              </sp:IssuedToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="a5338-493">セキュリティ ヘッダーの例 : SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="a5338-493">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="a5338-494">Request</span><span class="sxs-lookup"><span data-stu-id="a5338-494">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-495">Response</span><span class="sxs-lookup"><span data-stu-id="a5338-495">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="a5338-496">セキュリティ ヘッダーの例 : EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="a5338-496">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="a5338-497">Request</span><span class="sxs-lookup"><span data-stu-id="a5338-497">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-498">Response</span><span class="sxs-lookup"><span data-stu-id="a5338-498">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="65-using-sslnegotiated-for-service-authentication"></a><span data-ttu-id="a5338-499">6.5 SslNegotiated を使用したサービス認証</span><span class="sxs-lookup"><span data-stu-id="a5338-499">6.5 Using SslNegotiated for Service Authentication</span></span>  
 <span data-ttu-id="a5338-500">このセクションでは、WS-SecureConversation (WS-SC) ごとのセキュリティ コンテキスト トークンである保護トークンと共に、対称バインディングを使用する認証モードのグループについて説明します。WS-SecureConversation (WS-SC) のキー値は、WS-Trust (WS-T) RST/RSTR メッセージで TLS プロトコルを実行することによりネゴシエートされます。</span><span class="sxs-lookup"><span data-stu-id="a5338-500">This section describes a group of authentication modes that use a symmetric binding with the protection token being a Security Context Token per WS-SecureConversation (WS-SC) whose key value is negotiated by executing the TLS protocol over WS-Trust (WS-T) RST/RSTR messages.</span></span> <span data-ttu-id="a5338-501">WS-Trust を使用した TLS ハンドシェイク実装の詳細は、TLSNEGO に記述されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-501">Details of the TLS handshake implementation using WS-Trust are described in TLSNEGO.</span></span> <span data-ttu-id="a5338-502">ここで示すメッセージの例は、セキュリティ コンテキストに関連付けられた SCT が、ハンドシェイクによって既に確立されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="a5338-502">Here in the message examples we will assume that SCT with an associated security context is already established through a handshake.</span></span>  
  
 <span data-ttu-id="a5338-503">使用するバインディングは、以下のプロパティが設定された対称バインディングです。</span><span class="sxs-lookup"><span data-stu-id="a5338-503">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="a5338-504">保護トークン: インクルード モードが .../IncludeToken/Never に設定された SslContextToken</span><span class="sxs-lookup"><span data-stu-id="a5338-504">Protection Token: SslContextToken, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="a5338-505">トークンの保護 : False</span><span class="sxs-lookup"><span data-stu-id="a5338-505">Token Protection: False</span></span>  
  
 <span data-ttu-id="a5338-506">ヘッダーと本文全体の署名 : True</span><span class="sxs-lookup"><span data-stu-id="a5338-506">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="a5338-507">保護の順序 : SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="a5338-507">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="a5338-508">署名の暗号化 : True</span><span class="sxs-lookup"><span data-stu-id="a5338-508">Encrypt Signature: True</span></span>  
  
#### <a name="651-policy-for-sslnegotiated-service-authentication"></a><span data-ttu-id="a5338-509">6.5.1 SslNegotiated サービス認証のポリシー</span><span class="sxs-lookup"><span data-stu-id="a5338-509">6.5.1 Policy for SslNegotiated service authentication</span></span>  
 <span data-ttu-id="a5338-510">このセクションで説明するすべての認証モードのポリシーは、使用する署名付きサポート トークンまたは保証トークンだけが異なります。</span><span class="sxs-lookup"><span data-stu-id="a5338-510">Policy for all authentication modes in this section are similar and differ only by specific signed supporting or endorsing tokens used.</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SslNegotiated_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <mssp:SslContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' />  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                </wsp:Policy>  
              </mssp:SslContextToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <!-- Supporting token assertions go here -->  
      ..  
      <sp:Wss11>
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
#### <a name="652-anonymousforsslnegotiated"></a><span data-ttu-id="a5338-511">6.5.2 AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="a5338-511">6.5.2 AnonymousForSslNegotiated</span></span>  
 <span data-ttu-id="a5338-512">この認証モードでは、クライアントは匿名になり、X.509 証明書を使用してサービスが認証されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-512">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="a5338-513">使用するバインディングは、前述の 6.5.1 に示した対称バインディングのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="a5338-513">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="a5338-514">ポリシー</span><span class="sxs-lookup"><span data-stu-id="a5338-514">Policy</span></span>  
  
 <span data-ttu-id="a5338-515">バインディングの詳細については、前述の 6.5.1 の「ポリシー」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5338-515">See Policy in 6.5.1 above for binding details.</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="a5338-516">セキュリティ ヘッダーの例 : SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="a5338-516">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="a5338-517">Request</span><span class="sxs-lookup"><span data-stu-id="a5338-517">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-518">Response</span><span class="sxs-lookup"><span data-stu-id="a5338-518">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="a5338-519">セキュリティ ヘッダーの例 : EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="a5338-519">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="a5338-520">Request</span><span class="sxs-lookup"><span data-stu-id="a5338-520">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-521">Response</span><span class="sxs-lookup"><span data-stu-id="a5338-521">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="653-usernameforsslnegotiated"></a><span data-ttu-id="a5338-522">6.5.3 UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="a5338-522">6.5.3 UserNameForSslNegotiated</span></span>  
 <span data-ttu-id="a5338-523">この認証モードでは、クライアントはユーザー名トークンを使用して認証を行います。ユーザー名トークンは、署名付きサポート トークンとして SOAP 層に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-523">With this authentication mode the client is authenticates using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="a5338-524">サービスは X.509 証明書を使用して認証されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-524">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="a5338-525">使用するバインディングは、6.5.1 で説明した対称バインディングのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="a5338-525">The binding used is an instance of symmetric binding as described in 6.5.1.</span></span>  
  
 <span data-ttu-id="a5338-526">ポリシー</span><span class="sxs-lookup"><span data-stu-id="a5338-526">Policy</span></span>  
  
 <span data-ttu-id="a5338-527">バインディングの詳細については、前述の 6.5.1 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5338-527">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="a5338-528">署名付きサポート トークン</span><span class="sxs-lookup"><span data-stu-id="a5338-528">Signed Supporting Token</span></span>  
  
```xml  
<sp:SignedSupportingTokens>  
  <wsp:Policy>  
    <sp:UsernameToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:WssUsernameToken10 />
      </wsp:Policy>  
    </sp:UsernameToken>  
  </wsp:Policy>  
</sp:SignedSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="a5338-529">セキュリティ ヘッダーの例 : SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="a5338-529">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="a5338-530">Request</span><span class="sxs-lookup"><span data-stu-id="a5338-530">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-531">Response</span><span class="sxs-lookup"><span data-stu-id="a5338-531">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="a5338-532">セキュリティ ヘッダーの例 : EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="a5338-532">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="a5338-533">Request</span><span class="sxs-lookup"><span data-stu-id="a5338-533">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-534">Response</span><span class="sxs-lookup"><span data-stu-id="a5338-534">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="654-issuedtokenforsslnegotiated"></a><span data-ttu-id="a5338-535">6.5.4 IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="a5338-535">6.5.4 IssuedTokenForSslNegotiated</span></span>  
 <span data-ttu-id="a5338-536">この認証モードでは、クライアントはサービスに対する認証を行わず、STS により発行されたトークンを示すことで、共有キーの有無を示します。</span><span class="sxs-lookup"><span data-stu-id="a5338-536">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="a5338-537">発行済みトークンは、保証サポート トークンとして SOAP 層に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-537">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="a5338-538">サービスは X.509 証明書を使用して認証されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-538">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="a5338-539">使用するバインディングは、前述の 6.5.1 に示した対称バインディングのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="a5338-539">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="a5338-540">ポリシー</span><span class="sxs-lookup"><span data-stu-id="a5338-540">Policy</span></span>  
  
 <span data-ttu-id="a5338-541">バインディングの詳細については、前述の 6.5.1 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5338-541">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="a5338-542">保証サポート トークン</span><span class="sxs-lookup"><span data-stu-id="a5338-542">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <sp:RequestSecurityTokenTemplate>  
        <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
        </wst:KeyType>
      </sp:RequestSecurityTokenTemplate>  
      <wsp:Policy>  
        <sp:RequireDerivedKeys />
        <sp:RequireInternalReference />
      </wsp:Policy>  
    </sp:IssuedToken>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="a5338-543">セキュリティ ヘッダーの例 : SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="a5338-543">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="a5338-544">Request</span><span class="sxs-lookup"><span data-stu-id="a5338-544">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-545">Response</span><span class="sxs-lookup"><span data-stu-id="a5338-545">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="a5338-546">セキュリティ ヘッダーの例 : EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="a5338-546">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="a5338-547">Request</span><span class="sxs-lookup"><span data-stu-id="a5338-547">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-548">Response</span><span class="sxs-lookup"><span data-stu-id="a5338-548">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="655-mutualsslnegotiated"></a><span data-ttu-id="a5338-549">6.5.5 MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="a5338-549">6.5.5 MutualSslNegotiated</span></span>  
 <span data-ttu-id="a5338-550">この認証モードでは、クライアントとサービスは X.509 証明書を使用して認証を行います。</span><span class="sxs-lookup"><span data-stu-id="a5338-550">With this authentication mode the client and the service authenticate using X.509 certificates.</span></span> <span data-ttu-id="a5338-551">使用するバインディングは、前述の 6.5.1 に示した対称バインディングのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="a5338-551">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="a5338-552">ポリシー</span><span class="sxs-lookup"><span data-stu-id="a5338-552">Policy</span></span>  
  
 <span data-ttu-id="a5338-553">バインディングの詳細については、前述の 6.5.1 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5338-553">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="a5338-554">保証サポート トークン</span><span class="sxs-lookup"><span data-stu-id="a5338-554">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:X509Token sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:RequireThumbprintReference />
        <sp:WssX509V3Token10 />
      </wsp:Policy>  
    </sp:X509Token>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="a5338-555">セキュリティ ヘッダーの例 : SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="a5338-555">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="a5338-556">Request</span><span class="sxs-lookup"><span data-stu-id="a5338-556">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-557">Response</span><span class="sxs-lookup"><span data-stu-id="a5338-557">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="a5338-558">セキュリティ ヘッダーの例 : EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="a5338-558">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="a5338-559">Request</span><span class="sxs-lookup"><span data-stu-id="a5338-559">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-560">Response</span><span class="sxs-lookup"><span data-stu-id="a5338-560">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="66-sspinegotiated"></a><span data-ttu-id="a5338-561">6.6 SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="a5338-561">6.6 SspiNegotiated</span></span>  
 <span data-ttu-id="a5338-562">この認証モードを使用すると、クライアントとサーバーの認証を実行するために、ネゴシエーション プロトコルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-562">With this authentication mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="a5338-563">Kerberos を使用できる場合は Kerberos が使用され、それ以外の場合は NTLM が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-563">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="a5338-564">使用するバインディングは、以下のプロパティが設定された対称バインディングです。</span><span class="sxs-lookup"><span data-stu-id="a5338-564">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="a5338-565">保護トークン: インクルード モードが .../IncludeToken/AlwaysToRecipient に設定された SpnegoContextToken</span><span class="sxs-lookup"><span data-stu-id="a5338-565">Protection Token: SpnegoContextToken, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="a5338-566">トークンの保護 : False</span><span class="sxs-lookup"><span data-stu-id="a5338-566">Token Protection: False</span></span>  
  
 <span data-ttu-id="a5338-567">ヘッダーと本文全体の署名 : True</span><span class="sxs-lookup"><span data-stu-id="a5338-567">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="a5338-568">保護の順序 : SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="a5338-568">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="a5338-569">署名の暗号化 : True</span><span class="sxs-lookup"><span data-stu-id="a5338-569">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="a5338-570">ポリシー</span><span class="sxs-lookup"><span data-stu-id="a5338-570">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='CustomBinding_ISimple13_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:SpnegoContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                </wsp:Policy>  
              </sp:SpnegoContextToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="a5338-571">セキュリティ ヘッダーの例 : SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="a5338-571">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="a5338-572">Request</span><span class="sxs-lookup"><span data-stu-id="a5338-572">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-573">Response</span><span class="sxs-lookup"><span data-stu-id="a5338-573">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="a5338-574">セキュリティ ヘッダーの例 : EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="a5338-574">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="a5338-575">Request</span><span class="sxs-lookup"><span data-stu-id="a5338-575">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-576">Response</span><span class="sxs-lookup"><span data-stu-id="a5338-576">Response</span></span>  
  
```xml  
<wsse:Security>  
<wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="67-secureconversation"></a><span data-ttu-id="a5338-577">6.7 SecureConversation</span><span class="sxs-lookup"><span data-stu-id="a5338-577">6.7 SecureConversation</span></span>  
 <span data-ttu-id="a5338-578">使用するバインディングは、WS-SecureConversation (WS-SC) ごとの SCT を保護トークンとして使用する対称バインディングです。</span><span class="sxs-lookup"><span data-stu-id="a5338-578">The binding used is a symmetric binding with the protection token being a SCT per WS-SecureConversation (WS-SC).</span></span> <span data-ttu-id="a5338-579">入れ子になったバインディング (このバインディング自体も、ネゴシエーション プロトコルを使用する対称バインディングです) に従い、SCT は WS-Trust (WS-Trust) または WS-SecureConversation (WS-SC) を使用してネゴシエートされます。</span><span class="sxs-lookup"><span data-stu-id="a5338-579">The SCT is negotiated using WS-Trust (WS-Trust) or WS-SecureConversation (WS-SC) according to a nested binding, which is itself a symmetric binding that uses a negotiation protocol.</span></span> <span data-ttu-id="a5338-580">ネゴシエーション プロトコルは、可能であれば Kerberos を使用してクライアントとサーバーの認証を行います。</span><span class="sxs-lookup"><span data-stu-id="a5338-580">The negotiation protocol will use Kerberos to perform client and server authentication if possible.</span></span> <span data-ttu-id="a5338-581">Kerberos を使用できない場合は、NTLM が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a5338-581">If Kerberos cannot be used, it will fall back to NTLM.</span></span>  
  
 <span data-ttu-id="a5338-582">ポリシー</span><span class="sxs-lookup"><span data-stu-id="a5338-582">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SecureConversation_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:SecureConversationToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                  <sp:BootstrapPolicy>  
                    <wsp:Policy>  
                      <sp:SignedParts>  
                        <sp:Body />
                        <sp:Header Name='To' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='From' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='FaultTo' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='ReplyTo' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='MessageID' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='RelatesTo' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='Action' Namespace='http://www.w3.org/2005/08/addressing' />
                      </sp:SignedParts>  
                      <sp:EncryptedParts>  
                        <sp:Body />
                      </sp:EncryptedParts>  
                      <sp:SymmetricBinding>  
                        <wsp:Policy>  
                          <sp:ProtectionToken>  
                            <wsp:Policy>  
                              <sp:SpnegoContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                                <wsp:Policy>  
                                  <sp:RequireDerivedKeys />
                                </wsp:Policy>  
                              </sp:SpnegoContextToken>  
                            </wsp:Policy>  
                          </sp:ProtectionToken>  
                          <sp:AlgorithmSuite>  
                            <wsp:Policy>  
                              <sp:Basic256 />
                            </wsp:Policy>  
                          </sp:AlgorithmSuite>  
                          <sp:Layout>  
                            <wsp:Policy>  
                              <sp:Strict />
                            </wsp:Policy>  
                          </sp:Layout>  
                          <sp:IncludeTimestamp />
                          <sp:EncryptSignature />
                          <sp:OnlySignEntireHeadersAndBody />
                        </wsp:Policy>  
                      </sp:SymmetricBinding>  
                      <sp:Wss11>  
                        <wsp:Policy>  
                          <sp:MustSupportRefKeyIdentifier />
                          <sp:MustSupportRefIssuerSerial />
                          <sp:MustSupportRefThumbprint />
                          <sp:MustSupportRefEncryptedKey />
                        </wsp:Policy>  
                      </sp:Wss11>  
                      <sp:Trust10>  
                        <wsp:Policy>  
                          <sp:MustSupportIssuedTokens />
                          <sp:RequireClientEntropy />
                          <sp:RequireServerEntropy />
                        </wsp:Policy>  
                      </sp:Trust10>  
                    </wsp:Policy>  
                  </sp:BootstrapPolicy>  
                </wsp:Policy>  
              </sp:SecureConversationToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="a5338-583">セキュリティ ヘッダーの例 : SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="a5338-583">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="a5338-584">Request</span><span class="sxs-lookup"><span data-stu-id="a5338-584">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-585">Response</span><span class="sxs-lookup"><span data-stu-id="a5338-585">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="a5338-586">セキュリティ ヘッダーの例 : EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="a5338-586">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="a5338-587">Request</span><span class="sxs-lookup"><span data-stu-id="a5338-587">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="a5338-588">Response</span><span class="sxs-lookup"><span data-stu-id="a5338-588">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```
