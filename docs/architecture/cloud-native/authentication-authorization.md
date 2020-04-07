---
title: クラウド ネイティブ アプリでの認証と承認
description: Azure 用クラウド ネイティブ .NET アプリの設計 |クラウド ネイティブ アプリでの認証と承認
ms.date: 03/02/2020
ms.openlocfilehash: 6261a0a72405bc1c984a04a7851aea4dd6664ddf
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805549"
---
# <a name="authentication-and-authorization-in-cloud-native-apps"></a><span data-ttu-id="c48dd-103">クラウドネイティブのアプリにおける認証と承認</span><span class="sxs-lookup"><span data-stu-id="c48dd-103">Authentication and authorization in cloud-native apps</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="c48dd-104">*認証*は、セキュリティ プリンシパルの ID を決定するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="c48dd-104">*Authentication* is the process of determining the identity of a security principal.</span></span> <span data-ttu-id="c48dd-105">*承認*とは、アクションを実行したり、リソースにアクセスしたりするための認証されたプリンシパルアクセス許可を付与する行為です。</span><span class="sxs-lookup"><span data-stu-id="c48dd-105">*Authorization* is the act of granting an authenticated principal permission to perform an action or access a resource.</span></span> <span data-ttu-id="c48dd-106">認証がに短縮`AuthN`され、承認が に`AuthZ`短縮される場合があります。</span><span class="sxs-lookup"><span data-stu-id="c48dd-106">Sometimes authentication is shortened to `AuthN` and authorization is shortened to `AuthZ`.</span></span> <span data-ttu-id="c48dd-107">クラウドネイティブ アプリケーションは、クライアントとアプリケーションの両方がどのプラットフォームまたはデバイス上で世界中のどこでも実行できるため、オープン HTTP ベースのプロトコルを使用してセキュリティ プリンシパルを認証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c48dd-107">Cloud-native applications need to rely on open HTTP-based protocols to authenticate security principals since both clients and applications could be running anywhere in the world on any platform or device.</span></span> <span data-ttu-id="c48dd-108">唯一の共通の要因は HTTP です。</span><span class="sxs-lookup"><span data-stu-id="c48dd-108">The only common factor is HTTP.</span></span>

<span data-ttu-id="c48dd-109">多くの組織は、Active Directory フェデレーション サービス (ADFS) などのローカル認証サービスに依然として依存しています。</span><span class="sxs-lookup"><span data-stu-id="c48dd-109">Many organizations still rely on local authentication services like Active Directory Federation Services (ADFS).</span></span> <span data-ttu-id="c48dd-110">このアプローチは従来、オンプレミスの認証ニーズに適した組織に役立っていますが、クラウドネイティブアプリケーションは、クラウド専用に設計されたシステムから恩恵を受けています。</span><span class="sxs-lookup"><span data-stu-id="c48dd-110">While this approach has traditionally served organizations well for on premises authentication needs, cloud-native applications benefit from systems designed specifically for the cloud.</span></span> <span data-ttu-id="c48dd-111">最近の2019年の英国国家サイバーセキュリティセンター(NCSC)のアドバイザリーは、「Azure AD を主要な認証ソースとして使用している組織は、実際には ADFS と比較してリスクを下げる」と述べています。</span><span class="sxs-lookup"><span data-stu-id="c48dd-111">A recent 2019 United Kingdom National Cyber Security Centre (NCSC) advisory states that "organizations using Azure AD as their primary authentication source will actually lower their risk compared to ADFS."</span></span> <span data-ttu-id="c48dd-112">[この分析](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/)で概説されている理由には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="c48dd-112">Some reasons outlined in [this analysis](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/) include:</span></span>

- <span data-ttu-id="c48dd-113">Microsoft 資格情報保護テクノロジのフル セットへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="c48dd-113">Access to full set of Microsoft credential protection technologies.</span></span>
- <span data-ttu-id="c48dd-114">ほとんどの組織は、既にある程度 Azure AD に依存しています。</span><span class="sxs-lookup"><span data-stu-id="c48dd-114">Most organizations are already relying on Azure AD to some extent.</span></span>
- <span data-ttu-id="c48dd-115">NTLM ハッシュの二重ハッシュにより、ローカル Active Directory で動作する資格情報が侵害されないことが保証されます。</span><span class="sxs-lookup"><span data-stu-id="c48dd-115">Double hashing of NTLM hashes ensures compromise won't allow credentials that work in local Active Directory.</span></span>

## <a name="references"></a><span data-ttu-id="c48dd-116">References</span><span class="sxs-lookup"><span data-stu-id="c48dd-116">References</span></span>

- [<span data-ttu-id="c48dd-117">認証の基本</span><span class="sxs-lookup"><span data-stu-id="c48dd-117">Authentication basics</span></span>](https://docs.microsoft.com/azure/active-directory/develop/authentication-scenarios)
- [<span data-ttu-id="c48dd-118">アクセス トークンとクレーム</span><span class="sxs-lookup"><span data-stu-id="c48dd-118">Access tokens and claims</span></span>](https://docs.microsoft.com/azure/active-directory/develop/access-tokens)
- [<span data-ttu-id="c48dd-119">オンプレミスの認証サービスを捨てる時が来たかもしれない</span><span class="sxs-lookup"><span data-stu-id="c48dd-119">It may be time to ditch your on premises authentication services</span></span>](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/)

>[!div class="step-by-step"]
><span data-ttu-id="c48dd-120">[前へ](identity.md)
>[次へ](azure-active-directory.md)</span><span class="sxs-lookup"><span data-stu-id="c48dd-120">[Previous](identity.md)
[Next](azure-active-directory.md)</span></span>
