---
title: セキュリティ
description: Azure 向けのクラウドネイティブ .NET アプリの設計 |保護
ms.date: 06/30/2019
ms.openlocfilehash: 848255de70038798417a558543d0b1ea8cff1e37
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2019
ms.locfileid: "73840995"
---
# <a name="security"></a><span data-ttu-id="dc313-103">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="dc313-103">Security</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="dc313-104">1日ではなく、会社がハッキングされたり、ユーザーのデータが失われたりすることについて、ニュースに何のストーリーも含まれていません。</span><span class="sxs-lookup"><span data-stu-id="dc313-104">Not a day goes by where the news doesn't contain some story about a company being hacked or somehow losing their customers' data.</span></span> <span data-ttu-id="dc313-105">他の国では、セキュリティを後で扱うことによって作成された問題を解決できません。</span><span class="sxs-lookup"><span data-stu-id="dc313-105">Even countries aren't immune to the problems created by treating security as an afterthought.</span></span> <span data-ttu-id="dc313-106">長年にわたり、企業は顧客データのセキュリティと、実際にはネットワーク全体を "優れた" ものとして扱ってきました。</span><span class="sxs-lookup"><span data-stu-id="dc313-106">For years, companies have treated the security of customer data and, in fact, their entire networks as something of a "nice to have".</span></span> <span data-ttu-id="dc313-107">Windows server は修正プログラム脆弱性に残されており、従来のバージョンの PHP は実行されたままで、MongoDB データベースは世界中にオープンになっています。</span><span class="sxs-lookup"><span data-stu-id="dc313-107">Windows servers were left unpatched, ancient versions of PHP kept running and MongoDB databases left wide open to the world.</span></span>

<span data-ttu-id="dc313-108">しかし、アプリケーションをビルドして展開するときに、セキュリティ上の考え方を維持するために、実際の結果になることはありません。</span><span class="sxs-lookup"><span data-stu-id="dc313-108">However, there are starting to be real-world consequences for not maintaining a security mindset when building and deploying applications.</span></span> <span data-ttu-id="dc313-109">多くの企業では、 [Notpetya](https://www.wired.com/story/notpetya-cyberattack-ukraine-russia-code-crashed-the-world/)の2017の発生中にサーバーとデスクトップにパッチが適用されていない場合に発生する可能性があることを学習しました。</span><span class="sxs-lookup"><span data-stu-id="dc313-109">Many companies learned the hard way what can happen when servers and desktops aren't patched during the 2017 outbreak of [NotPetya](https://www.wired.com/story/notpetya-cyberattack-ukraine-russia-code-crashed-the-world/).</span></span> <span data-ttu-id="dc313-110">これらの攻撃のコストは数十億に簡単に到達しましたが、この1つの攻撃からの損失が100億米ドルであるという見積もりもあります。</span><span class="sxs-lookup"><span data-stu-id="dc313-110">The cost of these attacks has easily reached into the billions, with some estimates putting the losses from this single attack at 10 billion US dollars.</span></span>

<span data-ttu-id="dc313-111">政府機関も、インシデントのハッキングには対応していません。</span><span class="sxs-lookup"><span data-stu-id="dc313-111">Even governments aren't immune to hacking incidents.</span></span> <span data-ttu-id="dc313-112">Baltimore の町は[犯罪](https://www.vox.com/recode/2019/5/21/18634505/baltimore-ransom-robbinhood-mayor-jack-young-hackers)者によって ransom を保持していました。これにより、市民が請求を支払ったり、都市サービスを使用したりすることが不可能になります。</span><span class="sxs-lookup"><span data-stu-id="dc313-112">The city of Baltimore was held ransom by [criminals](https://www.vox.com/recode/2019/5/21/18634505/baltimore-ransom-robbinhood-mayor-jack-young-hackers) making it impossible for citizens to pay their bills or use city services.</span></span>

<span data-ttu-id="dc313-113">また、個人データに対して特定のデータ保護を義務付ける法律が強化されています。</span><span class="sxs-lookup"><span data-stu-id="dc313-113">There has also been an increase in legislation that mandates certain data protections for personal data.</span></span> <span data-ttu-id="dc313-114">ヨーロッパでは、GDPR は年を超えて有効になっています。さらに、カリフォルニア州は、2020年1月1日より有効になる CCDA と呼ばれる独自のバージョンを渡しました。</span><span class="sxs-lookup"><span data-stu-id="dc313-114">In Europe, GDPR has been in effect for more than a year and, more recently, California passed their own version called CCDA, which comes into effect January 1, 2020.</span></span> <span data-ttu-id="dc313-115">GDPR の下にある罰金は、企業をビジネスから除外するためにあれにすることができます。</span><span class="sxs-lookup"><span data-stu-id="dc313-115">The fines under GDPR can be so punishing as to put companies out of business.</span></span> <span data-ttu-id="dc313-116">Google は既に違反のために 5000万 Euro を fined していますが、これはバケットの中でも、潜在的な罰金と比較したものです。</span><span class="sxs-lookup"><span data-stu-id="dc313-116">Google has already been fined 50 million Euros for violations, but that's just a drop in the bucket compared with the potential fines.</span></span>

<span data-ttu-id="dc313-117">つまり、セキュリティは重要なビジネスです。</span><span class="sxs-lookup"><span data-stu-id="dc313-117">In short, security is serious business.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="dc313-118">[前へ](identity-server.md)
>[次へ](azure-security.md)</span><span class="sxs-lookup"><span data-stu-id="dc313-118">[Previous](identity-server.md)
[Next](azure-security.md)</span></span>
