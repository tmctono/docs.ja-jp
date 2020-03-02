---
title: .NET 用語集
description: .NET のドキュメントで使われている用語からいくつか選択してその意味を説明します。
ms.date: 01/22/2019
ms.technology: dotnet-standard
ms.openlocfilehash: 8da1d858835210590a80a624fb8989fbfe8e0a91
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160093"
---
# <a name="net-glossary"></a><span data-ttu-id="203ed-103">.NET 用語集</span><span class="sxs-lookup"><span data-stu-id="203ed-103">.NET Glossary</span></span>

<span data-ttu-id="203ed-104">この用語集の主な目的は、.NET のドキュメントで定義なしに頻繁に出現する用語と頭字語の意味を明確にすることです。</span><span class="sxs-lookup"><span data-stu-id="203ed-104">The primary goal of this glossary is to clarify meanings of selected terms and acronyms that appear frequently in the .NET documentation without definitions.</span></span>

## <a name="aot"></a><span data-ttu-id="203ed-105">AOT</span><span class="sxs-lookup"><span data-stu-id="203ed-105">AOT</span></span>

<span data-ttu-id="203ed-106">Ahead Of Time コンパイラ。</span><span class="sxs-lookup"><span data-stu-id="203ed-106">Ahead-of-time compiler.</span></span>

<span data-ttu-id="203ed-107">[JIT](#jit) と同様に、このコンパイラも [IL](#il) をマシン コードに変換します。</span><span class="sxs-lookup"><span data-stu-id="203ed-107">Similar to [JIT](#jit), this compiler also translates [IL](#il) to machine code.</span></span> <span data-ttu-id="203ed-108">JIT コンパイルとは異なり、AOT コンパイルはアプリケーションが実行される前に行われ、通常は、別のコンピューターで実行されます。</span><span class="sxs-lookup"><span data-stu-id="203ed-108">In contrast to JIT compilation, AOT compilation happens before the application is executed and is usually performed on a different machine.</span></span> <span data-ttu-id="203ed-109">AOT ツール チェーンは実行時にコンパイルしないので、コンパイルに費やされる時間を最小限に抑える必要はありません。</span><span class="sxs-lookup"><span data-stu-id="203ed-109">Because AOT tool chains don't compile at runtime, they don't have to minimize time spent compiling.</span></span> <span data-ttu-id="203ed-110">つまり、より多くの時間を最適化に費やすことができます。</span><span class="sxs-lookup"><span data-stu-id="203ed-110">That means they can spend more time optimizing.</span></span> <span data-ttu-id="203ed-111">AOT のコンテキストはアプリケーション全体であるため、AOT コンパイラはモジュール間のリンクとプログラム全体の分析も実行します。これは、すべての参照が追跡されて、1 つの実行可能ファイルが生成されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="203ed-111">Since the context of AOT is the entire application, the AOT compiler also performs cross-module linking and whole-program analysis, which means that all references are followed and a single executable is produced.</span></span>

<span data-ttu-id="203ed-112">「[CoreRT](#corert)」と「[.NET Native](#net-native)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="203ed-112">See [CoreRT](#corert) and [.NET Native](#net-native).</span></span>

## <a name="aspnet"></a><span data-ttu-id="203ed-113">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="203ed-113">ASP.NET</span></span>

<span data-ttu-id="203ed-114">.NET Framework に付属している ASP.NET の元の実装。</span><span class="sxs-lookup"><span data-stu-id="203ed-114">The original ASP.NET implementation that ships with the .NET Framework.</span></span>

<span data-ttu-id="203ed-115">ASP.NET は、ASP.NET Core を含む ASP.NET の両方の実装を指す包括的な用語として使われることがあります。</span><span class="sxs-lookup"><span data-stu-id="203ed-115">Sometimes ASP.NET is an umbrella term that refers to both ASP.NET implementations including ASP.NET Core.</span></span> <span data-ttu-id="203ed-116">どちらを意味するかはコンテキストによって決まります。</span><span class="sxs-lookup"><span data-stu-id="203ed-116">The meaning that the term carries in any given instance is determined by context.</span></span> <span data-ttu-id="203ed-117">両方の実装を意味するために ASP.NET を使っているのではないことを明確にしたい場合は、ASP.NET 4.x を参照してください。</span><span class="sxs-lookup"><span data-stu-id="203ed-117">Refer to ASP.NET 4.x when you want to make it clear that you’re not using ASP.NET to mean both implementations.</span></span>

<span data-ttu-id="203ed-118">[ASP.NET のドキュメント](/aspnet/#pivot=aspnet)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="203ed-118">See [ASP.NET documentation](/aspnet/#pivot=aspnet).</span></span>

## <a name="aspnet-core"></a><span data-ttu-id="203ed-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="203ed-119">ASP.NET Core</span></span>

<span data-ttu-id="203ed-120">.NET Core 上に構築された ASP.NET のクロスプラットフォームで高パフォーマンスなオープン ソースの実装。</span><span class="sxs-lookup"><span data-stu-id="203ed-120">A cross-platform, high-performance, open source implementation of ASP.NET built on .NET Core.</span></span>

<span data-ttu-id="203ed-121">[ASP.NET Core のドキュメント](/aspnet/#pivot=core)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="203ed-121">See [ASP.NET Core documentation](/aspnet/#pivot=core).</span></span>

## <a name="assembly"></a><span data-ttu-id="203ed-122">アセンブリ</span><span class="sxs-lookup"><span data-stu-id="203ed-122">assembly</span></span>

<span data-ttu-id="203ed-123">アプリケーションまたは他のアセンブリから呼び出すことができる API のコレクションを含む *.dll*/ *.exe* ファイル。</span><span class="sxs-lookup"><span data-stu-id="203ed-123">A *.dll*/*.exe* file that can contain a collection of APIs that can be called by applications or other assemblies.</span></span>

<span data-ttu-id="203ed-124">アセンブリは、インターフェイス、クラス、構造体、列挙型、デリゲートなどの種類を含むことができます。</span><span class="sxs-lookup"><span data-stu-id="203ed-124">An assembly may include types such as interfaces, classes, structures, enumerations, and delegates.</span></span> <span data-ttu-id="203ed-125">プロジェクトの *bin* フォルダー内のアセンブリは、"*バイナリ*" と呼ばれることもあります。</span><span class="sxs-lookup"><span data-stu-id="203ed-125">Assemblies in a project's *bin* folder are sometimes referred to as *binaries*.</span></span> <span data-ttu-id="203ed-126">「[ライブラリ](#library)」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="203ed-126">See also [library](#library).</span></span>

## <a name="clr"></a><span data-ttu-id="203ed-127">CLR</span><span class="sxs-lookup"><span data-stu-id="203ed-127">CLR</span></span>

<span data-ttu-id="203ed-128">共通言語ランタイム (Common Language Runtime)。</span><span class="sxs-lookup"><span data-stu-id="203ed-128">Common Language Runtime.</span></span>

<span data-ttu-id="203ed-129">厳密な意味はコンテキストによって異なりますが、通常は、.NET Framework のランタイムを指します。</span><span class="sxs-lookup"><span data-stu-id="203ed-129">The exact meaning depends on the context, but this usually refers to the runtime of the .NET Framework.</span></span> <span data-ttu-id="203ed-130">CLR は、メモリの割り当てと管理を行います。</span><span class="sxs-lookup"><span data-stu-id="203ed-130">The CLR handles memory allocation and management.</span></span> <span data-ttu-id="203ed-131">CLR は、アプリの実行だけでなく、[JIT](#jit) コンパイラを使って実行時にコードを生成してコンパイルする仮想マシンでもあります。</span><span class="sxs-lookup"><span data-stu-id="203ed-131">The CLR is also a virtual machine that not only executes apps but also generates and compiles code on-the-fly using a [JIT](#jit) compiler.</span></span> <span data-ttu-id="203ed-132">現在の Microsoft CLR の実装は Windows だけです。</span><span class="sxs-lookup"><span data-stu-id="203ed-132">The current Microsoft CLR implementation is Windows only.</span></span>

## <a name="coreclr"></a><span data-ttu-id="203ed-133">CoreCLR</span><span class="sxs-lookup"><span data-stu-id="203ed-133">CoreCLR</span></span>

<span data-ttu-id="203ed-134">.NET Core 共通言語ランタイム (.NET Core Common Language Runtime)。</span><span class="sxs-lookup"><span data-stu-id="203ed-134">.NET Core Common Language Runtime.</span></span>

<span data-ttu-id="203ed-135">この CLR は、CLR と同じコード ベースから作成されます。</span><span class="sxs-lookup"><span data-stu-id="203ed-135">This CLR is built from the same code base as the CLR.</span></span> <span data-ttu-id="203ed-136">もともと、CoreCLR は Silverlight のランタイムであり、複数のプラットフォーム (具体的には Windows と OS X) で実行するように設計されていました。現在の CoreCLR は .NET Core の一部であり、CLR の簡素化されたバージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="203ed-136">Originally, CoreCLR was the runtime of Silverlight and was designed to run on multiple platforms, specifically Windows and OS X. CoreCLR is now part of .NET Core and represents a simplified version of the CLR.</span></span> <span data-ttu-id="203ed-137">まだ[クロスプラットフォーム](#cross-platform) ランタイムであり、多くの Linux ディストリビューションのサポートを含むようになっています。</span><span class="sxs-lookup"><span data-stu-id="203ed-137">It's still a [cross-platform](#cross-platform) runtime, now including support for many Linux distributions.</span></span> <span data-ttu-id="203ed-138">CoreCLR は、JIT とコード実行機能を備えた仮想マシンでもあります。</span><span class="sxs-lookup"><span data-stu-id="203ed-138">CoreCLR is also a virtual machine with JIT and code execution capabilities.</span></span>

## <a name="corefx"></a><span data-ttu-id="203ed-139">CoreFX</span><span class="sxs-lookup"><span data-stu-id="203ed-139">CoreFX</span></span>

<span data-ttu-id="203ed-140">.NET Core 基本クラス ライブラリ (BCL)</span><span class="sxs-lookup"><span data-stu-id="203ed-140">.NET Core Base Class Library (BCL)</span></span>

<span data-ttu-id="203ed-141">System.\* (および限られた範囲の Microsoft.\*) 名前空間を構成するライブラリのセット。</span><span class="sxs-lookup"><span data-stu-id="203ed-141">A set of libraries that comprise the System.\* (and to a limited extent Microsoft.\*) namespaces.</span></span> <span data-ttu-id="203ed-142">BCL は汎用の下位レベル フレームワークであり、ASP.NET Core などの上位レベル アプリケーション フレームワークはそれを基にして構築されています。</span><span class="sxs-lookup"><span data-stu-id="203ed-142">The BCL is a general purpose, lower-level framework that higher-level application frameworks, such as ASP.NET Core, build on.</span></span> <span data-ttu-id="203ed-143">.NET Core BCL のソース コードは [.NET Core ランタイム リポジトリ](https://github.com/dotnet/runtime)に含まれます。</span><span class="sxs-lookup"><span data-stu-id="203ed-143">The source code of the .NET Core BCL is contained in the [.NET Core runtime repository](https://github.com/dotnet/runtime).</span></span> <span data-ttu-id="203ed-144">ただし、.NET Core API の大部分は .NET Framework でも使うことができるため、CoreFX は .NET Framework BCL が分岐したものと考えることができます。</span><span class="sxs-lookup"><span data-stu-id="203ed-144">However, the majority of the .NET Core APIs are also available in the .NET Framework, so you can think of CoreFX as a fork of the .NET Framework BCL.</span></span>

## <a name="corert"></a><span data-ttu-id="203ed-145">CoreRT</span><span class="sxs-lookup"><span data-stu-id="203ed-145">CoreRT</span></span>

<span data-ttu-id="203ed-146">.NET Core ランタイム。</span><span class="sxs-lookup"><span data-stu-id="203ed-146">.NET Core runtime.</span></span>

<span data-ttu-id="203ed-147">CLR/CoreCLR とは異なり、CoreRT は仮想マシンではありません。つまり、[JIT](#jit) が含まれないため、実行時にコードを生成して実行する機能はありません。</span><span class="sxs-lookup"><span data-stu-id="203ed-147">In contrast to the CLR/CoreCLR, CoreRT is not a virtual machine, which means it doesn't include the facilities to generate and run code on-the-fly because it doesn't include a [JIT](#jit).</span></span> <span data-ttu-id="203ed-148">ただし、[GC](#gc) およびランタイム型識別 (RTTI) とリフレクションの機能は備えています。</span><span class="sxs-lookup"><span data-stu-id="203ed-148">It does, however, include the [GC](#gc) and the ability for runtime type identification (RTTI) and reflection.</span></span> <span data-ttu-id="203ed-149">ただ、CoreRT の型システムはリフレクション用のメタデータが必要ないように設計されています。</span><span class="sxs-lookup"><span data-stu-id="203ed-149">However, its type system is designed so that metadata for reflection isn't required.</span></span> <span data-ttu-id="203ed-150">これにより、[AOT](#aot) ツール チェーンで余分なメタデータのリンクを削除し、(さらに重要なこととして) アプリが使っていないコードを特定することができます。</span><span class="sxs-lookup"><span data-stu-id="203ed-150">This enables having an [AOT](#aot) tool chain that can link away superfluous metadata and (more importantly) identify code that the app doesn't use.</span></span> <span data-ttu-id="203ed-151">CoreRT は開発中です。</span><span class="sxs-lookup"><span data-stu-id="203ed-151">CoreRT is in development.</span></span>

<span data-ttu-id="203ed-152">[.NET Native と CoreRT の概要](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="203ed-152">See [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md).</span></span>

## <a name="cross-platform"></a><span data-ttu-id="203ed-153">クロスプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="203ed-153">cross-platform</span></span>

<span data-ttu-id="203ed-154">Linux、Windows、iOS など、複数の異なるオペレーティング システム上で使用できるアプリケーションを開発し、実行することができます。OS ごとに作成し直す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="203ed-154">The ability to develop and execute an application that can be used on multiple different operating systems, such as Linux, Windows and iOS, without having to re-write specifically for each one.</span></span> <span data-ttu-id="203ed-155">そのため、異なるプラットフォーム上のアプリケーション間でコードを再利用し、一貫性を保つことができます。</span><span class="sxs-lookup"><span data-stu-id="203ed-155">This enables code re-use and consistency between applications on different platforms.</span></span>

## <a name="ecosystem"></a><span data-ttu-id="203ed-156">エコシステム</span><span class="sxs-lookup"><span data-stu-id="203ed-156">ecosystem</span></span>

<span data-ttu-id="203ed-157">特定のテクノロジ用のアプリケーションを構築して実行するために使われるすべての実行時ソフトウェア、開発ツール、およびコミュニティ リソース。</span><span class="sxs-lookup"><span data-stu-id="203ed-157">All of the runtime software, development tools, and community resources that are used to build and run applications for a given technology.</span></span>

<span data-ttu-id="203ed-158">".NET エコシステム" という用語は ".NET スタック" などの用語と似ていますが、サードパーティのアプリとライブラリを含む点が異なります。</span><span class="sxs-lookup"><span data-stu-id="203ed-158">The term ".NET ecosystem" differs from similar terms such as ".NET stack" in its inclusion of third-party apps and libraries.</span></span> <span data-ttu-id="203ed-159">文章での使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="203ed-159">Here's an example in a sentence:</span></span>

- <span data-ttu-id="203ed-160">"[.NET Standard](#net-standard) の背後にある意図は、.NET エコシステムの高度な統一性を確立することです。"</span><span class="sxs-lookup"><span data-stu-id="203ed-160">"The motivation behind the [.NET Standard](#net-standard) is to establish greater uniformity in the .NET ecosystem."</span></span>

## <a name="framework"></a><span data-ttu-id="203ed-161">フレームワーク</span><span class="sxs-lookup"><span data-stu-id="203ed-161">framework</span></span>

<span data-ttu-id="203ed-162">一般に、特定のテクノロジに基づくアプリケーションの開発と展開を容易にする API の包括的なコレクション。</span><span class="sxs-lookup"><span data-stu-id="203ed-162">In general, a comprehensive collection of APIs that facilitates development and deployment of applications that are based on a particular technology.</span></span> <span data-ttu-id="203ed-163">この一般的な意味でのアプリケーション フレームワークの例としては、ASP.NET Core や Windows フォームなどがあります。</span><span class="sxs-lookup"><span data-stu-id="203ed-163">In this general sense, ASP.NET Core and Windows Forms are examples of application frameworks.</span></span> <span data-ttu-id="203ed-164">「[ライブラリ](#library)」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="203ed-164">See also [library](#library).</span></span>

<span data-ttu-id="203ed-165">以下の語句で使われている "フレームワーク" という用語には、さらに具体的な技術的意味があります。</span><span class="sxs-lookup"><span data-stu-id="203ed-165">The word "framework" has a more specific technical meaning in the following terms:</span></span>

- [<span data-ttu-id="203ed-166">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="203ed-166">.NET Framework</span></span>](#net-framework)
- [<span data-ttu-id="203ed-167">ターゲット フレームワーク</span><span class="sxs-lookup"><span data-stu-id="203ed-167">target framework</span></span>](#target-framework)
- [<span data-ttu-id="203ed-168">TFM (ターゲット フレームワーク モニカー)</span><span class="sxs-lookup"><span data-stu-id="203ed-168">TFM (target framework moniker)</span></span>](#tfm)

<span data-ttu-id="203ed-169">既存のドキュメントでは、[.NET の実装](#implementation-of-net)を指して "フレームワーク" が使われていることがあります。</span><span class="sxs-lookup"><span data-stu-id="203ed-169">In the existing documentation, "framework" sometimes refers to an [implementation of .NET](#implementation-of-net).</span></span> <span data-ttu-id="203ed-170">たとえば、.NET Core をフレームワークと呼んでいる場合があります。</span><span class="sxs-lookup"><span data-stu-id="203ed-170">For example, an article may call .NET Core a framework.</span></span> <span data-ttu-id="203ed-171">このような混乱を招く使用法をドキュメントから除去することが予定されています。</span><span class="sxs-lookup"><span data-stu-id="203ed-171">We plan to eliminate this confusing usage from the documentation.</span></span>

## <a name="gc"></a><span data-ttu-id="203ed-172">[GC]</span><span class="sxs-lookup"><span data-stu-id="203ed-172">GC</span></span>

<span data-ttu-id="203ed-173">ガベージ コレクター (Garbage Collector)。</span><span class="sxs-lookup"><span data-stu-id="203ed-173">Garbage collector.</span></span>

<span data-ttu-id="203ed-174">ガベージ コレクターは、自動メモリ管理の実装です。</span><span class="sxs-lookup"><span data-stu-id="203ed-174">The garbage collector is an implementation of automatic memory management.</span></span>  <span data-ttu-id="203ed-175">GC は、使われなくなったオブジェクトによって占有されているメモリを解放します。</span><span class="sxs-lookup"><span data-stu-id="203ed-175">The GC frees memory occupied by objects that are no longer in use.</span></span>

<span data-ttu-id="203ed-176">「[ガベージ コレクション](garbage-collection/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="203ed-176">See [Garbage Collection](garbage-collection/index.md).</span></span>

## <a name="il"></a><span data-ttu-id="203ed-177">IL</span><span class="sxs-lookup"><span data-stu-id="203ed-177">IL</span></span>

<span data-ttu-id="203ed-178">中間言語 (Intermediate Language)。</span><span class="sxs-lookup"><span data-stu-id="203ed-178">Intermediate language.</span></span>

<span data-ttu-id="203ed-179">C# などの高レベル .NET 言語は、中間言語 (IL) と呼ばれるハードウェアに依存しない命令セットにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="203ed-179">Higher-level .NET languages, such as C#, compile down to a hardware-agnostic instruction set, which is called Intermediate Language (IL).</span></span> <span data-ttu-id="203ed-180">IL は、MSIL (Microsoft IL) や CIL (Common IL) などと呼ばれることもあります。</span><span class="sxs-lookup"><span data-stu-id="203ed-180">IL is sometimes referred to as MSIL (Microsoft IL) or CIL (Common IL).</span></span>

## <a name="jit"></a><span data-ttu-id="203ed-181">JIT</span><span class="sxs-lookup"><span data-stu-id="203ed-181">JIT</span></span>

<span data-ttu-id="203ed-182">Just-In-Time コンパイラ。</span><span class="sxs-lookup"><span data-stu-id="203ed-182">Just-in-time compiler.</span></span>

<span data-ttu-id="203ed-183">[AOT](#aot) と同様に、このコンパイラは [IL](#il) をプロセッサが理解するマシン コードに変換します。</span><span class="sxs-lookup"><span data-stu-id="203ed-183">Similar to [AOT](#aot), this compiler translates [IL](#il) to machine code that the processor understands.</span></span> <span data-ttu-id="203ed-184">AOT とは異なり、JIT のコンパイルはオンデマンドで行われ、コードを実行する必要があるコンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="203ed-184">Unlike AOT, JIT compilation happens on demand and is performed on the same machine that the code needs to run on.</span></span> <span data-ttu-id="203ed-185">JIT コンパイルはアプリケーションの実行中に行われるため、コンパイル時間は実行時間の一部になります。</span><span class="sxs-lookup"><span data-stu-id="203ed-185">Since JIT compilation occurs during execution of the application, compile time is part of the run time.</span></span> <span data-ttu-id="203ed-186">したがって、JIT コンパイラでは、コードの最適化に要する時間と、結果のコードによって得られる時間の節約のバランスを考える必要があります。</span><span class="sxs-lookup"><span data-stu-id="203ed-186">Thus, JIT compilers have to balance time spent optimizing code against the savings that the resulting code can produce.</span></span> <span data-ttu-id="203ed-187">ただし、JIT は実際のハードウェアを認識するので、開発者はさまざまな実装を出荷する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="203ed-187">But a JIT knows the actual hardware and can free developers from having to ship different implementations.</span></span>

## <a name="implementation-of-net"></a><span data-ttu-id="203ed-188">.NET の実装</span><span class="sxs-lookup"><span data-stu-id="203ed-188">implementation of .NET</span></span>

<span data-ttu-id="203ed-189">.NET の実装には次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="203ed-189">An implementation of .NET includes the following:</span></span>

- <span data-ttu-id="203ed-190">1 つまたは複数のランタイム。</span><span class="sxs-lookup"><span data-stu-id="203ed-190">One or more runtimes.</span></span> <span data-ttu-id="203ed-191">次に例を示します。 CLR、CoreCLR、CoreRT。</span><span class="sxs-lookup"><span data-stu-id="203ed-191">Examples: CLR, CoreCLR, CoreRT.</span></span>
- <span data-ttu-id="203ed-192">.NET Standard の 1 つのバージョンを実装し、他の API を含むことができるクラス ライブラリ。</span><span class="sxs-lookup"><span data-stu-id="203ed-192">A class library that implements a version of the .NET Standard and may include additional APIs.</span></span> <span data-ttu-id="203ed-193">たとえば、.NET Framework 基本クラス ライブラリや .NET Core 基本クラス ライブラリなどです。</span><span class="sxs-lookup"><span data-stu-id="203ed-193">Examples: .NET Framework Base Class Library, .NET Core Base Class Library.</span></span>
- <span data-ttu-id="203ed-194">必要に応じて、1 つまたは複数のアプリケーション フレームワーク。</span><span class="sxs-lookup"><span data-stu-id="203ed-194">Optionally, one or more application frameworks.</span></span> <span data-ttu-id="203ed-195">次に例を示します。 .NET Framework には ASP.NET、Windows フォーム、WPF が含まれます。</span><span class="sxs-lookup"><span data-stu-id="203ed-195">Examples: ASP.NET, Windows Forms, and WPF are included in the .NET Framework.</span></span>
- <span data-ttu-id="203ed-196">必要に応じて、開発ツール。</span><span class="sxs-lookup"><span data-stu-id="203ed-196">Optionally, development tools.</span></span> <span data-ttu-id="203ed-197">一部の開発ツールは、複数の実装間で共有されます。</span><span class="sxs-lookup"><span data-stu-id="203ed-197">Some development tools are shared among multiple implementations.</span></span>

<span data-ttu-id="203ed-198">.NET の実装の例:</span><span class="sxs-lookup"><span data-stu-id="203ed-198">Examples of .NET implementations:</span></span>

- [<span data-ttu-id="203ed-199">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="203ed-199">.NET Framework</span></span>](#net-framework)
- [<span data-ttu-id="203ed-200">.NET Core</span><span class="sxs-lookup"><span data-stu-id="203ed-200">.NET Core</span></span>](#net-core)
- [<span data-ttu-id="203ed-201">ユニバーサル Windows プラットフォーム (UWP)</span><span class="sxs-lookup"><span data-stu-id="203ed-201">Universal Windows Platform (UWP)</span></span>](#uwp)

## <a name="library"></a><span data-ttu-id="203ed-202">ライブラリ</span><span class="sxs-lookup"><span data-stu-id="203ed-202">library</span></span>

<span data-ttu-id="203ed-203">アプリまたは他のライブラリで呼び出すことができる API のコレクション。</span><span class="sxs-lookup"><span data-stu-id="203ed-203">A collection of APIs that can be called by apps or other libraries.</span></span> <span data-ttu-id="203ed-204">.NET ライブラリは 1 つ以上の[アセンブリ](#assembly)で構成されます。</span><span class="sxs-lookup"><span data-stu-id="203ed-204">A .NET library is composed of one or more [assemblies](#assembly).</span></span>

<span data-ttu-id="203ed-205">ライブラリと[フレームワーク](#framework)は同義語として使われることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="203ed-205">The words library and [framework](#framework) are often used synonymously.</span></span>

## <a name="metapackage"></a><span data-ttu-id="203ed-206">メタパッケージ</span><span class="sxs-lookup"><span data-stu-id="203ed-206">metapackage</span></span>

<span data-ttu-id="203ed-207">それ自体のライブラリを持たず、依存するもののリストのみを含む NuGet パッケージ。</span><span class="sxs-lookup"><span data-stu-id="203ed-207">A NuGet package that has no library of its own but is only a list of dependencies.</span></span> <span data-ttu-id="203ed-208">含まれるパッケージは、必要に応じて、ターゲット フレームワーク用の API を確立できます。</span><span class="sxs-lookup"><span data-stu-id="203ed-208">The included packages can optionally establish the API for a target framework.</span></span>

<span data-ttu-id="203ed-209">「[パッケージ、メタパッケージ、フレームワーク](../core/packages.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="203ed-209">See [Packages, Metapackages and Frameworks](../core/packages.md)</span></span>

## <a name="mono"></a><span data-ttu-id="203ed-210">Mono</span><span class="sxs-lookup"><span data-stu-id="203ed-210">Mono</span></span>

<span data-ttu-id="203ed-211">Mono はオープン ソースであり、主に小規模なランタイムが必要な場合に使用される[クロスプラットフォーム](#cross-platform)の .NET 実装です。</span><span class="sxs-lookup"><span data-stu-id="203ed-211">Mono is an open source, [cross-platform](#cross-platform) .NET implementation that is mainly used when a small runtime is required.</span></span> <span data-ttu-id="203ed-212">Android、Mac、iOS、tvOS、および watchOS 上の Xamarin アプリケーションで利用されるランタイムで、フットプリントが小さいアプリに重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="203ed-212">It is the runtime that powers Xamarin applications on Android, Mac, iOS, tvOS and watchOS and is focused primarily on apps that require a small footprint.</span></span>

<span data-ttu-id="203ed-213">現在公開されているすべての .NET Standard バージョンをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="203ed-213">It supports all of the currently published .NET Standard versions.</span></span>

<span data-ttu-id="203ed-214">これまで Mono は .NET Framework の多数の API を実装し、Unix で人気の高い機能の一部をエミュレートしていました。</span><span class="sxs-lookup"><span data-stu-id="203ed-214">Historically, Mono implemented the larger API of the .NET Framework and emulated some of the most popular capabilities on Unix.</span></span> <span data-ttu-id="203ed-215">また、Unix のそのような機能に依存する .NET アプリケーションを実行するために使用されることもあります。</span><span class="sxs-lookup"><span data-stu-id="203ed-215">It is sometimes used to run .NET applications that rely on those capabilities on Unix.</span></span>

<span data-ttu-id="203ed-216">一般的に Mono は、Just-In-Time コンパイラと共に使用されますが、iOS のようなプラットフォームに使用される完全な静的コンパイラ (Ahead Of Time コンパイル) としても機能します。</span><span class="sxs-lookup"><span data-stu-id="203ed-216">Mono is typically used with a just-in-time compiler, but it also features a full static compiler (ahead-of-time compilation) that is used on platforms like iOS.</span></span>

<span data-ttu-id="203ed-217">Mono について詳しくは、[Mono のドキュメント](https://www.mono-project.com/docs/)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="203ed-217">To learn more about Mono, see the [Mono documentation](https://www.mono-project.com/docs/).</span></span>

## <a name="net"></a><span data-ttu-id="203ed-218">.NET</span><span class="sxs-lookup"><span data-stu-id="203ed-218">.NET</span></span>

<span data-ttu-id="203ed-219">[.NET Standard](#net-standard) とすべての [.NET の実装](#implementation-of-net)およびワークロードを表す包括的な用語。</span><span class="sxs-lookup"><span data-stu-id="203ed-219">The umbrella term for [.NET Standard](#net-standard) and all [.NET implementations](#implementation-of-net) and workloads.</span></span> <span data-ttu-id="203ed-220">常にすべて大文字で表し、".Net" とは表記されません。</span><span class="sxs-lookup"><span data-stu-id="203ed-220">Always capitalized, never ".Net".</span></span>

<span data-ttu-id="203ed-221">「[.NET ガイド](index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="203ed-221">See the [.NET Guide](index.md)</span></span>

## <a name="net-core"></a><span data-ttu-id="203ed-222">.NET Core</span><span class="sxs-lookup"><span data-stu-id="203ed-222">.NET Core</span></span>

<span data-ttu-id="203ed-223">.NET のクロスプラットフォームで高パフォーマンスなオープン ソースの実装。</span><span class="sxs-lookup"><span data-stu-id="203ed-223">A cross-platform, high-performance, open source implementation of .NET.</span></span> <span data-ttu-id="203ed-224">Core 共通言語ランタイム (CoreCLR)、Core AOT ランタイム (CoreRT、開発中)、Core 基本クラス ライブラリ、Core SDK が含まれます。</span><span class="sxs-lookup"><span data-stu-id="203ed-224">Includes the Core Common Language Runtime (CoreCLR), the Core AOT Runtime (CoreRT, in development), the Core Base Class Library, and the Core SDK.</span></span>

<span data-ttu-id="203ed-225">「[.NET Core](../core/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="203ed-225">See [.NET Core](../core/index.md).</span></span>

## <a name="net-core-cli"></a><span data-ttu-id="203ed-226">.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="203ed-226">.NET Core CLI</span></span>

<span data-ttu-id="203ed-227">.NET Core アプリケーション開発用のクロスプラットフォーム ツールチェーン。</span><span class="sxs-lookup"><span data-stu-id="203ed-227">A cross-platform toolchain for developing .NET Core applications.</span></span>

<span data-ttu-id="203ed-228">[.NET Core CLI](../core/tools/index.md) に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="203ed-228">See [.NET Core CLI](../core/tools/index.md).</span></span>

## <a name="net-core-sdk"></a><span data-ttu-id="203ed-229">.NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="203ed-229">.NET Core SDK</span></span>

<span data-ttu-id="203ed-230">一連のライブラリとツールであり、開発者はこれを利用して .NET Core のアプリケーションやライブラリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="203ed-230">A set of libraries and tools that allow developers to create .NET Core applications and libraries.</span></span> <span data-ttu-id="203ed-231">アプリ構築用の [.NET Core CLI](#net-core-cli)、アプリの構築および実行用の .NET Core ライブラリとランタイム、CLI コマンドとアプリケーションを実行する dotnet 実行可能ファイル (*dotnet.exe*) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="203ed-231">Includes the [.NET Core CLI](#net-core-cli) for building apps, .NET Core libraries and runtime for building and running apps, and the dotnet executable (*dotnet.exe*) that runs CLI commands and runs applications.</span></span>

<span data-ttu-id="203ed-232">「[.NET Core SDK 概要](../core/sdk.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="203ed-232">See [.NET Core SDK Overview](../core/sdk.md).</span></span>

## <a name="net-framework"></a><span data-ttu-id="203ed-233">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="203ed-233">.NET Framework</span></span>

<span data-ttu-id="203ed-234">Windows でのみ動作する .NET の実装。</span><span class="sxs-lookup"><span data-stu-id="203ed-234">An implementation of .NET that runs only on Windows.</span></span> <span data-ttu-id="203ed-235">共通言語ランタイム (CLR)、基本クラス ライブラリ、および ASP.NET、Windows フォーム、WPF などのアプリケーション フレームワーク ライブラリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="203ed-235">Includes the Common Language Runtime (CLR), the Base Class Library, and application framework libraries such as ASP.NET, Windows Forms, and WPF.</span></span>

<span data-ttu-id="203ed-236">「[.NET Framework ガイド](../framework/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="203ed-236">See [.NET Framework Guide](../framework/index.md).</span></span>

## <a name="net-native"></a><span data-ttu-id="203ed-237">.NET Native</span><span class="sxs-lookup"><span data-stu-id="203ed-237">.NET Native</span></span>

<span data-ttu-id="203ed-238">Just-In-Time (JIT) ではなく Ahead Of Time (AOT) でネイティブ コードを生成するコンパイラ ツール チェーン。</span><span class="sxs-lookup"><span data-stu-id="203ed-238">A compiler tool chain that produces native code ahead-of-time (AOT), as opposed to just-in-time (JIT).</span></span>

<span data-ttu-id="203ed-239">コンパイルは、C++ のコンパイラやリンカーと同様に、開発者のコンピューターで行われます。</span><span class="sxs-lookup"><span data-stu-id="203ed-239">Compilation happens on the developer's machine similar to the way a C++ compiler and linker works.</span></span> <span data-ttu-id="203ed-240">未使用のコードが削除され、より多くの時間がコードの最適化に費やされます。</span><span class="sxs-lookup"><span data-stu-id="203ed-240">It removes unused code and spends more time optimizing it.</span></span> <span data-ttu-id="203ed-241">ライブラリからコードを抽出し、実行可能ファイルにそれらをマージします。</span><span class="sxs-lookup"><span data-stu-id="203ed-241">It extracts code from libraries and merges them into the executable.</span></span> <span data-ttu-id="203ed-242">結果は、アプリ全体を表す 1 つのモジュールです。</span><span class="sxs-lookup"><span data-stu-id="203ed-242">The result is a single module that represents the entire app.</span></span>

<span data-ttu-id="203ed-243">UWP は、.NET Native によってサポートされる最初のアプリケーション フレームワークでした。</span><span class="sxs-lookup"><span data-stu-id="203ed-243">UWP was the first application framework supported by .NET Native.</span></span> <span data-ttu-id="203ed-244">現在では、Windows、macOS、Linux 用のネイティブ コンソール アプリの構築がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="203ed-244">Now, we support building native console apps for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="203ed-245">「[Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)」(.NET Native と CoreRT の概要) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="203ed-245">See [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span></span>

## <a name="net-standard"></a><span data-ttu-id="203ed-246">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="203ed-246">.NET Standard</span></span>

<span data-ttu-id="203ed-247">.NET の各実装で使用可能な .NET API の正式な仕様。</span><span class="sxs-lookup"><span data-stu-id="203ed-247">A formal specification of .NET APIs that are available in each .NET implementation.</span></span>

<span data-ttu-id="203ed-248">.NET Standard の仕様は、ドキュメントではライブラリとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="203ed-248">The .NET Standard specification is sometimes called a library in the documentation.</span></span> <span data-ttu-id="203ed-249">ライブラリには仕様 (インターフェイス) だけでなく API の実装も含まれるため、.NET Standard を "ライブラリ" と呼ぶのは誤解を招きます。</span><span class="sxs-lookup"><span data-stu-id="203ed-249">Because a library includes API implementations, not only specifications (interfaces), it's misleading to call .NET Standard a "library."</span></span> <span data-ttu-id="203ed-250">.NET Standard メタパッケージ (`NETStandard.Library`) の名前を参照する場合を除き、そのような使用法をドキュメントから消去する予定です。</span><span class="sxs-lookup"><span data-stu-id="203ed-250">We plan to eliminate that usage from the documentation, except in reference to the name of the .NET Standard metapackage (`NETStandard.Library`).</span></span>

<span data-ttu-id="203ed-251">「[.NET Standard](net-standard.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="203ed-251">See [.NET Standard](net-standard.md).</span></span>

## <a name="ngen"></a><span data-ttu-id="203ed-252">NGEN</span><span class="sxs-lookup"><span data-stu-id="203ed-252">NGEN</span></span>

<span data-ttu-id="203ed-253">ネイティブ (イメージ) 生成。</span><span class="sxs-lookup"><span data-stu-id="203ed-253">Native (image) generation.</span></span>

<span data-ttu-id="203ed-254">このテクノロジは、永続的な JIT コンパイラと考えることができます。</span><span class="sxs-lookup"><span data-stu-id="203ed-254">You can think of this technology as a persistent JIT compiler.</span></span> <span data-ttu-id="203ed-255">通常はコードが実行されるコンピューター上でコードをコンパイルしますが、一般にコンパイルはインストール時に行われます。</span><span class="sxs-lookup"><span data-stu-id="203ed-255">It usually compiles code on the machine where the code is executed, but compilation typically occurs at install time.</span></span>

## <a name="package"></a><span data-ttu-id="203ed-256">package</span><span class="sxs-lookup"><span data-stu-id="203ed-256">package</span></span>

<span data-ttu-id="203ed-257">NuGet パッケージ &mdash; または単にパッケージ &mdash; は、同じ名前の 1 つまたは複数のアセンブリと、作成者名などの追加メタデータを含む、 *.zip* ファイルです。</span><span class="sxs-lookup"><span data-stu-id="203ed-257">A NuGet package &mdash; or just a package &mdash; is a *.zip* file with one or more assemblies of the same name along with additional metadata such as the author name.</span></span>

<span data-ttu-id="203ed-258">*.zip* ファイルは、拡張子が *.nupkg* であり、複数のターゲット フレームワークとバージョンで使う *.dll* ファイルや *.xml* ファイルなどのアセットを含むことができます。</span><span class="sxs-lookup"><span data-stu-id="203ed-258">The *.zip* file has a *.nupkg* extension and may contain assets, such as *.dll* files and *.xml* files, for use with multiple target frameworks and versions.</span></span> <span data-ttu-id="203ed-259">アプリまたはライブラリでインストールされるときに、アプリまたはライブラリで指定されているターゲット フレームワークに基づいて適切なアセットが選択されます。</span><span class="sxs-lookup"><span data-stu-id="203ed-259">When installed in an app or library, the appropriate assets are selected based on the target framework specified by the app or library.</span></span> <span data-ttu-id="203ed-260">インターフェイスを定義するアセットは *ref* フォルダーにあり、実装を定義するアセットは *lib* フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="203ed-260">The assets that define the interface are in the *ref* folder, and the assets that define the implementation are in the *lib* folder.</span></span>

## <a name="platform"></a><span data-ttu-id="203ed-261">platform</span><span class="sxs-lookup"><span data-stu-id="203ed-261">platform</span></span>

<span data-ttu-id="203ed-262">オペレーティング システムとそれが動作するハードウェア (Windows、macOS、Linux、iOS、Android)。</span><span class="sxs-lookup"><span data-stu-id="203ed-262">An operating system and the hardware it runs on, such as Windows, macOS, Linux, iOS, and Android.</span></span>

<span data-ttu-id="203ed-263">文章での使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="203ed-263">Here are examples of usage in sentences:</span></span>

- <span data-ttu-id="203ed-264">".NET Core は、.NET のクロスプラットフォームの実装です。"</span><span class="sxs-lookup"><span data-stu-id="203ed-264">".NET Core is a cross-platform implementation of .NET."</span></span>
- <span data-ttu-id="203ed-265">"PCL プロファイルは Microsoft のプラットフォームを表し、.NET Standard はプラットフォームに依存しません。"</span><span class="sxs-lookup"><span data-stu-id="203ed-265">"PCL profiles represent Microsoft platforms, while the .NET Standard is agnostic to platform."</span></span>

<span data-ttu-id="203ed-266">.NET のドキュメントでは、.NET の実装またはすべての実装を含む .NET スタックの意味で ".NET プラットフォーム" が使われることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="203ed-266">The .NET documentation frequently uses ".NET platform" to mean either an implementation of .NET or the .NET stack including all implementations.</span></span> <span data-ttu-id="203ed-267">これらの使用法はどちらも本来の (OS/ハードウェア) の意味と紛らわしい場合があるので、ドキュメントから削除される予定です。</span><span class="sxs-lookup"><span data-stu-id="203ed-267">Both of these usages tend to get confused with the primary (OS/hardware) meaning, so we plan to eliminate these usages from the documentation.</span></span>

## <a name="runtime"></a><span data-ttu-id="203ed-268">ランタイム</span><span class="sxs-lookup"><span data-stu-id="203ed-268">runtime</span></span>

<span data-ttu-id="203ed-269">マネージド プログラムの実行環境。</span><span class="sxs-lookup"><span data-stu-id="203ed-269">The execution environment for a managed program.</span></span>

<span data-ttu-id="203ed-270">OS は、ランタイム環境の一部ですが、.NET ランタイムの一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="203ed-270">The OS is part of the runtime environment but is not part of the .NET runtime.</span></span> <span data-ttu-id="203ed-271">.NET ランタイムの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="203ed-271">Here are some examples of .NET runtimes:</span></span>

- <span data-ttu-id="203ed-272">共通言語ランタイム (CLR)</span><span class="sxs-lookup"><span data-stu-id="203ed-272">Common Language Runtime (CLR)</span></span>
- <span data-ttu-id="203ed-273">Core 共通言語ランタイム (CoreCLR)</span><span class="sxs-lookup"><span data-stu-id="203ed-273">Core Common Language Runtime (CoreCLR)</span></span>
- <span data-ttu-id="203ed-274">.NET Native (UWP の場合)</span><span class="sxs-lookup"><span data-stu-id="203ed-274">.NET Native (for UWP)</span></span>
- <span data-ttu-id="203ed-275">Mono ランタイム</span><span class="sxs-lookup"><span data-stu-id="203ed-275">Mono runtime</span></span>

<span data-ttu-id="203ed-276">.NET のドキュメントでは、.NET の実装の意味で "ランタイム" が使われることがあります。</span><span class="sxs-lookup"><span data-stu-id="203ed-276">The .NET documentation sometimes uses "runtime" to mean an implementation of .NET.</span></span> <span data-ttu-id="203ed-277">たとえば、次の文章の "ランタイム" は "実装" に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="203ed-277">For example, in the following sentences "runtime" should be replaced with "implementation":</span></span>

- <span data-ttu-id="203ed-278">"さまざまな .NET ランタイムで、.NET Standard の特定のバージョンが実装されます。"</span><span class="sxs-lookup"><span data-stu-id="203ed-278">"The various .NET runtimes implement specific versions of .NET Standard."</span></span>
- <span data-ttu-id="203ed-279">"複数のランタイムでの実行を意図したライブラリは、このフレームワークを対象とする必要があります。"</span><span class="sxs-lookup"><span data-stu-id="203ed-279">"Libraries that are intended to run on multiple runtimes should target this framework."</span></span> <span data-ttu-id="203ed-280">(.NET Standard を指している場合)</span><span class="sxs-lookup"><span data-stu-id="203ed-280">(referring to .NET Standard)</span></span>
- <span data-ttu-id="203ed-281">"さまざまな .NET ランタイムで、.NET Standard の特定のバージョンが実装されます。</span><span class="sxs-lookup"><span data-stu-id="203ed-281">"The various .NET runtimes implement specific versions of .NET Standard.</span></span> <span data-ttu-id="203ed-282">…</span><span class="sxs-lookup"><span data-stu-id="203ed-282">…</span></span> <span data-ttu-id="203ed-283">.NET ランタイムの各バージョンは、サポートしている .NET Standard の最高のバージョンをアドバタイズします …"</span><span class="sxs-lookup"><span data-stu-id="203ed-283">Each .NET runtime version advertises the highest .NET Standard version it supports …"</span></span>

<span data-ttu-id="203ed-284">このような一貫性のない使用法は除去される予定です。</span><span class="sxs-lookup"><span data-stu-id="203ed-284">We plan to eliminate this inconsistent usage.</span></span>

## <a name="stack"></a><span data-ttu-id="203ed-285">スタック</span><span class="sxs-lookup"><span data-stu-id="203ed-285">stack</span></span>

<span data-ttu-id="203ed-286">全体としてアプリケーションの構築と実行に使われるプログラミング テクノロジのセット。</span><span class="sxs-lookup"><span data-stu-id="203ed-286">A set of programming technologies that are used together to build and run applications.</span></span>

<span data-ttu-id="203ed-287">".NET スタック" は、.NET Standard および .NET のすべての実装を指します。</span><span class="sxs-lookup"><span data-stu-id="203ed-287">"The .NET stack" refers to the .NET Standard and all .NET implementations.</span></span> <span data-ttu-id="203ed-288">".NET スタック" という語句が .NET の 1 つの実装を示すこともあります。</span><span class="sxs-lookup"><span data-stu-id="203ed-288">The phrase "a .NET stack" may refer to one implementation of .NET.</span></span>

## <a name="target-framework"></a><span data-ttu-id="203ed-289">ターゲット フレームワーク</span><span class="sxs-lookup"><span data-stu-id="203ed-289">target framework</span></span>

<span data-ttu-id="203ed-290">.NET アプリまたはライブラリが依存する API のコレクション。</span><span class="sxs-lookup"><span data-stu-id="203ed-290">The collection of APIs that a .NET app or library relies on.</span></span>

<span data-ttu-id="203ed-291">アプリまたはライブラリは、.NET Standard の 1 つのバージョン (.NET Standard 2.0 など) をターゲットにできます。 .NET Standard は、.NET のすべての実装で標準化された API のセットの仕様です。</span><span class="sxs-lookup"><span data-stu-id="203ed-291">An app or library can target a version of .NET Standard (for example, .NET Standard 2.0), which is specification for a standardized set of APIs across all .NET implementations.</span></span> <span data-ttu-id="203ed-292">また、アプリまたはライブラリは、.NET の特定の実装のバージョンをターゲットにすることもでき、その場合は実装固有の API にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="203ed-292">An app or library can also target a version of a specific .NET implementation, in which case it gets access to implementation-specific APIs.</span></span> <span data-ttu-id="203ed-293">たとえば、Xamarin.iOS をターゲットにするアプリは、Xamarin が提供する iOS API ラッパーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="203ed-293">For example, an app that targets Xamarin.iOS gets access to Xamarin-provided iOS API wrappers.</span></span>

<span data-ttu-id="203ed-294">一部のターゲット フレームワーク (.NET Framework など) では、使用可能な API は .NET の実装がシステムにインストールするアセンブリによって定義され、アプリケーション フレームワーク API (たとえば ASP.NET、WinForms) を含む場合があります。</span><span class="sxs-lookup"><span data-stu-id="203ed-294">For some target frameworks (for example, the .NET Framework) the available APIs are defined by the assemblies that a .NET implementation installs on a system, which may include application framework APIs (for example, ASP.NET, WinForms).</span></span> <span data-ttu-id="203ed-295">パッケージ ベースのターゲット フレームワーク (.NET Standard、.NET Core など) では、フレームワーク API はアプリまたはライブラリでインストールされるパッケージによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="203ed-295">For package-based target frameworks (such as .NET Standard and .NET Core), the framework APIs are defined by the packages installed in the app or library.</span></span> <span data-ttu-id="203ed-296">その場合、ターゲット フレームワークでは、全体としてフレームワークを構成するすべてのパッケージを参照するメタパッケージが暗黙的に指定されます。</span><span class="sxs-lookup"><span data-stu-id="203ed-296">In that case, the target framework implicitly specifies a metapackage that references all the packages that together make up the framework.</span></span>

<span data-ttu-id="203ed-297">「[ターゲット フレームワーク](frameworks.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="203ed-297">See [Target Frameworks](frameworks.md).</span></span>

## <a name="tfm"></a><span data-ttu-id="203ed-298">TFM</span><span class="sxs-lookup"><span data-stu-id="203ed-298">TFM</span></span>

<span data-ttu-id="203ed-299">ターゲット フレームワーク モニカー (Target Framework Moniker)。</span><span class="sxs-lookup"><span data-stu-id="203ed-299">Target framework moniker.</span></span>

<span data-ttu-id="203ed-300">.NET アプリまたはライブラリのターゲット フレームワークを指定するための標準化されたトークン形式。</span><span class="sxs-lookup"><span data-stu-id="203ed-300">A standardized token format for specifying the target framework of a .NET app or library.</span></span> <span data-ttu-id="203ed-301">通常、ターゲット フレームワークは短い名前によって参照されます (`net462` など)。</span><span class="sxs-lookup"><span data-stu-id="203ed-301">Target frameworks are typically referenced by a short name, such as `net462`.</span></span> <span data-ttu-id="203ed-302">長い形式の TFM (.NETFramework,Version=4.6.2 など) も存在しますが、一般に、ターゲット フレームワークの指定には使われません。</span><span class="sxs-lookup"><span data-stu-id="203ed-302">Long-form TFMs (such as .NETFramework,Version=4.6.2) exist but are not generally used to specify a target framework.</span></span>

<span data-ttu-id="203ed-303">「[ターゲット フレームワーク](frameworks.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="203ed-303">See [Target Frameworks](frameworks.md).</span></span>

## <a name="uwp"></a><span data-ttu-id="203ed-304">UWP</span><span class="sxs-lookup"><span data-stu-id="203ed-304">UWP</span></span>

<span data-ttu-id="203ed-305">ユニバーサル Windows プラットフォーム (Universal Windows Platform)。</span><span class="sxs-lookup"><span data-stu-id="203ed-305">Universal Windows Platform.</span></span>

<span data-ttu-id="203ed-306">モノのインターネット (IoT) のために最新のタッチ対応の Windows アプリケーションとソフトウェアを構築するために使われる .NET の実装。</span><span class="sxs-lookup"><span data-stu-id="203ed-306">An implementation of .NET that is used for building modern, touch-enabled Windows applications and software for the Internet of Things (IoT).</span></span> <span data-ttu-id="203ed-307">PC、タブレット、ファブレット、携帯電話、Xbox など、ターゲットにする可能性があるさまざまな種類のデバイスを統一するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="203ed-307">It's designed to unify the different types of devices that you may want to target, including PCs, tablets, phablets, phones, and even the Xbox.</span></span> <span data-ttu-id="203ed-308">UWP は、一元的なアプリ ストア、実行環境 (AppContainer)、Win32 の代わりに使う Windows API のセット (WinRT) など、多くのサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="203ed-308">UWP provides many services, such as a centralized app store, an execution environment (AppContainer), and a set of Windows APIs to use instead of Win32 (WinRT).</span></span> <span data-ttu-id="203ed-309">アプリは、C++、C#、Visual Basic、および JavaScript で記述することができます。</span><span class="sxs-lookup"><span data-stu-id="203ed-309">Apps can be written in C++, C#, Visual Basic, and JavaScript.</span></span> <span data-ttu-id="203ed-310">C# と Visual Basic を使うときは、.NET Core によって .NET API が提供されます。</span><span class="sxs-lookup"><span data-stu-id="203ed-310">When using C# and Visual Basic, the .NET APIs are provided by .NET Core.</span></span>

## <a name="see-also"></a><span data-ttu-id="203ed-311">関連項目</span><span class="sxs-lookup"><span data-stu-id="203ed-311">See also</span></span>

- [<span data-ttu-id="203ed-312">.NET のガイド</span><span class="sxs-lookup"><span data-stu-id="203ed-312">.NET Guide</span></span>](index.md)
- [<span data-ttu-id="203ed-313">.NET Framework ガイド</span><span class="sxs-lookup"><span data-stu-id="203ed-313">.NET Framework Guide</span></span>](../framework/index.md)
- [<span data-ttu-id="203ed-314">.NET Core</span><span class="sxs-lookup"><span data-stu-id="203ed-314">.NET Core</span></span>](../core/index.md)
- [<span data-ttu-id="203ed-315">ASP.NET の概要</span><span class="sxs-lookup"><span data-stu-id="203ed-315">ASP.NET Overview</span></span>](/aspnet/index#pivot=aspnet)
- [<span data-ttu-id="203ed-316">ASP.NET Core の概要</span><span class="sxs-lookup"><span data-stu-id="203ed-316">ASP.NET Core Overview</span></span>](/aspnet/index#pivot=core)
