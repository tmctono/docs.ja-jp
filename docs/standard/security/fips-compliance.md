---
title: FIPS 準拠-.NET Core
description: .NET Core Federal Information Processing Standards (FIPS) 準拠について説明します。
ms.date: 11/20/2019
author: Rick-Anderson
ms.author: riande
ms.openlocfilehash: cf640c857e79ae811dd38d57a0e5301b7bc96572
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2019
ms.locfileid: "74205078"
---
# <a name="net-core-federal-information-processing-standard-fips-compliance"></a><span data-ttu-id="fa3a6-103">.NET Core Federal Information Processing Standards (FIPS) 準拠</span><span class="sxs-lookup"><span data-stu-id="fa3a6-103">.NET Core Federal Information Processing Standard (FIPS) compliance</span></span>

<span data-ttu-id="fa3a6-104">Federal Information Processing Standards (FIPS) 公開140-2 は、情報技術製品の暗号化モジュールに最低限必要なセキュリティ要件を規定する米国政府の標準です。詳細については、「」のセクション5131で定義されています。1996のテクノロジ管理の改善。</span><span class="sxs-lookup"><span data-stu-id="fa3a6-104">The Federal Information Processing Standard (FIPS) Publication 140-2 is a U.S. government standard that defines minimum security requirements for cryptographic modules in information technology products, as defined in Section 5131 of the Information Technology Management Reform Act of 1996.</span></span>

<span data-ttu-id="fa3a6-105">.NET Core:</span><span class="sxs-lookup"><span data-stu-id="fa3a6-105">.NET Core:</span></span>

* <span data-ttu-id="fa3a6-106">は、基になるオペレーティングシステムが提供する標準モジュールに暗号化プリミティブの呼び出しを渡します。</span><span class="sxs-lookup"><span data-stu-id="fa3a6-106">Passes cryptographic primitives calls through to the standard modules the underlying operating system provides.</span></span>
* <span data-ttu-id="fa3a6-107">では、.NET Core アプリで FIPS 承認アルゴリズムまたはキーサイズを使用することは強制**されません**。</span><span class="sxs-lookup"><span data-stu-id="fa3a6-107">Does **not** enforce the use of FIPS Approved algorithms or key sizes in .NET Core apps.</span></span>

<span data-ttu-id="fa3a6-108">システム管理者は、オペレーティングシステムの FIPS 準拠を構成する役割を担います。</span><span class="sxs-lookup"><span data-stu-id="fa3a6-108">The system administrator is responsible for configuring the FIPS compliance for an operating system.</span></span>

<span data-ttu-id="fa3a6-109">コードが FIPS 準拠環境用に記述されている場合、開発者は準拠していない FIPS アルゴリズムが使用されていないことを確認する責任があります。</span><span class="sxs-lookup"><span data-stu-id="fa3a6-109">If code is written for a FIPS-compliant environment, the developer is responsible for ensuring that non-compliant FIPS algorithms aren't used.</span></span>

<span data-ttu-id="fa3a6-110">FIPS 準拠の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa3a6-110">For more information on FIPS compliance, see the following articles:</span></span>

* [<span data-ttu-id="fa3a6-111">Windows FIPS 準拠</span><span class="sxs-lookup"><span data-stu-id="fa3a6-111">Windows FIPS Compliance</span></span>](/windows/security/threat-protection/fips-140-validation)
* [<span data-ttu-id="fa3a6-112">FIPS 準拠のための Windows の構成</span><span class="sxs-lookup"><span data-stu-id="fa3a6-112">Configuring Windows for FIPS Compliance</span></span>](/windows/security/threat-protection/security-policy-settings/system-cryptography-use-fips-compliant-algorithms-for-encryption-hashing-and-signing)
* [<span data-ttu-id="fa3a6-113">10.2. 連邦情報処理標準 (FIPS)</span><span class="sxs-lookup"><span data-stu-id="fa3a6-113">10.2. FEDERAL INFORMATION PROCESSING STANDARD (FIPS)</span></span>](https://access.redhat.com/documentation/red_hat_enterprise_linux/6/html/security_guide/sect-security_guide-federal_standards_and_regulations-federal_information_processing_standard)
