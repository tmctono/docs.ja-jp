---
title: クラウドネイティブアプリでの認証と承認
description: Azure 向けのクラウドネイティブ .NET アプリの設計 |クラウドネイティブアプリでの認証と承認
ms.date: 06/30/2019
ms.openlocfilehash: a397175e98c2e8103d2a8c372c81fcca65f19b11
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2019
ms.locfileid: "73840749"
---
# <a name="authentication-and-authorization-in-cloud-native-apps"></a><span data-ttu-id="0a014-103">クラウドネイティブのアプリにおける認証と承認</span><span class="sxs-lookup"><span data-stu-id="0a014-103">Authentication and authorization in cloud-native apps</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="0a014-104">*認証*は、セキュリティプリンシパルの id を特定するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="0a014-104">*Authentication* is the process of determining the identity of a security principal.</span></span> <span data-ttu-id="0a014-105">*承認*とは、認証されたプリンシパルのアクセス許可を付与して、アクションを実行したり、リソースにアクセスしたりする行為です。</span><span class="sxs-lookup"><span data-stu-id="0a014-105">*Authorization* is the act of granting an authenticated principal permission to perform an action or access a resource.</span></span> <span data-ttu-id="0a014-106">`AuthN` に対して認証が短縮され、`AuthZ`に対して承認が短縮されることがあります。</span><span class="sxs-lookup"><span data-stu-id="0a014-106">Sometimes authentication is shortened to `AuthN` and authorization is shortened to `AuthZ`.</span></span> <span data-ttu-id="0a014-107">クラウドネイティブアプリケーションは、クライアントとアプリケーションの両方が任意のプラットフォームまたはデバイスで実行される可能性があるため、セキュリティプリンシパルを認証するためにオープン HTTP ベースのプロトコルに依存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a014-107">Cloud-native applications need to rely on open HTTP-based protocols to authenticate security principals since both clients and applications could be running anywhere in the world on any platform or device.</span></span> <span data-ttu-id="0a014-108">唯一の共通要素は HTTP です。</span><span class="sxs-lookup"><span data-stu-id="0a014-108">The only common factor is HTTP.</span></span>

<span data-ttu-id="0a014-109">多くの組織は、Active Directory フェデレーションサービス (AD FS) (ADFS) などのローカル認証サービスを引き続き利用しています。</span><span class="sxs-lookup"><span data-stu-id="0a014-109">Many organizations still rely on local authentication services like Active Directory Federation Services (ADFS).</span></span> <span data-ttu-id="0a014-110">このアプローチは従来、オンプレミスの認証ニーズに適していますが、クラウドネイティブアプリケーションは、クラウド専用に設計されたシステムの恩恵を受けています。</span><span class="sxs-lookup"><span data-stu-id="0a014-110">While this approach has traditionally served organizations well for on premises authentication needs, cloud-native applications benefit from systems designed specifically for the cloud.</span></span> <span data-ttu-id="0a014-111">最近の2019英国国立サイバーセキュリティセンター (NCSC) 勧告では、"Azure AD をプライマリ認証ソースとして使用する組織は、ADFS と比較して実際にリスクを下げることができます。"</span><span class="sxs-lookup"><span data-stu-id="0a014-111">A recent 2019 United Kingdom National Cyber Security Centre (NCSC) advisory states that "organizations using Azure AD as their primary authentication source will actually lower their risk compared to ADFS."</span></span> <span data-ttu-id="0a014-112">[この分析](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/)では、次のような理由が考えられます。</span><span class="sxs-lookup"><span data-stu-id="0a014-112">Some reasons outlined in [this analysis](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/) include:</span></span>

- <span data-ttu-id="0a014-113">Microsoft credential protection テクノロジの完全なセットへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="0a014-113">Access to full set of Microsoft credential protection technologies.</span></span>
- <span data-ttu-id="0a014-114">ほとんどの組織は、既に何らかの範囲の Azure AD に依存しています。</span><span class="sxs-lookup"><span data-stu-id="0a014-114">Most organizations are already relying on Azure AD to some extent.</span></span>
- <span data-ttu-id="0a014-115">NTLM ハッシュを二重にハッシュすると、ローカル Active Directory で動作する資格情報が侵害されることがなくなります。</span><span class="sxs-lookup"><span data-stu-id="0a014-115">Double hashing of NTLM hashes ensures compromise won't allow credentials that work in local Active Directory.</span></span>

## <a name="references"></a><span data-ttu-id="0a014-116">参照</span><span class="sxs-lookup"><span data-stu-id="0a014-116">References</span></span>

- [<span data-ttu-id="0a014-117">認証の基本</span><span class="sxs-lookup"><span data-stu-id="0a014-117">Authentication basics</span></span>](https://docs.microsoft.com/azure/active-directory/develop/authentication-scenarios)
- [<span data-ttu-id="0a014-118">アクセストークンと要求</span><span class="sxs-lookup"><span data-stu-id="0a014-118">Access tokens and claims</span></span>](https://docs.microsoft.com/azure/active-directory/develop/access-tokens)
- [<span data-ttu-id="0a014-119">オンプレミスの認証サービスを溝に時間がかかる場合があります</span><span class="sxs-lookup"><span data-stu-id="0a014-119">It may be time to ditch your on premises authentication services</span></span>](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/)

>[!div class="step-by-step"]
><span data-ttu-id="0a014-120">[前へ](identity.md)
>[次へ](azure-active-directory.md)</span><span class="sxs-lookup"><span data-stu-id="0a014-120">[Previous](identity.md)
[Next](azure-active-directory.md)</span></span>
