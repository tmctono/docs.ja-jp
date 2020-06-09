---
title: 依存関係の読み込み - .NET Core
description: .NET Core でのマネージドおよびアンマネージドの依存関係の読み込みの概要
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.topic: overview
ms.openlocfilehash: 34deb802183f20cc92449c21eb7e149cc002850f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84284223"
---
# <a name="dependency-loading-in-net-core"></a><span data-ttu-id="e6da4-103">.NET Core での依存関係の読み込み</span><span class="sxs-lookup"><span data-stu-id="e6da4-103">Dependency loading in .NET Core</span></span>

<span data-ttu-id="e6da4-104">すべての .NET Core アプリケーションには依存関係があります。</span><span class="sxs-lookup"><span data-stu-id="e6da4-104">Every .NET Core application has dependencies.</span></span> <span data-ttu-id="e6da4-105">単純な `hello world` アプリでも、.NET Core クラス ライブラリの一部に依存関係があります。</span><span class="sxs-lookup"><span data-stu-id="e6da4-105">Even the simple `hello world` app has dependencies on portions of the .NET Core class libraries.</span></span>

<span data-ttu-id="e6da4-106">.NET Core の既定のアセンブリ読み込みロジックについて理解すると、デプロイに関する一般的な問題を理解し、デバッグするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e6da4-106">Understanding .NET Core default assembly loading logic can help understanding and debugging typical deployment issues.</span></span>

<span data-ttu-id="e6da4-107">アプリケーションによっては、依存関係が実行時に動的に決定されます。</span><span class="sxs-lookup"><span data-stu-id="e6da4-107">In some applications, dependencies are dynamically determined at run time.</span></span> <span data-ttu-id="e6da4-108">このような状況では、マネージド アセンブリおよびアンマネージドの依存関係がどのように読み込まれるかを理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="e6da4-108">In these situations, it's critical to understand how managed assemblies and unmanaged dependencies are loaded.</span></span>

## <a name="understanding-assemblyloadcontext"></a><span data-ttu-id="e6da4-109">AssemblyLoadContext について</span><span class="sxs-lookup"><span data-stu-id="e6da4-109">Understanding AssemblyLoadContext</span></span>

<span data-ttu-id="e6da4-110"><xref:System.Runtime.Loader.AssemblyLoadContext> API は、.NET Core 読み込みデザインの中核となるものです。</span><span class="sxs-lookup"><span data-stu-id="e6da4-110">The <xref:System.Runtime.Loader.AssemblyLoadContext> API is central to the .NET Core loading design.</span></span> <span data-ttu-id="e6da4-111">[AssemblyLoadContext について](understanding-assemblyloadcontext.md)の記事では、設計の概念についての概要を示します。</span><span class="sxs-lookup"><span data-stu-id="e6da4-111">The [Understanding AssemblyLoadContext](understanding-assemblyloadcontext.md) article provides a conceptual overview to the design.</span></span>

## <a name="loading-details"></a><span data-ttu-id="e6da4-112">読み込みの詳細</span><span class="sxs-lookup"><span data-stu-id="e6da4-112">Loading details</span></span>

<span data-ttu-id="e6da4-113">読み込みアルゴリズムの詳細については、次のいくつかの記事で簡単に説明されています。</span><span class="sxs-lookup"><span data-stu-id="e6da4-113">The loading algorithm details are covered briefly in several articles:</span></span>

- [<span data-ttu-id="e6da4-114">マネージド アセンブリの読み込みアルゴリズム</span><span class="sxs-lookup"><span data-stu-id="e6da4-114">Managed assembly loading algorithm</span></span>](loading-managed.md)
- [<span data-ttu-id="e6da4-115">サテライト アセンブリの読み込みアルゴリズム</span><span class="sxs-lookup"><span data-stu-id="e6da4-115">Satellite assembly loading algorithm</span></span>](loading-resources.md)
- [<span data-ttu-id="e6da4-116">アンマネージド (ネイティブ) ライブラリの読み込みアルゴリズム</span><span class="sxs-lookup"><span data-stu-id="e6da4-116">Unmanaged (native) library loading algorithm</span></span>](loading-unmanaged.md)
- [<span data-ttu-id="e6da4-117">既定のプローブ</span><span class="sxs-lookup"><span data-stu-id="e6da4-117">Default probing</span></span>](default-probing.md)

## <a name="create-a-net-core-application-with-plugins"></a><span data-ttu-id="e6da4-118">プラグインがある .NET Core アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="e6da4-118">Create a .NET Core application with plugins</span></span>

<span data-ttu-id="e6da4-119">チュートリアル「[プラグインがある .NET Core アプリケーションを作成する](../tutorials/creating-app-with-plugin-support.md)」では、カスタムの AssemblyLoadContext の作成方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e6da4-119">The tutorial [Create a .NET Core application with plugins](../tutorials/creating-app-with-plugin-support.md) describes how to create a custom AssemblyLoadContext.</span></span> <span data-ttu-id="e6da4-120">ここでは <xref:System.Runtime.Loader.AssemblyDependencyResolver> を使用して、プラグインの依存関係を解決します。</span><span class="sxs-lookup"><span data-stu-id="e6da4-120">It uses an <xref:System.Runtime.Loader.AssemblyDependencyResolver> to resolve the dependencies of the plugin.</span></span> <span data-ttu-id="e6da4-121">このチュートリアルでは、ホスト アプリケーションからプラグインの依存関係を正しく分離します。</span><span class="sxs-lookup"><span data-stu-id="e6da4-121">The tutorial correctly isolates the plugin's dependencies from the hosting application.</span></span>

## <a name="how-to-use-and-debug-assembly-unloadability-in-net-core"></a><span data-ttu-id="e6da4-122">.NET Core でアセンブリのアンローダビリティを使用およびデバッグする方法</span><span class="sxs-lookup"><span data-stu-id="e6da4-122">How to use and debug assembly unloadability in .NET Core</span></span>

<span data-ttu-id="e6da4-123">「[.NET Core でアセンブリのアンローダビリティを使用およびデバッグする方法](../../standard/assembly/unloadability.md)」の記事は、ステップ バイ ステップのチュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="e6da4-123">The [How to use and debug assembly unloadability in .NET Core](../../standard/assembly/unloadability.md) article is a step-by-step tutorial.</span></span> <span data-ttu-id="e6da4-124">ここでは、.NET Core アプリケーションを読み込んで実行し、アンロードする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e6da4-124">It shows how to load a .NET Core application, execute, and then unload it.</span></span> <span data-ttu-id="e6da4-125">この記事ではデバッグのヒントも示します。</span><span class="sxs-lookup"><span data-stu-id="e6da4-125">The article also provides debugging tips.</span></span>
