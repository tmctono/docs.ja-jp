---
title: WPF 破壊的変更
description: .NET Core および .NET 5 の Windows Presentation Framework における破壊的変更の一覧を示します。
ms.date: 09/08/2020
ms.openlocfilehash: 3bd5cb585509118fbc3ca9ca08c6ed15b4853b93
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679306"
---
# <a name="breaking-changes-in-windows-presentation-framework-wpf"></a><span data-ttu-id="91f14-103">Windows Presentation Foundation (WPF) の破壊的変更</span><span class="sxs-lookup"><span data-stu-id="91f14-103">Breaking changes in Windows Presentation Framework (WPF)</span></span>

<span data-ttu-id="91f14-104">WPF のサポートは、.NET Core にバージョン 3.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="91f14-104">WPF support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="91f14-105">この記事では、WPF の破壊的変更を、導入された .NET のバージョン別に説明します。</span><span class="sxs-lookup"><span data-stu-id="91f14-105">This article lists breaking changes for WPF by the .NET version in which they were introduced.</span></span> <span data-ttu-id="91f14-106">この記事は、.NET Framework または以前のバージョンの .NET Core (3.0 以降) から WPF アプリをアップグレードするユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="91f14-106">If you're upgrading a WPF app from .NET Framework or from a previous version of .NET Core (3.0 or later), this article applies to you.</span></span>

<span data-ttu-id="91f14-107">このページでは、次の破壊的変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="91f14-107">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="91f14-108">互換性に影響する変更点</span><span class="sxs-lookup"><span data-stu-id="91f14-108">Breaking change</span></span> | <span data-ttu-id="91f14-109">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="91f14-109">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="91f14-110">WPF アプリと WinForms アプリで OutputType が WinExe に設定されている</span><span class="sxs-lookup"><span data-stu-id="91f14-110">OutputType set to WinExe for WPF and WinForms apps</span></span>](#outputtype-set-to-winexe-for-wpf-and-winforms-apps) | <span data-ttu-id="91f14-111">5.0</span><span class="sxs-lookup"><span data-stu-id="91f14-111">5.0</span></span> |
| [<span data-ttu-id="91f14-112">WinForms と WPF アプリで Microsoft.NET.Sdk が使用される</span><span class="sxs-lookup"><span data-stu-id="91f14-112">WinForms and WPF apps use Microsoft.NET.Sdk</span></span>](#winforms-and-wpf-apps-use-microsoftnetsdk) | <span data-ttu-id="91f14-113">5.0</span><span class="sxs-lookup"><span data-stu-id="91f14-113">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="91f14-114">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="91f14-114">.NET 5.0</span></span>

[!INCLUDE [automatically-infer-winexe-output-type](../../../includes/core-changes/windowsforms/5.0/automatically-infer-winexe-output-type.md)]

***

[!INCLUDE [sdk-and-target-framework-change](../../../includes/core-changes/windowsforms/5.0/sdk-and-target-framework-change.md)]

***
