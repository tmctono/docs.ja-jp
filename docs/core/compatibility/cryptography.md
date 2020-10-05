---
title: 暗号での破壊的変更
description: .NET Core で暗号化に関連する破壊的変更の一覧を示します。
ms.date: 04/22/2020
ms.openlocfilehash: 667d983fc6f2592c2169f97d328cd7947c8bcc81
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406149"
---
# <a name="cryptography-breaking-changes"></a><span data-ttu-id="24c09-103">暗号での破壊的変更</span><span class="sxs-lookup"><span data-stu-id="24c09-103">Cryptography breaking changes</span></span>

<span data-ttu-id="24c09-104">このページでは、次の破壊的変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="24c09-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="24c09-105">互換性に影響する変更点</span><span class="sxs-lookup"><span data-stu-id="24c09-105">Breaking change</span></span> | <span data-ttu-id="24c09-106">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="24c09-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="24c09-107">Blazor WebAssembly で System.Security.Cryptography API がサポートされない</span><span class="sxs-lookup"><span data-stu-id="24c09-107">System.Security.Cryptography APIs not supported on Blazor WebAssembly</span></span>](#systemsecuritycryptography-apis-not-supported-on-blazor-webassembly) | <span data-ttu-id="24c09-108">5.0</span><span class="sxs-lookup"><span data-stu-id="24c09-108">5.0</span></span> |
| [<span data-ttu-id="24c09-109">System.Security.Cryptography.Oid は機能的に初期化専用</span><span class="sxs-lookup"><span data-stu-id="24c09-109">System.Security.Cryptography.Oid is functionally init-only</span></span>](#systemsecuritycryptographyoid-is-functionally-init-only) | <span data-ttu-id="24c09-110">5.0</span><span class="sxs-lookup"><span data-stu-id="24c09-110">5.0</span></span> |
| [<span data-ttu-id="24c09-111">Linux で BEGIN TRUSTED CERTIFICATE 構文がサポートされなくなった</span><span class="sxs-lookup"><span data-stu-id="24c09-111">BEGIN TRUSTED CERTIFICATE syntax no longer supported on Linux</span></span>](#begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux) | <span data-ttu-id="24c09-112">3.0</span><span class="sxs-lookup"><span data-stu-id="24c09-112">3.0</span></span> |
| [<span data-ttu-id="24c09-113">EnvelopedCms で AES-256 暗号化を既定で使用</span><span class="sxs-lookup"><span data-stu-id="24c09-113">EnvelopedCms defaults to AES-256 encryption</span></span>](#envelopedcms-defaults-to-aes-256-encryption) | <span data-ttu-id="24c09-114">3.0</span><span class="sxs-lookup"><span data-stu-id="24c09-114">3.0</span></span> |
| [<span data-ttu-id="24c09-115">RSAOpenSsl キー生成の最小サイズの増加</span><span class="sxs-lookup"><span data-stu-id="24c09-115">Minimum size for RSAOpenSsl key generation has increased</span></span>](#minimum-size-for-rsaopenssl-key-generation-has-increased) | <span data-ttu-id="24c09-116">3.0</span><span class="sxs-lookup"><span data-stu-id="24c09-116">3.0</span></span> |
| [<span data-ttu-id="24c09-117">.NET Core 3.0 では、OpenSSL 1.0.x よりも OpenSSL 1.1.x を優先する</span><span class="sxs-lookup"><span data-stu-id="24c09-117">.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x</span></span>](#net-core-30-prefers-openssl-11x-to-openssl-10x) | <span data-ttu-id="24c09-118">3.0</span><span class="sxs-lookup"><span data-stu-id="24c09-118">3.0</span></span> |
| [<span data-ttu-id="24c09-119">CryptoStream.Dispose は書き込み時にのみ最後のブロックを変換する</span><span class="sxs-lookup"><span data-stu-id="24c09-119">CryptoStream.Dispose transforms final block only when writing</span></span>](#cryptostreamdispose-transforms-final-block-only-when-writing) | <span data-ttu-id="24c09-120">3.0</span><span class="sxs-lookup"><span data-stu-id="24c09-120">3.0</span></span> |
| [<span data-ttu-id="24c09-121">SignedCms.ComputeSignature のブール型パラメーターの尊重</span><span class="sxs-lookup"><span data-stu-id="24c09-121">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>](#boolean-parameter-of-signedcmscomputesignature-is-respected) | <span data-ttu-id="24c09-122">2.1</span><span class="sxs-lookup"><span data-stu-id="24c09-122">2.1</span></span> |

## <a name="net-50"></a><span data-ttu-id="24c09-123">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="24c09-123">.NET 5.0</span></span>

[!INCLUDE[Cryptography APIs not supported on Blazor WebAssembly](~/includes/core-changes/cryptography/5.0/cryptography-apis-not-supported-on-blazor-webassembly.md)]

***

[!INCLUDE [cryptography-oid-init-only](../../../includes/core-changes/cryptography/5.0/cryptography-oid-init-only.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="24c09-124">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="24c09-124">.NET Core 3.0</span></span>

[!INCLUDE [begin-trusted-cert-linux](~/includes/core-changes/cryptography/3.0/begin-trusted-cert-linux.md)]

***

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/3.0/envelopedcms-defaults-to-aes256.md)]

***

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/3.0/minimum-rsaopenssl-key-size-change.md)]

***

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/3.0/net-core-3-0-prefers-openssl-1-1-x.md)]

***

[!INCLUDE [CryptoStream.Dispose transforms final block only when writing](~/includes/core-changes/cryptography/3.0/cryptography-cryptostream-dispose-final-block-write.md)]

***

## <a name="net-core-21"></a><span data-ttu-id="24c09-125">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="24c09-125">.NET Core 2.1</span></span>

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

***
