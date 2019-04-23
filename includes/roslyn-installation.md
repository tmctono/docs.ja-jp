---
ms.openlocfilehash: 72acd0029d0189de1c724856572957f111b9d18f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804435"
---
## <a name="installation-instructions"></a><span data-ttu-id="2aedb-101">インストール手順</span><span class="sxs-lookup"><span data-stu-id="2aedb-101">Installation instructions</span></span> 

<span data-ttu-id="2aedb-102">**Visual Studio インストーラー**で **.NET Compiler Platform SDK** を見つけるには、以下の 2 つの異なる方法があります。</span><span class="sxs-lookup"><span data-stu-id="2aedb-102">There are two different ways to find the **.NET Compiler Platform SDK** in the **Visual Studio Installer**:</span></span>

### <a name="install-using-the-workloads-view"></a><span data-ttu-id="2aedb-103">ワークロード ビューを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="2aedb-103">Install using the Workloads view</span></span>

<span data-ttu-id="2aedb-104">.NET Compiler Platform SDK は、Visual Studio 拡張機能の開発ワークロードの一部として自動的に選択されません。</span><span class="sxs-lookup"><span data-stu-id="2aedb-104">The .NET Compiler Platform SDK is not automatically selected as part of the Visual Studio extension development workload.</span></span> <span data-ttu-id="2aedb-105">省略可能なコンポーネントとして選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2aedb-105">You must select it as an optional component.</span></span>

1. <span data-ttu-id="2aedb-106">**Visual Studio インストーラー**を実行します。</span><span class="sxs-lookup"><span data-stu-id="2aedb-106">Run **Visual Studio Installer**</span></span> 
1. <span data-ttu-id="2aedb-107">**[変更]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2aedb-107">Select **Modify**</span></span> 
1. <span data-ttu-id="2aedb-108">**Visual Studio 拡張機能の開発**ワークロードを確認します。</span><span class="sxs-lookup"><span data-stu-id="2aedb-108">Check the **Visual Studio extension development** workload.</span></span>
1. <span data-ttu-id="2aedb-109">概要ツリーの **[Visual Studio 拡張機能の開発]** ノードを開きます。</span><span class="sxs-lookup"><span data-stu-id="2aedb-109">Open the **Visual Studio extension development** node in the summary tree.</span></span>
1. <span data-ttu-id="2aedb-110">**[.NET Compiler Platform SDK]** のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="2aedb-110">Check the box for **.NET Compiler Platform SDK**.</span></span> <span data-ttu-id="2aedb-111">省略可能なコンポーネントの最後に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2aedb-111">You'll find it last under the optional components.</span></span>

<span data-ttu-id="2aedb-112">また、必要に応じて、**DGML エディター**のビジュアライザーでグラフを表示します。</span><span class="sxs-lookup"><span data-stu-id="2aedb-112">Optionally, you'll also want the **DGML editor** to display graphs in the visualizer:</span></span>

1. <span data-ttu-id="2aedb-113">概要ツリーの **[個別のコンポーネント]** ノードを開きます。</span><span class="sxs-lookup"><span data-stu-id="2aedb-113">Open the **Individual components** node in the summary tree.</span></span>
1. <span data-ttu-id="2aedb-114">**[DGML エディター]** のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="2aedb-114">Check the box for **DGML editor**</span></span>

### <a name="install-using-the-individual-components-tab"></a><span data-ttu-id="2aedb-115">[個別のコンポーネント] タブを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="2aedb-115">Install using the Individual components tab</span></span>

1. <span data-ttu-id="2aedb-116">**Visual Studio インストーラー**を実行します。</span><span class="sxs-lookup"><span data-stu-id="2aedb-116">Run **Visual Studio Installer**</span></span> 
1. <span data-ttu-id="2aedb-117">**[変更]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2aedb-117">Select **Modify**</span></span> 
1. <span data-ttu-id="2aedb-118">**[個別のコンポーネント]** タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="2aedb-118">Select the **Individual components** tab</span></span> 
1. <span data-ttu-id="2aedb-119">**[.NET Compiler Platform SDK]** のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="2aedb-119">Check the box for **.NET Compiler Platform SDK**.</span></span> <span data-ttu-id="2aedb-120">**[コンパイラ、ビルド ツール、およびランタイム]** セクションの上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2aedb-120">You'll find it at the top under the **Compilers, build tools, and runtimes** section.</span></span>

<span data-ttu-id="2aedb-121">また、必要に応じて、**DGML エディター**のビジュアライザーでグラフを表示します。</span><span class="sxs-lookup"><span data-stu-id="2aedb-121">Optionally, you'll also want the **DGML editor** to display graphs in the visualizer:</span></span>

1. <span data-ttu-id="2aedb-122">**[DGML エディター]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="2aedb-122">Check the box for **DGML editor**.</span></span> <span data-ttu-id="2aedb-123">**[コード ツール]** セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2aedb-123">You'll find it under the **Code tools** section.</span></span>
