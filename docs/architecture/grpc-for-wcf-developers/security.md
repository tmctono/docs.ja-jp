---
title: gRPC アプリケーションのセキュリティ - WCF 開発者向け gRPC
description: gRPC におけるコールとチャネル認証と承認の概要。
ms.date: 09/02/2019
ms.openlocfilehash: 70cbf441bbc1b299b997f7d1f02bcd2bf7fde60c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147816"
---
# <a name="security-in-grpc-applications"></a><span data-ttu-id="28107-103">gRPC アプリケーションのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="28107-103">Security in gRPC applications</span></span>

<span data-ttu-id="28107-104">実際のシナリオでは、アプリケーションとサービスのセキュリティ保護が不可欠です。</span><span class="sxs-lookup"><span data-stu-id="28107-104">In any real-world scenario, securing applications and services is essential.</span></span> <span data-ttu-id="28107-105">セキュリティは、次の 3 つの主要な領域をカバーします。</span><span class="sxs-lookup"><span data-stu-id="28107-105">Security covers three key areas:</span></span>

* <span data-ttu-id="28107-106">ネットワーク トラフィックを暗号化して、悪意のあるハッカーによる傍受を防ぎます。</span><span class="sxs-lookup"><span data-stu-id="28107-106">Encrypting network traffic to prevent malicious hackers from intercepting it.</span></span>
* <span data-ttu-id="28107-107">クライアントとサーバーを認証して、ID と信頼を確立する。</span><span class="sxs-lookup"><span data-stu-id="28107-107">Authenticating clients and servers to establish identity and trust.</span></span>
* <span data-ttu-id="28107-108">システムへのアクセスを制御し、ID に基づいてアクセス許可を適用するクライアントを承認します。</span><span class="sxs-lookup"><span data-stu-id="28107-108">Authorizing clients to control access to systems and apply permissions based on identity.</span></span>

> [!NOTE]
> <span data-ttu-id="28107-109">*認証*は、クライアントまたはサーバーの ID の確立に関係します。</span><span class="sxs-lookup"><span data-stu-id="28107-109">*Authentication* is concerned with establishing the identity of a client or server.</span></span> <span data-ttu-id="28107-110">*承認*は、クライアントがリソースにアクセスする権限を持っているかどうか、またはコマンドを発行する権限を持っているかどうかを判断することに関係します。</span><span class="sxs-lookup"><span data-stu-id="28107-110">*Authorization* is concerned with determining whether a client has permission to access a resource or issue a command.</span></span>

<span data-ttu-id="28107-111">この章では、ASP.NETコアの gRPC での認証と承認の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="28107-111">This chapter will cover the facilities for authentication and authorization in gRPC for ASP.NET Core.</span></span> <span data-ttu-id="28107-112">また、TLS 暗号化接続を通じたネットワーク セキュリティについても説明します。</span><span class="sxs-lookup"><span data-stu-id="28107-112">It will also discuss network security through TLS encrypted connections.</span></span>

## <a name="wcf-authentication-and-authorization"></a><span data-ttu-id="28107-113">WCF 認証と承認</span><span class="sxs-lookup"><span data-stu-id="28107-113">WCF authentication and authorization</span></span>

<span data-ttu-id="28107-114">Windows 通信ファウンデーション (WCF) では、使用するトランスポートとバインドに応じて、認証と承認がさまざまな方法で処理されました。</span><span class="sxs-lookup"><span data-stu-id="28107-114">In Windows Communication Foundation (WCF), authentication and authorization were handled in different ways, depending on the transports and bindings being used.</span></span> <span data-ttu-id="28107-115">WCF は、さまざまな\*WS-セキュリティ標準をサポートしました。</span><span class="sxs-lookup"><span data-stu-id="28107-115">WCF supported various WS-\* security standards.</span></span> <span data-ttu-id="28107-116">また、Windows システム間の IIS サービスまたは NetTCP サービスで実行されている HTTP サービスの Windows 認証もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="28107-116">It also supported Windows authentication for HTTP services running in IIS or NetTCP services between Windows systems.</span></span>

## <a name="grpc-authentication-and-authorization"></a><span data-ttu-id="28107-117">gRPC 認証と承認</span><span class="sxs-lookup"><span data-stu-id="28107-117">gRPC authentication and authorization</span></span>

<span data-ttu-id="28107-118">gRPC 認証と承認は、次の 2 つのレベルで機能します。</span><span class="sxs-lookup"><span data-stu-id="28107-118">gRPC authentication and authorization works on two levels:</span></span>

* <span data-ttu-id="28107-119">呼び出しレベルの認証/承認は、通常、呼び出しが行われたときにメタデータに適用されるトークンを介して処理されます。</span><span class="sxs-lookup"><span data-stu-id="28107-119">Call-level authentication/authorization is usually handled through tokens that are applied in metadata when the call is made.</span></span>
* <span data-ttu-id="28107-120">チャネル レベルの認証では、接続レベルで適用されるクライアント証明書が使用されます。</span><span class="sxs-lookup"><span data-stu-id="28107-120">Channel-level authentication uses a client certificate that's applied at the connection level.</span></span> <span data-ttu-id="28107-121">また、チャネルのすべての呼び出しに自動的に適用される呼び出しレベルの認証/承認資格情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="28107-121">It can also include call-level authentication/authorization credentials to be applied to every call on the channel automatically.</span></span>

<span data-ttu-id="28107-122">これらのメカニズムの一方または両方を使用して、サービスのセキュリティを確保できます。</span><span class="sxs-lookup"><span data-stu-id="28107-122">You can use either or both of these mechanisms to help secure your service.</span></span>

<span data-ttu-id="28107-123">gRPC の ASP.NET コア実装では、標準の ASP.NET コア メカニズムのほとんどを通じて認証と承認をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="28107-123">The ASP.NET Core implementation of gRPC supports authentication and authorization through most of the standard ASP.NET Core mechanisms:</span></span>

- <span data-ttu-id="28107-124">通話認証</span><span class="sxs-lookup"><span data-stu-id="28107-124">Call authentication</span></span>
  - <span data-ttu-id="28107-125">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="28107-125">Azure Active Directory</span></span>
  - <span data-ttu-id="28107-126">アイデンティティサーバー</span><span class="sxs-lookup"><span data-stu-id="28107-126">IdentityServer</span></span>
  - <span data-ttu-id="28107-127">JWT ベアラー トークン</span><span class="sxs-lookup"><span data-stu-id="28107-127">JWT Bearer Token</span></span>
  - <span data-ttu-id="28107-128">OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="28107-128">OAuth 2.0</span></span>
  - <span data-ttu-id="28107-129">OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="28107-129">OpenID Connect</span></span>
  - <span data-ttu-id="28107-130">WS-Federation</span><span class="sxs-lookup"><span data-stu-id="28107-130">WS-Federation</span></span>
- <span data-ttu-id="28107-131">チャネル認証</span><span class="sxs-lookup"><span data-stu-id="28107-131">Channel authentication</span></span>
  - <span data-ttu-id="28107-132">クライアント証明書</span><span class="sxs-lookup"><span data-stu-id="28107-132">Client certificate</span></span>

<span data-ttu-id="28107-133">呼び出し認証方法はすべて*トークン*に基づいています。</span><span class="sxs-lookup"><span data-stu-id="28107-133">The call authentication methods are all based on *tokens*.</span></span> <span data-ttu-id="28107-134">唯一の違いは、トークンの生成方法と、ASP.NET Core サービスでトークンを検証するために使用されるライブラリです。</span><span class="sxs-lookup"><span data-stu-id="28107-134">The only real difference is how the tokens are generated and the libraries that are used to validate the tokens in the ASP.NET Core service.</span></span>

<span data-ttu-id="28107-135">詳細については、[認証と承認](/aspnet/core/grpc/authn-and-authz)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28107-135">For more information, see the [Authentication and authorization](/aspnet/core/grpc/authn-and-authz) article.</span></span>

> [!NOTE]
> <span data-ttu-id="28107-136">tls 暗号化 HTTP/2 接続で gRPC を使用している場合、チャネルレベル認証を使用しない場合でも、クライアントとサーバー間のすべてのトラフィックが暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="28107-136">When you're using gRPC over a TLS-encrypted HTTP/2 connection, all traffic between clients and servers is encrypted, even if you don't use channel-level authentication.</span></span>

<span data-ttu-id="28107-137">この章では、gRPC サービスにコール資格情報とチャネル資格情報を適用する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="28107-137">This chapter will show how to apply call credentials and channel credentials to a gRPC service.</span></span> <span data-ttu-id="28107-138">また、.NET Core gRPC クライアントからの資格情報を使用してサービスを認証する方法も示します。</span><span class="sxs-lookup"><span data-stu-id="28107-138">It will also show how to use credentials from a .NET Core gRPC client to authenticate with the service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="28107-139">[前次](client-libraries.md)
>[Next](call-credentials.md)</span><span class="sxs-lookup"><span data-stu-id="28107-139">[Previous](client-libraries.md)
[Next](call-credentials.md)</span></span>
