---
title: Main() とコマンドライン引数 - C# プログラミング ガイド
ms.date: 08/02/2017
f1_keywords:
- CS5001
- main_CSharpKeyword
- Main
helpviewer_keywords:
- Main method [C#]
- C# language, command-line arguments
- arguments [C#], command-line
- command line [C#], arguments
- command-line arguments [C#], Main method
ms.assetid: 73a17231-cf96-44ea-aa8a-54807c6fb1f4
ms.openlocfilehash: 0571ec6dbc42f103ec922a6b2b13a52510640a78
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "75700602"
---
# <a name="main-and-command-line-arguments-c-programming-guide"></a><span data-ttu-id="bc7fe-102">Main() とコマンドライン引数 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="bc7fe-102">Main() and command-line arguments (C# Programming Guide)</span></span>

<span data-ttu-id="bc7fe-103">`Main` メソッドは、C# アプリケーションのエントリ ポイントです</span><span class="sxs-lookup"><span data-stu-id="bc7fe-103">The `Main` method is the entry point of a C# application.</span></span> <span data-ttu-id="bc7fe-104">(ライブラリおよびサービスでは、エントリ ポイントとしての `Main` メソッドは必要ありません)。アプリケーションを起動すると、最初に `Main` メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-104">(Libraries and services do not require a `Main` method as an entry point.) When the application is started, the `Main` method is the first method that is invoked.</span></span>

 <span data-ttu-id="bc7fe-105">C# プログラムのエントリ ポイントは 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-105">There can only be one entry point in a C# program.</span></span> <span data-ttu-id="bc7fe-106">`Main` メソッドを持つクラスが 2 つ以上ある場合、プログラムをコンパイルする際に **/main** コンパイラ オプションを使用して、どの `Main` メソッドをエントリ ポイントとして使用するかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-106">If you have more than one class that has a `Main` method, you must compile your program with the **/main** compiler option to specify which `Main` method to use as the entry point.</span></span> <span data-ttu-id="bc7fe-107">詳細については、「[-main (C# コンパイラ オプション)](../../language-reference/compiler-options/main-compiler-option.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-107">For more information, see [-main (C# Compiler Options)](../../language-reference/compiler-options/main-compiler-option.md).</span></span>

[!code-csharp[csProgGuideMain#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#17)]

## <a name="overview"></a><span data-ttu-id="bc7fe-108">概要</span><span class="sxs-lookup"><span data-stu-id="bc7fe-108">Overview</span></span>

- <span data-ttu-id="bc7fe-109">`Main` メソッドは実行可能プログラムのエントリ ポイントであり、ここでプログラムの制御を開始および終了します。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-109">The `Main` method is the entry point of an executable program; it is where the program control starts and ends.</span></span>
- <span data-ttu-id="bc7fe-110">`Main` は、クラスまたは構造体の内部で宣言されます。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-110">`Main` is declared inside a class or struct.</span></span> <span data-ttu-id="bc7fe-111">`Main` は [static](../../language-reference/keywords/static.md) である必要がありますが、[public](../../language-reference/keywords/public.md) である必要はありません</span><span class="sxs-lookup"><span data-stu-id="bc7fe-111">`Main` must be [static](../../language-reference/keywords/static.md) and it need not be [public](../../language-reference/keywords/public.md).</span></span> <span data-ttu-id="bc7fe-112">(先ほどの例では、既定の [private](../../language-reference/keywords/private.md) のアクセスを受け取ります)。外側のクラスまたは構造体は、static である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-112">(In the earlier example, it receives the default access of [private](../../language-reference/keywords/private.md).) The enclosing class or struct is not required to be static.</span></span>
- <span data-ttu-id="bc7fe-113">`Main` の戻り値の型は、`void` または `int` のいずれかになります。C# 7.1 以降では `Task` または `Task<int>` になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-113">`Main` can either have a `void`, `int`, or, starting with C# 7.1, `Task`, or `Task<int>` return type.</span></span>
- <span data-ttu-id="bc7fe-114">`Main` で `Task` または `Task<int>` が返される場合に限り、`Main` の宣言に [`async`](../../language-reference/keywords/async.md) 修飾子を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-114">If and only if `Main` returns a `Task` or `Task<int>`, the declaration of `Main` may include the [`async`](../../language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="bc7fe-115">この条件により、`async void Main` メソッドが明確に除外されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-115">Note that this specifically excludes an `async void Main` method.</span></span>
- <span data-ttu-id="bc7fe-116">`Main` メソッドを宣言する際、コマンドライン引数を含む `string[]` パラメーターは指定してもしなくてもかまいません。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-116">The `Main` method can be declared with or without a `string[]` parameter that contains command-line arguments.</span></span> <span data-ttu-id="bc7fe-117">Visual Studio を使用して Windows アプリケーションを作成する場合、このパラメーターを手動で追加するか <xref:System.Environment.GetCommandLineArgs> メソッドを使用して、[コマンドライン引数](command-line-arguments.md)を取得できます。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-117">When using Visual Studio to create Windows applications, you can add the parameter manually or else use the <xref:System.Environment.GetCommandLineArgs> method to obtain the [command-line arguments](command-line-arguments.md).</span></span> <span data-ttu-id="bc7fe-118">パラメーターは、インデックス 0 のコマンドライン引数として読み取られます。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-118">Parameters are read as zero-indexed command-line arguments.</span></span> <span data-ttu-id="bc7fe-119">C や C++ とは異なり、プログラムの名前は、<xref:System.Environment.GetCommandLineArgs> の最初の要素です。`args` 配列の最初のコマンドライン引数として扱われることはありません。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-119">Unlike C and C++, the name of the program is not treated as the first command-line argument in the `args` array, but it is the first element of the <xref:System.Environment.GetCommandLineArgs> method.</span></span>

<span data-ttu-id="bc7fe-120">有効な `Main` の署名の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-120">The following is a list of valid `Main` signatures:</span></span>

```csharp
public static void Main() { }
public static int Main() { }
public static void Main(string[] args) { }
public static int Main(string[] args) { }
public static async Task Main() { }
public static async Task<int> Main() { }
public static async Task Main(string[] args) { }
public static async Task<int> Main(string[] args) { }
```

<span data-ttu-id="bc7fe-121">コンソール アプリケーションの `Main` で `await` を使用して非同期操作を開始する必要がある場合、戻り値の型 `async`、`Task`、`Task<int>` を追加することでプログラム コードを簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="bc7fe-121">The addition of `async` and `Task`, `Task<int>` return types simplifies program code when console applications need to start and `await` asynchronous operations in `Main`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="bc7fe-122">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="bc7fe-122">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="bc7fe-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc7fe-123">See also</span></span>

- [<span data-ttu-id="bc7fe-124">csc.exe を使用したコマンド ラインからのビルド</span><span class="sxs-lookup"><span data-stu-id="bc7fe-124">Command-line Building With csc.exe</span></span>](../../language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [<span data-ttu-id="bc7fe-125">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="bc7fe-125">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="bc7fe-126">メソッド</span><span class="sxs-lookup"><span data-stu-id="bc7fe-126">Methods</span></span>](../classes-and-structs/methods.md)
- [<span data-ttu-id="bc7fe-127">インサイド C# プログラム</span><span class="sxs-lookup"><span data-stu-id="bc7fe-127">Inside a C# Program</span></span>](../inside-a-program/index.md)
