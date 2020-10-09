---
title: MSBuild に関する破壊的変更
description: MSBuild for .NET Core における破壊的変更の一覧を示します。
ms.date: 02/10/2020
ms.openlocfilehash: b57c70d21e061c59f26b11a025d4d05ce3b8ca99
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654739"
---
# <a name="msbuild-breaking-changes"></a><span data-ttu-id="7352a-103">MSBuild に関する破壊的変更</span><span class="sxs-lookup"><span data-stu-id="7352a-103">MSBuild breaking changes</span></span>

<span data-ttu-id="7352a-104">このページでは、次の破壊的変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="7352a-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="7352a-105">互換性に影響する変更点</span><span class="sxs-lookup"><span data-stu-id="7352a-105">Breaking change</span></span> | <span data-ttu-id="7352a-106">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="7352a-106">Version introduced</span></span> |
| - | - |
| [<span data-ttu-id="7352a-107">.NET 5 を対象とする場合に NETCOREAPP3_1 プリプロセッサ シンボルが定義されない</span><span class="sxs-lookup"><span data-stu-id="7352a-107">NETCOREAPP3_1 preprocessor symbol is not defined when targeting .NET 5</span></span>](#netcoreapp3_1-preprocessor-symbol-is-not-defined-when-targeting-net-5) | <span data-ttu-id="7352a-108">5.0</span><span class="sxs-lookup"><span data-stu-id="7352a-108">5.0</span></span> |
| [<span data-ttu-id="7352a-109">PublishDepsFilePath の動作の変更</span><span class="sxs-lookup"><span data-stu-id="7352a-109">PublishDepsFilePath behavior change</span></span>](#publishdepsfilepath-behavior-change) | <span data-ttu-id="7352a-110">5.0</span><span class="sxs-lookup"><span data-stu-id="7352a-110">5.0</span></span> |
| [<span data-ttu-id="7352a-111">Directory.Packages.props ファイルが既定でインポートされる</span><span class="sxs-lookup"><span data-stu-id="7352a-111">Directory.Packages.props files is imported by default</span></span>](#directorypackagesprops-files-is-imported-by-default) | <span data-ttu-id="7352a-112">5.0</span><span class="sxs-lookup"><span data-stu-id="7352a-112">5.0</span></span> |
| [<span data-ttu-id="7352a-113">リソース マニフェストのファイル名の変更</span><span class="sxs-lookup"><span data-stu-id="7352a-113">Resource manifest file name change</span></span>](#resource-manifest-file-name-change) | <span data-ttu-id="7352a-114">3.0</span><span class="sxs-lookup"><span data-stu-id="7352a-114">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="7352a-115">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="7352a-115">.NET 5.0</span></span>

[!INCLUDE [netcoreapp3_1-preprocessor-symbol-not-defined](../../../includes/core-changes/msbuild/5.0/netcoreapp3_1-preprocessor-symbol-not-defined.md)]

***

[!INCLUDE [publishdepsfilepath-behavior-change](../../../includes/core-changes/msbuild/5.0/publishdepsfilepath-behavior-change.md)]

***

[!INCLUDE [directory-packages-props-imported-by-default](../../../includes/core-changes/msbuild/5.0/directory-packages-props-imported-by-default.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="7352a-116">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="7352a-116">.NET Core 3.0</span></span>

[!INCLUDE[Resource file names](~/includes/core-changes/msbuild/3.0/resource-manifest-name.md)]

***
