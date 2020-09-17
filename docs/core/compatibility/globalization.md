---
title: グローバリゼーションに関する破壊的変更
description: .NET Core におけるグローバリゼーションでの破壊的変更の一覧を示します。
ms.date: 04/07/2020
ms.openlocfilehash: 93990d89204df1b2d7498e1d748378fae05598c3
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065067"
---
# <a name="globalization-breaking-changes"></a><span data-ttu-id="7e7a4-103">グローバリゼーションに関する破壊的変更</span><span class="sxs-lookup"><span data-stu-id="7e7a4-103">Globalization breaking changes</span></span>

<span data-ttu-id="7e7a4-104">このページでは、次の破壊的変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="7e7a4-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="7e7a4-105">互換性に影響する変更点</span><span class="sxs-lookup"><span data-stu-id="7e7a4-105">Breaking change</span></span> | <span data-ttu-id="7e7a4-106">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="7e7a4-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="7e7a4-107">一部の Latin-1 文字に対して変更された Unicode カテゴリ</span><span class="sxs-lookup"><span data-stu-id="7e7a4-107">Unicode category changed for some Latin-1 characters</span></span>](#unicode-category-changed-for-some-latin-1-characters) | <span data-ttu-id="7e7a4-108">5.0</span><span class="sxs-lookup"><span data-stu-id="7e7a4-108">5.0</span></span> |
| [<span data-ttu-id="7e7a4-109">グローバリゼーション API では Windows 上の ICU ライブラリが使用される</span><span class="sxs-lookup"><span data-stu-id="7e7a4-109">Globalization APIs use ICU libraries on Windows</span></span>](#globalization-apis-use-icu-libraries-on-windows) | <span data-ttu-id="7e7a4-110">5.0</span><span class="sxs-lookup"><span data-stu-id="7e7a4-110">5.0</span></span> |
| [<span data-ttu-id="7e7a4-111">StringInfo と TextElementEnumerator は現在 UAX29 に準拠する</span><span class="sxs-lookup"><span data-stu-id="7e7a4-111">StringInfo and TextElementEnumerator are now UAX29-compliant</span></span>](#stringinfo-and-textelementenumerator-are-now-uax29-compliant) | <span data-ttu-id="7e7a4-112">5.0</span><span class="sxs-lookup"><span data-stu-id="7e7a4-112">5.0</span></span> |
| [<span data-ttu-id="7e7a4-113">"C" ロケールをインバリアント ロケールにマップ</span><span class="sxs-lookup"><span data-stu-id="7e7a4-113">"C" locale maps to the invariant locale</span></span>](#c-locale-maps-to-the-invariant-locale) | <span data-ttu-id="7e7a4-114">3.0</span><span class="sxs-lookup"><span data-stu-id="7e7a4-114">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="7e7a4-115">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="7e7a4-115">.NET 5.0</span></span>

[!INCLUDE [unicode-categories-for-latin1-chars](../../../includes/core-changes/globalization/5.0/unicode-categories-for-latin1-chars.md)]

***

[!INCLUDE [icu-globalization-api](../../../includes/core-changes/globalization/5.0/icu-globalization-api.md)]

***

[!INCLUDE [uax29-compliant-grapheme-enumeration](../../../includes/core-changes/globalization/5.0/uax29-compliant-grapheme-enumeration.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="7e7a4-116">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="7e7a4-116">.NET Core 3.0</span></span>

[!INCLUDE["C" locale maps to the invariant locale](~/includes/core-changes/globalization/3.0/c-locale-maps-to-invariant-locale.md)]

***
