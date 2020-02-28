---
title: 暗号での破壊的変更
description: .NET Core で暗号化に関連する破壊的変更の一覧を示します。
ms.date: 02/10/2020
ms.openlocfilehash: c25eefa8e3ee01ed7a1df4ec4aa9225f2c347a4d
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449222"
---
# <a name="cryptography-breaking-changes"></a><span data-ttu-id="d1ebf-103">暗号での破壊的変更</span><span class="sxs-lookup"><span data-stu-id="d1ebf-103">Cryptography breaking changes</span></span>

<span data-ttu-id="d1ebf-104">このページでは、次の破壊的変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1ebf-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="d1ebf-105">互換性に影響する変更点</span><span class="sxs-lookup"><span data-stu-id="d1ebf-105">Breaking change</span></span> | <span data-ttu-id="d1ebf-106">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="d1ebf-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="d1ebf-107">EnvelopedCms で AES-256 暗号化を既定で使用</span><span class="sxs-lookup"><span data-stu-id="d1ebf-107">EnvelopedCms defaults to AES-256 encryption</span></span>](#envelopedcms-defaults-to-aes-256-encryption) | <span data-ttu-id="d1ebf-108">3.0</span><span class="sxs-lookup"><span data-stu-id="d1ebf-108">3.0</span></span> |
| [<span data-ttu-id="d1ebf-109">RSAOpenSsl キー生成の最小サイズの増加</span><span class="sxs-lookup"><span data-stu-id="d1ebf-109">Minimum size for RSAOpenSsl key generation has increased</span></span>](#minimum-size-for-rsaopenssl-key-generation-has-increased) | <span data-ttu-id="d1ebf-110">3.0</span><span class="sxs-lookup"><span data-stu-id="d1ebf-110">3.0</span></span> |
| [<span data-ttu-id="d1ebf-111">.NET Core 3.0 では、OpenSSL 1.0.x よりも OpenSSL 1.1.x を優先する</span><span class="sxs-lookup"><span data-stu-id="d1ebf-111">.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x</span></span>](#net-core-30-prefers-openssl-11x-to-openssl-10x) | <span data-ttu-id="d1ebf-112">3.0</span><span class="sxs-lookup"><span data-stu-id="d1ebf-112">3.0</span></span> |
| [<span data-ttu-id="d1ebf-113">Pkcs8PrivateKeyInfo コンストラクターでの引数の検証の改善</span><span class="sxs-lookup"><span data-stu-id="d1ebf-113">Better argument validation in the Pkcs8PrivateKeyInfo constructor</span></span>](#better-argument-validation-in-the-pkcs8privatekeyinfo-constructor) | <span data-ttu-id="d1ebf-114">3.0</span><span class="sxs-lookup"><span data-stu-id="d1ebf-114">3.0</span></span> |
| [<span data-ttu-id="d1ebf-115">SignedCms.ComputeSignature のブール型パラメーターの尊重</span><span class="sxs-lookup"><span data-stu-id="d1ebf-115">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>](#boolean-parameter-of-signedcmscomputesignature-is-respected) | <span data-ttu-id="d1ebf-116">2.1</span><span class="sxs-lookup"><span data-stu-id="d1ebf-116">2.1</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="d1ebf-117">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d1ebf-117">.NET Core 3.0</span></span>

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/3.0/envelopedcms-defaults-to-aes256.md)]

***

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/3.0/minimum-rsaopenssl-key-size-change.md)]

***

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/3.0/net-core-3-0-prefers-openssl-1-1-x.md)]

***

[!INCLUDE[Better argument validation in the Pkcs8PrivateKeyInfo constructor](~/includes/core-changes/cryptography/3.0/better-argument-validation-in-pkcs8privatekeyinfo-ctor.md)]

***

## <a name="net-core-21"></a><span data-ttu-id="d1ebf-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="d1ebf-118">.NET Core 2.1</span></span>

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

***
