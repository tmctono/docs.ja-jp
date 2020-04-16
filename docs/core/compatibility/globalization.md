---
title: グローバリゼーションに関する破壊的変更
description: .NET Core におけるグローバリゼーションでの破壊的変更の一覧を示します。
ms.date: 04/07/2020
ms.openlocfilehash: 1436f9e2ec540b0f8b1e710b25c2115646d4e5b4
ms.sourcegitcommit: 2b3b2d684259463ddfc76ad680e5e09fdc1984d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2020
ms.locfileid: "80888171"
---
# <a name="globalization-breaking-changes"></a><span data-ttu-id="dc2d1-103">グローバリゼーションに関する破壊的変更</span><span class="sxs-lookup"><span data-stu-id="dc2d1-103">Globalization breaking changes</span></span>

<span data-ttu-id="dc2d1-104">このページでは、次の破壊的変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="dc2d1-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="dc2d1-105">互換性に影響する変更点</span><span class="sxs-lookup"><span data-stu-id="dc2d1-105">Breaking change</span></span> | <span data-ttu-id="dc2d1-106">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="dc2d1-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="dc2d1-107">StringInfo と TextElementEnumerator は現在 UAX29 に準拠する</span><span class="sxs-lookup"><span data-stu-id="dc2d1-107">StringInfo and TextElementEnumerator are now UAX29-compliant</span></span>](#stringinfo-and-textelementenumerator-are-now-uax29-compliant) | <span data-ttu-id="dc2d1-108">5.0</span><span class="sxs-lookup"><span data-stu-id="dc2d1-108">5.0</span></span> |
| [<span data-ttu-id="dc2d1-109">"C" ロケールをインバリアント ロケールにマップ</span><span class="sxs-lookup"><span data-stu-id="dc2d1-109">"C" locale maps to the invariant locale</span></span>](#c-locale-maps-to-the-invariant-locale) | <span data-ttu-id="dc2d1-110">3.0</span><span class="sxs-lookup"><span data-stu-id="dc2d1-110">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="dc2d1-111">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="dc2d1-111">.NET 5.0</span></span>

[!INCLUDE [uax29-compliant-grapheme-enumeration](../../../includes/core-changes/globalization/5.0/uax29-compliant-grapheme-enumeration.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="dc2d1-112">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="dc2d1-112">.NET Core 3.0</span></span>

[!INCLUDE["C" locale maps to the invariant locale](~/includes/core-changes/globalization/3.0/c-locale-maps-to-invariant-locale.md)]

***
