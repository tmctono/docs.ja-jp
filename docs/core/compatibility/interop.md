---
title: 相互運用性の破壊的変更
description: .NET Core と .NET 5.0 以降の相互運用性における破壊的変更を一覧で示します。
ms.date: 06/23/2020
ms.openlocfilehash: a38fb1837e565be33f8ae1119480c8f1ae848ab0
ms.sourcegitcommit: b4a46f6d7ebf44c0035627d00924164bcae2db30
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91438044"
---
# <a name="interop-breaking-changes"></a><span data-ttu-id="edd9b-103">相互運用性の破壊的変更</span><span class="sxs-lookup"><span data-stu-id="edd9b-103">Interop breaking changes</span></span>

<span data-ttu-id="edd9b-104">このページでは、次の破壊的変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="edd9b-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="edd9b-105">互換性に影響する変更点</span><span class="sxs-lookup"><span data-stu-id="edd9b-105">Breaking change</span></span> | <span data-ttu-id="edd9b-106">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="edd9b-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="edd9b-107">RCW を `InterfaceIsIInspectable` インターフェイスにキャストすると、PlatformNotSupportedException がスローされます</span><span class="sxs-lookup"><span data-stu-id="edd9b-107">Casting RCW to an `InterfaceIsIInspectable` interface throws PlatformNotSupportedException</span></span>](#casting-rcw-to-an-interfaceisiinspectable-interface-throws-platformnotsupportedexception) | <span data-ttu-id="edd9b-108">5.0</span><span class="sxs-lookup"><span data-stu-id="edd9b-108">5.0</span></span> |
| [<span data-ttu-id="edd9b-109">Windows 以外のプラットフォームでは A/W サフィックスのプローブは行われません</span><span class="sxs-lookup"><span data-stu-id="edd9b-109">No A/W suffix probing on non-Windows platforms</span></span>](#no-aw-suffix-probing-on-non-windows-platforms) | <span data-ttu-id="edd9b-110">5.0</span><span class="sxs-lookup"><span data-stu-id="edd9b-110">5.0</span></span> |
| [<span data-ttu-id="edd9b-111">WinRT の組み込みサポートは .NET から削除されています</span><span class="sxs-lookup"><span data-stu-id="edd9b-111">Built-in support for WinRT is removed from .NET</span></span>](#built-in-support-for-winrt-is-removed-from-net) | <span data-ttu-id="edd9b-112">5.0</span><span class="sxs-lookup"><span data-stu-id="edd9b-112">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="edd9b-113">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="edd9b-113">.NET 5.0</span></span>

[!INCLUDE [casting-rcw-to-inspectable-interface-throws-exception](../../../includes/core-changes/interop/5.0/casting-rcw-to-inspectable-interface-throws-exception.md)]

***

[!INCLUDE [function-suffix-pinvoke](../../../includes/core-changes/interop/5.0/function-suffix-pinvoke.md)]

***

[!INCLUDE [built-in-support-for-winrt-removed](~/includes/core-changes/interop/5.0/built-in-support-for-winrt-removed.md)]

***
