---
title: 暗号での破壊的変更
description: .NET Core で暗号化に関連する破壊的変更の一覧を示します。
ms.date: 04/22/2020
ms.openlocfilehash: 66049473083d87b4c84408f35a04193a4563c2b3
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135603"
---
# <a name="cryptography-breaking-changes"></a><span data-ttu-id="320fa-103">暗号での破壊的変更</span><span class="sxs-lookup"><span data-stu-id="320fa-103">Cryptography breaking changes</span></span>

<span data-ttu-id="320fa-104">このページでは、次の破壊的変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="320fa-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="320fa-105">互換性に影響する変更点</span><span class="sxs-lookup"><span data-stu-id="320fa-105">Breaking change</span></span> | <span data-ttu-id="320fa-106">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="320fa-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="320fa-107">Linux で BEGIN TRUSTED CERTIFICATE 構文がサポートされなくなった</span><span class="sxs-lookup"><span data-stu-id="320fa-107">BEGIN TRUSTED CERTIFICATE syntax no longer supported on Linux</span></span>](#begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux) | <span data-ttu-id="320fa-108">3.0</span><span class="sxs-lookup"><span data-stu-id="320fa-108">3.0</span></span> |
| [<span data-ttu-id="320fa-109">EnvelopedCms で AES-256 暗号化を既定で使用</span><span class="sxs-lookup"><span data-stu-id="320fa-109">EnvelopedCms defaults to AES-256 encryption</span></span>](#envelopedcms-defaults-to-aes-256-encryption) | <span data-ttu-id="320fa-110">3.0</span><span class="sxs-lookup"><span data-stu-id="320fa-110">3.0</span></span> |
| [<span data-ttu-id="320fa-111">RSAOpenSsl キー生成の最小サイズの増加</span><span class="sxs-lookup"><span data-stu-id="320fa-111">Minimum size for RSAOpenSsl key generation has increased</span></span>](#minimum-size-for-rsaopenssl-key-generation-has-increased) | <span data-ttu-id="320fa-112">3.0</span><span class="sxs-lookup"><span data-stu-id="320fa-112">3.0</span></span> |
| [<span data-ttu-id="320fa-113">.NET Core 3.0 では、OpenSSL 1.0.x よりも OpenSSL 1.1.x を優先する</span><span class="sxs-lookup"><span data-stu-id="320fa-113">.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x</span></span>](#net-core-30-prefers-openssl-11x-to-openssl-10x) | <span data-ttu-id="320fa-114">3.0</span><span class="sxs-lookup"><span data-stu-id="320fa-114">3.0</span></span> |
| [<span data-ttu-id="320fa-115">Pkcs8PrivateKeyInfo コンストラクターでの引数の検証の改善</span><span class="sxs-lookup"><span data-stu-id="320fa-115">Better argument validation in the Pkcs8PrivateKeyInfo constructor</span></span>](#better-argument-validation-in-the-pkcs8privatekeyinfo-constructor) | <span data-ttu-id="320fa-116">3.0</span><span class="sxs-lookup"><span data-stu-id="320fa-116">3.0</span></span> |
| [<span data-ttu-id="320fa-117">SignedCms.ComputeSignature のブール型パラメーターの尊重</span><span class="sxs-lookup"><span data-stu-id="320fa-117">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>](#boolean-parameter-of-signedcmscomputesignature-is-respected) | <span data-ttu-id="320fa-118">2.1</span><span class="sxs-lookup"><span data-stu-id="320fa-118">2.1</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="320fa-119">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="320fa-119">.NET Core 3.0</span></span>

[!INCLUDE [begin-trusted-cert-linux](~/includes/core-changes/cryptography/3.0/begin-trusted-cert-linux.md)]

***

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/3.0/envelopedcms-defaults-to-aes256.md)]

***

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/3.0/minimum-rsaopenssl-key-size-change.md)]

***

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/3.0/net-core-3-0-prefers-openssl-1-1-x.md)]

***

[!INCLUDE[Better argument validation in the Pkcs8PrivateKeyInfo constructor](~/includes/core-changes/cryptography/3.0/better-argument-validation-in-pkcs8privatekeyinfo-ctor.md)]

***

## <a name="net-core-21"></a><span data-ttu-id="320fa-120">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="320fa-120">.NET Core 2.1</span></span>

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

***
