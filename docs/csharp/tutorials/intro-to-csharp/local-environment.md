---
title: C# の概要 - 開発ツールに対する理解を深める
description: この記事では、コンピューターで C# アプリケーションと .NET アプリケーションを開発するためのツールの基礎を提供します。
ms.date: 10/23/2018
ms.openlocfilehash: 0b1df9e733eef92b1eeb0a7f3ba3ba49602f219d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156572"
---
# <a name="become-familiar-with-the-net-development-tools"></a><span data-ttu-id="93bb1-103">.NET 開発ツールに対する理解を深める</span><span class="sxs-lookup"><span data-stu-id="93bb1-103">Become familiar with the .NET development tools</span></span>

<span data-ttu-id="93bb1-104">コンピューターでチュートリアルを実行する最初の手順は、開発環境を設定することです。</span><span class="sxs-lookup"><span data-stu-id="93bb1-104">The first step in running a tutorial on your machine is to set up a development environment.</span></span>
<span data-ttu-id="93bb1-105">Windows、Linux、または macOS 上でローカルの開発環境を設定する手順については、.NET チュートリアル [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) (10 分で Hello World) に記載されています。</span><span class="sxs-lookup"><span data-stu-id="93bb1-105">The .NET tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) has instructions for setting up your local development environment on Windows, Linux, or macOS.</span></span>

<span data-ttu-id="93bb1-106">または、[.NET Core SDK](https://dotnet.microsoft.com/download) と [Visual Studio Code](https://code.visualstudio.com/) をインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="93bb1-106">Alternatively, you can install the [.NET Core SDK](https://dotnet.microsoft.com/download) and [Visual Studio Code](https://code.visualstudio.com/).</span></span>

## <a name="basic-application-development-flow"></a><span data-ttu-id="93bb1-107">アプリケーション開発の基本フロー</span><span class="sxs-lookup"><span data-stu-id="93bb1-107">Basic application development flow</span></span>

<span data-ttu-id="93bb1-108">[`dotnet new`](../../../core/tools/dotnet-new.md) コマンドを使用してアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="93bb1-108">You'll create applications using the [`dotnet new`](../../../core/tools/dotnet-new.md) command.</span></span> <span data-ttu-id="93bb1-109">このコマンドによってアプリケーションに必要なファイルとアセットが生成されます。</span><span class="sxs-lookup"><span data-stu-id="93bb1-109">This command generates the files and assets necessary for your application.</span></span> <span data-ttu-id="93bb1-110">C# の概要チュートリアルではすべて、アプリケーションの種類 `console` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="93bb1-110">The introduction to C# tutorials all use the `console` application type.</span></span> <span data-ttu-id="93bb1-111">基本を習得したら、他の種類のアプリケーションに応用できます。</span><span class="sxs-lookup"><span data-stu-id="93bb1-111">Once you've got the basics, you can expand to other application types.</span></span>

<span data-ttu-id="93bb1-112">その他には、実行可能ファイルをビルドする [`dotnet build`](../../../core/tools/dotnet-build.md) コマンド、実行可能ファイルを実行する [`dotnet run`](../../../core/tools/dotnet-run.md) コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="93bb1-112">The other commands you'll use are [`dotnet build`](../../../core/tools/dotnet-build.md) to build the executable, and [`dotnet run`](../../../core/tools/dotnet-run.md) to run the executable.</span></span>

## <a name="pick-your-tutorial"></a><span data-ttu-id="93bb1-113">チュートリアルを選択する</span><span class="sxs-lookup"><span data-stu-id="93bb1-113">Pick your tutorial</span></span>

<span data-ttu-id="93bb1-114">最初に次のいずれかのチュートリアルを選択します。</span><span class="sxs-lookup"><span data-stu-id="93bb1-114">You can start with any of the following tutorials:</span></span>

## <a name="numbers-in-c"></a>[<span data-ttu-id="93bb1-115">C# における数値</span><span class="sxs-lookup"><span data-stu-id="93bb1-115">Numbers in C#</span></span>](numbers-in-csharp-local.md)

<span data-ttu-id="93bb1-116">「[C# における数値](numbers-in-csharp-local.md)」チュートリアルでは、コンピューターが数値を格納する方法と、異なる数値型で計算を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="93bb1-116">In the [Numbers in C#](numbers-in-csharp-local.md) tutorial, you'll learn how computers store numbers and how to perform calculations with different numeric types.</span></span> <span data-ttu-id="93bb1-117">丸めの基本と C# を使用した数学計算方法を学習します。</span><span class="sxs-lookup"><span data-stu-id="93bb1-117">You'll learn the basics of rounding and how to perform mathematical calculations using C#.</span></span>

<span data-ttu-id="93bb1-118">このチュートリアルでは、「[Hello World](hello-world.yml)」レッスンが終了していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="93bb1-118">This tutorial assumes that you have finished the [Hello world](hello-world.yml) lesson.</span></span>

## <a name="branches-and-loops"></a>[<span data-ttu-id="93bb1-119">分岐とループ</span><span class="sxs-lookup"><span data-stu-id="93bb1-119">Branches and loops</span></span>](branches-and-loops-local.md)

<span data-ttu-id="93bb1-120">「[分岐とループ](branches-and-loops-local.md)」のチュートリアルでは、変数に格納された値に基づいて、さまざまなパスでコードを実行するための基礎について説明します。</span><span class="sxs-lookup"><span data-stu-id="93bb1-120">The [Branches and loops](branches-and-loops-local.md) tutorial teaches the basics of selecting different paths of code execution based on the values stored in variables.</span></span> <span data-ttu-id="93bb1-121">プログラムが決定して異なる操作を選択する上で基本となる、制御フローの基礎を学習します。</span><span class="sxs-lookup"><span data-stu-id="93bb1-121">You'll learn the basics of control flow, which is the basis of how programs make decisions and choose different actions.</span></span>

<span data-ttu-id="93bb1-122">このチュートリアルでは、「[Hello World](hello-world.yml)」レッスンと「[C# における数値](numbers-in-csharp-local.md)」レッスンを終了していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="93bb1-122">This tutorial assumes that you have finished the [Hello world](hello-world.yml) and [Numbers in C#](numbers-in-csharp-local.md) lessons.</span></span>

## <a name="list-collection"></a>[<span data-ttu-id="93bb1-123">リスト コレクション</span><span class="sxs-lookup"><span data-stu-id="93bb1-123">List collection</span></span>](arrays-and-collections.md)

<span data-ttu-id="93bb1-124">「[リスト コレクション](arrays-and-collections.md)」レッスンでは、データのシーケンスを格納するリスト コレクション型について説明します。</span><span class="sxs-lookup"><span data-stu-id="93bb1-124">The [List collection](arrays-and-collections.md) lesson gives you a tour of the List collection type that stores sequences of data.</span></span> <span data-ttu-id="93bb1-125">項目の追加方法や削除方法、項目の検索方法、リストを並べ替える方法を学習します。</span><span class="sxs-lookup"><span data-stu-id="93bb1-125">You'll learn how to add and remove items, search for items, and sort the lists.</span></span> <span data-ttu-id="93bb1-126">さまざまな種類のリストを紹介します。</span><span class="sxs-lookup"><span data-stu-id="93bb1-126">You'll explore different kinds of lists.</span></span>

<span data-ttu-id="93bb1-127">このチュートリアルでは、上に挙げたレッスンを終了していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="93bb1-127">This tutorial assumes that you have finished the lessons listed above.</span></span>

## <a name="introduction-to-classes"></a>[<span data-ttu-id="93bb1-128">クラスの概要</span><span class="sxs-lookup"><span data-stu-id="93bb1-128">Introduction to classes</span></span>](introduction-to-classes.md)

<span data-ttu-id="93bb1-129">この C# 概要の最後のチュートリアルはお使いのコンピューターでのみ実行できます。自分のローカル開発環境と .NET Core を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93bb1-129">This final introduction to C# tutorial is only available to run on your machine, using your own local development environment and .NET Core.</span></span>
<span data-ttu-id="93bb1-130">コンソール アプリケーションを構築し、C# 言語に含まれるオブジェクト指向の基本的な機能について学習します。</span><span class="sxs-lookup"><span data-stu-id="93bb1-130">You'll build a console application and see the basic object-oriented features that are part of the C# language.</span></span>
