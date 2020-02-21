---
title: GRPC アプリケーションのセキュリティ-WCF 開発者向け gRPC
description: GRPC での呼び出しとチャネルの認証および承認の概要。
ms.date: 09/02/2019
ms.openlocfilehash: d5804ad5de4a834eb81b90fa1ea7a61969a0b42f
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503408"
---
# <a name="security-in-grpc-applications"></a><span data-ttu-id="be3a3-103">gRPC アプリケーションのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="be3a3-103">Security in gRPC applications</span></span>

<span data-ttu-id="be3a3-104">実際のシナリオでは、アプリケーションとサービスのセキュリティ保護が不可欠です。</span><span class="sxs-lookup"><span data-stu-id="be3a3-104">In any real-world scenario, securing applications and services is essential.</span></span> <span data-ttu-id="be3a3-105">セキュリティには3つの主要領域があります。</span><span class="sxs-lookup"><span data-stu-id="be3a3-105">Security covers three key areas:</span></span> 

* <span data-ttu-id="be3a3-106">ネットワークトラフィックを暗号化して、悪意のあるハッカーによって傍受されるのを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="be3a3-106">Encrypting network traffic to prevent malicious hackers from intercepting it.</span></span>
* <span data-ttu-id="be3a3-107">クライアントとサーバーを認証して、id と信頼を確立します。</span><span class="sxs-lookup"><span data-stu-id="be3a3-107">Authenticating clients and servers to establish identity and trust.</span></span>
* <span data-ttu-id="be3a3-108">クライアントがシステムへのアクセスを制御し、id に基づいてアクセス許可を適用することを承認します。</span><span class="sxs-lookup"><span data-stu-id="be3a3-108">Authorizing clients to control access to systems and apply permissions based on identity.</span></span>

> [!NOTE]
> <span data-ttu-id="be3a3-109">*認証*は、クライアントまたはサーバーの id を確立することに関係します。</span><span class="sxs-lookup"><span data-stu-id="be3a3-109">*Authentication* is concerned with establishing the identity of a client or server.</span></span> <span data-ttu-id="be3a3-110">*承認*は、クライアントがリソースにアクセスするためのアクセス許可を持っているか、コマンドを発行するかを判断することに関係します。</span><span class="sxs-lookup"><span data-stu-id="be3a3-110">*Authorization* is concerned with determining whether a client has permission to access a resource or issue a command.</span></span>

<span data-ttu-id="be3a3-111">この章では、ASP.NET Core 用の gRPC での認証と承認の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="be3a3-111">This chapter will cover the facilities for authentication and authorization in gRPC for ASP.NET Core.</span></span> <span data-ttu-id="be3a3-112">また、TLS で暗号化された接続を使用したネットワークセキュリティについても説明します。</span><span class="sxs-lookup"><span data-stu-id="be3a3-112">It will also discuss network security through TLS encrypted connections.</span></span>

## <a name="wcf-authentication-and-authorization"></a><span data-ttu-id="be3a3-113">WCF の認証と承認</span><span class="sxs-lookup"><span data-stu-id="be3a3-113">WCF authentication and authorization</span></span>

<span data-ttu-id="be3a3-114">Windows Communication Foundation (WCF) では、認証と承認は、使用されているトランスポートとバインドに応じて、さまざまな方法で処理されていました。</span><span class="sxs-lookup"><span data-stu-id="be3a3-114">In Windows Communication Foundation (WCF), authentication and authorization were handled in different ways, depending on the transports and bindings being used.</span></span> <span data-ttu-id="be3a3-115">WCF では、さまざまな WS\* セキュリティ標準がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="be3a3-115">WCF supported various WS-\* security standards.</span></span> <span data-ttu-id="be3a3-116">また、windows システム間で IIS または NetTCP サービスで実行されている HTTP サービスの Windows 認証もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="be3a3-116">It also supported Windows authentication for HTTP services running in IIS or NetTCP services between Windows systems.</span></span>

## <a name="grpc-authentication-and-authorization"></a><span data-ttu-id="be3a3-117">gRPC の認証と承認</span><span class="sxs-lookup"><span data-stu-id="be3a3-117">gRPC authentication and authorization</span></span>

<span data-ttu-id="be3a3-118">gRPC の認証と承認は、次の2つのレベルで機能します。</span><span class="sxs-lookup"><span data-stu-id="be3a3-118">gRPC authentication and authorization works on two levels:</span></span>

* <span data-ttu-id="be3a3-119">呼び出しレベルの認証/承認は、通常、呼び出しが行われたときにメタデータに適用されるトークンを使用して処理されます。</span><span class="sxs-lookup"><span data-stu-id="be3a3-119">Call-level authentication/authorization is usually handled through tokens that are applied in metadata when the call is made.</span></span> 
* <span data-ttu-id="be3a3-120">チャネルレベルの認証では、接続レベルで適用されるクライアント証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="be3a3-120">Channel-level authentication uses a client certificate that's applied at the connection level.</span></span> <span data-ttu-id="be3a3-121">また、チャネルのすべての呼び出しに自動的に適用される、呼び出しレベルの認証/承認の資格情報を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="be3a3-121">It can also include call-level authentication/authorization credentials to be applied to every call on the channel automatically.</span></span> 

<span data-ttu-id="be3a3-122">これらのメカニズムのいずれかまたは両方を使用して、サービスをセキュリティで保護することができます。</span><span class="sxs-lookup"><span data-stu-id="be3a3-122">You can use either or both of these mechanisms to help secure your service.</span></span>

<span data-ttu-id="be3a3-123">GRPC の ASP.NET Core 実装では、ほとんどの標準的な ASP.NET Core メカニズムによる認証と承認をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="be3a3-123">The ASP.NET Core implementation of gRPC supports authentication and authorization through most of the standard ASP.NET Core mechanisms:</span></span>

- <span data-ttu-id="be3a3-124">認証の呼び出し</span><span class="sxs-lookup"><span data-stu-id="be3a3-124">Call authentication</span></span>
  - <span data-ttu-id="be3a3-125">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="be3a3-125">Azure Active Directory</span></span>
  - <span data-ttu-id="be3a3-126">IdentityServer</span><span class="sxs-lookup"><span data-stu-id="be3a3-126">IdentityServer</span></span>
  - <span data-ttu-id="be3a3-127">JWT ベアラートークン</span><span class="sxs-lookup"><span data-stu-id="be3a3-127">JWT Bearer Token</span></span>
  - <span data-ttu-id="be3a3-128">OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="be3a3-128">OAuth 2.0</span></span>
  - <span data-ttu-id="be3a3-129">OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="be3a3-129">OpenID Connect</span></span>
  - <span data-ttu-id="be3a3-130">WS-Federation</span><span class="sxs-lookup"><span data-stu-id="be3a3-130">WS-Federation</span></span>
- <span data-ttu-id="be3a3-131">チャネル認証</span><span class="sxs-lookup"><span data-stu-id="be3a3-131">Channel authentication</span></span>
  - <span data-ttu-id="be3a3-132">クライアント認証</span><span class="sxs-lookup"><span data-stu-id="be3a3-132">Client certificate</span></span>

<span data-ttu-id="be3a3-133">呼び出しの認証方法はすべて、*トークン*に基づいています。</span><span class="sxs-lookup"><span data-stu-id="be3a3-133">The call authentication methods are all based on *tokens*.</span></span> <span data-ttu-id="be3a3-134">実際の違いは、トークンが生成される方法と、ASP.NET Core サービスでトークンを検証するために使用されるライブラリです。</span><span class="sxs-lookup"><span data-stu-id="be3a3-134">The only real difference is how the tokens are generated and the libraries that are used to validate the tokens in the ASP.NET Core service.</span></span>

<span data-ttu-id="be3a3-135">詳細については、[認証と承認](/aspnet/core/grpc/authn-and-authz)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be3a3-135">For more information, see the [Authentication and authorization](/aspnet/core/grpc/authn-and-authz) article.</span></span>

> [!NOTE]
> <span data-ttu-id="be3a3-136">TLS で暗号化された HTTP/2 接続で gRPC を使用している場合は、チャネルレベルの認証を使用しない場合でも、クライアントとサーバー間のすべてのトラフィックが暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="be3a3-136">When you're using gRPC over a TLS-encrypted HTTP/2 connection, all traffic between clients and servers is encrypted, even if you don't use channel-level authentication.</span></span>

<span data-ttu-id="be3a3-137">この章では、gRPC サービスに呼び出し資格情報とチャネル資格情報を適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="be3a3-137">This chapter will show how to apply call credentials and channel credentials to a gRPC service.</span></span> <span data-ttu-id="be3a3-138">また、.NET Core gRPC クライアントの資格情報を使用してサービスで認証する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="be3a3-138">It will also show how to use credentials from a .NET Core gRPC client to authenticate with the service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="be3a3-139">[前へ](client-libraries.md)
>[次へ](call-credentials.md)</span><span class="sxs-lookup"><span data-stu-id="be3a3-139">[Previous](client-libraries.md)
[Next](call-credentials.md)</span></span>
