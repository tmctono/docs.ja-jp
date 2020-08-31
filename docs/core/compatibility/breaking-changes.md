---
title: 互換性に影響する変更
description: .NET Core の各バージョンの破壊的変更について説明します。
ms.date: 11/27/2019
ms.openlocfilehash: 73c1576aa92f0e236ead0ca1a12ac26efcbf3cbe
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88810899"
---
# <a name="breaking-change-selectors"></a><span data-ttu-id="00ab7-103">破壊的変更のセレクター</span><span class="sxs-lookup"><span data-stu-id="00ab7-103">Breaking change selectors</span></span>

<span data-ttu-id="00ab7-104">次のバージョンと領域のセレクターでは、.NET Core、ASP.NET Core、EF Core の異なるバージョン間で適用可能な破壊的変更がフィルターして一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="00ab7-104">The following version and area selectors provide a filtered list of applicable breaking changes between different versions of .NET Core, ASP.NET Core, and EF Core.</span></span> <span data-ttu-id="00ab7-105">目次でバージョン別やテクノロジ領域別の記事も参照できます。</span><span class="sxs-lookup"><span data-stu-id="00ab7-105">You can also browse version-to-version or technology area articles in the table of contents.</span></span>

## <a name="by-version"></a><span data-ttu-id="00ab7-106">バージョン別</span><span class="sxs-lookup"><span data-stu-id="00ab7-106">By version</span></span>

<span data-ttu-id="00ab7-107">現在ターゲットにしている .NET のバージョンを選択してから、移行先の .NET Core のバージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="00ab7-107">Select the .NET version that you're currently targeting and then the .NET Core version you wish to migrate to:</span></span>

> [!div class="op_multi_selector" title1="ターゲット バージョンから" title2="移行されたバージョンへ"]
>
> - [(3.1 | 5.0)](3.1-5.0.md)
> - [(3.0 | 3.1)](3.0-3.1.md)
> - [(2.2 | 3.1)](2.2-3.1.md)
> - [(2.2 | 3.0)](2.2-3.0.md)
> - [(2.0 | 2.1)](2.0-2.1.md)
> - [(.NET Framework | .NET Core)](fx-core.md)

## <a name="by-technology-area"></a><span data-ttu-id="00ab7-116">テクノロジ領域別</span><span class="sxs-lookup"><span data-stu-id="00ab7-116">By technology area</span></span>

<span data-ttu-id="00ab7-117">関心のある .NET Core テクノロジ領域を選択してください。</span><span class="sxs-lookup"><span data-stu-id="00ab7-117">Select the .NET Core technology area that you're interested in.</span></span> <span data-ttu-id="00ab7-118">個々の変更は .NET Core のバージョン順になっています。</span><span class="sxs-lookup"><span data-stu-id="00ab7-118">Individual changes are ordered by .NET Core version.</span></span>

> [!div class="op_single_selector"]
>
> - [ASP.NET Core](aspnetcore.md)
> - [コード分析](code-analysis.md)
> - [Core .NET ライブラリ](corefx.md)
> - [暗号](cryptography.md)
> - [EF Core](/ef/core/what-is-new/ef-core-3.0/breaking-changes)
> - [グローバリゼーション](globalization.md)
> - [Interop](interop.md)
> - [ネットワーク](networking.md)
> - [シリアル化](serialization.md)
> - [Visual Basic](visualbasic.md)
> - [Windows フォーム](winforms.md)

## <a name="github-issues-and-announcements"></a><span data-ttu-id="00ab7-130">GitHub のイシューとお知らせ</span><span class="sxs-lookup"><span data-stu-id="00ab7-130">GitHub issues and announcements</span></span>

<span data-ttu-id="00ab7-131">また、次の GitHub リポジトリでは、.NET Core で導入された破壊的変更について詳しく説明している個々の問題を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="00ab7-131">You can also view individual issues that detail the breaking changes introduced in .NET Core in the following GitHub repositories:</span></span>

- <span data-ttu-id="00ab7-132">.NET Core の場合は、[dotnet/ docs](https://github.com/dotnet/docs/issues?q=is%3Aissue+label%3Abreaking-change) リポジトリ。</span><span class="sxs-lookup"><span data-stu-id="00ab7-132">For .NET Core, the [dotnet/docs](https://github.com/dotnet/docs/issues?q=is%3Aissue+label%3Abreaking-change) repository.</span></span>
- <span data-ttu-id="00ab7-133">ASP.NET Core の場合は、[aspnet/Announcements](https://github.com/aspnet/Announcements/issues?q=is%3Aissue+is%3Aopen+label%3A%22Breaking+change%22+label%3A3.0.0) リポジトリ。</span><span class="sxs-lookup"><span data-stu-id="00ab7-133">For ASP.NET Core, the [aspnet/Announcements](https://github.com/aspnet/Announcements/issues?q=is%3Aissue+is%3Aopen+label%3A%22Breaking+change%22+label%3A3.0.0) repository.</span></span>
- <span data-ttu-id="00ab7-134">Entity Framework Core の場合は、[dotnet/efcore](https://github.com/dotnet/efcore/issues?q=is%3Aopen+is%3Aissue+label%3Abreaking-change) リポジトリ。</span><span class="sxs-lookup"><span data-stu-id="00ab7-134">For Entity Framework Core, the [dotnet/efcore](https://github.com/dotnet/efcore/issues?q=is%3Aopen+is%3Aissue+label%3Abreaking-change) repository.</span></span>

## <a name="see-also"></a><span data-ttu-id="00ab7-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="00ab7-135">See also</span></span>

- [<span data-ttu-id="00ab7-136">.NET Framework から .NET Core に移行する</span><span class="sxs-lookup"><span data-stu-id="00ab7-136">Migrate from .NET Framework to .NET Core</span></span>](../porting/index.md)
