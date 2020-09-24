---
title: MSBuild に関する破壊的変更
description: MSBuild for .NET Core における破壊的変更の一覧を示します。
ms.date: 02/10/2020
ms.openlocfilehash: 7493516dff68b8bd45740c9877ebf21886e667ff
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679328"
---
# <a name="msbuild-breaking-changes"></a><span data-ttu-id="99ec1-103">MSBuild に関する破壊的変更</span><span class="sxs-lookup"><span data-stu-id="99ec1-103">MSBuild breaking changes</span></span>

<span data-ttu-id="99ec1-104">このページでは、次の破壊的変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="99ec1-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="99ec1-105">互換性に影響する変更点</span><span class="sxs-lookup"><span data-stu-id="99ec1-105">Breaking change</span></span> | <span data-ttu-id="99ec1-106">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="99ec1-106">Version introduced</span></span> |
| - | - |
| [<span data-ttu-id="99ec1-107">PublishDepsFilePath の動作の変更</span><span class="sxs-lookup"><span data-stu-id="99ec1-107">PublishDepsFilePath behavior change</span></span>](#publishdepsfilepath-behavior-change) | <span data-ttu-id="99ec1-108">5.0</span><span class="sxs-lookup"><span data-stu-id="99ec1-108">5.0</span></span> |
| [<span data-ttu-id="99ec1-109">Directory.Packages.props ファイルが既定でインポートされる</span><span class="sxs-lookup"><span data-stu-id="99ec1-109">Directory.Packages.props files is imported by default</span></span>](#directorypackagesprops-files-is-imported-by-default) | <span data-ttu-id="99ec1-110">5.0</span><span class="sxs-lookup"><span data-stu-id="99ec1-110">5.0</span></span> |
| [<span data-ttu-id="99ec1-111">リソース マニフェストのファイル名の変更</span><span class="sxs-lookup"><span data-stu-id="99ec1-111">Resource manifest file name change</span></span>](#resource-manifest-file-name-change) | <span data-ttu-id="99ec1-112">3.0</span><span class="sxs-lookup"><span data-stu-id="99ec1-112">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="99ec1-113">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="99ec1-113">.NET 5.0</span></span>

[!INCLUDE [publishdepsfilepath-behavior-change](../../../includes/core-changes/msbuild/5.0/publishdepsfilepath-behavior-change.md)]

***

[!INCLUDE [directory-packages-props-imported-by-default](../../../includes/core-changes/msbuild/5.0/directory-packages-props-imported-by-default.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="99ec1-114">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="99ec1-114">.NET Core 3.0</span></span>

[!INCLUDE[Resource file names](~/includes/core-changes/msbuild/3.0/resource-manifest-name.md)]

***
