---
title: LINQ の使用
description: このチュートリアルでは、LINQ を使用してシーケンスを生成し、LINQ クエリで使用するためのメソッドを作成し、先行評価と遅延評価を区別する方法を説明します。
ms.date: 10/29/2018
ms.assetid: 0db12548-82cb-4903-ac88-13103d70aa77
ms.openlocfilehash: e37c013add02f651875db7b908ae2b49711d996d
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2019
ms.locfileid: "67609308"
---
# <a name="working-with-linq"></a><span data-ttu-id="d4b17-103">LINQ の使用</span><span class="sxs-lookup"><span data-stu-id="d4b17-103">Working with LINQ</span></span>

## <a name="introduction"></a><span data-ttu-id="d4b17-104">はじめに</span><span class="sxs-lookup"><span data-stu-id="d4b17-104">Introduction</span></span>

<span data-ttu-id="d4b17-105">このチュートリアルでは、.NET Core と C# 言語の機能を説明します。</span><span class="sxs-lookup"><span data-stu-id="d4b17-105">This tutorial teaches you features in .NET Core and the C# language.</span></span> <span data-ttu-id="d4b17-106">内容は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d4b17-106">You’ll learn:</span></span>

- <span data-ttu-id="d4b17-107">LINQ を使用してシーケンスを生成する方法。</span><span class="sxs-lookup"><span data-stu-id="d4b17-107">How to generate sequences with LINQ.</span></span>
- <span data-ttu-id="d4b17-108">LINQ クエリで簡単に使用できるメソッドを記述する方法</span><span class="sxs-lookup"><span data-stu-id="d4b17-108">How to write methods that can be easily used in LINQ queries.</span></span>
- <span data-ttu-id="d4b17-109">先行評価と遅延評価を区別する方法</span><span class="sxs-lookup"><span data-stu-id="d4b17-109">How to distinguish between eager and lazy evaluation.</span></span>

<span data-ttu-id="d4b17-110">これらの方法を、マジシャンの基本的スキルの 1 つである[ファロ― シャッフル](https://en.wikipedia.org/wiki/Faro_shuffle)を再現するアプリケーションを作成しながら学習していきます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-110">You'll learn these techniques by building an application that demonstrates one of the basic skills of any magician: the [faro shuffle](https://en.wikipedia.org/wiki/Faro_shuffle).</span></span> <span data-ttu-id="d4b17-111">ファロ― シャッフルとは、簡単に言うと、カード デッキを正確に 2 等分し、双方のデッキから 1 枚ずつ交互に並ぶようにシャッフルして、元のデッキを並べ替えることです。</span><span class="sxs-lookup"><span data-stu-id="d4b17-111">Briefly, a faro shuffle is a technique where you split a card deck exactly in half, then the shuffle interleaves each one card from each half to rebuild the original deck.</span></span>

<span data-ttu-id="d4b17-112">マジシャンがこの手法を使用するのは、シャッフルした後もそれぞれのカードの位置がわかり、カードの順序が繰り返しのパターンになるからです。</span><span class="sxs-lookup"><span data-stu-id="d4b17-112">Magicians use this technique because every card is in a known location after each shuffle, and the order is a repeating pattern.</span></span>

<span data-ttu-id="d4b17-113">ここでは、データ シーケンスの操作として気軽に見ていきましょう。</span><span class="sxs-lookup"><span data-stu-id="d4b17-113">For your purposes, it is a light hearted look at manipulating sequences of data.</span></span> <span data-ttu-id="d4b17-114">これから作成するアプリケーションでは、カード デッキを構築し、シャッフルのシーケンスを実行し、その都度シーケンスを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-114">The application you'll build will construct a card deck, and then perform a sequence of shuffles, writing the sequence out each time.</span></span> <span data-ttu-id="d4b17-115">また、更新された順序を元の順序と比較します。</span><span class="sxs-lookup"><span data-stu-id="d4b17-115">You'll also compare the updated order to the original order.</span></span>

<span data-ttu-id="d4b17-116">このチュートリアルには、複数の手順があります。</span><span class="sxs-lookup"><span data-stu-id="d4b17-116">This tutorial has multiple steps.</span></span> <span data-ttu-id="d4b17-117">各手順の後に、アプリケーションを実行して進行状況を確認できます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-117">After each step, you can run the application and see the progress.</span></span> <span data-ttu-id="d4b17-118">GitHub の dotnet/samples リポジトリでは、[完全版のサンプル](https://github.com/dotnet/samples/blob/master/csharp/getting-started/console-linq)を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-118">You can also see the [completed sample](https://github.com/dotnet/samples/blob/master/csharp/getting-started/console-linq) in the dotnet/samples GitHub repository.</span></span> <span data-ttu-id="d4b17-119">ダウンロード方法については、「[サンプルおよびチュートリアル](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4b17-119">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d4b17-120">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d4b17-120">Prerequisites</span></span>

<span data-ttu-id="d4b17-121">お使いのコンピューターを、.NET Core が実行されるように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4b17-121">You’ll need to setup your machine to run .NET core.</span></span> <span data-ttu-id="d4b17-122">インストールの手順については、[.NET Core](https://www.microsoft.com/net/core) のページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4b17-122">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span> <span data-ttu-id="d4b17-123">このアプリケーションは、Windows、Ubuntu Linux、OS X または Docker コンテナーで実行できます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-123">You can run this application on Windows, Ubuntu Linux, OS X or in a Docker container.</span></span> <span data-ttu-id="d4b17-124">お好みのコード エディターをインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="d4b17-124">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="d4b17-125">次の説明では、オープン ソースのクロス プラットフォーム エディターである [Visual Studio Code](https://code.visualstudio.com/) を使用しています。</span><span class="sxs-lookup"><span data-stu-id="d4b17-125">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="d4b17-126">しかし、他の使い慣れたツールを使用しても構いません。</span><span class="sxs-lookup"><span data-stu-id="d4b17-126">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="d4b17-127">アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="d4b17-127">Create the Application</span></span>

<span data-ttu-id="d4b17-128">最初に新しいアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4b17-128">The first step is to create a new application.</span></span> <span data-ttu-id="d4b17-129">コマンド プロンプトを開き、アプリケーション用の新しいディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4b17-129">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="d4b17-130">それを、現在のディレクトリとしてください。</span><span class="sxs-lookup"><span data-stu-id="d4b17-130">Make that the current directory.</span></span> <span data-ttu-id="d4b17-131">コマンド プロンプトで `dotnet new console` のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="d4b17-131">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="d4b17-132">これで、基本的な "Hello World" アプリケーションのスターター ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-132">This creates the starter files for a basic "Hello World" application.</span></span>

<span data-ttu-id="d4b17-133">C# を始めて使用する方向けに、[このチュートリアル](console-teleprompter.md)で C# プログラムの構造について説明しています。</span><span class="sxs-lookup"><span data-stu-id="d4b17-133">If you've never used C# before, [this tutorial](console-teleprompter.md) explains the structure of a C# program.</span></span> <span data-ttu-id="d4b17-134">そのチュートリアルを先に読んでから、ここに戻って LINQ の詳細について学ぶのも良いでしょう。</span><span class="sxs-lookup"><span data-stu-id="d4b17-134">You can read that and then return here to learn more about LINQ.</span></span>

## <a name="creating-the-data-set"></a><span data-ttu-id="d4b17-135">データ セットの作成</span><span class="sxs-lookup"><span data-stu-id="d4b17-135">Creating the Data Set</span></span>

<span data-ttu-id="d4b17-136">開始する前に、`dotnet new console` によって生成された `Program.cs` ファイルの上部に次の行があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d4b17-136">Before you begin, make sure that the following lines are at the top of the `Program.cs` file generated by `dotnet new console`:</span></span>

```csharp
// Program.cs
using System;
using System.Collections.Generic;
using System.Linq;
```

<span data-ttu-id="d4b17-137">これら 3 つの行 (`using` ステートメント) がファイルの上部にない場合、プログラムはコンパイルされません。</span><span class="sxs-lookup"><span data-stu-id="d4b17-137">If these three lines (`using` statements) aren't at the top of the file, our program will not compile.</span></span>

<span data-ttu-id="d4b17-138">必要になる参照のすべてが用意できたので、カード デッキを構成するものは何かを考えます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-138">Now that you have all of the references that you'll need, consider what constitutes a deck of cards.</span></span> <span data-ttu-id="d4b17-139">一般的に、1 組のトランプ カードには 4 種類の絵札 (スート) があり、スートごとに 13 個の値があります。</span><span class="sxs-lookup"><span data-stu-id="d4b17-139">Commonly, a deck of playing cards has four suits, and each suit has thirteen values.</span></span> <span data-ttu-id="d4b17-140">通常は、`Card` クラスをすぐに作成し、`Card` オブジェクトのコレクションを手動で設定することを検討するかもしれません。</span><span class="sxs-lookup"><span data-stu-id="d4b17-140">Normally, you might consider creating a `Card` class right off the bat and populating a collection of `Card` objects by hand.</span></span> <span data-ttu-id="d4b17-141">LINQ では、カード デッキの作成を通常の方法よりも簡潔に処理することができます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-141">With LINQ, you can be more concise than the usual way of dealing with creating a deck of cards.</span></span> <span data-ttu-id="d4b17-142">`Card` クラスを作成する代わりに、それぞれがスートとランクを表す 2 つのシーケンスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-142">Instead of creating a `Card` class, you can create two sequences to represent suits and ranks, respectively.</span></span> <span data-ttu-id="d4b17-143">文字列の <xref:System.Collections.Generic.IEnumerable%601> としてランクとスートを生成する、非常に単純な "[*反復子メソッド*](../iterators.md#enumeration-sources-with-iterator-methods)" のペアを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4b17-143">You'll create a really simple pair of [*iterator methods*](../iterators.md#enumeration-sources-with-iterator-methods) that will generate the ranks and suits as <xref:System.Collections.Generic.IEnumerable%601>s of strings:</span></span>

```csharp
// Program.cs
// The Main() method

static IEnumerable<string> Suits()
{
    yield return "clubs";
    yield return "diamonds";
    yield return "hearts";
    yield return "spades";
}

static IEnumerable<string> Ranks()
{
    yield return "two";
    yield return "three";
    yield return "four";
    yield return "five";
    yield return "six";
    yield return "seven";
    yield return "eight";
    yield return "nine";
    yield return "ten";
    yield return "jack";
    yield return "queen";
    yield return "king";
    yield return "ace";
}
```

<span data-ttu-id="d4b17-144">`Program.cs` ファイル内の `Main` メソッドの下にこれらを配置します。</span><span class="sxs-lookup"><span data-stu-id="d4b17-144">Place these underneath the `Main` method in your `Program.cs` file.</span></span> <span data-ttu-id="d4b17-145">これら 2 つのメソッドは両方とも、`yield return` 構文を使用して実行中にシーケンスを生成します。</span><span class="sxs-lookup"><span data-stu-id="d4b17-145">These two methods both utilize the `yield return` syntax to produce a sequence as they run.</span></span> <span data-ttu-id="d4b17-146">コンパイラは <xref:System.Collections.Generic.IEnumerable%601> を実装するオブジェクトをビルドし、要求に応じて文字列のシーケンスを生成します。</span><span class="sxs-lookup"><span data-stu-id="d4b17-146">The compiler builds an object that implements <xref:System.Collections.Generic.IEnumerable%601> and generates the sequence of strings as they are requested.</span></span>

<span data-ttu-id="d4b17-147">次に、これらの反復子メソッドを使用して、カード デッキを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4b17-147">Now, use these iterator methods to create the deck of cards.</span></span> <span data-ttu-id="d4b17-148">`Main` メソッドの中に LINQ クエリを配置します。</span><span class="sxs-lookup"><span data-stu-id="d4b17-148">You'll place the LINQ query in our `Main` method.</span></span> <span data-ttu-id="d4b17-149">次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d4b17-149">Here's a look at it:</span></span>

```csharp
// Program.cs
static void Main(string[] args)
{
    var startingDeck = from s in Suits()
                       from r in Ranks()
                       select new { Suit = s, Rank = r };

    // Display each card that we've generated and placed in startingDeck in the console
    foreach (var card in startingDeck)
    {
        Console.WriteLine(card);
    }
}
```

<span data-ttu-id="d4b17-150">複数の `from` 句は 1 つの <xref:System.Linq.Enumerable.SelectMany%2A> を生成し、これが、最初のシーケンス内の各要素と 2 番目のシーケンス内の各要素とを組み合わせた 1 つのシーケンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4b17-150">The multiple `from` clauses produce a <xref:System.Linq.Enumerable.SelectMany%2A>, which creates a single sequence from combining each element in the first sequence with each element in the second sequence.</span></span> <span data-ttu-id="d4b17-151">ここでは順序が重要です。</span><span class="sxs-lookup"><span data-stu-id="d4b17-151">The order is important for our purposes.</span></span> <span data-ttu-id="d4b17-152">最初のソース シーケンス (Suits) 内の最初の要素が、2 番目のシーケンス (Ranks) のすべての要素と組み合わされます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-152">The first element in the first source sequence (Suits) is combined with every element in the second sequence (Ranks).</span></span> <span data-ttu-id="d4b17-153">これで、最初のスートのカード 13 枚すべてが生成されます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-153">This produces all thirteen cards of first suit.</span></span> <span data-ttu-id="d4b17-154">このプロセスを、最初のシーケンス (Suits) 内の各要素について繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d4b17-154">That process is repeated with each element in the first sequence (Suits).</span></span> <span data-ttu-id="d4b17-155">その結果、はじめにスート順に並んで、次に値の順に並んだカード デッキができます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-155">The end result is a deck of cards ordered by suits, followed by values.</span></span>

<span data-ttu-id="d4b17-156">LINQ を記述するときに、上記に示したクエリ構文を使用することを選択した場合でも、メソッド構文を使用することを選択した場合でも、片方の形式の構文から他方の構文の形式に常に移動できることを覚えておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="d4b17-156">It's important to keep in mind that whether you choose to write your LINQ in the query syntax used above or use method syntax instead, it's always possible to go from one form of syntax to the other.</span></span> <span data-ttu-id="d4b17-157">クエリ構文で記述された上記のクエリは、次のようにメソッド構文で記述できます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-157">The above query written in query syntax can be written in method syntax as:</span></span>

```csharp
var startingDeck = Suits().SelectMany(suit => Ranks().Select(rank => new { Suit = suit, Rank = rank }));
```

<span data-ttu-id="d4b17-158">クエリ構文で記述された LINQ ステートメントは、コンパイラによって、同等のメソッド呼び出し構文に変換されます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-158">The compiler translates LINQ statements written with query syntax into the equivalent method call syntax.</span></span> <span data-ttu-id="d4b17-159">そのため、選択した構文に関係なく、クエリの 2 つのバージョンでは同じ結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-159">Therefore, regardless of your syntax choice, the two versions of the query produce the same result.</span></span> <span data-ttu-id="d4b17-160">ご自分の状況にとって最善の構文を選択してください。たとえば、チームで作業している場合に、メソッド構文に慣れていないメンバーがいる場合は、クエリ構文の使用を勧めるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="d4b17-160">Choose which syntax works best for your situation: for instance, if you're working in a team where some of the members have difficulty with method syntax, try to prefer using query syntax.</span></span>

<span data-ttu-id="d4b17-161">この時点で、作成したサンプルを実行してみてください。</span><span class="sxs-lookup"><span data-stu-id="d4b17-161">Go ahead and run the sample you've built at this point.</span></span> <span data-ttu-id="d4b17-162">デッキにある 52 枚のカードがすべて表示されます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-162">It will display all 52 cards in the deck.</span></span> <span data-ttu-id="d4b17-163">デバッガ―でこのサンプルを実行すると、`Suits()` メソッドと `Ranks()` メソッドがどのように実行されるか理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-163">You may find it very helpful to run this sample under a debugger to observe how the `Suits()` and `Ranks()` methods execute.</span></span> <span data-ttu-id="d4b17-164">各シーケンス内の各文字列が必要な場合にのみ生成されることがよくわかります。</span><span class="sxs-lookup"><span data-stu-id="d4b17-164">You can clearly see that each string in each sequence is generated only as it is needed.</span></span>

![アプリが 52 枚のカードを書き出しているコンソール ウィンドウ](./media/working-with-linq/console-52-card-application.png)

## <a name="manipulating-the-order"></a><span data-ttu-id="d4b17-166">順序の操作</span><span class="sxs-lookup"><span data-stu-id="d4b17-166">Manipulating the Order</span></span>

<span data-ttu-id="d4b17-167">次に、カード デッキをどのようにシャッフルするかに注目します。</span><span class="sxs-lookup"><span data-stu-id="d4b17-167">Next, focus on how you're going to shuffle the cards in the deck.</span></span> <span data-ttu-id="d4b17-168">適切なシャッフルの最初の手順は、カード デッキを 2 つの山に分けることです。</span><span class="sxs-lookup"><span data-stu-id="d4b17-168">The first step in any good shuffle is to split the deck in two.</span></span> <span data-ttu-id="d4b17-169">LINQ API の一部である <xref:System.Linq.Enumerable.Take%2A> メソッドと <xref:System.Linq.Enumerable.Skip%2A> メソッドの機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-169">The <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> methods that are part of the LINQ APIs provide that feature for you.</span></span> <span data-ttu-id="d4b17-170">それらを `foreach` ループの下に配置します。</span><span class="sxs-lookup"><span data-stu-id="d4b17-170">Place them underneath the `foreach` loop:</span></span>

```csharp
// Program.cs
public static void Main(string[] args)
{
    var startingDeck = from s in Suits()
                       from r in Ranks()
                       select new { Suit = s, Rank = r };

    foreach (var c in startingDeck)
    {
        Console.WriteLine(c);
    }

    // 52 cards in a deck, so 52 / 2 = 26
    var top = startingDeck.Take(26);
    var bottom = startingDeck.Skip(26);
}
```

<span data-ttu-id="d4b17-171">ただし、標準ライブラリの中には利用できるシャッフル メソッドがないので、自分で作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4b17-171">However, there's no shuffle method to take advantage of in the standard library, so you'll have to write your own.</span></span> <span data-ttu-id="d4b17-172">作成するシャッフル メソッドには、LINQ ベースのプログラムで使用できるさまざまなテクニックが例示されているので、このプロセスの各部分を手順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="d4b17-172">The shuffle method you'll be creating illustrates several techniques that you'll use with LINQ-based programs, so each part of this process will be explained in steps.</span></span>

<span data-ttu-id="d4b17-173">LINQ クエリから返される <xref:System.Collections.Generic.IEnumerable%601> を操作する方法に対していくつかの機能を追加するには、[拡張メソッド](../../csharp/programming-guide/classes-and-structs/extension-methods.md)と呼ばれる特別な種類のメソッドをいくつか記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4b17-173">In order to add some functionality to how you interact with the <xref:System.Collections.Generic.IEnumerable%601> you'll get back from LINQ queries, you'll need to write some special kinds of methods called [extension methods](../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span></span> <span data-ttu-id="d4b17-174">手短に言うと、拡張メソッドとは、既に存在する型に機能を追加する際に、元の型を変更せずに新しい機能を追加するという特別な目的を持つ*静的メソッド*です。</span><span class="sxs-lookup"><span data-stu-id="d4b17-174">Briefly, an extension method is a special purpose *static method* that adds new functionality to an already-existing type without having to modify the original type you want to add functionality to.</span></span>

<span data-ttu-id="d4b17-175">`Extensions.cs` という名前の新しい *static* クラス ファイルをプログラムに追加した後、最初の拡張メソッドをビルドすることで、自分の拡張メソッドに新しいホームを与えます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-175">Give your extension methods a new home by adding a new *static* class file to your program called `Extensions.cs`, and then start building out the first extension method:</span></span>

```csharp
// Extensions.cs
using System;
using System.Collections.Generic;
using System.Linq;

namespace LinqFaroShuffle
{
    public static class Extensions
    {
        public static IEnumerable<T> InterleaveSequenceWith<T>(this IEnumerable<T> first, IEnumerable<T> second)
        {
            // Your implementation will go here soon enough
        }
    }
}
```

<span data-ttu-id="d4b17-176">少しの間、メソッド シグネチャ、特にパラメーターを調べてみてください。</span><span class="sxs-lookup"><span data-stu-id="d4b17-176">Look at the method signature for a moment, specifically the parameters:</span></span>

```csharp
public static IEnumerable<T> InterleaveSequenceWith<T> (this IEnumerable<T> first, IEnumerable<T> second)
```

<span data-ttu-id="d4b17-177">メソッドの最初の引数に `this` 修飾子が追加されているのがわかります。</span><span class="sxs-lookup"><span data-stu-id="d4b17-177">You can see the addition of the `this` modifier on the first argument to the method.</span></span> <span data-ttu-id="d4b17-178">つまり、最初の引数の型のメンバー メソッドと同じように、メソッドを呼び出すということです。</span><span class="sxs-lookup"><span data-stu-id="d4b17-178">That means you call the method as though it were a member method of the type of the first argument.</span></span> <span data-ttu-id="d4b17-179">また、このメソッドの宣言は標準的な表現形式に従い、入力と出力の型が `IEnumerable<T>` となります。</span><span class="sxs-lookup"><span data-stu-id="d4b17-179">This method declaration also follows a standard idiom where the input and output types are `IEnumerable<T>`.</span></span> <span data-ttu-id="d4b17-180">これによって LINQ メソッドが連結され、より複雑なクエリを実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d4b17-180">That practice enables LINQ methods to be chained together to perform more complex queries.</span></span>

<span data-ttu-id="d4b17-181">当然ながら、デッキを二等分したため、これらを結合させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4b17-181">Naturally, since you split the deck into halves, you'll need to join those halves together.</span></span> <span data-ttu-id="d4b17-182">コードでは、これは、<xref:System.Linq.Enumerable.Take%2A> と <xref:System.Linq.Enumerable.Skip%2A> を同時に実行し、要素を *`interleaving`* して取得したシーケンスの両方を列挙し、1 つのシーケンス (今シャッフルが行なわれたカード デッキ) を作成することを意味します。</span><span class="sxs-lookup"><span data-stu-id="d4b17-182">In code, this means you'll be enumerating both of the sequences you acquired through <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> at once, *`interleaving`* the elements, and creating one sequence: your now-shuffled deck of cards.</span></span> <span data-ttu-id="d4b17-183">2 つのシーケンスで動作する LINQ メソッドを作成するには、<xref:System.Collections.Generic.IEnumerable%601> がどのように動作するかを理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4b17-183">Writing a LINQ method that works with two sequences requires that you understand how <xref:System.Collections.Generic.IEnumerable%601> works.</span></span>

<span data-ttu-id="d4b17-184"><xref:System.Collections.Generic.IEnumerable%601> インターフェイスには <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> のメソッドが 1 つあります。</span><span class="sxs-lookup"><span data-stu-id="d4b17-184">The <xref:System.Collections.Generic.IEnumerable%601> interface has one method: <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>.</span></span> <span data-ttu-id="d4b17-185"><xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> によって返されるオブジェクトには、次の要素に移動するメソッドと、シーケンス内の現在の要素を取得するプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="d4b17-185">The object returned by <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> has a method to move to the next element, and a property that retrieves the current element in the sequence.</span></span> <span data-ttu-id="d4b17-186">これら 2 つのメンバーを使用して、コレクションを列挙し、要素を返します。</span><span class="sxs-lookup"><span data-stu-id="d4b17-186">You will use those two members to enumerate the collection and return the elements.</span></span> <span data-ttu-id="d4b17-187">このインターリーブ メソッドは反復子メソッドになるので、コレクションを作成してそのコレクションを返す代わりに、上記の `yield return` 構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d4b17-187">This Interleave method will be an iterator method, so instead of building a collection and returning the collection, you'll use the `yield return` syntax shown above.</span></span>

<span data-ttu-id="d4b17-188">そのメソッドの実装を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="d4b17-188">Here's the implementation of that method:</span></span>

[!CODE-csharp[InterleaveSequenceWith](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet1)]

<span data-ttu-id="d4b17-189">このメソッドが作成できたので、`Main` メソッドに戻り、デッキを 1 回シャッフルします。</span><span class="sxs-lookup"><span data-stu-id="d4b17-189">Now that you've written this method, go back to the `Main` method and shuffle the deck once:</span></span>

```csharp
// Program.cs
public static void Main(string[] args)
{
    var startingDeck = from s in Suits()
                       from r in Ranks()
                       select new { Suit = s, Rank = r };

    foreach (var c in startingDeck)
    {
        Console.WriteLine(c);
    }

    var top = startingDeck.Take(26);
    var bottom = startingDeck.Skip(26);
    var shuffle = top.InterleaveSequenceWith(bottom);

    foreach (var c in shuffle)
    {
        Console.WriteLine(c);
    }
}
```

## <a name="comparisons"></a><span data-ttu-id="d4b17-190">比較</span><span class="sxs-lookup"><span data-stu-id="d4b17-190">Comparisons</span></span>

<span data-ttu-id="d4b17-191">デッキを元の順序に戻すまでに何回シャッフルが必要でしょうか。</span><span class="sxs-lookup"><span data-stu-id="d4b17-191">How many shuffles it takes to set the deck back to its original order?</span></span> <span data-ttu-id="d4b17-192">これを見つけるには、2 つのシーケンスが等しいかどうかを判断するメソッドを記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4b17-192">To find out, you'll need to write a method that determines if two sequences are equal.</span></span> <span data-ttu-id="d4b17-193">そのメソッドを記述したら、デッキをループでシャッフルするコードを配置し、どの時点で元の順序に戻るかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4b17-193">After you have that method, you'll need to place the code that shuffles the deck in a loop, and check to see when the deck is back in order.</span></span>

<span data-ttu-id="d4b17-194">2 つのシーケンスが等しいかどうかを判断するメソッドの記述は簡単です。</span><span class="sxs-lookup"><span data-stu-id="d4b17-194">Writing a method to determine if the two sequences are equal should be straightforward.</span></span> <span data-ttu-id="d4b17-195">デッキのシャッフル用に記述したメソッドと似た構造です。</span><span class="sxs-lookup"><span data-stu-id="d4b17-195">It's a similar structure to the method you wrote to shuffle the deck.</span></span> <span data-ttu-id="d4b17-196">今回に限り、各要素を `yield return` するのではなく、各シーケンスの一致する要素を比較します。</span><span class="sxs-lookup"><span data-stu-id="d4b17-196">Only this time, instead of `yield return`ing each element, you'll compare the matching elements of each sequence.</span></span> <span data-ttu-id="d4b17-197">シーケンス全体が列挙されている場合、各要素が一致すれば、シーケンスは同じです。</span><span class="sxs-lookup"><span data-stu-id="d4b17-197">When the entire sequence has been enumerated, if every element matches, the sequences are the same:</span></span>

[!CODE-csharp[SequenceEquals](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet2)]

<span data-ttu-id="d4b17-198">これは 2 つ目の LINQ の表現形式であるターミナル メソッドを示しています。</span><span class="sxs-lookup"><span data-stu-id="d4b17-198">This shows a second LINQ idiom: terminal methods.</span></span> <span data-ttu-id="d4b17-199">これらは、シーケンスを入力として受け取り (この場合 2 つのシーケンス)、単一のスカラー値を返します。</span><span class="sxs-lookup"><span data-stu-id="d4b17-199">They take a sequence as input (or in this case, two sequences), and return a single scalar value.</span></span> <span data-ttu-id="d4b17-200">ターミナル メソッドを使用した場合、それらは常に LINQ クエリ用のメソッド チェーンの最後のメソッドになります。そのため、名前が "ターミナル" (終点) になっています。</span><span class="sxs-lookup"><span data-stu-id="d4b17-200">When using terminal methods, they are always the final method in a chain of methods for a LINQ query, hence the name "terminal".</span></span>

<span data-ttu-id="d4b17-201">これは、デッキが元の順序に戻るタイミングの判定に使用すると、どのように動作するかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-201">You can see this in action when you use it to determine when the deck is back in its original order.</span></span> <span data-ttu-id="d4b17-202">ループ内にシャッフルのコードを配置し、`SequenceEquals()` メソッドを適用して、シーケンスが元の順序に戻った時点で停止します。</span><span class="sxs-lookup"><span data-stu-id="d4b17-202">Put the shuffle code inside a loop, and stop when the sequence is back in its original order by applying the `SequenceEquals()` method.</span></span> <span data-ttu-id="d4b17-203">シーケンスではなく単一の値を返すため、常にクエリ内の最後のメソッドになることがわかります。</span><span class="sxs-lookup"><span data-stu-id="d4b17-203">You can see it would always be the final method in any query, because it returns a single value instead of a sequence:</span></span>

```csharp
// Program.cs
static void Main(string[] args)
{
    // Query for building the deck

    // Shuffling using InterleaveSequenceWith<T>();

    var times = 0;
    // We can re-use the shuffle variable from earlier, or you can make a new one
    shuffle = startingDeck;
    do
    {
        shuffle = shuffle.Take(26).InterleaveSequenceWith(shuffle.Skip(26));

        foreach (var card in shuffle)
        {
            Console.WriteLine(card);
        }
        Console.WriteLine();
        times++;

    } while (!startingDeck.SequenceEquals(shuffle));

    Console.WriteLine(times);
}
```

<span data-ttu-id="d4b17-204">ここでコードを実行して、シャッフルごとにデッキがどのように整列するかを書き留めておいてください。</span><span class="sxs-lookup"><span data-stu-id="d4b17-204">Run the code you've got so far and take note of how the deck rearranges on each shuffle.</span></span> <span data-ttu-id="d4b17-205">8 回のシャッフル (do-while loop の繰り返し) 後に、デッキは、開始時の LINQ クエリから作成された初回の構成に戻ります。</span><span class="sxs-lookup"><span data-stu-id="d4b17-205">After 8 shuffles (iterations of the do-while loop), the deck returns to the original configuration it was in when you first created it from the starting LINQ query.</span></span>

## <a name="optimizations"></a><span data-ttu-id="d4b17-206">最適化</span><span class="sxs-lookup"><span data-stu-id="d4b17-206">Optimizations</span></span>

<span data-ttu-id="d4b17-207">ここまでで構築したサンプルは、*アウト シャッフル* (一番上と一番下のカードが毎回同じになること) を実行するものです。</span><span class="sxs-lookup"><span data-stu-id="d4b17-207">The sample you've built so far executes an *out shuffle*, where the top and bottom cards stay the same on each run.</span></span> <span data-ttu-id="d4b17-208">ここで 1 つ変更を加えましょう。"*イン シャッフル* " を代わりに使用します。ここでは、52 枚のカードすべての位置が変わります。</span><span class="sxs-lookup"><span data-stu-id="d4b17-208">Let's make one change: we'll use an *in shuffle* instead, where all 52 cards change position.</span></span> <span data-ttu-id="d4b17-209">イン シャッフルでは、下半分の一番上のカードが、デッキの最上部に来るように、デッキをインターウィーブします。</span><span class="sxs-lookup"><span data-stu-id="d4b17-209">For an in shuffle, you interleave the deck so that the first card in the bottom half becomes the first card in the deck.</span></span> <span data-ttu-id="d4b17-210">つまり、上半分の一番下のカードがデッキの最下部のカードになります。</span><span class="sxs-lookup"><span data-stu-id="d4b17-210">That means the last card in the top half becomes the bottom card.</span></span> <span data-ttu-id="d4b17-211">これは、1 行のコードを変更する単純な変更です。</span><span class="sxs-lookup"><span data-stu-id="d4b17-211">This is a simple change to a singular line of code.</span></span> <span data-ttu-id="d4b17-212"><xref:System.Linq.Enumerable.Take%2A> と <xref:System.Linq.Enumerable.Skip%2A> の位置を入れ替えることで、現在のシャッフル クエリを更新します。</span><span class="sxs-lookup"><span data-stu-id="d4b17-212">Update the current shuffle query by switching the positions of <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A>.</span></span> <span data-ttu-id="d4b17-213">これにより、デッキの上半分と下半分の順序が変更されます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-213">This will change the order of the top and bottom halves of the deck:</span></span>

```csharp
shuffle = shuffle.Skip(26).InterleaveSequenceWith(shuffle.Take(26));
```

<span data-ttu-id="d4b17-214">プログラムを再実行すると、デッキが元の順序に戻るのに反復が 52 回行われることがわかります。</span><span class="sxs-lookup"><span data-stu-id="d4b17-214">Run the program again, and you'll see that it takes 52 iterations for the deck to reorder itself.</span></span> <span data-ttu-id="d4b17-215">プログラムを実行し続けると、著しくパフォーマンスが低下することがわかります。</span><span class="sxs-lookup"><span data-stu-id="d4b17-215">You'll also start to notice some serious performance degradations as the program continues to run.</span></span>

<span data-ttu-id="d4b17-216">これには多くの理由があります。</span><span class="sxs-lookup"><span data-stu-id="d4b17-216">There are a number of reasons for this.</span></span> <span data-ttu-id="d4b17-217">このパフォーマンスの低下の主な原因の 1 つを説明できます。それは、"[*遅延評価*](../programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)" の非効率的な使用です。</span><span class="sxs-lookup"><span data-stu-id="d4b17-217">You can tackle one of the major causes of this performance drop: inefficient use of [*lazy evaluation*](../programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span></span>

<span data-ttu-id="d4b17-218">手短に言えば、遅延評価とは、ステートメントの値が必要になるまで、その評価が実行されないことです。</span><span class="sxs-lookup"><span data-stu-id="d4b17-218">Briefly, lazy evaluation states that the evaluation of a statement is not performed until its value is needed.</span></span> <span data-ttu-id="d4b17-219">遅延して評価されているステートメントは LINQ クエリです。</span><span class="sxs-lookup"><span data-stu-id="d4b17-219">LINQ queries are statements that are evaluated lazily.</span></span> <span data-ttu-id="d4b17-220">シーケンスは、要素が要求された場合にのみ生成されます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-220">The sequences are generated only as the elements are requested.</span></span> <span data-ttu-id="d4b17-221">通常、これは LINQ の利点です。</span><span class="sxs-lookup"><span data-stu-id="d4b17-221">Usually, that's a major benefit of LINQ.</span></span> <span data-ttu-id="d4b17-222">しかし、このプログラムのような使い方をする場合、実行時間が急激に増加する要因となります。</span><span class="sxs-lookup"><span data-stu-id="d4b17-222">However, in a use such as this program, this causes exponential growth in execution time.</span></span>

<span data-ttu-id="d4b17-223">元のデッキを LINQ クエリを使用して生成したことを思い出してください。</span><span class="sxs-lookup"><span data-stu-id="d4b17-223">Remember that we generated the original deck using a LINQ query.</span></span> <span data-ttu-id="d4b17-224">毎回のシャッフルは、直前のデッキに LINQ クエリを 3 回実行することによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-224">Each shuffle is generated by performing three LINQ queries on the previous deck.</span></span> <span data-ttu-id="d4b17-225">これらはすべて遅延実行されます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-225">All these are performed lazily.</span></span> <span data-ttu-id="d4b17-226">つまり、シーケンスが要求されるたびに再度実行されるということです。</span><span class="sxs-lookup"><span data-stu-id="d4b17-226">That also means they are performed again each time the sequence is requested.</span></span> <span data-ttu-id="d4b17-227">52 回反復されるまでに、元のデッキを何度も何度も再生成しているのです。</span><span class="sxs-lookup"><span data-stu-id="d4b17-227">By the time you get to the 52nd iteration, you're regenerating the original deck many, many times.</span></span> <span data-ttu-id="d4b17-228">ログを記述してこの動作を示しましょう。</span><span class="sxs-lookup"><span data-stu-id="d4b17-228">Let's write a log to demonstrate this behavior.</span></span> <span data-ttu-id="d4b17-229">その次に修正します。</span><span class="sxs-lookup"><span data-stu-id="d4b17-229">Then, you'll fix it.</span></span>

<span data-ttu-id="d4b17-230">`Extensions.cs` ファイルに、次のメソッドを入力するかコピーします。</span><span class="sxs-lookup"><span data-stu-id="d4b17-230">In your `Extensions.cs` file, type in or copy the method below.</span></span> <span data-ttu-id="d4b17-231">この拡張メソッドによって、プロジェクト ディレクトリ内に `debug.log` と呼ばれる新しいファイルが作成され、このログ ファイルに現在どのようなクエリが実行されているかが記録されます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-231">This extension method creates a new file called `debug.log` within your project directory and records what query is currently being executed to the log file.</span></span> <span data-ttu-id="d4b17-232">この拡張メソッドはどんなクエリにも追加でき、そのクエリが実行されたことをマークできます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-232">This extension method can be appended to any query to mark that the query executed.</span></span>

[!CODE-csharp[LogQuery](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet3)]

<span data-ttu-id="d4b17-233">`File` の下に、存在しないことを意味する赤い波線が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-233">You will see a red squiggle under `File`, meaning it doesn't exist.</span></span> <span data-ttu-id="d4b17-234">コンパイラがどのような `File` かを把握できないため、これはコンパイルされません。</span><span class="sxs-lookup"><span data-stu-id="d4b17-234">It won't compile, since the compiler doesn't know what `File` is.</span></span> <span data-ttu-id="d4b17-235">この問題を解決するには、`Extensions.cs` の最初の行の下に次のコード行を追加してください。</span><span class="sxs-lookup"><span data-stu-id="d4b17-235">To solve this problem, make sure to add the following line of code under the very first line in `Extensions.cs`:</span></span>

```csharp
using System.IO;
```

<span data-ttu-id="d4b17-236">これでイシューが解決し、赤のエラーは表示されなくなるはずです。</span><span class="sxs-lookup"><span data-stu-id="d4b17-236">This should solve the issue and the red error disappears.</span></span>

<span data-ttu-id="d4b17-237">次に、各クエリの定義をログ メッセージでインストルメントします。</span><span class="sxs-lookup"><span data-stu-id="d4b17-237">Next, instrument the definition of each query with a log message:</span></span>

```csharp
// Program.cs
public static void Main(string[] args)
{
    var startingDeck = (from s in Suits().LogQuery("Suit Generation")
                        from r in Ranks().LogQuery("Rank Generation")
                        select new { Suit = s, Rank = r }).LogQuery("Starting Deck");

    foreach (var c in startingDeck)
    {
        Console.WriteLine(c);
    }

    Console.WriteLine();
    var times = 0;
    var shuffle = startingDeck;

    do
    {
        // Out shuffle
        /*
        shuffle = shuffle.Take(26)
            .LogQuery("Top Half")
            .InterleaveSequenceWith(shuffle.Skip(26)
            .LogQuery("Bottom Half"))
            .LogQuery("Shuffle");
        */

        // In shuffle
        shuffle = shuffle.Skip(26).LogQuery("Bottom Half")
                .InterleaveSequenceWith(shuffle.Take(26).LogQuery("Top Half"))
                .LogQuery("Shuffle");

        foreach (var c in shuffle)
        {
            Console.WriteLine(c);
        }

        times++;
        Console.WriteLine(times);
    } while (!startingDeck.SequenceEquals(shuffle));

    Console.WriteLine(times);
}
```

<span data-ttu-id="d4b17-238">クエリにアクセスするたびにログをとるわけではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d4b17-238">Notice that you don't log every time you access a query.</span></span> <span data-ttu-id="d4b17-239">元のクエリを作成する場合にのみログをとります。</span><span class="sxs-lookup"><span data-stu-id="d4b17-239">You log only when you create the original query.</span></span> <span data-ttu-id="d4b17-240">プログラムの実行にはまだ時間がかかりますが、これで理由がわかるようになりました。</span><span class="sxs-lookup"><span data-stu-id="d4b17-240">The program still takes a long time to run, but now you can see why.</span></span> <span data-ttu-id="d4b17-241">ログを有効にしたままイン シャッフルを実行すると時間がかかりすぎると感じる場合は、アウト シャッフルに戻してください。</span><span class="sxs-lookup"><span data-stu-id="d4b17-241">If you run out of patience running the in shuffle with logging turned on, switch back to the out shuffle.</span></span> <span data-ttu-id="d4b17-242">それでも遅延評価の影響はわかります。</span><span class="sxs-lookup"><span data-stu-id="d4b17-242">You'll still see the lazy evaluation effects.</span></span> <span data-ttu-id="d4b17-243">1 回の実行で、すべての値とスートの生成を含めてクエリを 2592 回実行します。</span><span class="sxs-lookup"><span data-stu-id="d4b17-243">In one run, it executes 2592 queries, including all the value and suit generation.</span></span>

<span data-ttu-id="d4b17-244">ここでコードのパフォーマンスを向上させて、実行回数を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-244">You can improve the performance of the code here to reduce the number of executions you make.</span></span> <span data-ttu-id="d4b17-245">実行できる単純な修正は、カード デッキを構築する元の LINQ クエリの結果を "*キャッシュ*" することです。</span><span class="sxs-lookup"><span data-stu-id="d4b17-245">A simple fix you can make is to *cache* the results of the original LINQ query that constructs the deck of cards.</span></span> <span data-ttu-id="d4b17-246">現時点では、do-while loop が繰り返されるたびに、何度もクエリが実行され、カード デッキが再構築され、シャッフルが毎回実行されています。</span><span class="sxs-lookup"><span data-stu-id="d4b17-246">Currently, you're executing the queries again and again every time the do-while loop goes through an iteration, re-constructing the deck of cards and reshuffling it every time.</span></span> <span data-ttu-id="d4b17-247">カード デッキをキャッシュするには、LINQ メソッドの <xref:System.Linq.Enumerable.ToArray%2A> と <xref:System.Linq.Enumerable.ToList%2A> を活用できます。それらをクエリに追加すると、実行するように指示したのと同じアクションが実行されますが、今回は、呼び出すように選択したメソッドに応じて、結果が配列または一覧内に格納されます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-247">To cache the deck of cards, you can leverage the LINQ methods <xref:System.Linq.Enumerable.ToArray%2A> and <xref:System.Linq.Enumerable.ToList%2A>; when you append them to the queries, they'll perform the same actions you've told them to, but now they'll store the results in an array or a list, depending on which method you choose to call.</span></span> <span data-ttu-id="d4b17-248">LINQ メソッド <xref:System.Linq.Enumerable.ToArray%2A> を両方のクエリに追加し、もう一度プログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="d4b17-248">Append the LINQ method <xref:System.Linq.Enumerable.ToArray%2A> to both queries and run the program again:</span></span>

[!CODE-csharp[Main](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet1)]

<span data-ttu-id="d4b17-249">これで、アウト シャッフルのクエリが 30 回に減少します。</span><span class="sxs-lookup"><span data-stu-id="d4b17-249">Now the out shuffle is down to 30 queries.</span></span> <span data-ttu-id="d4b17-250">イン シャッフルで再実行しても、同様の改善がみられます。今回は 162 回のクエリが実行されます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-250">Run again with the in shuffle and you'll see similar improvements: it now executes 162 queries.</span></span>

<span data-ttu-id="d4b17-251">この例は、遅延評価がパフォーマンス問題を引き起こす可能性があるユース ケースを強調することを**意図**していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d4b17-251">Please note that this example is **designed** to highlight the use cases where lazy evaluation can cause performance difficulties.</span></span> <span data-ttu-id="d4b17-252">遅延評価がどこでコードのパフォーマンスに影響を与える可能性があるかを確認することは重要ですが、すべてのクエリを先行評価で実行する必要があるわけではないことを理解することも同じように重要です。</span><span class="sxs-lookup"><span data-stu-id="d4b17-252">While it's important to see where lazy evaluation can impact code performance, it's equally important to understand that not all queries should run eagerly.</span></span> <span data-ttu-id="d4b17-253"><xref:System.Linq.Enumerable.ToArray%2A> の無使用によってパフォーマンス ヒットが発生するのは、カード デッキの新しい並びが、毎回、直前の並びから作成されるためです。</span><span class="sxs-lookup"><span data-stu-id="d4b17-253">The performance hit you incur without using <xref:System.Linq.Enumerable.ToArray%2A> is because each new arrangement of the deck of cards is built from the previous arrangement.</span></span> <span data-ttu-id="d4b17-254">遅延評価を使用すると、`startingDeck` を作成したコードを実行するときでさえも、新しいデッキ構成が毎回最初のデッキから作成されることになります。</span><span class="sxs-lookup"><span data-stu-id="d4b17-254">Using lazy evaluation means each new deck configuration is built from the original deck, even executing the code that built the `startingDeck`.</span></span> <span data-ttu-id="d4b17-255">これでは、余分な作業が多く発生してしまいます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-255">That causes a large amount of extra work.</span></span>

<span data-ttu-id="d4b17-256">実際には、先行評価を使用すると効率的に動作するアルゴリズムもあれば、遅延評価を使用したほうがよいアルゴリズムもあります。</span><span class="sxs-lookup"><span data-stu-id="d4b17-256">In practice, some algorithms run well using eager evaluation, and others run well using lazy evaluation.</span></span> <span data-ttu-id="d4b17-257">日常の使用では、データ ソースがデータベース エンジンのように個別のプロセスである場合は、遅延評価のほうが通常は適しています。</span><span class="sxs-lookup"><span data-stu-id="d4b17-257">For daily usage, lazy evaluation is usually a better choice when the data source is a separate process, like a database engine.</span></span> <span data-ttu-id="d4b17-258">データベースでは、遅延評価を使用すると、より複雑なクエリがデータベース プロセスに対して 1 往復だけ実行された後、残りのコードに戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="d4b17-258">For databases, lazy evaluation allows more complex queries to execute only one round trip to the database process and back to the rest of your code.</span></span> <span data-ttu-id="d4b17-259">LINQ には遅延評価と先行評価のどちらを利用するかを選択できる柔軟性があるため、プロセスを測定して、最善のパフォーマンスをもたらすほうの種類の評価を選択してください。</span><span class="sxs-lookup"><span data-stu-id="d4b17-259">LINQ is flexible whether you choose to utilize lazy or eager evaluation, so measure your processes and pick whichever kind of evaluation gives you the best performance.</span></span>

## <a name="conclusion"></a><span data-ttu-id="d4b17-260">まとめ</span><span class="sxs-lookup"><span data-stu-id="d4b17-260">Conclusion</span></span>

<span data-ttu-id="d4b17-261">このプロジェクトでは、以下を扱いました。</span><span class="sxs-lookup"><span data-stu-id="d4b17-261">In this project, you covered:</span></span>
- <span data-ttu-id="d4b17-262">LINQ クエリを使用してデータを集計して、意味のあるシーケンスにする</span><span class="sxs-lookup"><span data-stu-id="d4b17-262">using LINQ queries to aggregate data into a meaningful sequence</span></span>
- <span data-ttu-id="d4b17-263">拡張メソッドを記述して、LINQ クエリに独自のカスタム機能を追加する</span><span class="sxs-lookup"><span data-stu-id="d4b17-263">writing Extension methods to add our own custom functionality to LINQ queries</span></span>
- <span data-ttu-id="d4b17-264">LINQ クエリによって速度の低下のようなパフォーマンスの問題が発生する可能性があるコード内の領域を見つける</span><span class="sxs-lookup"><span data-stu-id="d4b17-264">locating areas in our code where our LINQ queries might run into performance issues like degraded speed</span></span>
- <span data-ttu-id="d4b17-265">LINQ クエリに関する遅延評価と選考評価と、クエリのパフォーマンスにおけるそれらの意味</span><span class="sxs-lookup"><span data-stu-id="d4b17-265">lazy and eager evaluation in regards to LINQ queries and the implications they might have on query performance</span></span>

<span data-ttu-id="d4b17-266">LINQ の他に、マジシャンがカードのトリックで使用するテクニックについて少し学びました。</span><span class="sxs-lookup"><span data-stu-id="d4b17-266">Aside from LINQ, you learned a bit about a technique magicians use for card tricks.</span></span> <span data-ttu-id="d4b17-267">マジシャンは、すべてのカードをデッキのどこに移動させるかを制御できるため、ファロー シャッフルを使用しています。</span><span class="sxs-lookup"><span data-stu-id="d4b17-267">Magicians use the Faro shuffle because they can control where every card moves in the deck.</span></span> <span data-ttu-id="d4b17-268">これがわかったからといって、種明かしをしてマジックを台無しにしないでください。</span><span class="sxs-lookup"><span data-stu-id="d4b17-268">Now that you know, don't spoil it for everyone else!</span></span>

<span data-ttu-id="d4b17-269">LINQ の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4b17-269">For more information on LINQ, see:</span></span>
- [<span data-ttu-id="d4b17-270">統合言語クエリ (LINQ)</span><span class="sxs-lookup"><span data-stu-id="d4b17-270">Language Integrated Query (LINQ)</span></span>](../programming-guide/concepts/linq/index.md)
  - [<span data-ttu-id="d4b17-271">LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="d4b17-271">Introduction to LINQ</span></span>](../programming-guide/concepts/linq/index.md)
  - [<span data-ttu-id="d4b17-272">LINQ クエリの基本操作 (C#)</span><span class="sxs-lookup"><span data-stu-id="d4b17-272">Basic LINQ Query Operations (C#)</span></span>](../programming-guide/concepts/linq/basic-linq-query-operations.md)
  - [<span data-ttu-id="d4b17-273">LINQ によるデータ変換 (C#)</span><span class="sxs-lookup"><span data-stu-id="d4b17-273">Data Transformations With LINQ (C#)</span></span>](../programming-guide/concepts/linq/data-transformations-with-linq.md)
  - [<span data-ttu-id="d4b17-274">LINQ でのクエリ構文とメソッド構文 (C#)</span><span class="sxs-lookup"><span data-stu-id="d4b17-274">Query Syntax and Method Syntax in LINQ (C#)</span></span>](../programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md)
  - [<span data-ttu-id="d4b17-275">LINQ をサポートする C# の機能</span><span class="sxs-lookup"><span data-stu-id="d4b17-275">C# Features That Support LINQ</span></span>](../programming-guide/concepts/linq/features-that-support-linq.md)
