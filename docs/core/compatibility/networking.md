---
title: ネットワークに関する破壊的変更
description: .NET Core のネットワークに関する破壊的変更の一覧を示します。
ms.date: 05/05/2020
ms.openlocfilehash: 568d26bde43ccd6e19fbe2d947f576ef5f99450a
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608484"
---
# <a name="networking-breaking-changes"></a><span data-ttu-id="2df26-103">ネットワークに関する破壊的変更</span><span class="sxs-lookup"><span data-stu-id="2df26-103">Networking breaking changes</span></span>

<span data-ttu-id="2df26-104">このページでは、次の破壊的変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="2df26-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="2df26-105">互換性に影響する変更点</span><span class="sxs-lookup"><span data-stu-id="2df26-105">Breaking change</span></span> | <span data-ttu-id="2df26-106">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="2df26-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="2df26-107">.NET ランタイムからの WinHttpHandler の削除</span><span class="sxs-lookup"><span data-stu-id="2df26-107">WinHttpHandler removed from .NET runtime</span></span>](#winhttphandler-removed-from-net-runtime) | <span data-ttu-id="2df26-108">5.0</span><span class="sxs-lookup"><span data-stu-id="2df26-108">5.0</span></span> |
| [<span data-ttu-id="2df26-109">MulticastOption.Group で null 値を受け付けない</span><span class="sxs-lookup"><span data-stu-id="2df26-109">MulticastOption.Group doesn't accept a null value</span></span>](#multicastoptiongroup-doesnt-accept-a-null-value) | <span data-ttu-id="2df26-110">5.0</span><span class="sxs-lookup"><span data-stu-id="2df26-110">5.0</span></span> |
| [<span data-ttu-id="2df26-111">HttpRequestMessage.Version の既定値が 1.1 に変更された</span><span class="sxs-lookup"><span data-stu-id="2df26-111">Default value of HttpRequestMessage.Version changed to 1.1</span></span>](#default-value-of-httprequestmessageversion-changed-to-11) | <span data-ttu-id="2df26-112">3.0</span><span class="sxs-lookup"><span data-stu-id="2df26-112">3.0</span></span> |
| [<span data-ttu-id="2df26-113">WebClient.CancelAsync がすぐにキャンセルされない場合がある</span><span class="sxs-lookup"><span data-stu-id="2df26-113">WebClient.CancelAsync doesn't always cancel immediately</span></span>](#webclientcancelasync-doesnt-always-cancel-immediately) | <span data-ttu-id="2df26-114">2.0</span><span class="sxs-lookup"><span data-stu-id="2df26-114">2.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="2df26-115">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="2df26-115">.NET 5.0</span></span>

[!INCLUDE [winhttphandler-removed-from-runtime](../../../includes/core-changes/networking/5.0/winhttphandler-removed-from-runtime.md)]

***

[!INCLUDE [multicastoption-group-doesnt-accept-null](../../../includes/core-changes/networking/5.0/multicastoption-group-doesnt-accept-null.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="2df26-116">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="2df26-116">.NET Core 3.0</span></span>

[!INCLUDE[Default value of HttpRequestMessage.Version changed to 1.1](~/includes/core-changes/networking/3.0/httprequestmessage-version-change.md)]

***

## <a name="net-core-20"></a><span data-ttu-id="2df26-117">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="2df26-117">.NET Core 2.0</span></span>

[!INCLUDE [behavior-change-webclient-cancelasync](../../../includes/core-changes/networking/2.0/behavior-change-webclient-cancelasync.md)]

***
