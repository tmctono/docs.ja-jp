---
title: グローバリゼーションに関する破壊的変更
description: .NET Core におけるグローバリゼーションでの破壊的変更の一覧を示します。
ms.date: 04/07/2020
ms.openlocfilehash: 0c3367cb3515c6f473f53be6062b54f2e836b8c5
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702305"
---
# <a name="globalization-breaking-changes"></a><span data-ttu-id="183d5-103">グローバリゼーションに関する破壊的変更</span><span class="sxs-lookup"><span data-stu-id="183d5-103">Globalization breaking changes</span></span>

<span data-ttu-id="183d5-104">このページでは、次の破壊的変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="183d5-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="183d5-105">互換性に影響する変更点</span><span class="sxs-lookup"><span data-stu-id="183d5-105">Breaking change</span></span> | <span data-ttu-id="183d5-106">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="183d5-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="183d5-107">グローバリゼーション API では Windows 上の ICU ライブラリが使用される</span><span class="sxs-lookup"><span data-stu-id="183d5-107">Globalization APIs use ICU libraries on Windows</span></span>](#globalization-apis-use-icu-libraries-on-windows) | <span data-ttu-id="183d5-108">5.0</span><span class="sxs-lookup"><span data-stu-id="183d5-108">5.0</span></span> |
| [<span data-ttu-id="183d5-109">StringInfo と TextElementEnumerator は現在 UAX29 に準拠する</span><span class="sxs-lookup"><span data-stu-id="183d5-109">StringInfo and TextElementEnumerator are now UAX29-compliant</span></span>](#stringinfo-and-textelementenumerator-are-now-uax29-compliant) | <span data-ttu-id="183d5-110">5.0</span><span class="sxs-lookup"><span data-stu-id="183d5-110">5.0</span></span> |
| [<span data-ttu-id="183d5-111">"C" ロケールをインバリアント ロケールにマップ</span><span class="sxs-lookup"><span data-stu-id="183d5-111">"C" locale maps to the invariant locale</span></span>](#c-locale-maps-to-the-invariant-locale) | <span data-ttu-id="183d5-112">3.0</span><span class="sxs-lookup"><span data-stu-id="183d5-112">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="183d5-113">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="183d5-113">.NET 5.0</span></span>

[!INCLUDE [icu-globalization-api](../../../includes/core-changes/globalization/5.0/icu-globalization-api.md)]

***

[!INCLUDE [uax29-compliant-grapheme-enumeration](../../../includes/core-changes/globalization/5.0/uax29-compliant-grapheme-enumeration.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="183d5-114">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="183d5-114">.NET Core 3.0</span></span>

[!INCLUDE["C" locale maps to the invariant locale](~/includes/core-changes/globalization/3.0/c-locale-maps-to-invariant-locale.md)]

***
