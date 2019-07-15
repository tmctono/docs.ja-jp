---
ms.openlocfilehash: dab6b435a885d862d08f94dd31de79625f19bcc0
ms.sourcegitcommit: 6472349821dbe202d01182bc2cfe9d7176eaaa6c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2019
ms.locfileid: "67870504"
---
## <a name="installation-instructions---visual-studio-installer"></a><span data-ttu-id="ccced-101">インストール手順 - Visual Studio インストーラー</span><span class="sxs-lookup"><span data-stu-id="ccced-101">Installation instructions - Visual Studio Installer</span></span>

<span data-ttu-id="ccced-102">**Visual Studio インストーラー**で **.NET Compiler Platform SDK** を見つけるには、以下の 2 つの異なる方法があります。</span><span class="sxs-lookup"><span data-stu-id="ccced-102">There are two different ways to find the **.NET Compiler Platform SDK** in the **Visual Studio Installer**:</span></span>

### <a name="install-using-the-visual-studio-installer---workloads-view"></a><span data-ttu-id="ccced-103">Visual Studio インストーラーを使用したインストール - ワークロード ビュー</span><span class="sxs-lookup"><span data-stu-id="ccced-103">Install using the Visual Studio Installer - Workloads view</span></span>

<span data-ttu-id="ccced-104">.NET Compiler Platform SDK は、Visual Studio 拡張機能の開発ワークロードの一部として自動的に選択されません。</span><span class="sxs-lookup"><span data-stu-id="ccced-104">The .NET Compiler Platform SDK is not automatically selected as part of the Visual Studio extension development workload.</span></span> <span data-ttu-id="ccced-105">省略可能なコンポーネントとして選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccced-105">You must select it as an optional component.</span></span>

1. <span data-ttu-id="ccced-106">**Visual Studio インストーラー**を実行します。</span><span class="sxs-lookup"><span data-stu-id="ccced-106">Run **Visual Studio Installer**</span></span> 
1. <span data-ttu-id="ccced-107">**[変更]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ccced-107">Select **Modify**</span></span> 
1. <span data-ttu-id="ccced-108">**Visual Studio 拡張機能の開発**ワークロードを確認します。</span><span class="sxs-lookup"><span data-stu-id="ccced-108">Check the **Visual Studio extension development** workload.</span></span>
1. <span data-ttu-id="ccced-109">概要ツリーの **[Visual Studio 拡張機能の開発]** ノードを開きます。</span><span class="sxs-lookup"><span data-stu-id="ccced-109">Open the **Visual Studio extension development** node in the summary tree.</span></span>
1. <span data-ttu-id="ccced-110">**[.NET Compiler Platform SDK]** のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="ccced-110">Check the box for **.NET Compiler Platform SDK**.</span></span> <span data-ttu-id="ccced-111">省略可能なコンポーネントの最後に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ccced-111">You'll find it last under the optional components.</span></span>

<span data-ttu-id="ccced-112">また、必要に応じて、**DGML エディター**のビジュアライザーでグラフを表示します。</span><span class="sxs-lookup"><span data-stu-id="ccced-112">Optionally, you'll also want the **DGML editor** to display graphs in the visualizer:</span></span>

1. <span data-ttu-id="ccced-113">概要ツリーの **[個別のコンポーネント]** ノードを開きます。</span><span class="sxs-lookup"><span data-stu-id="ccced-113">Open the **Individual components** node in the summary tree.</span></span>
1. <span data-ttu-id="ccced-114">**[DGML エディター]** のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="ccced-114">Check the box for **DGML editor**</span></span>

### <a name="install-using-the-visual-studio-installer---individual-components-tab"></a><span data-ttu-id="ccced-115">Visual Studio インストーラーを使用したインストール - [個別のコンポーネント] タブ</span><span class="sxs-lookup"><span data-stu-id="ccced-115">Install using the Visual Studio Installer - Individual components tab</span></span>

1. <span data-ttu-id="ccced-116">**Visual Studio インストーラー**を実行します。</span><span class="sxs-lookup"><span data-stu-id="ccced-116">Run **Visual Studio Installer**</span></span> 
1. <span data-ttu-id="ccced-117">**[変更]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ccced-117">Select **Modify**</span></span> 
1. <span data-ttu-id="ccced-118">**[個別のコンポーネント]** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="ccced-118">Select the **Individual components** tab</span></span> 
1. <span data-ttu-id="ccced-119">**[.NET Compiler Platform SDK]** のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="ccced-119">Check the box for **.NET Compiler Platform SDK**.</span></span> <span data-ttu-id="ccced-120">**[コンパイラ、ビルド ツール、およびランタイム]** セクションの上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ccced-120">You'll find it at the top under the **Compilers, build tools, and runtimes** section.</span></span>

<span data-ttu-id="ccced-121">また、必要に応じて、**DGML エディター**のビジュアライザーでグラフを表示します。</span><span class="sxs-lookup"><span data-stu-id="ccced-121">Optionally, you'll also want the **DGML editor** to display graphs in the visualizer:</span></span>

1. <span data-ttu-id="ccced-122">**[DGML エディター]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="ccced-122">Check the box for **DGML editor**.</span></span> <span data-ttu-id="ccced-123">**[コード ツール]** セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ccced-123">You'll find it under the **Code tools** section.</span></span>
