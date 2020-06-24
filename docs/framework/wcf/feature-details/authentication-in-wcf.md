---
title: WCF での認証
description: Windows 認証、x.509 証明書、ユーザー名とパスワードなどの認証を提供する、WCF のいくつかのメカニズムについて説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
ms.openlocfilehash: 4c3348cfb84b8571dc1f24b774ffcd691aaa5001
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247521"
---
# <a name="authentication-in-wcf"></a><span data-ttu-id="1b08d-103">WCF での認証</span><span class="sxs-lookup"><span data-stu-id="1b08d-103">Authentication in WCF</span></span>
<span data-ttu-id="1b08d-104">次のトピックでは、Windows 認証、x.509 証明書、ユーザー名とパスワードなどの認証を提供する Windows Communication Foundation (WCF) のさまざまなメカニズムについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1b08d-104">The following topics show a number of different mechanisms in Windows Communication Foundation (WCF) that provide authentication, for example, Windows authentication, X.509 certificates, and user name and passwords.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1b08d-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1b08d-105">In This Section</span></span>  
 [<span data-ttu-id="1b08d-106">方法: ASP.NET メンバーシップ プロバイダーを使用する</span><span class="sxs-lookup"><span data-stu-id="1b08d-106">How to: Use the ASP.NET Membership Provider</span></span>](how-to-use-the-aspnet-membership-provider.md)  
 <span data-ttu-id="1b08d-107">ASP.NET の機能には、メンバーシップとロール プロバイダー、認証のためのユーザー名とパスワードの組み合わせを格納するデータベース、および承認のためのユーザー ロールがあります。</span><span class="sxs-lookup"><span data-stu-id="1b08d-107">ASP.NET features include a membership and role provider, a database to store user name/password pairs for authentication, and user roles for authorization.</span></span> <span data-ttu-id="1b08d-108">このトピックでは、WCF サービスが同じデータベースを使用してユーザーを認証および承認する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1b08d-108">This topic explains how WCF services can use the same database to authenticate and authorize users.</span></span>  
  
 [<span data-ttu-id="1b08d-109">方法: カスタム ユーザー名およびパスワード検証を使用する</span><span class="sxs-lookup"><span data-stu-id="1b08d-109">How to: Use a Custom User Name and Password Validator</span></span>](how-to-use-a-custom-user-name-and-password-validator.md)  
 <span data-ttu-id="1b08d-110">カスタム ユーザー名およびパスワード検証を統合する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1b08d-110">Demonstrates how to integrate a custom user name/password validator.</span></span>  
  
 [<span data-ttu-id="1b08d-111">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="1b08d-111">Service Identity and Authentication</span></span>](service-identity-and-authentication.md)  
 <span data-ttu-id="1b08d-112">追加の保護手段として、クライアントはサービスの予期される*id*を指定することによってサービスを認証できます。</span><span class="sxs-lookup"><span data-stu-id="1b08d-112">As an extra safeguard, a client can authenticate the service by specifying the expected *identity* of the service.</span></span> <span data-ttu-id="1b08d-113">予想される ID とサービスから返される ID が一致しない場合、認証は失敗します。</span><span class="sxs-lookup"><span data-stu-id="1b08d-113">If the expected identity and the identity returned by the service do not match, authentication fails.</span></span>  
  
 [<span data-ttu-id="1b08d-114">セキュリティ ネゴシエーションとタイムアウト</span><span class="sxs-lookup"><span data-stu-id="1b08d-114">Security Negotiation and Timeouts</span></span>](security-negotiation-and-timeouts.md)  
 <span data-ttu-id="1b08d-115"><xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> クラスの <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> プロパティの使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1b08d-115">Describes how to use the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property in the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> class.</span></span>  
  
 [<span data-ttu-id="1b08d-116">Windows 認証エラーのデバッグ</span><span class="sxs-lookup"><span data-stu-id="1b08d-116">Debugging Windows Authentication Errors</span></span>](debugging-windows-authentication-errors.md)  
 <span data-ttu-id="1b08d-117">Windows 認証の使用時に発生する一般的な問題について重点的に説明します。</span><span class="sxs-lookup"><span data-stu-id="1b08d-117">Focuses on common problems encountered when using Windows authentication.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1b08d-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b08d-118">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="1b08d-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b08d-119">Related Sections</span></span>  
 [<span data-ttu-id="1b08d-120">一般的なセキュリティ シナリオ</span><span class="sxs-lookup"><span data-stu-id="1b08d-120">Common Security Scenarios</span></span>](common-security-scenarios.md)  
  
## <a name="see-also"></a><span data-ttu-id="1b08d-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b08d-121">See also</span></span>

- [<span data-ttu-id="1b08d-122">セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="1b08d-122">Security Overview</span></span>](security-overview.md)
- <span data-ttu-id="1b08d-123">[Windows Server AppFabric のセキュリティ モデル](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="1b08d-123">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
