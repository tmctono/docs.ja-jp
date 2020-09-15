---
title: 互換性に影響する変更
description: .NET Core の各バージョンの破壊的変更について説明します。
ms.date: 11/27/2019
ms.openlocfilehash: eea6542acb9fa659af764bfd3a2af00fd9740191
ms.sourcegitcommit: 1e8382d0ce8b5515864f8fbb178b9fd692a7503f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "89656276"
---
# <a name="breaking-change-selectors"></a><span data-ttu-id="47f07-103">破壊的変更のセレクター</span><span class="sxs-lookup"><span data-stu-id="47f07-103">Breaking change selectors</span></span>

<span data-ttu-id="47f07-104">次のバージョンと領域のセレクターでは、.NET Core、ASP.NET Core、EF Core の異なるバージョン間で適用可能な破壊的変更がフィルターして一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="47f07-104">The following version and area selectors provide a filtered list of applicable breaking changes between different versions of .NET Core, ASP.NET Core, and EF Core.</span></span> <span data-ttu-id="47f07-105">目次でバージョン別やテクノロジ領域別の記事も参照できます。</span><span class="sxs-lookup"><span data-stu-id="47f07-105">You can also browse version-to-version or technology area articles in the table of contents.</span></span>

## <a name="by-version"></a><span data-ttu-id="47f07-106">バージョン別</span><span class="sxs-lookup"><span data-stu-id="47f07-106">By version</span></span>

<span data-ttu-id="47f07-107">現在ターゲットにしている .NET のバージョンを選択してから、移行先の .NET Core のバージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="47f07-107">Select the .NET version that you're currently targeting and then the .NET Core version you wish to migrate to:</span></span>

> [!div class="op_multi_selector" title1="ターゲット バージョンから" title2="移行されたバージョンへ"]
>
> - [(3.1 | 5.0)](3.1-5.0.md)
> - [(3.0 | 3.1)](3.0-3.1.md)
> - [(2.2 | 3.1)](2.2-3.1.md)
> - [(2.2 | 3.0)](2.2-3.0.md)
> - [(2.0 | 2.1)](2.0-2.1.md)
> - [(.NET Framework | .NET Core)](fx-core.md)

## <a name="by-technology-area"></a><span data-ttu-id="47f07-116">テクノロジ領域別</span><span class="sxs-lookup"><span data-stu-id="47f07-116">By technology area</span></span>

<span data-ttu-id="47f07-117">関心のある .NET Core テクノロジ領域を選択してください。</span><span class="sxs-lookup"><span data-stu-id="47f07-117">Select the .NET Core technology area that you're interested in.</span></span> <span data-ttu-id="47f07-118">個々の変更は .NET Core のバージョン順になっています。</span><span class="sxs-lookup"><span data-stu-id="47f07-118">Individual changes are ordered by .NET Core version.</span></span>

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
> - [WPF](wpf.md)

## <a name="github-issues-and-announcements"></a><span data-ttu-id="47f07-131">GitHub のイシューとお知らせ</span><span class="sxs-lookup"><span data-stu-id="47f07-131">GitHub issues and announcements</span></span>

<span data-ttu-id="47f07-132">また、次の GitHub リポジトリでは、.NET Core で導入された破壊的変更について詳しく説明している個々の問題を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="47f07-132">You can also view individual issues that detail the breaking changes introduced in .NET Core in the following GitHub repositories:</span></span>

- <span data-ttu-id="47f07-133">.NET Core の場合は、[dotnet/ docs](https://github.com/dotnet/docs/issues?q=is%3Aissue+label%3Abreaking-change) リポジトリ。</span><span class="sxs-lookup"><span data-stu-id="47f07-133">For .NET Core, the [dotnet/docs](https://github.com/dotnet/docs/issues?q=is%3Aissue+label%3Abreaking-change) repository.</span></span>
- <span data-ttu-id="47f07-134">ASP.NET Core の場合は、[aspnet/Announcements](https://github.com/aspnet/Announcements/issues?q=is%3Aissue+is%3Aopen+label%3A%22Breaking+change%22+label%3A3.0.0) リポジトリ。</span><span class="sxs-lookup"><span data-stu-id="47f07-134">For ASP.NET Core, the [aspnet/Announcements](https://github.com/aspnet/Announcements/issues?q=is%3Aissue+is%3Aopen+label%3A%22Breaking+change%22+label%3A3.0.0) repository.</span></span>
- <span data-ttu-id="47f07-135">Entity Framework Core の場合は、[dotnet/efcore](https://github.com/dotnet/efcore/issues?q=is%3Aopen+is%3Aissue+label%3Abreaking-change) リポジトリ。</span><span class="sxs-lookup"><span data-stu-id="47f07-135">For Entity Framework Core, the [dotnet/efcore](https://github.com/dotnet/efcore/issues?q=is%3Aopen+is%3Aissue+label%3Abreaking-change) repository.</span></span>

## <a name="see-also"></a><span data-ttu-id="47f07-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="47f07-136">See also</span></span>

- [<span data-ttu-id="47f07-137">.NET Framework から .NET Core に移行する</span><span class="sxs-lookup"><span data-stu-id="47f07-137">Migrate from .NET Framework to .NET Core</span></span>](../porting/index.md)
