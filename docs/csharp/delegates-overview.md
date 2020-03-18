---
title: デリゲートの概要
description: この概要トピックでは、基本的な概念を紹介し、デリゲートの言語上の設計目標について説明します。
ms.date: 06/20/2016
ms.technology: csharp-fundamentals
ms.assetid: 59b61d77-84e5-457b-8da5-fb5f24ca6ed6
ms.openlocfilehash: fd594f77c034533a1d5aee1d8279e9b727284311
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146230"
---
# <a name="introduction-to-delegates"></a><span data-ttu-id="e3b47-103">デリゲートの概要</span><span class="sxs-lookup"><span data-stu-id="e3b47-103">Introduction to Delegates</span></span>

<span data-ttu-id="e3b47-104">デリゲートは、.NET における "*遅延バインディング*" のメカニズムです。</span><span class="sxs-lookup"><span data-stu-id="e3b47-104">Delegates provide a *late binding* mechanism in .NET.</span></span> <span data-ttu-id="e3b47-105">遅延バインディングとは、皆さんが作成するアルゴリズムについて、その一部を実装するメソッドを呼び出し元からも少なくとも 1 つ与えることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e3b47-105">Late Binding means that you create an algorithm where the caller also supplies at least one method that implements part of the algorithm.</span></span>

<span data-ttu-id="e3b47-106">たとえば天文学アプリケーションで、一連の星を並べ替えることを考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="e3b47-106">For example, consider sorting a list of stars in an astronomy application.</span></span>
<span data-ttu-id="e3b47-107">星の並べ替え基準には、地球からの距離や星の等級、知覚的な明るさを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="e3b47-107">You may choose to sort those stars by their distance from the earth, or the magnitude of the star, or their perceived brightness.</span></span>

<span data-ttu-id="e3b47-108">いずれの場合も、Sort() メソッドが行うことは基本的に同じです。つまり何らかの比較に基づいて一連の項目を整列します。</span><span class="sxs-lookup"><span data-stu-id="e3b47-108">In all those cases, the Sort() method does essentially the same thing: arranges the items in the list based on some comparison.</span></span> <span data-ttu-id="e3b47-109">しかし、2 つの星を比較するコードは、並べ替えの基準によって異なります。</span><span class="sxs-lookup"><span data-stu-id="e3b47-109">The code that compares two stars is different for each of the sort orderings.</span></span>

<span data-ttu-id="e3b47-110">ソフトウェアには、この種の手法が半世紀にわたって使用されてきました。</span><span class="sxs-lookup"><span data-stu-id="e3b47-110">These kinds of solutions have been used in software for half a century.</span></span>
<span data-ttu-id="e3b47-111">C# 言語のデリゲートの概念は、きわめて優れた言語機能と、その概念を中心にしたタイプ セーフ機能を実現します。</span><span class="sxs-lookup"><span data-stu-id="e3b47-111">The C# language delegate concept provides first class language support, and type safety around the concept.</span></span>

<span data-ttu-id="e3b47-112">本シリーズの中で後述しているように、このようなアルゴリズム向けに記述された C# コードはタイプ セーフであり、引数や戻り値の型については、言語とコンパイラの機能を利用して型の一致が保証されます。</span><span class="sxs-lookup"><span data-stu-id="e3b47-112">As you'll see later in this series, the C# code you write for algorithms like this is type safe, and leverages the language and the compiler to ensure that the types match for arguments and return types.</span></span>

## <a name="language-design-goals-for-delegates"></a><span data-ttu-id="e3b47-113">デリゲートの言語上の設計目標</span><span class="sxs-lookup"><span data-stu-id="e3b47-113">Language Design Goals for Delegates</span></span>

<span data-ttu-id="e3b47-114">最終的にデリゲートとなる機能を実現するにあたって、言語の設計者たちはさまざまな目標を設定しました。</span><span class="sxs-lookup"><span data-stu-id="e3b47-114">The language designers enumerated several goals for the feature that eventually became delegates.</span></span>

<span data-ttu-id="e3b47-115">設計チームが目指したのは、あらゆる遅延バインディング アルゴリズムに適用できる共通の言語概念です。</span><span class="sxs-lookup"><span data-stu-id="e3b47-115">The team wanted a common language construct that could be used for any late binding algorithms.</span></span> <span data-ttu-id="e3b47-116">つまり、開発者が 1 つの概念を身に付ければ、ソフトウェアに関するさまざまな課題にその知識を応用できるような言語の実現を目標に掲げたのです。</span><span class="sxs-lookup"><span data-stu-id="e3b47-116">That enables developers to learn one concept, and use that same concept across many different software problems.</span></span>

<span data-ttu-id="e3b47-117">次に設計チームが目指したのは、シングルキャストとマルチキャストの両方のメソッド呼び出しをサポートすることでした。</span><span class="sxs-lookup"><span data-stu-id="e3b47-117">Second, the team wanted to support both single and multicast method calls.</span></span> <span data-ttu-id="e3b47-118">(マルチキャスト デリゲートは、複数のメソッド呼び出しを連結するデリゲートです。</span><span class="sxs-lookup"><span data-stu-id="e3b47-118">(Multicast delegates are delegates that chain together multiple method calls.</span></span>
<span data-ttu-id="e3b47-119">[このシリーズの後の記事](delegate-class.md)で例を見ます。)</span><span class="sxs-lookup"><span data-stu-id="e3b47-119">You'll see examples [later in this series](delegate-class.md).)</span></span>

<span data-ttu-id="e3b47-120">設計チームは、C# のあらゆるコード要素に関して開発者たちが当然と考えるレベルのタイプ セーフティをデリゲートにおいても実現したいと考えていたのです。</span><span class="sxs-lookup"><span data-stu-id="e3b47-120">The team wanted delegates to support the same type safety that developers expect from all C# constructs.</span></span>

<span data-ttu-id="e3b47-121">また、設計チームは、デリゲートを初めとする遅延バインディング アルゴリズムの利便性が大いに発揮される具体的なパターンは、イベント パターンであると認識していました。</span><span class="sxs-lookup"><span data-stu-id="e3b47-121">Finally, the team recognized that an event pattern is one specific pattern where delegates, or any late binding algorithm, is very useful.</span></span> <span data-ttu-id="e3b47-122">.NET のイベントの基本的なパターンをデリゲートのコードで確実に実現したいと考えていたのです。</span><span class="sxs-lookup"><span data-stu-id="e3b47-122">The team wanted to ensure that the code for delegates could provide the basis for the .NET event pattern.</span></span>

<span data-ttu-id="e3b47-123">そうした目標に向けたすべての作業の成果として C# と .NET にサポートされたのが、デリゲートとイベントです。</span><span class="sxs-lookup"><span data-stu-id="e3b47-123">The result of all that work was the delegate and event support in C# and .NET.</span></span> <span data-ttu-id="e3b47-124">以降このセクションの記事では、言語の機能やライブラリのサポート、デリゲートを扱う際に用いられる一般的な用語について取り上げています。</span><span class="sxs-lookup"><span data-stu-id="e3b47-124">The remaining articles in this section will cover the language features, the library support, and the common idioms that are used when you work with delegates.</span></span>

<span data-ttu-id="e3b47-125">`delegate` キーワードとそれによって生成されるコード、</span><span class="sxs-lookup"><span data-stu-id="e3b47-125">You'll learn about the `delegate` keyword and what code it generates.</span></span> <span data-ttu-id="e3b47-126">`System.Delegate` クラスの機能とその使い方、</span><span class="sxs-lookup"><span data-stu-id="e3b47-126">You'll learn about the features in the `System.Delegate` class, and how those features are used.</span></span> <span data-ttu-id="e3b47-127">タイプ セーフなデリゲートの作成方法、デリゲート経由で呼び出すことのできるメソッドの作成方法のほか、</span><span class="sxs-lookup"><span data-stu-id="e3b47-127">You'll learn how to create type safe delegates, and how to create methods that can be invoked through delegates.</span></span> <span data-ttu-id="e3b47-128">ラムダ式を使ったデリゲートやイベントの扱い方、</span><span class="sxs-lookup"><span data-stu-id="e3b47-128">You'll also learn how to work with delegates and events by using Lambda expressions.</span></span> <span data-ttu-id="e3b47-129">LINQ の構成要素としてデリゲートがどこで使われているか、</span><span class="sxs-lookup"><span data-stu-id="e3b47-129">You'll see where delegates become one of the building blocks for LINQ.</span></span> <span data-ttu-id="e3b47-130">.NET のイベント パターンの基礎としてデリゲートがどのように使われ、両者がどのように違うのかについても説明します。</span><span class="sxs-lookup"><span data-stu-id="e3b47-130">You'll learn how delegates are the basis for the .NET event pattern, and how they are different.</span></span>

<span data-ttu-id="e3b47-131">すべての記事を読み終えると、.NET のプログラミングやフレームワーク API を利用するうえでの不可欠な要素として、デリゲートがどのように活かされているのかがおわかりいただけると思います。</span><span class="sxs-lookup"><span data-stu-id="e3b47-131">Overall, you'll see how delegates are an integral part of programming in .NET and working with the framework APIs.</span></span>

<span data-ttu-id="e3b47-132">それでは始めましょう。</span><span class="sxs-lookup"><span data-stu-id="e3b47-132">Let's get started.</span></span>

[<span data-ttu-id="e3b47-133">次へ</span><span class="sxs-lookup"><span data-stu-id="e3b47-133">Next</span></span>](delegate-class.md)
