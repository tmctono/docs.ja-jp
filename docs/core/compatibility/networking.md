---
title: ネットワークに関する破壊的変更
description: .NET Core のネットワークに関する破壊的変更の一覧を示します。
ms.date: 05/05/2020
ms.openlocfilehash: 07e0b2e062ce244cd6312bbe08bcc63db4c74347
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859629"
---
# <a name="networking-breaking-changes"></a><span data-ttu-id="82a82-103">ネットワークに関する破壊的変更</span><span class="sxs-lookup"><span data-stu-id="82a82-103">Networking breaking changes</span></span>

<span data-ttu-id="82a82-104">このページでは、次の破壊的変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="82a82-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="82a82-105">互換性に影響する変更点</span><span class="sxs-lookup"><span data-stu-id="82a82-105">Breaking change</span></span> | <span data-ttu-id="82a82-106">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="82a82-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="82a82-107">HttpRequestMessage.Version の既定値が 1.1 に変更された</span><span class="sxs-lookup"><span data-stu-id="82a82-107">Default value of HttpRequestMessage.Version changed to 1.1</span></span>](#default-value-of-httprequestmessageversion-changed-to-11) | <span data-ttu-id="82a82-108">3.0</span><span class="sxs-lookup"><span data-stu-id="82a82-108">3.0</span></span> |
| [<span data-ttu-id="82a82-109">WebClient.CancelAsync がすぐにキャンセルされない場合がある</span><span class="sxs-lookup"><span data-stu-id="82a82-109">WebClient.CancelAsync doesn't always cancel immediately</span></span>](#webclientcancelasync-doesnt-always-cancel-immediately) | <span data-ttu-id="82a82-110">2.0</span><span class="sxs-lookup"><span data-stu-id="82a82-110">2.0</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="82a82-111">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="82a82-111">.NET Core 3.0</span></span>

[!INCLUDE[Default value of HttpRequestMessage.Version changed to 1.1](~/includes/core-changes/networking/3.0/httprequestmessage-version-change.md)]

***

## <a name="net-core-20"></a><span data-ttu-id="82a82-112">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="82a82-112">.NET Core 2.0</span></span>

[!INCLUDE [behavior-change-webclient-cancelasync](../../../includes/core-changes/networking/2.0/behavior-change-webclient-cancelasync.md)]

***
