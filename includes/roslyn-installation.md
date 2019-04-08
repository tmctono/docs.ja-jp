---
ms.openlocfilehash: 72acd0029d0189de1c724856572957f111b9d18f
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760392"
---
## <a name="installation-instructions"></a><span data-ttu-id="64269-101">インストール手順</span><span class="sxs-lookup"><span data-stu-id="64269-101">Installation instructions</span></span> 

<span data-ttu-id="64269-102">**Visual Studio インストーラー**で **.NET Compiler Platform SDK** を見つけるには、以下の 2 つの異なる方法があります。</span><span class="sxs-lookup"><span data-stu-id="64269-102">There are two different ways to find the **.NET Compiler Platform SDK** in the **Visual Studio Installer**:</span></span>

### <a name="install-using-the-workloads-view"></a><span data-ttu-id="64269-103">ワークロード ビューを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="64269-103">Install using the Workloads view</span></span>

<span data-ttu-id="64269-104">.NET Compiler Platform SDK は、Visual Studio 拡張機能の開発ワークロードの一部として自動的に選択されません。</span><span class="sxs-lookup"><span data-stu-id="64269-104">The .NET Compiler Platform SDK is not automatically selected as part of the Visual Studio extension development workload.</span></span> <span data-ttu-id="64269-105">省略可能なコンポーネントとして選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64269-105">You must select it as an optional component.</span></span>

1. <span data-ttu-id="64269-106">**Visual Studio インストーラー**を実行します。</span><span class="sxs-lookup"><span data-stu-id="64269-106">Run **Visual Studio Installer**</span></span> 
1. <span data-ttu-id="64269-107">**[変更]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="64269-107">Select **Modify**</span></span> 
1. <span data-ttu-id="64269-108">**Visual Studio 拡張機能の開発**ワークロードを確認します。</span><span class="sxs-lookup"><span data-stu-id="64269-108">Check the **Visual Studio extension development** workload.</span></span>
1. <span data-ttu-id="64269-109">概要ツリーの **[Visual Studio 拡張機能の開発]** ノードを開きます。</span><span class="sxs-lookup"><span data-stu-id="64269-109">Open the **Visual Studio extension development** node in the summary tree.</span></span>
1. <span data-ttu-id="64269-110">**[.NET Compiler Platform SDK]** のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="64269-110">Check the box for **.NET Compiler Platform SDK**.</span></span> <span data-ttu-id="64269-111">省略可能なコンポーネントの最後に表示されます。</span><span class="sxs-lookup"><span data-stu-id="64269-111">You'll find it last under the optional components.</span></span>

<span data-ttu-id="64269-112">また、必要に応じて、**DGML エディター**のビジュアライザーでグラフを表示します。</span><span class="sxs-lookup"><span data-stu-id="64269-112">Optionally, you'll also want the **DGML editor** to display graphs in the visualizer:</span></span>

1. <span data-ttu-id="64269-113">概要ツリーの **[個別のコンポーネント]** ノードを開きます。</span><span class="sxs-lookup"><span data-stu-id="64269-113">Open the **Individual components** node in the summary tree.</span></span>
1. <span data-ttu-id="64269-114">**[DGML エディター]** のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="64269-114">Check the box for **DGML editor**</span></span>

### <a name="install-using-the-individual-components-tab"></a><span data-ttu-id="64269-115">[個別のコンポーネント] タブを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="64269-115">Install using the Individual components tab</span></span>

1. <span data-ttu-id="64269-116">**Visual Studio インストーラー**を実行します。</span><span class="sxs-lookup"><span data-stu-id="64269-116">Run **Visual Studio Installer**</span></span> 
1. <span data-ttu-id="64269-117">**[変更]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="64269-117">Select **Modify**</span></span> 
1. <span data-ttu-id="64269-118">**[個別のコンポーネント]** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="64269-118">Select the **Individual components** tab</span></span> 
1. <span data-ttu-id="64269-119">**[.NET Compiler Platform SDK]** のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="64269-119">Check the box for **.NET Compiler Platform SDK**.</span></span> <span data-ttu-id="64269-120">**[コンパイラ、ビルド ツール、およびランタイム]** セクションの上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="64269-120">You'll find it at the top under the **Compilers, build tools, and runtimes** section.</span></span>

<span data-ttu-id="64269-121">また、必要に応じて、**DGML エディター**のビジュアライザーでグラフを表示します。</span><span class="sxs-lookup"><span data-stu-id="64269-121">Optionally, you'll also want the **DGML editor** to display graphs in the visualizer:</span></span>

1. <span data-ttu-id="64269-122">**[DGML エディター]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="64269-122">Check the box for **DGML editor**.</span></span> <span data-ttu-id="64269-123">**[コード ツール]** セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="64269-123">You'll find it under the **Code tools** section.</span></span>
