---
title: ID
description: Azure 向けのクラウドネイティブ .NET アプリの設計 |アイデンティティ
ms.date: 05/13/2020
ms.openlocfilehash: 66ff29947093d7c4fe57b11039190836dc37db08
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91163753"
---
# <a name="identity"></a><span data-ttu-id="c3b06-103">ID</span><span class="sxs-lookup"><span data-stu-id="c3b06-103">Identity</span></span>

<span data-ttu-id="c3b06-104">ほとんどのソフトウェアアプリケーションは、それらを呼び出すユーザーまたはプロセスに関する知識を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3b06-104">Most software applications need to have some knowledge of the user or process that is calling them.</span></span> <span data-ttu-id="c3b06-105">アプリケーションと対話するユーザーまたはプロセスはセキュリティプリンシパルと呼ばれ、これらのプリンシパルを認証および承認するプロセスは、id 管理または単に *id*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="c3b06-105">The user or process interacting with an application is known as a security principal, and the process of authenticating and authorizing these principals is known as identity management, or simply *identity*.</span></span> <span data-ttu-id="c3b06-106">単純なアプリケーションには、アプリケーション内のすべての id 管理を含めることができますが、この方法は、多くのアプリケーションやさまざまな種類のセキュリティプリンシパルには適していません。</span><span class="sxs-lookup"><span data-stu-id="c3b06-106">Simple applications may include all of their identity management within the application, but this approach doesn't scale well with many applications and many kinds of security principals.</span></span> <span data-ttu-id="c3b06-107">Windows では、Active Directory を使用して、一元的な認証と承認を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c3b06-107">Windows supports the use of Active Directory to provide centralized authentication and authorization.</span></span>

<!-- (insert figure showing Windows AD auth model) -->

<span data-ttu-id="c3b06-108">このソリューションは企業ネットワーク内で有効ですが、AD ドメインの外部にあるユーザーまたはアプリケーションが使用できるように設計されていません。</span><span class="sxs-lookup"><span data-stu-id="c3b06-108">While this solution is effective within corporate networks, it isn't designed for use by users or applications that are outside of the AD domain.</span></span> <span data-ttu-id="c3b06-109">インターネットベースのアプリケーションとクラウドネイティブアプリの増加により、セキュリティモデルが進化しました。</span><span class="sxs-lookup"><span data-stu-id="c3b06-109">With the growth of Internet-based applications and the rise of cloud-native apps, security models have evolved.</span></span>

<span data-ttu-id="c3b06-110">現在のクラウドネイティブ id モデルでは、アーキテクチャが分散されると想定されています。</span><span class="sxs-lookup"><span data-stu-id="c3b06-110">In today's cloud-native identity model, architecture is assumed to be distributed.</span></span> <span data-ttu-id="c3b06-111">アプリはどこにでもデプロイでき、どこからでも他のアプリと通信することができます。</span><span class="sxs-lookup"><span data-stu-id="c3b06-111">Apps can be deployed anywhere and may communicate with other apps anywhere.</span></span> <span data-ttu-id="c3b06-112">クライアントは、どこからでもこれらのアプリと通信できますが、実際には、クライアントはプラットフォームとデバイスの任意の組み合わせで構成される場合があります。</span><span class="sxs-lookup"><span data-stu-id="c3b06-112">Clients may communicate with these apps from anywhere, and in fact, clients may consist of any combination of platforms and devices.</span></span> <span data-ttu-id="c3b06-113">クラウドネイティブ id ソリューションでは、オープン標準を利用して、クライアントからのセキュリティで保護されたアプリケーションアクセスを実現します。</span><span class="sxs-lookup"><span data-stu-id="c3b06-113">Cloud-native identity solutions leverage open standards to achieve secure application access from clients.</span></span> <span data-ttu-id="c3b06-114">これらのクライアントは、Pc や電話の人間のユーザーから、オンラインでホストされている他のアプリまで、世界中の任意のソフトウェアプラットフォームを実行しているトップボックスと IOT デバイスを設定できます。</span><span class="sxs-lookup"><span data-stu-id="c3b06-114">These clients range from human users on PCs or phones, to other apps hosted anywhere online, to set-top boxes and IOT devices running any software platform anywhere in the world.</span></span>

<span data-ttu-id="c3b06-115">最新のクラウドネイティブ id ソリューションでは、通常、セキュリティトークンサービス/サーバー (STS) によって発行されたアクセストークンを、id が決定された後、セキュリティプリンシパルに利用します。</span><span class="sxs-lookup"><span data-stu-id="c3b06-115">Modern cloud-native identity solutions typically leverage access tokens that are issued by a secure token service/server (STS) to a security principal once their identity is determined.</span></span> <span data-ttu-id="c3b06-116">アクセストークン (通常は JSON Web トークン (JWT)) には、セキュリティプリンシパルに関する *クレーム* が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c3b06-116">The access token, typically a JSON Web Token (JWT), includes *claims* about the security principal.</span></span> <span data-ttu-id="c3b06-117">これらの要求には、最小限のユーザー id が含まれますが、アプリケーションでプリンシパルに付与するアクセスレベルを決定するために使用できる追加の要求も含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c3b06-117">These claims will minimally include the user's identity but may also include additional claims that can be used by applications to determine the level of access to grant the principal.</span></span>

<!-- (insert figure showing basic handshake involving a principal, an STS, and an app) -->

<span data-ttu-id="c3b06-118">通常、STS はプリンシパルの認証のみを行います。</span><span class="sxs-lookup"><span data-stu-id="c3b06-118">Typically, the STS is only responsible for authenticating the principal.</span></span> <span data-ttu-id="c3b06-119">リソースへのアクセスレベルを決定することは、アプリケーションの他の部分に残されます。</span><span class="sxs-lookup"><span data-stu-id="c3b06-119">Determining their level of access to resources is left to other parts of the application.</span></span>

## <a name="references"></a><span data-ttu-id="c3b06-120">References</span><span class="sxs-lookup"><span data-stu-id="c3b06-120">References</span></span>

- [<span data-ttu-id="c3b06-121">Microsoft ID プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="c3b06-121">Microsoft identity platform</span></span>](/azure/active-directory/develop/)

>[!div class="step-by-step"]
><span data-ttu-id="c3b06-122">[前へ](azure-monitor.md)
>[次へ](authentication-authorization.md)</span><span class="sxs-lookup"><span data-stu-id="c3b06-122">[Previous](azure-monitor.md)
[Next](authentication-authorization.md)</span></span>
