---
title: Docker アプリの開発環境
description: Docker 開発のライフ サイクルをサポートする最も重要な開発ツールのオプションの確認を取得します。
ms.date: 02/15/2019
ms.openlocfilehash: 0f71ffa5e6870f45908e4def6577120a17ec744c
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641414"
---
# <a name="development-environment-for-docker-apps"></a><span data-ttu-id="0b246-103">Docker アプリの開発環境</span><span class="sxs-lookup"><span data-stu-id="0b246-103">Development environment for Docker apps</span></span>

## <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="0b246-104">開発ツールの選択:IDE またはエディター</span><span class="sxs-lookup"><span data-stu-id="0b246-104">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="0b246-105">いたとしてもする場合、完全で強力な IDE または軽量でアジャイルなエディターでは、マイクロソフトは、Docker アプリケーションの開発なったときに対応しています。</span><span class="sxs-lookup"><span data-stu-id="0b246-105">No matter if you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when it comes to developing Docker applications.</span></span>

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a><span data-ttu-id="0b246-106">Visual Studio Code と Docker CLI (Mac、Linux、および Windows 用のクロス プラットフォーム ツール)</span><span class="sxs-lookup"><span data-stu-id="0b246-106">Visual Studio Code and Docker CLI (cross-platform tools for Mac, Linux, and Windows)</span></span>

<span data-ttu-id="0b246-107">軽量でクロスプラット フォーム対応のエディターが任意の開発言語をサポートしている場合は、Visual Studio Code と Docker CLI を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="0b246-107">If you prefer a lightweight, cross-platform editor supporting any development language, you can use Visual Studio Code and Docker CLI.</span></span> <span data-ttu-id="0b246-108">これらの製品では、開発者のワークフローを合理化するための重要なは、簡単かつ堅牢のエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="0b246-108">These products provide a simple yet robust experience, which is critical for streamlining the developer workflow.</span></span> <span data-ttu-id="0b246-109">"Docker for Mac"または"Docker for Windows"(開発環境) をインストールすると、Docker 開発者は、Windows または Linux (ランタイム環境) の両方のアプリを構築するのに 1 つの Docker CLI を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0b246-109">By installing "Docker for Mac" or "Docker for Windows" (development environment), Docker developers can use a single Docker CLI to build apps for both Windows or Linux (runtime environment).</span></span> <span data-ttu-id="0b246-110">さらに、Visual Studio Code エディターから Docker コマンドを実行するには、Dockerfile とショートカット タスク用の IntelliSense での Docker の拡張機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0b246-110">Plus, Visual Studio Code supports extensions for Docker with IntelliSense for Dockerfiles and shortcut-tasks to run Docker commands from the editor.</span></span>

> [!NOTE]
>
> <span data-ttu-id="0b246-111">Visual Studio Code をダウンロードするには<https://code.visualstudio.com/download>します。</span><span class="sxs-lookup"><span data-stu-id="0b246-111">To download Visual Studio Code, go to <https://code.visualstudio.com/download>.</span></span>
>
> <span data-ttu-id="0b246-112">Mac および Windows 用 Docker をダウンロードするには<https://www.docker.com/products/docker>します。</span><span class="sxs-lookup"><span data-stu-id="0b246-112">To download Docker for Mac and Windows, go to <https://www.docker.com/products/docker>.</span></span>

### <a name="visual-studio-with-docker-tools-windows-development-machine"></a><span data-ttu-id="0b246-113">Visual Studio と Docker Tools (Windows 開発用コンピューター)</span><span class="sxs-lookup"><span data-stu-id="0b246-113">Visual Studio with Docker Tools (Windows development machine)</span></span>

<span data-ttu-id="0b246-114">Visual Studio 2017 (またはそれ以降) を使用することをお勧めします。 有効になっている組み込みの Docker ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="0b246-114">We recommend you use Visual Studio 2017 (or later) with the built-in Docker Tools enabled.</span></span> <span data-ttu-id="0b246-115">Visual Studio を使用して開発、実行、および選択した Docker 環境で直接アプリケーションを検証することができます。</span><span class="sxs-lookup"><span data-stu-id="0b246-115">With Visual Studio, you can develop, run, and validate your applications directly in the chosen Docker environment.</span></span> <span data-ttu-id="0b246-116">F5 キーを押して、Docker ホストで直接アプリケーション (1 つのコンテナーまたは複数のコンテナー) をデバッグまたはを編集して、コンテナーを再構築しなくても、アプリを更新するには、Ctrl + F5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="0b246-116">Press F5 to debug your application (single container or multiple containers) directly in a Docker host, or press Ctrl+F5 to edit and refresh your app without having to rebuild the container.</span></span> <span data-ttu-id="0b246-117">Linux または Windows の Docker コンテナーを作成するための Windows 開発者向けの最も簡単で最も強力な選択肢となります。</span><span class="sxs-lookup"><span data-stu-id="0b246-117">It's the simplest and most powerful choice for Windows developers to create Docker containers for Linux or Windows.</span></span>

### <a name="visual-studio-for-mac-mac-development-machine"></a><span data-ttu-id="0b246-118">Visual Studio for Mac (Mac 開発用コンピューター)</span><span class="sxs-lookup"><span data-stu-id="0b246-118">Visual Studio for Mac (Mac development machine)</span></span>

<span data-ttu-id="0b246-119">使用することができます[Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) Docker ベースのアプリケーションを開発するときにします。</span><span class="sxs-lookup"><span data-stu-id="0b246-119">You can use [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) when developing Docker-based applications.</span></span> <span data-ttu-id="0b246-120">Visual Studio for Mac は、Visual Studio Code for mac と比較した場合の高度な IDE を提供しています</span><span class="sxs-lookup"><span data-stu-id="0b246-120">Visual Studio for Mac offers a richer IDE when compared to Visual Studio Code for Mac.</span></span>

## <a name="language-and-framework-choices"></a><span data-ttu-id="0b246-121">言語とフレームワークの選択</span><span class="sxs-lookup"><span data-stu-id="0b246-121">Language and framework choices</span></span>

<span data-ttu-id="0b246-122">ほとんどの最新の言語でマイクロソフトのツールを使用する Docker アプリケーションを開発することができます。</span><span class="sxs-lookup"><span data-stu-id="0b246-122">You can develop Docker applications using Microsoft tools with most modern languages.</span></span> <span data-ttu-id="0b246-123">最初のリストを次に示しますが、それに制限されておらず。</span><span class="sxs-lookup"><span data-stu-id="0b246-123">The following is an initial list, but you're not limited to it:</span></span>

- <span data-ttu-id="0b246-124">.NET Core および ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0b246-124">.NET Core and ASP.NET Core</span></span>
- <span data-ttu-id="0b246-125">Node.js</span><span class="sxs-lookup"><span data-stu-id="0b246-125">Node.js</span></span>
- <span data-ttu-id="0b246-126">移動</span><span class="sxs-lookup"><span data-stu-id="0b246-126">Go</span></span>
- <span data-ttu-id="0b246-127">Java</span><span class="sxs-lookup"><span data-stu-id="0b246-127">Java</span></span>
- <span data-ttu-id="0b246-128">Ruby</span><span class="sxs-lookup"><span data-stu-id="0b246-128">Ruby</span></span>
- <span data-ttu-id="0b246-129">Python</span><span class="sxs-lookup"><span data-stu-id="0b246-129">Python</span></span>

<span data-ttu-id="0b246-130">基本的には、Linux または Windows で Docker でサポートされている最新の言語を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="0b246-130">Basically, you can use any modern language supported by Docker in Linux or Windows.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="0b246-131">[前へ](deploy-azure-kubernetes-service.md)
>[次へ](docker-apps-inner-loop-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="0b246-131">[Previous](deploy-azure-kubernetes-service.md)
[Next](docker-apps-inner-loop-workflow.md)</span></span>
