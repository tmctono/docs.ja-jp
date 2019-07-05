---
title: モデル ビルダーのインストール方法
description: ML.NET モデル ビルダー ツールのインストール方法について説明します
author: luisquintanilla
ms.author: luquinta
ms.date: 06/21/2019
ms.custom: mvc, how-to
ms.openlocfilehash: 54ab595c56f816517180aab48022c7df207fe84d
ms.sourcegitcommit: 52e588dc2ee74d484cd07ac60076be25cbf777ab
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2019
ms.locfileid: "67410570"
---
# <a name="how-to-install-mlnet-model-builder"></a><span data-ttu-id="875cf-103">ML.NET モデル ビルダーのインストール方法</span><span class="sxs-lookup"><span data-stu-id="875cf-103">How to install ML.NET Model Builder</span></span>

<span data-ttu-id="875cf-104">ML.NET モデル ビルダーをインストールして .NET アプリケーションに機械学習を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="875cf-104">Learn how to install ML.NET Model Builder to add machine learning to your .NET applications.</span></span>

> [!NOTE]
> <span data-ttu-id="875cf-105">モデル ビルダーは現在のところ、プレビュー段階です。</span><span class="sxs-lookup"><span data-stu-id="875cf-105">Model Builder is currently in Preview.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="875cf-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="875cf-106">Pre-requisites</span></span>

- <span data-ttu-id="875cf-107">Visual Studio 2017 15.9.12 以降 / Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="875cf-107">Visual Studio 2017 15.9.12 or later / Visual Studio 2019</span></span>
- <span data-ttu-id="875cf-108">.NET Core 2.1 以降の SDK</span><span class="sxs-lookup"><span data-stu-id="875cf-108">.NET Core 2.1 or later SDK</span></span>

## <a name="limitations"></a><span data-ttu-id="875cf-109">制限事項</span><span class="sxs-lookup"><span data-stu-id="875cf-109">Limitations</span></span>

- <span data-ttu-id="875cf-110">ML.NET モデル ビルダー拡張機能は現在のところ、Windows 上の Visual Studio でのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="875cf-110">ML.NET Model Builder Extension currently only works on Visual Studio on Windows.</span></span>
- <span data-ttu-id="875cf-111">トレーニング データセットの制限は 1 GB までの制限があります</span><span class="sxs-lookup"><span data-stu-id="875cf-111">Training dataset limit of 1GB</span></span>
- <span data-ttu-id="875cf-112">SQL Server のトレーニング用の行は 10 万行までの制限があります。</span><span class="sxs-lookup"><span data-stu-id="875cf-112">SQL Server has a limit of 100 thousand rows for training</span></span>
- <span data-ttu-id="875cf-113">Visual Studio 2017 用の Microsoft SQL Server Data Tools はサポートされていません</span><span class="sxs-lookup"><span data-stu-id="875cf-113">Microsoft SQL Server Data Tools for Visual Studio 2017 is not supported</span></span>

## <a name="install"></a><span data-ttu-id="875cf-114">インストール</span><span class="sxs-lookup"><span data-stu-id="875cf-114">Install</span></span>

<span data-ttu-id="875cf-115">ML.NET モデル ビルダーは、Visual Studio Marketplace または Visual Studio からインストールできます。</span><span class="sxs-lookup"><span data-stu-id="875cf-115">ML.NET Model builder can be installed either through the Visual Studio Marketplace or from within Visual Studio.</span></span> 

### <a name="visual-studio-marketplace"></a><span data-ttu-id="875cf-116">Visual Studio Marketplace</span><span class="sxs-lookup"><span data-stu-id="875cf-116">Visual Studio Marketplace</span></span>

1. <span data-ttu-id="875cf-117">[Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07) からダウンロード</span><span class="sxs-lookup"><span data-stu-id="875cf-117">Download from [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07)</span></span>
1. <span data-ttu-id="875cf-118">指示に従って該当する Visual Studio バージョンにインストールします</span><span class="sxs-lookup"><span data-stu-id="875cf-118">Follow prompts to install onto respective Visual Studio version</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="875cf-119">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="875cf-119">Visual Studio 2017</span></span>

1. <span data-ttu-id="875cf-120">メニュー バーで、 **[ツール]**  >  **[拡張機能と更新プログラム]** の順に選択します</span><span class="sxs-lookup"><span data-stu-id="875cf-120">In the menu bar, select **Tools** > **Extensions and Updates**</span></span>
1. <span data-ttu-id="875cf-121">*[拡張機能と更新プログラム]* プロンプト内で、 *[オンライン]* ノードを選択します</span><span class="sxs-lookup"><span data-stu-id="875cf-121">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="875cf-122">検索バーで「*ML.NET モデル ビルダー*」を検索し、結果から「ML.NET モデル ビルダー (Preview)」を選択します</span><span class="sxs-lookup"><span data-stu-id="875cf-122">In the search bar, search for *ML.NET Model Builder* and from the results, select ML.NET Model Builder (Preview)</span></span>
1. <span data-ttu-id="875cf-123">プロンプトの指示に従って、インストールを行います</span><span class="sxs-lookup"><span data-stu-id="875cf-123">Follow the prompts to complete the installation</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="875cf-124">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="875cf-124">Visual Studio 2019</span></span>

1. <span data-ttu-id="875cf-125">メニュー バーで **[拡張機能]**  >  **[拡張機能の管理]** の順に選択します</span><span class="sxs-lookup"><span data-stu-id="875cf-125">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>
1. <span data-ttu-id="875cf-126">*[拡張機能と更新プログラム]* プロンプト内で、 *[オンライン]* ノードを選択します</span><span class="sxs-lookup"><span data-stu-id="875cf-126">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="875cf-127">検索バーに「*ML.NET モデル ビルダー*」と入力し、「ML.NET モデル ビルダー (Preview)」を選択します</span><span class="sxs-lookup"><span data-stu-id="875cf-127">Type *ML.NET Model Builder* into the search bar select ML.NET Model Builder (Preview)</span></span>
1. <span data-ttu-id="875cf-128">プロンプトの指示に従って、インストールを行います</span><span class="sxs-lookup"><span data-stu-id="875cf-128">Follow the prompts to complete the installation</span></span>

## <a name="uninstall"></a><span data-ttu-id="875cf-129">[アンインストール]</span><span class="sxs-lookup"><span data-stu-id="875cf-129">Uninstall</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="875cf-130">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="875cf-130">Visual Studio 2017</span></span>

1. <span data-ttu-id="875cf-131">メニュー バーで、 **[ツール]**  >  **[拡張機能と更新プログラム]** の順に選択します</span><span class="sxs-lookup"><span data-stu-id="875cf-131">On the menu bar, select **Tools** > **Extensions and Updates**</span></span>
1. <span data-ttu-id="875cf-132">*[拡張機能と更新プログラム]* プロンプト内で、 *[インストール済み]* ノードを展開し、 *[ツール]* を選択します</span><span class="sxs-lookup"><span data-stu-id="875cf-132">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="875cf-133">ツールの一覧から「ML.NET モデル ビルダー (Preview)」を選択し、 *[アンインストール]* を選択します</span><span class="sxs-lookup"><span data-stu-id="875cf-133">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>
1. <span data-ttu-id="875cf-134">プロンプトの指示に従って、アンインストールを行います</span><span class="sxs-lookup"><span data-stu-id="875cf-134">Follow the prompts to complete the uninstallation.</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="875cf-135">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="875cf-135">Visual Studio 2019</span></span>

1. <span data-ttu-id="875cf-136">メニュー バーで **[拡張機能]**  >  **[拡張機能の管理]** の順に選択します</span><span class="sxs-lookup"><span data-stu-id="875cf-136">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>
1. <span data-ttu-id="875cf-137">*[拡張機能と更新プログラム]* プロンプト内で、 *[インストール済み]* ノードを展開し、 *[ツール]* を選択します</span><span class="sxs-lookup"><span data-stu-id="875cf-137">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="875cf-138">ツールの一覧から「ML.NET モデル ビルダー (Preview)」を選択し、 *[アンインストール]* を選択します</span><span class="sxs-lookup"><span data-stu-id="875cf-138">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>
1. <span data-ttu-id="875cf-139">プロンプトの指示に従って、アンインストールを行います</span><span class="sxs-lookup"><span data-stu-id="875cf-139">Follow the prompts to complete the uninstallation.</span></span>

## <a name="upgrade"></a><span data-ttu-id="875cf-140">Upgrade</span><span class="sxs-lookup"><span data-stu-id="875cf-140">Upgrade</span></span>

<span data-ttu-id="875cf-141">アップグレード プロセスは、インストール プロセスに似ています。</span><span class="sxs-lookup"><span data-stu-id="875cf-141">The upgrade process is similar to the installation process.</span></span> <span data-ttu-id="875cf-142">Visual Studio Marketplace から最新バージョンをダウンロードするか、または Visual Studio で拡張機能マネージャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="875cf-142">Either download the latest version from Visual Studio Marketplace or use the Extensions Manager in Visual Studio.</span></span>
