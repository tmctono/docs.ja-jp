---
title: GRPC アプリケーションのセキュリティ-WCF 開発者向け gRPC
description: GRPC での呼び出しとチャネルの認証および承認の概要。
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: d0b7ff5bef755c5eeb9b3c419dcda1cb75ac4031
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841373"
---
# <a name="security-in-grpc-applications"></a><span data-ttu-id="d43b5-103">gRPC アプリケーションのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="d43b5-103">Security in gRPC applications</span></span>

<span data-ttu-id="d43b5-104">実際のシナリオでは、アプリケーションとサービスのセキュリティ保護が不可欠です。</span><span class="sxs-lookup"><span data-stu-id="d43b5-104">In any real-world scenario, securing applications and services is essential.</span></span> <span data-ttu-id="d43b5-105">セキュリティには3つの重要な領域があります。ネットワークトラフィックを暗号化して、不正なアクターによる傍受を防ぐことができます。クライアントとサーバーを認証して id と信頼を確立するまた、クライアントがシステムへのアクセスを制御し、id に基づいてアクセス許可を適用することを承認します。</span><span class="sxs-lookup"><span data-stu-id="d43b5-105">Security covers three key areas: encrypting network traffic to prevent it from being intercepted by bad actors; authenticating clients and servers to establish identity and trust; and authorizing clients to control access to systems and apply permissions based on identity.</span></span>

> [!NOTE]
> <span data-ttu-id="d43b5-106">**認証**は、クライアントまたはサーバーの id を確立することに関係します。</span><span class="sxs-lookup"><span data-stu-id="d43b5-106">**Authentication** is concerned with establishing the identity of a client or server.</span></span> <span data-ttu-id="d43b5-107">**承認**は、クライアントがリソースにアクセスするためのアクセス許可を持っているか、コマンドを発行するかを判断することに関係します。</span><span class="sxs-lookup"><span data-stu-id="d43b5-107">**Authorization** is concerned with determining whether a client has permission to access a resource or issue a command.</span></span>

<span data-ttu-id="d43b5-108">この章では、ASP.NET Core 用の gRPC での認証と承認の機能について説明し、TLS で暗号化された接続を使用したネットワークセキュリティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d43b5-108">This chapter will cover the facilities for authentication and authorization in gRPC for ASP.NET Core, and discuss network security using TLS encrypted connections.</span></span>

## <a name="wcf-authentication-and-authorization"></a><span data-ttu-id="d43b5-109">WCF の認証と承認</span><span class="sxs-lookup"><span data-stu-id="d43b5-109">WCF authentication and authorization</span></span>

<span data-ttu-id="d43b5-110">WCF では、認証と承認は、使用されているトランスポートとバインドに応じて、さまざまな方法で処理されていました。</span><span class="sxs-lookup"><span data-stu-id="d43b5-110">In WCF, authentication and authorization were handled in different ways depending on the transports and bindings being used.</span></span> <span data-ttu-id="d43b5-111">WCF では、さまざまな WS\* セキュリティ標準がサポートされています。また、Windows システム間で IIS または NetTCP サービスで実行されている HTTP サービス用の Windows 認証もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d43b5-111">WCF supported various WS-\* security standards, as well as Windows authentication for HTTP services running in IIS or NetTCP services between Windows systems.</span></span>

## <a name="grpc-authentication-and-authorization"></a><span data-ttu-id="d43b5-112">gRPC の認証と承認</span><span class="sxs-lookup"><span data-stu-id="d43b5-112">gRPC authentication and authorization</span></span>

<span data-ttu-id="d43b5-113">gRPC の認証と承認は、2つのレベルで機能します。</span><span class="sxs-lookup"><span data-stu-id="d43b5-113">gRPC authentication and authorization works on two levels.</span></span> <span data-ttu-id="d43b5-114">呼び出しレベルの認証/承認は、通常、呼び出しが行われたときにメタデータに適用されるトークンを使用して処理されます。</span><span class="sxs-lookup"><span data-stu-id="d43b5-114">Call-level authentication/authorization is usually handled using tokens that are applied in metadata when the call is made.</span></span> <span data-ttu-id="d43b5-115">チャネルレベルの認証では、接続レベルで適用されるクライアント証明書を使用します。また、チャネルのすべての呼び出しに自動的に適用される呼び出しレベルの認証/承認資格情報を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="d43b5-115">Channel-level authentication uses a client certificate that is applied at the connection level, and can also include call-level authentication/authorization credentials to be applied to every call on the channel automatically.</span></span> <span data-ttu-id="d43b5-116">これらのメカニズムのいずれかまたは両方を使用して、サービスをセキュリティで保護することができます。</span><span class="sxs-lookup"><span data-stu-id="d43b5-116">You can use either or both of these mechanisms to secure your service.</span></span>

<span data-ttu-id="d43b5-117">GRPC の ASP.NET Core 実装では、ほとんどの標準 ASP.NET Core 機構を使用した認証と承認をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d43b5-117">The ASP.NET Core implementation of gRPC supports authentication and authorization using most of the standard ASP.NET Core mechanisms:</span></span>

- <span data-ttu-id="d43b5-118">認証の呼び出し</span><span class="sxs-lookup"><span data-stu-id="d43b5-118">Call authentication</span></span>
  - <span data-ttu-id="d43b5-119">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d43b5-119">Azure Active Directory</span></span>
  - <span data-ttu-id="d43b5-120">IdentityServer</span><span class="sxs-lookup"><span data-stu-id="d43b5-120">IdentityServer</span></span>
  - <span data-ttu-id="d43b5-121">JWT ベアラートークン</span><span class="sxs-lookup"><span data-stu-id="d43b5-121">JWT Bearer Token</span></span>
  - <span data-ttu-id="d43b5-122">OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="d43b5-122">OAuth 2.0</span></span>
  - <span data-ttu-id="d43b5-123">OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="d43b5-123">OpenID Connect</span></span>
  - <span data-ttu-id="d43b5-124">WS-Federation</span><span class="sxs-lookup"><span data-stu-id="d43b5-124">WS-Federation</span></span>
- <span data-ttu-id="d43b5-125">チャネル認証</span><span class="sxs-lookup"><span data-stu-id="d43b5-125">Channel authentication</span></span>
  - <span data-ttu-id="d43b5-126">クライアント証明書</span><span class="sxs-lookup"><span data-stu-id="d43b5-126">Client Certificate</span></span>

<span data-ttu-id="d43b5-127">呼び出しの認証方法はすべて、*トークン*に基づいています。</span><span class="sxs-lookup"><span data-stu-id="d43b5-127">The call authentication methods are all based on *tokens*.</span></span> <span data-ttu-id="d43b5-128">実際の違いは、トークンが生成される方法と、ASP.NET Core サービスでトークンを検証するために使用されるライブラリです。</span><span class="sxs-lookup"><span data-stu-id="d43b5-128">The only real difference is how the token is generated and the libraries that are used to validate the tokens in the ASP.NET Core service.</span></span>

<span data-ttu-id="d43b5-129">詳細については、 [Microsoft Docs に関する認証と承認に関するドキュメント](https://docs.microsoft.com/aspnet/core/grpc/authn-and-authz?view=aspnetcore-3.0)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d43b5-129">For more information, see the [Authentication and authorization documentation on Microsoft Docs](https://docs.microsoft.com/aspnet/core/grpc/authn-and-authz?view=aspnetcore-3.0).</span></span>

> [!NOTE]
> <span data-ttu-id="d43b5-130">TLS で暗号化された HTTP/2 接続で gRPC を使用する場合、チャネルレベルの認証を使用しない場合でも、クライアントとサーバー間のすべてのトラフィックが暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="d43b5-130">When using gRPC over a TLS-encrypted HTTP/2 connection, all traffic between clients and servers is encrypted, even if you don't use channel-level authentication.</span></span>

<span data-ttu-id="d43b5-131">この章では、gRPC サービスに呼び出し資格情報とチャネル資格情報を適用する方法と、.NET Core gRPC クライアントから資格情報を使用してサービスで認証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d43b5-131">This chapter will show how to apply call credentials and channel credentials to a gRPC service, and how to use credentials from a .NET Core gRPC client to authenticate with the service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d43b5-132">[前へ](client-libraries.md)
>[次へ](call-credentials.md)</span><span class="sxs-lookup"><span data-stu-id="d43b5-132">[Previous](client-libraries.md)
[Next](call-credentials.md)</span></span>
