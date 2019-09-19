---
title: .NET ネイティブによるアプリのコンパイル
ms.date: 03/30/2017
helpviewer_keywords:
- native compilation
- .NET and native code
- compilation with .NET Native
- .NET Native
- C# and native compilation
ms.assetid: 47cd5648-9469-4b1d-804c-43cc04384045
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5993cfdb0f50d8e474a4f18280d181d9ec2fdfa4
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049652"
---
# <a name="compiling-apps-with-net-native"></a><span data-ttu-id="d8c2d-102">.NET ネイティブによるアプリのコンパイル</span><span class="sxs-lookup"><span data-stu-id="d8c2d-102">Compiling Apps with .NET Native</span></span>

<span data-ttu-id="d8c2d-103">.NET ネイティブは、Visual Studio 2015 以降のバージョンに付属している Windows アプリをビルドおよび配置するためのプリコンパイルテクノロジです。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-103">.NET Native is a precompilation technology for building and deploying Windows apps that is included with Visual Studio 2015 and later versions.</span></span> <span data-ttu-id="d8c2d-104">マネージド コード (C# または Visual Basic) で記述された、.NET Framework および Windows 10 を対象とするアプリのリリース バージョンを自動的にネイティブ コードにコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-104">It automatically compiles the release version of apps that are written in managed code (C# or Visual Basic) and that target the .NET Framework and Windows 10 to native code.</span></span>

<span data-ttu-id="d8c2d-105">通常、.NET Framework を対象とするアプリは中間言語 (IL) にコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-105">Typically, apps that target the .NET Framework are compiled to intermediate language (IL).</span></span> <span data-ttu-id="d8c2d-106">実行時に、Just-In-Time (JIT) コンパイラによって IL がネイティブ コードに変換されます。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-106">At run time, the just-in-time (JIT) compiler translates the IL to native code.</span></span> <span data-ttu-id="d8c2d-107">これに対し、.NET ネイティブは、Windows アプリを直接ネイティブコードにコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-107">In contrast, .NET Native compiles Windows apps directly to native code.</span></span> <span data-ttu-id="d8c2d-108">開発者にとって、これは次のことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-108">For developers, this means:</span></span>

- <span data-ttu-id="d8c2d-109">アプリは、ネイティブコードのパフォーマンスを特徴としています。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-109">Your apps feature the performance of native code.</span></span> <span data-ttu-id="d8c2d-110">通常、パフォーマンスは、最初に IL にコンパイルされてから JIT コンパイラによってネイティブコードにコンパイルされるコードよりも優れています。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-110">Usually, performance will be superior to code that is first compiled to IL and then compiled to native code by the JIT compiler.</span></span>

- <span data-ttu-id="d8c2d-111">引き続き C# または Visual Basic でプログラムを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-111">You can continue to program in C# or Visual Basic.</span></span>

- <span data-ttu-id="d8c2d-112">クラス ライブラリ、自動メモリ管理とガベージ コレクション、例外処理など、.NET Framework で提供されるリソースを引き続き利用できます。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-112">You can continue to take advantage of the resources provided by the .NET Framework, including its class library, automatic memory management and garbage collection, and exception handling.</span></span>

<span data-ttu-id="d8c2d-113">アプリのユーザーのために、.NET ネイティブには次のような利点があります。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-113">For users of your apps, .NET Native offers these advantages:</span></span>

- <span data-ttu-id="d8c2d-114">大部分のアプリとシナリオの実行時間が短縮されます。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-114">Faster execution times for the majority of apps and scenarios.</span></span>

- <span data-ttu-id="d8c2d-115">ほとんどのアプリとシナリオで、起動時間が短縮されます。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-115">Faster startup times for the majority of apps and scenarios.</span></span>

- <span data-ttu-id="d8c2d-116">デプロイコストと更新コストが低くなります。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-116">Low deployment and update costs.</span></span>

- <span data-ttu-id="d8c2d-117">アプリのメモリ使用量が最適化されています。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-117">Optimized app memory usage.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8c2d-118">アプリとシナリオの大部分では、IL または NGEN イメージにコンパイルされたアプリと比較した場合、起動時間が大幅に短縮され、パフォーマンスが向上します。 .NET ネイティブ。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-118">For the vast majority of apps and scenarios, .NET Native offers significantly faster startup times and superior performance when compared to an app compiled to IL or to an NGEN image.</span></span> <span data-ttu-id="d8c2d-119">ただし、結果は異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-119">However, your results may vary.</span></span> <span data-ttu-id="d8c2d-120">.NET ネイティブのパフォーマンスの向上によってアプリのパフォーマンスを向上させるには、アプリの non-.NET ネイティブバージョンとのパフォーマンスを比較する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-120">To ensure that your app has benefited from the performance enhancements of .NET Native, you should compare its performance with that of the non-.NET Native version of your app.</span></span> <span data-ttu-id="d8c2d-121">詳細については、「[パフォーマンスセッションの概要](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-121">For more information, see [Performance Session Overview](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview).</span></span>

<span data-ttu-id="d8c2d-122">ただし .NET ネイティブには、ネイティブコードへのコンパイル以外にも関係があります。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-122">But .NET Native involves more than a compilation to native code.</span></span> <span data-ttu-id="d8c2d-123">.NET Framework アプリのビルド方法と実行方法が変更されます。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-123">It transforms the way that .NET Framework apps are built and executed.</span></span> <span data-ttu-id="d8c2d-124">特に次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-124">In particular:</span></span>

- <span data-ttu-id="d8c2d-125">プリコンパイル時に、.NET Framework の必要な部分がアプリに静的にリンクされます。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-125">During precompilation, required portions of the .NET Framework are statically linked into your app.</span></span> <span data-ttu-id="d8c2d-126">これにより、アプリは .NET Framework のアプリ ローカルのライブラリを使用して実行でき、コンパイラはグローバル分析を実行してパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-126">This allows the app to run with app-local libraries of the .NET Framework, and the compiler to perform global analysis to deliver performance wins.</span></span> <span data-ttu-id="d8c2d-127">その結果、.NET Framework の更新後であっても、アプリは常に高速に起動します。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-127">As a result, apps launch consistently faster even after .NET Framework updates.</span></span>

- <span data-ttu-id="d8c2d-128">.NET ネイティブランタイムは静的プリコンパイル用に最適化されており、ほとんどのケースでは優れたパフォーマンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-128">The .NET Native runtime is optimized for static precompilation and in the vast majority of cases offers superior performance.</span></span> <span data-ttu-id="d8c2d-129">同時に、開発者に役立つ主要なリフレクション機能もあります。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-129">At the same time, it retains the core reflection features that developers find so productive.</span></span>

- <span data-ttu-id="d8c2d-130">.NET ネイティブは、静的プリコンパイルシナリオ用C++に最適化された、コンパイラと同じバックエンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-130">.NET Native uses the same back end as the C++ compiler, which is optimized for static precompilation scenarios.</span></span>

<span data-ttu-id="d8c2d-131">.NET ネイティブは、次の表に示すようC++に、内部のものとC++同じまたは類似のツールを使用するため、のパフォーマンス上の利点をマネージコードの開発者にもたらします。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-131">.NET Native is able to bring the performance benefits of C++ to managed code developers because it uses the same or similar tools as C++ under the hood, as shown in this table.</span></span>

||<span data-ttu-id="d8c2d-132">.NET Native</span><span class="sxs-lookup"><span data-stu-id="d8c2d-132">.NET Native</span></span>|<span data-ttu-id="d8c2d-133">C++</span><span class="sxs-lookup"><span data-stu-id="d8c2d-133">C++</span></span>|
|-|----------------------------------------------------------------|-----------|
|<span data-ttu-id="d8c2d-134">ライブラリ</span><span class="sxs-lookup"><span data-stu-id="d8c2d-134">Libraries</span></span>|<span data-ttu-id="d8c2d-135">.NET Framework + Windows ランタイム</span><span class="sxs-lookup"><span data-stu-id="d8c2d-135">The .NET Framework + Windows Runtime</span></span>|<span data-ttu-id="d8c2d-136">Win32 + Windows ランタイム</span><span class="sxs-lookup"><span data-stu-id="d8c2d-136">Win32 + Windows Runtime</span></span>|
|<span data-ttu-id="d8c2d-137">コンパイラ</span><span class="sxs-lookup"><span data-stu-id="d8c2d-137">Compiler</span></span>|<span data-ttu-id="d8c2d-138">UTC 最適化コンパイラ</span><span class="sxs-lookup"><span data-stu-id="d8c2d-138">UTC optimizing compiler</span></span>|<span data-ttu-id="d8c2d-139">UTC 最適化コンパイラ</span><span class="sxs-lookup"><span data-stu-id="d8c2d-139">UTC optimizing compiler</span></span>|
|<span data-ttu-id="d8c2d-140">配置</span><span class="sxs-lookup"><span data-stu-id="d8c2d-140">Deployed</span></span>|<span data-ttu-id="d8c2d-141">実行可能バイナリ</span><span class="sxs-lookup"><span data-stu-id="d8c2d-141">Ready-to-run binaries</span></span>|<span data-ttu-id="d8c2d-142">実行可能バイナリ (ASM)</span><span class="sxs-lookup"><span data-stu-id="d8c2d-142">Ready-to-run binaries (ASM)</span></span>|
|<span data-ttu-id="d8c2d-143">ランタイム</span><span class="sxs-lookup"><span data-stu-id="d8c2d-143">Runtime</span></span>|<span data-ttu-id="d8c2d-144">MRT.dll (最小 CLR ランタイム)</span><span class="sxs-lookup"><span data-stu-id="d8c2d-144">MRT.dll (Minimal CLR Runtime)</span></span>|<span data-ttu-id="d8c2d-145">CRT.dll (C ランタイム)</span><span class="sxs-lookup"><span data-stu-id="d8c2d-145">CRT.dll (C Runtime)</span></span>|

<span data-ttu-id="d8c2d-146">Windows 10 用の Windows アプリの場合は、.NET ネイティブ コード コンパイル バイナリをアプリ パッケージ (.appx ファイル) に入れて Windows ストアにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-146">For Windows apps for Windows 10, you upload .NET Native Code Compilation binaries in app packages (.appx files) to the Windows Store.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d8c2d-147">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d8c2d-147">In This Section</span></span>

<span data-ttu-id="d8c2d-148">.NET ネイティブ コード コンパイルを使用したアプリ開発の詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-148">For more information about developing apps with .NET Native Code Compilation, see these topics:</span></span>

- [<span data-ttu-id="d8c2d-149">.NET ネイティブの概要</span><span class="sxs-lookup"><span data-stu-id="d8c2d-149">Getting Started with .NET Native Code Compilation: The Developer Experience Walkthrough</span></span>](getting-started-with-net-native.md)

- <span data-ttu-id="d8c2d-150">[.NET ネイティブとコンパイル:](net-native-and-compilation.md).NET ネイティブ、プロジェクトをネイティブコードにコンパイルする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="d8c2d-150">[.NET Native and Compilation:](net-native-and-compilation.md) How .NET Native compiles your project to native code.</span></span>

- [<span data-ttu-id="d8c2d-151">リフレクションおよび .NET ネイティブ</span><span class="sxs-lookup"><span data-stu-id="d8c2d-151">Reflection and .NET Native</span></span>](reflection-and-net-native.md)

  - [<span data-ttu-id="d8c2d-152">リフレクションに依存する API</span><span class="sxs-lookup"><span data-stu-id="d8c2d-152">APIs That Rely on Reflection</span></span>](apis-that-rely-on-reflection.md)

  - [<span data-ttu-id="d8c2d-153">リフレクション API リファレンス</span><span class="sxs-lookup"><span data-stu-id="d8c2d-153">Reflection API Reference</span></span>](net-native-reflection-api-reference.md)

  - [<span data-ttu-id="d8c2d-154">ランタイム ディレクティブ (rd.xml) 構成ファイル リファレンス</span><span class="sxs-lookup"><span data-stu-id="d8c2d-154">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)

- [<span data-ttu-id="d8c2d-155">シリアル化とメタデータ</span><span class="sxs-lookup"><span data-stu-id="d8c2d-155">Serialization and Metadata</span></span>](serialization-and-metadata.md)

- [<span data-ttu-id="d8c2d-156">Windows ストア アプリの .NET ネイティブへの移行</span><span class="sxs-lookup"><span data-stu-id="d8c2d-156">Migrating Your Windows Store App to .NET Native</span></span>](migrating-your-windows-store-app-to-net-native.md)

- [<span data-ttu-id="d8c2d-157">.NET ネイティブの一般的なトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d8c2d-157">.NET Native General Troubleshooting</span></span>](net-native-general-troubleshooting.md)
