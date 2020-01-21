---
title: .NET Core 3.1 の新機能
description: .NET Core 3.1 の新機能について説明します。
dev_langs:
- csharp
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: eba3d21cfc787c5d388de31f988b835522118151
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2020
ms.locfileid: "75936925"
---
# <a name="whats-new-in-net-core-31"></a><span data-ttu-id="02b2d-103">.NET Core 3.1 の新機能</span><span class="sxs-lookup"><span data-stu-id="02b2d-103">What's new in .NET Core 3.1</span></span>

<span data-ttu-id="02b2d-104">この記事では、.NET Core 3.1 の新機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="02b2d-104">This article describes what is new in .NET Core 3.1.</span></span> <span data-ttu-id="02b2d-105">このリリースには、小規模であるが重要な修正に重点を置いた .NET Core 3.0 のマイナー機能強化が含まれています。</span><span class="sxs-lookup"><span data-stu-id="02b2d-105">This release contains minor improvements to .NET Core 3.0, focusing on small, but important, fixes.</span></span> <span data-ttu-id="02b2d-106">.NET Core 3.1 に関する最も重要な機能は、[長期的なサポート (LTS)](#long-term-support) リリースであるということです。</span><span class="sxs-lookup"><span data-stu-id="02b2d-106">The most important feature about .NET Core 3.1 is that it's a [long-term support (LTS)](#long-term-support) release.</span></span>

<span data-ttu-id="02b2d-107">Visual Studio 2019 を使用している場合は、.NET Core 3.1 プロジェクトを操作するために [Visual Studio 2019 バージョン 16.4](https://visualstudio.microsoft.com/downloads/) に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02b2d-107">If you're using Visual Studio 2019, you must update to [Visual Studio 2019 version 16.4](https://visualstudio.microsoft.com/downloads/) to work with .NET Core 3.1 projects.</span></span> <span data-ttu-id="02b2d-108">Visual Studio 全体の新機能の詳細については、[Visual Studio のブログ](https://devblogs.microsoft.com/visualstudio/tis-the-season-visual-studio-2019/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02b2d-108">For more information on what is new in Visual Studio, see the [Visual Studio Blog](https://devblogs.microsoft.com/visualstudio/tis-the-season-visual-studio-2019/).</span></span>

<span data-ttu-id="02b2d-109">Visual Studio for Mac でも .NET Core 3.1 がサポートされており、Visual Studio for Mac 8.4 Preview チャネルに含まれています。</span><span class="sxs-lookup"><span data-stu-id="02b2d-109">Visual Studio for Mac also supports and includes .NET Core 3.1, in the Visual Studio for Mac 8.4 Preview channel.</span></span> <span data-ttu-id="02b2d-110">.NET Core 3.1 を使用するには、Preview チャネルを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02b2d-110">You'll need to opt into the Preview channel to use .NET Core 3.1.</span></span>

<span data-ttu-id="02b2d-111">リリースの詳細については、「[.NET Core 3.1 についてのお知らせ](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02b2d-111">For more information about the release, see the [.NET Core 3.1 announcement](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).</span></span>

- <span data-ttu-id="02b2d-112">Windows、macOS、または Linux 上に [.NET Core 3.1 をダウンロードして使い始めましょう](https://dotnet.microsoft.com/download/dotnet-core/3.1)。</span><span class="sxs-lookup"><span data-stu-id="02b2d-112">[Download and get started with .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1) on Windows, macOS, or Linux.</span></span>

## <a name="long-term-support"></a><span data-ttu-id="02b2d-113">長期的なサポート</span><span class="sxs-lookup"><span data-stu-id="02b2d-113">Long-term support</span></span>

<span data-ttu-id="02b2d-114">.NET Core 3.1 は、次の 3 年間にわたって Microsoft のサポートが提供される LTS リリースです。</span><span class="sxs-lookup"><span data-stu-id="02b2d-114">.NET Core 3.1 is an LTS release with support from Microsoft for the next three years.</span></span> <span data-ttu-id="02b2d-115">アプリを .NET Core 3.1 に移行することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="02b2d-115">It's highly recommended that you move your apps to .NET Core 3.1.</span></span> <span data-ttu-id="02b2d-116">他のメジャー リリースの現在のライフサイクルは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="02b2d-116">The current lifecycle of other major releases is as follows:</span></span>

| <span data-ttu-id="02b2d-117">解放</span><span class="sxs-lookup"><span data-stu-id="02b2d-117">Release</span></span> | <span data-ttu-id="02b2d-118">メモ</span><span class="sxs-lookup"><span data-stu-id="02b2d-118">Note</span></span> |
| ------- | ---- |
| <span data-ttu-id="02b2d-119">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="02b2d-119">.NET Core 3.0</span></span> | <span data-ttu-id="02b2d-120">2020 年 3 月 3 日にサポートが終了します。</span><span class="sxs-lookup"><span data-stu-id="02b2d-120">End of life on March 3, 2020.</span></span>     |
| <span data-ttu-id="02b2d-121">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="02b2d-121">.NET Core 2.2</span></span> | <span data-ttu-id="02b2d-122">2019 年 12 月 23 日にサポートが終了します。</span><span class="sxs-lookup"><span data-stu-id="02b2d-122">End of life on December 23, 2019.</span></span> |
| <span data-ttu-id="02b2d-123">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="02b2d-123">.NET Core 2.1</span></span> | <span data-ttu-id="02b2d-124">2021 年 8 月 21 日にサポートが終了します。</span><span class="sxs-lookup"><span data-stu-id="02b2d-124">End of life on August 21, 2021.</span></span>    |

<span data-ttu-id="02b2d-125">詳細については、「[.NET Core のサポート ポリシー](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="02b2d-125">For more information, see the [.NET Core support policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

## <a name="windows-forms"></a><span data-ttu-id="02b2d-126">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="02b2d-126">Windows Forms</span></span>

<span data-ttu-id="02b2d-127">*Windows のみ*</span><span class="sxs-lookup"><span data-stu-id="02b2d-127">*Windows only*</span></span>

> [!WARNING]
> <span data-ttu-id="02b2d-128">Windows フォームで破壊的変更が行われています。</span><span class="sxs-lookup"><span data-stu-id="02b2d-128">There are breaking changes in Windows Forms.</span></span>

<span data-ttu-id="02b2d-129">Windows フォームには、Visual Studio Designer Toolbox でしばらくの間利用できなくなっているレガシ コントロールが含まれていました。</span><span class="sxs-lookup"><span data-stu-id="02b2d-129">Legacy controls were included in Windows Forms that have been unavailable in the Visual Studio Designer Toolbox for some time.</span></span> <span data-ttu-id="02b2d-130">これらは、.NET Framework 2.0 の新しいコントロールに置き換えられていました。</span><span class="sxs-lookup"><span data-stu-id="02b2d-130">These were replaced with new controls back in .NET Framework 2.0.</span></span> <span data-ttu-id="02b2d-131">これらは、Desktop SDK for .NET Core 3.1. から削除されています。</span><span class="sxs-lookup"><span data-stu-id="02b2d-131">These have been removed from the Desktop SDK for .NET Core 3.1.</span></span>

| <span data-ttu-id="02b2d-132">削除されたコントロール</span><span class="sxs-lookup"><span data-stu-id="02b2d-132">Removed control</span></span> | <span data-ttu-id="02b2d-133">推奨代替</span><span class="sxs-lookup"><span data-stu-id="02b2d-133">Recommended replacement</span></span> | <span data-ttu-id="02b2d-134">削除された関連 API</span><span class="sxs-lookup"><span data-stu-id="02b2d-134">Associated APIs removed</span></span> |
| --------------- | ----------------------- | ----------------------- |
| <span data-ttu-id="02b2d-135">DataGrid</span><span class="sxs-lookup"><span data-stu-id="02b2d-135">DataGrid</span></span>        | <xref:System.Windows.Forms.DataGridView>      | <span data-ttu-id="02b2d-136">DataGridCell</span><span class="sxs-lookup"><span data-stu-id="02b2d-136">DataGridCell</span></span><br/><span data-ttu-id="02b2d-137">DataGridRow</span><span class="sxs-lookup"><span data-stu-id="02b2d-137">DataGridRow</span></span><br/><span data-ttu-id="02b2d-138">DataGridTableCollection</span><span class="sxs-lookup"><span data-stu-id="02b2d-138">DataGridTableCollection</span></span><br/><span data-ttu-id="02b2d-139">DataGridColumnCollection</span><span class="sxs-lookup"><span data-stu-id="02b2d-139">DataGridColumnCollection</span></span><br/><span data-ttu-id="02b2d-140">DataGridTableStyle</span><span class="sxs-lookup"><span data-stu-id="02b2d-140">DataGridTableStyle</span></span><br/><span data-ttu-id="02b2d-141">DataGridColumnStyle</span><span class="sxs-lookup"><span data-stu-id="02b2d-141">DataGridColumnStyle</span></span><br/><span data-ttu-id="02b2d-142">DataGridLineStyle</span><span class="sxs-lookup"><span data-stu-id="02b2d-142">DataGridLineStyle</span></span><br/><span data-ttu-id="02b2d-143">DataGridParentRowsLabel</span><span class="sxs-lookup"><span data-stu-id="02b2d-143">DataGridParentRowsLabel</span></span><br/><span data-ttu-id="02b2d-144">DataGridParentRowsLabelStyle</span><span class="sxs-lookup"><span data-stu-id="02b2d-144">DataGridParentRowsLabelStyle</span></span><br/><span data-ttu-id="02b2d-145">DataGridBoolColumn</span><span class="sxs-lookup"><span data-stu-id="02b2d-145">DataGridBoolColumn</span></span><br/><span data-ttu-id="02b2d-146">DataGridTextBox</span><span class="sxs-lookup"><span data-stu-id="02b2d-146">DataGridTextBox</span></span><br/><span data-ttu-id="02b2d-147">GridColumnStylesCollection</span><span class="sxs-lookup"><span data-stu-id="02b2d-147">GridColumnStylesCollection</span></span><br/><span data-ttu-id="02b2d-148">GridTableStylesCollection</span><span class="sxs-lookup"><span data-stu-id="02b2d-148">GridTableStylesCollection</span></span><br/><span data-ttu-id="02b2d-149">HitTestType</span><span class="sxs-lookup"><span data-stu-id="02b2d-149">HitTestType</span></span> |
| <span data-ttu-id="02b2d-150">ToolBar</span><span class="sxs-lookup"><span data-stu-id="02b2d-150">ToolBar</span></span>         | <xref:System.Windows.Forms.ToolStrip>         | <span data-ttu-id="02b2d-151">ToolBarAppearance</span><span class="sxs-lookup"><span data-stu-id="02b2d-151">ToolBarAppearance</span></span> |
| <span data-ttu-id="02b2d-152">ToolBarButton</span><span class="sxs-lookup"><span data-stu-id="02b2d-152">ToolBarButton</span></span>   | <xref:System.Windows.Forms.ToolStripButton>   | <span data-ttu-id="02b2d-153">ToolBarButtonClickEventArgs</span><span class="sxs-lookup"><span data-stu-id="02b2d-153">ToolBarButtonClickEventArgs</span></span><br/><span data-ttu-id="02b2d-154">ToolBarButtonClickEventHandler</span><span class="sxs-lookup"><span data-stu-id="02b2d-154">ToolBarButtonClickEventHandler</span></span><br/><span data-ttu-id="02b2d-155">ToolBarButtonStyle</span><span class="sxs-lookup"><span data-stu-id="02b2d-155">ToolBarButtonStyle</span></span><br/><span data-ttu-id="02b2d-156">ToolBarTextAlign</span><span class="sxs-lookup"><span data-stu-id="02b2d-156">ToolBarTextAlign</span></span> |
| <span data-ttu-id="02b2d-157">ContextMenu</span><span class="sxs-lookup"><span data-stu-id="02b2d-157">ContextMenu</span></span>     | <xref:System.Windows.Forms.ContextMenuStrip>  |  |
| :::no-loc text="Menu"::: | <xref:System.Windows.Forms.ToolStripDropDown><br/><xref:System.Windows.Forms.ToolStripDropDownMenu> | <span data-ttu-id="02b2d-158">MenuItemCollection</span><span class="sxs-lookup"><span data-stu-id="02b2d-158">MenuItemCollection</span></span> |
| <span data-ttu-id="02b2d-159">MainMenu</span><span class="sxs-lookup"><span data-stu-id="02b2d-159">MainMenu</span></span>        | <xref:System.Windows.Forms.MenuStrip>         |  |
| <span data-ttu-id="02b2d-160">MenuItem</span><span class="sxs-lookup"><span data-stu-id="02b2d-160">MenuItem</span></span>        | <xref:System.Windows.Forms.ToolStripMenuItem> |  |

<span data-ttu-id="02b2d-161">アプリケーションを .NET Core 3.1 に更新し、コントロールの置き換えを行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="02b2d-161">We recommend you update your applications to .NET Core 3.1 and move to the replacement controls.</span></span> <span data-ttu-id="02b2d-162">コントロールの置き換えは、基本的には型の "検索と置換" という単純なプロセスです。</span><span class="sxs-lookup"><span data-stu-id="02b2d-162">Replacing the controls is a straightforward process, essentially "find and replace" on the type.</span></span>

## <a name="ccli"></a><span data-ttu-id="02b2d-163">C++/CLI</span><span class="sxs-lookup"><span data-stu-id="02b2d-163">C++/CLI</span></span>

<span data-ttu-id="02b2d-164">*Windows のみ*</span><span class="sxs-lookup"><span data-stu-id="02b2d-164">*Windows only*</span></span>

<span data-ttu-id="02b2d-165">C++/CLI (別名 "マネージド C++") プロジェクトを作成するためのサポートが追加されています。</span><span class="sxs-lookup"><span data-stu-id="02b2d-165">Support has been added for creating C++/CLI (also known as "managed C++") projects.</span></span> <span data-ttu-id="02b2d-166">これらのプロジェクトから生成されるバイナリは、.NET Core 3.0 以降のバージョンと互換性があります。</span><span class="sxs-lookup"><span data-stu-id="02b2d-166">Binaries produced from these projects are compatible with .NET Core 3.0 and later versions.</span></span>

<span data-ttu-id="02b2d-167">Visual Studio 2019 16.4 に C++/CLI のサポートを追加するには、[C++ ワークロードを使用するデスクトップ開発](https://docs.microsoft.com/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="02b2d-167">To add support for C++/CLI in Visual Studio 2019 16.4, install the [Desktop development with C++ workload](https://docs.microsoft.com/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads).</span></span> <span data-ttu-id="02b2d-168">このワークロードによって、次の 2 つのテンプレートが Visual Studio に追加されます。</span><span class="sxs-lookup"><span data-stu-id="02b2d-168">This workload adds two templates to Visual Studio:</span></span>

- <span data-ttu-id="02b2d-169">CLR クラス ライブラリ (.NET Core)</span><span class="sxs-lookup"><span data-stu-id="02b2d-169">CLR Class Library (.NET Core)</span></span>
- <span data-ttu-id="02b2d-170">CLR 空のプロジェクト (.NET Framework)</span><span class="sxs-lookup"><span data-stu-id="02b2d-170">CLR Empty Project (.NET Core)</span></span>

## <a name="next-steps"></a><span data-ttu-id="02b2d-171">次の手順</span><span class="sxs-lookup"><span data-stu-id="02b2d-171">Next steps</span></span>

- [<span data-ttu-id="02b2d-172">.NET Core 3.0 と 3.1 の間の破壊的変更を確認する</span><span class="sxs-lookup"><span data-stu-id="02b2d-172">Review the breaking changes between .NET Core 3.0 and 3.1.</span></span>](../compatibility/3.0-3.1.md)
- [<span data-ttu-id="02b2d-173">Windows フォーム アプリの .NET Core 3.1 における破壊的変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="02b2d-173">Review the breaking changes between in .NET Core 3.1 for Windows Forms apps.</span></span>](../compatibility/winforms.md#net-core-31)
