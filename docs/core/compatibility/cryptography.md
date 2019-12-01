---
title: 暗号に関する破壊的変更 - .NET Core
description: .NET Core での暗号に関連する破壊的変更の一覧を示します。
ms.date: 09/20/2019
ms.openlocfilehash: 1bd0a79d84885d475609c1f758797690e595a36d
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2019
ms.locfileid: "74567968"
---
# <a name="cryptography-breaking-changes"></a><span data-ttu-id="17882-103">暗号での破壊的変更</span><span class="sxs-lookup"><span data-stu-id="17882-103">Cryptography breaking changes</span></span>

<span data-ttu-id="17882-104">.NET Core のバージョンごとに暗号に関する破壊的変更の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="17882-104">The following is a list of cryptography-related breaking changes by .NET Core version.</span></span>

## <a name="net-core-30"></a><span data-ttu-id="17882-105">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="17882-105">.NET Core 3.0</span></span>

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/3.0/envelopedcms-defaults-to-aes256.md)]

***

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/3.0/minimum-rsaopenssl-key-size-change.md)]

***

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/3.0/net-core-3-0-prefers-openssl-1-1-x.md)]

## <a name="net-core-30-preview-9"></a><span data-ttu-id="17882-106">.NET Core 3.0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="17882-106">.NET Core 3.0 Preview 9</span></span>

[!INCLUDE[Better argument validation in the Pkcs8PrivateKeyInfo constructor](~/includes/core-changes/cryptography/3.0/better-argument-validation-in-pkcs8privatekeyinfo-ctor.md)]
