---
ms.openlocfilehash: 2872c5909b382e01fdd231019a12970caa3b77d2
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72526758"
---
## <a name="installation-instructions---visual-studio-installer"></a><span data-ttu-id="6c8d1-101">インストール手順 - Visual Studio インストーラー</span><span class="sxs-lookup"><span data-stu-id="6c8d1-101">Installation instructions - Visual Studio Installer</span></span>

<span data-ttu-id="6c8d1-102">**Visual Studio インストーラー**で **.NET Compiler Platform SDK** を見つけるには、以下の 2 つの異なる方法があります。</span><span class="sxs-lookup"><span data-stu-id="6c8d1-102">There are two different ways to find the **.NET Compiler Platform SDK** in the **Visual Studio Installer**:</span></span>

### <a name="install-using-the-visual-studio-installer---workloads-view"></a><span data-ttu-id="6c8d1-103">Visual Studio インストーラーを使用したインストール - ワークロード ビュー</span><span class="sxs-lookup"><span data-stu-id="6c8d1-103">Install using the Visual Studio Installer - Workloads view</span></span>

<span data-ttu-id="6c8d1-104">.NET Compiler Platform SDK は、Visual Studio 拡張機能の開発ワークロードの一部として自動的に選択されません。</span><span class="sxs-lookup"><span data-stu-id="6c8d1-104">The .NET Compiler Platform SDK is not automatically selected as part of the Visual Studio extension development workload.</span></span> <span data-ttu-id="6c8d1-105">省略可能なコンポーネントとして選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c8d1-105">You must select it as an optional component.</span></span>

1. <span data-ttu-id="6c8d1-106">**Visual Studio インストーラー**を実行します。</span><span class="sxs-lookup"><span data-stu-id="6c8d1-106">Run **Visual Studio Installer**</span></span>
1. <span data-ttu-id="6c8d1-107">**[変更]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6c8d1-107">Select **Modify**</span></span>
1. <span data-ttu-id="6c8d1-108">**Visual Studio 拡張機能の開発**ワークロードを確認します。</span><span class="sxs-lookup"><span data-stu-id="6c8d1-108">Check the **Visual Studio extension development** workload.</span></span>
1. <span data-ttu-id="6c8d1-109">概要ツリーの **[Visual Studio 拡張機能の開発]** ノードを開きます。</span><span class="sxs-lookup"><span data-stu-id="6c8d1-109">Open the **Visual Studio extension development** node in the summary tree.</span></span>
1. <span data-ttu-id="6c8d1-110">**[.NET Compiler Platform SDK]** のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6c8d1-110">Check the box for **.NET Compiler Platform SDK**.</span></span> <span data-ttu-id="6c8d1-111">省略可能なコンポーネントの最後に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c8d1-111">You'll find it last under the optional components.</span></span>

<span data-ttu-id="6c8d1-112">また、必要に応じて、**DGML エディター**のビジュアライザーでグラフを表示します。</span><span class="sxs-lookup"><span data-stu-id="6c8d1-112">Optionally, you'll also want the **DGML editor** to display graphs in the visualizer:</span></span>

1. <span data-ttu-id="6c8d1-113">概要ツリーの **[個別のコンポーネント]** ノードを開きます。</span><span class="sxs-lookup"><span data-stu-id="6c8d1-113">Open the **Individual components** node in the summary tree.</span></span>
1. <span data-ttu-id="6c8d1-114">**[DGML エディター]** のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6c8d1-114">Check the box for **DGML editor**</span></span>

### <a name="install-using-the-visual-studio-installer---individual-components-tab"></a><span data-ttu-id="6c8d1-115">Visual Studio インストーラーを使用したインストール - [個別のコンポーネント] タブ</span><span class="sxs-lookup"><span data-stu-id="6c8d1-115">Install using the Visual Studio Installer - Individual components tab</span></span>

1. <span data-ttu-id="6c8d1-116">**Visual Studio インストーラー**を実行します。</span><span class="sxs-lookup"><span data-stu-id="6c8d1-116">Run **Visual Studio Installer**</span></span>
1. <span data-ttu-id="6c8d1-117">**[変更]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6c8d1-117">Select **Modify**</span></span>
1. <span data-ttu-id="6c8d1-118">**[個別のコンポーネント]** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="6c8d1-118">Select the **Individual components** tab</span></span>
1. <span data-ttu-id="6c8d1-119">**[.NET Compiler Platform SDK]** のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6c8d1-119">Check the box for **.NET Compiler Platform SDK**.</span></span> <span data-ttu-id="6c8d1-120">**[コンパイラ、ビルド ツール、およびランタイム]** セクションの上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c8d1-120">You'll find it at the top under the **Compilers, build tools, and runtimes** section.</span></span>

<span data-ttu-id="6c8d1-121">また、必要に応じて、**DGML エディター**のビジュアライザーでグラフを表示します。</span><span class="sxs-lookup"><span data-stu-id="6c8d1-121">Optionally, you'll also want the **DGML editor** to display graphs in the visualizer:</span></span>

1. <span data-ttu-id="6c8d1-122">**[DGML エディター]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6c8d1-122">Check the box for **DGML editor**.</span></span> <span data-ttu-id="6c8d1-123">**[コード ツール]** セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c8d1-123">You'll find it under the **Code tools** section.</span></span>
