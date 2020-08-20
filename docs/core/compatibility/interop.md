---
title: 相互運用性の破壊的変更
description: .NET Core と .NET 5.0 以降の相互運用性における破壊的変更を一覧で示します。
ms.date: 06/23/2020
ms.openlocfilehash: bac60631f8515eaf102f9d6e75fe817baceb7824
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062426"
---
# <a name="interop-breaking-changes"></a><span data-ttu-id="cf076-103">相互運用性の破壊的変更</span><span class="sxs-lookup"><span data-stu-id="cf076-103">Interop breaking changes</span></span>

<span data-ttu-id="cf076-104">このページでは、次の破壊的変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="cf076-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="cf076-105">互換性に影響する変更点</span><span class="sxs-lookup"><span data-stu-id="cf076-105">Breaking change</span></span> | <span data-ttu-id="cf076-106">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="cf076-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="cf076-107">Windows 以外のプラットフォームでは A/W サフィックスのプローブは行われません</span><span class="sxs-lookup"><span data-stu-id="cf076-107">No A/W suffix probing on non-Windows platforms</span></span>](#no-aw-suffix-probing-on-non-windows-platforms) | <span data-ttu-id="cf076-108">5.0</span><span class="sxs-lookup"><span data-stu-id="cf076-108">5.0</span></span> |
| [<span data-ttu-id="cf076-109">WinRT の組み込みサポートは .NET から削除されています</span><span class="sxs-lookup"><span data-stu-id="cf076-109">Built-in support for WinRT is removed from .NET</span></span>](#built-in-support-for-winrt-is-removed-from-net) | <span data-ttu-id="cf076-110">5.0</span><span class="sxs-lookup"><span data-stu-id="cf076-110">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="cf076-111">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="cf076-111">.NET 5.0</span></span>

[!INCLUDE [function-suffix-pinvoke](../../../includes/core-changes/interop/5.0/function-suffix-pinvoke.md)]

***

[!INCLUDE [built-in-support-for-winrt-removed](~/includes/core-changes/interop/5.0/built-in-support-for-winrt-removed.md)]

***
