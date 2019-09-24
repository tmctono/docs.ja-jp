---
title: 概要 - C# ガイド
description: 短期間で C# の概念について学習でき、.NET Core アプリケーションを作成することができるようになるような、短くて簡単なチュートリアルを探します。
helpviewer_keywords:
- Visual C#, getting started
- getting started, Visual C#
author: rpetrusha
ms.author: ronpet
ms.date: 04/05/2019
ms.custom: seoapril2019
ms.openlocfilehash: b921db9abb65a1d470ada86784ecba1b649c9f09
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182439"
---
# <a name="get-started-with-c"></a><span data-ttu-id="43bb9-103">C\# の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="43bb9-103">Get started with C\#</span></span>

<span data-ttu-id="43bb9-104">このセクションでは、C# と .NET Core を使用して短時間でアプリケーションを構築できる、短いシンプルなチュートリアルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="43bb9-104">This section provides short, simple tutorials that let you quickly build an application using C# and .NET Core.</span></span> <span data-ttu-id="43bb9-105">Visual Studio 2017 と Visual Studio Code については、その概要を説明しているトピックがあります。</span><span class="sxs-lookup"><span data-stu-id="43bb9-105">There are getting started topics for Visual Studio 2017 and Visual Studio Code.</span></span> <span data-ttu-id="43bb9-106">これらの記事は、ある程度のプログラミング経験を仮定しています。</span><span class="sxs-lookup"><span data-stu-id="43bb9-106">These articles assume some programming experience.</span></span> <span data-ttu-id="43bb9-107">初めてプログラミングを行う場合は、[C# の概要](../tutorials/intro-to-csharp/index.md)に関する対話型チュートリアルをお試しください。</span><span class="sxs-lookup"><span data-stu-id="43bb9-107">If you are new to programming, try our [introduction to C#](../tutorials/intro-to-csharp/index.md) interactive tutorials.</span></span>

<span data-ttu-id="43bb9-108">次のトピックを参照できます。</span><span class="sxs-lookup"><span data-stu-id="43bb9-108">The following topics are available:</span></span>

- [<span data-ttu-id="43bb9-109">C# 言語と .NET Framework の概要</span><span class="sxs-lookup"><span data-stu-id="43bb9-109">Introduction to the C# Language and the .NET Framework</span></span>](introduction-to-the-csharp-language-and-the-net-framework.md)

     <span data-ttu-id="43bb9-110">C# 言語および .NET の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="43bb9-110">Provides an overview of the C# language and .NET.</span></span>

- [<span data-ttu-id="43bb9-111">Visual Studio 2017 での .NET Core を使用した C# Hello World アプリケーションの構築</span><span class="sxs-lookup"><span data-stu-id="43bb9-111">Building a C# Hello World application with .NET Core in Visual Studio 2017</span></span>](../../core/tutorials/with-visual-studio.md)

   <span data-ttu-id="43bb9-112">Visual Studio では、Windows または Mac 統合開発環境で、アプリケーションのコーディング、コンパイル、実行、デバッグ、プロファイル、発行を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="43bb9-112">Visual Studio lets you code, compile, run, debug, profile, and publish your applications from an integrated development environment for Windows or Mac.</span></span>

   <span data-ttu-id="43bb9-113">このトピックでは、単純な Hello World アプリケーションを作成して実行した後、やや対話的な Hello World アプリケーションとして実行するための修正を行います。</span><span class="sxs-lookup"><span data-stu-id="43bb9-113">The topic lets you create and run a simple Hello World application and then modify it to run a slightly more interactive Hello World application.</span></span> <span data-ttu-id="43bb9-114">アプリケーションのビルドと実行が完了したら、[デバッグ](../../core/tutorials/debugging-with-visual-studio.md)方法と[発行](../../core/tutorials/publishing-with-visual-studio.md)方法も学習することで、.NET Core でサポートされている任意のプラットフォームでアプリケーションを実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="43bb9-114">Once you've finished building and running your application, you can also learn how to [debug it](../../core/tutorials/debugging-with-visual-studio.md) and how to [publish it](../../core/tutorials/publishing-with-visual-studio.md) so that it can be run on any platform supported by .NET Core.</span></span>

- [<span data-ttu-id="43bb9-115">Visual Studio 2017 での C# と .NET Core を使用したクラス ライブラリの構築</span><span class="sxs-lookup"><span data-stu-id="43bb9-115">Building a class library with C# and .NET Core in Visual Studio 2017</span></span>](../../core/tutorials/library-with-visual-studio.md)

   <span data-ttu-id="43bb9-116">クラス ライブラリを使用して、別のアプリケーションから呼び出すことができる型と型のメンバーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="43bb9-116">A class library lets you define types and type members that can be called from another application.</span></span> <span data-ttu-id="43bb9-117">このトピックでは、文字列が大文字で始まるかどうかを決定する単一のメソッドがあるクラス ライブラリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="43bb9-117">This topic lets you create a class library with a single method that determines whether a string begins with an uppercase character.</span></span> <span data-ttu-id="43bb9-118">ライブラリの構築が完了したら、[単体テスト](../../core/tutorials/testing-library-with-visual-studio.md)を開発して、それが期待どおりに動作することを確認した後、[そのライブラリを使用したいアプリケーション](../../core/tutorials/consuming-library-with-visual-studio.md)で使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="43bb9-118">Once you've finished building the library, you can develop a [unit test](../../core/tutorials/testing-library-with-visual-studio.md) to ensure that it works as expected, and then you can make it available to [applications that want to consume it](../../core/tutorials/consuming-library-with-visual-studio.md).</span></span>

- [<span data-ttu-id="43bb9-119">C# および Visual Studio Code の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="43bb9-119">Get started with C# and Visual Studio Code</span></span>](../../core/tutorials/with-visual-studio-code.md)

   <span data-ttu-id="43bb9-120">Visual Studio Code は、最新の Web アプリケーションやクラウド アプリケーションのビルドとデバッグ向けに最適化された無料コード エディターです。</span><span class="sxs-lookup"><span data-stu-id="43bb9-120">Visual Studio Code is a free code editor optimized for building and debugging modern web and cloud applications.</span></span> <span data-ttu-id="43bb9-121">IntelliSense をサポートしており、Linux、macOS、Windows で使用できます。</span><span class="sxs-lookup"><span data-stu-id="43bb9-121">It supports IntelliSense and is available for Linux, macOS, and Windows.</span></span>

   <span data-ttu-id="43bb9-122">このトピックでは、Visual Studio Code と .NET Core を使用して、単純な Hello World アプリケーションを作成して実行する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="43bb9-122">This topic shows you how to create and run a simple Hello World application with Visual Studio Code and .NET Core.</span></span>

## <a name="related-sections"></a><span data-ttu-id="43bb9-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="43bb9-123">Related sections</span></span>

- [<span data-ttu-id="43bb9-124">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="43bb9-124">C# Programming Guide</span></span>](../programming-guide/index.md)

    <span data-ttu-id="43bb9-125">C# プログラミングの概念に関する情報を提供し、C# でさまざまなタスクを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="43bb9-125">Provides information about C# programming concepts, and describes how to perform various tasks in C#.</span></span>

- [<span data-ttu-id="43bb9-126">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="43bb9-126">C# Reference</span></span>](../language-reference/index.md)

    <span data-ttu-id="43bb9-127">C# のキーワード、演算子、プリプロセッサ ディレクティブ、コンパイラ オプション、およびコンパイラのエラーと警告に関する詳細なリファレンス情報を紹介します。</span><span class="sxs-lookup"><span data-stu-id="43bb9-127">Provides detailed reference information about C# keywords, operators, preprocessor directives, compiler options, and compiler errors and warnings.</span></span>

- [<span data-ttu-id="43bb9-128">チュートリアル</span><span class="sxs-lookup"><span data-stu-id="43bb9-128">Walkthroughs</span></span>](../walkthroughs.md)

    <span data-ttu-id="43bb9-129">C# を使用するプログラミングのチュートリアルと、各チュートリアルに関する簡単な説明へのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="43bb9-129">Provides links to programming walkthroughs that use C# and a brief description of each walkthrough.</span></span>

## <a name="see-also"></a><span data-ttu-id="43bb9-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="43bb9-130">See also</span></span>

- [<span data-ttu-id="43bb9-131">Visual Studio を使用した C# 開発</span><span class="sxs-lookup"><span data-stu-id="43bb9-131">C# Development with Visual Studio</span></span>](/visualstudio/get-started/csharp/)
