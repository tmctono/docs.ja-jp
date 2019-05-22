---
title: C# 7.1 の新機能
description: C# 7.1 の新機能の概要。
ms.date: 04/09/2019
ms.openlocfilehash: 4b7bd96e428f990b2db91a4cfd45da01dc133aac
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881543"
---
# <a name="whats-new-in-c-71"></a><span data-ttu-id="39d01-103">C# 7.1 の新機能</span><span class="sxs-lookup"><span data-stu-id="39d01-103">What's new in C# 7.1</span></span>

<span data-ttu-id="39d01-104">C# 7.1 は C# 言語の最初のポイント リリースです。</span><span class="sxs-lookup"><span data-stu-id="39d01-104">C# 7.1 is the first point release to the C# language.</span></span> <span data-ttu-id="39d01-105">この言語のリリース サイクルが増えたことになります。</span><span class="sxs-lookup"><span data-stu-id="39d01-105">It marks an increased release cadence for the language.</span></span> <span data-ttu-id="39d01-106">新機能は間もなく使用できます。理論的には、各々の新機能が用意できたときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="39d01-106">You can use the new features sooner, ideally when each new feature is ready.</span></span> <span data-ttu-id="39d01-107">C# 7.1 では、特定のバージョンの言語に合わせるようにコンパイラを構成する機能が追加されます。</span><span class="sxs-lookup"><span data-stu-id="39d01-107">C# 7.1 adds the ability to configure the compiler to match a specified version of the language.</span></span> <span data-ttu-id="39d01-108">ツールをアップグレードする決定と言語バージョンをアップグレードする決定を分けることができます。</span><span class="sxs-lookup"><span data-stu-id="39d01-108">That enables you to separate the decision to upgrade tools from the decision to upgrade language versions.</span></span>

<span data-ttu-id="39d01-109">C# 7.1 では、[言語バージョン選択](../language-reference/configure-language-version.md)構成要素、3 つの新しい言語機能、新しいコンパイラ動作が追加されます。</span><span class="sxs-lookup"><span data-stu-id="39d01-109">C# 7.1 adds the [language version selection](../language-reference/configure-language-version.md) configuration element, three new language features, and new compiler behavior.</span></span>

<span data-ttu-id="39d01-110">このリリースの新しい言語機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="39d01-110">The new language features in this release are:</span></span>

* [<span data-ttu-id="39d01-111">`async` `Main` メソッド</span><span class="sxs-lookup"><span data-stu-id="39d01-111">`async` `Main` method</span></span>](#async-main)
  - <span data-ttu-id="39d01-112">アプリケーションのエントリ ポイントに `async` 修飾子を設定できます。</span><span class="sxs-lookup"><span data-stu-id="39d01-112">The entry point for an application can have the `async` modifier.</span></span>
* [<span data-ttu-id="39d01-113">`default` リテラル式</span><span class="sxs-lookup"><span data-stu-id="39d01-113">`default` literal expressions</span></span>](#default-literal-expressions)
  - <span data-ttu-id="39d01-114">ターゲットの種類を推論できるとき、既定の値式で既定のリテラル式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="39d01-114">You can use default literal expressions in default value expressions when the target type can be inferred.</span></span>
* [<span data-ttu-id="39d01-115">推論されたタプル要素の名前</span><span class="sxs-lookup"><span data-stu-id="39d01-115">Inferred tuple element names</span></span>](#inferred-tuple-element-names)
  - <span data-ttu-id="39d01-116">タプル要素の名前は、多くの場合、タプル初期化から推論できます。</span><span class="sxs-lookup"><span data-stu-id="39d01-116">The names of tuple elements can be inferred from tuple initialization in many cases.</span></span>
* [<span data-ttu-id="39d01-117">ジェネリック型パラメーターのパターン マッチ</span><span class="sxs-lookup"><span data-stu-id="39d01-117">Pattern matching on generic type parameters</span></span>](#pattern-matching-on-generic-type-parameters)
  - <span data-ttu-id="39d01-118">型がジェネリック型パラメーターである変数にパターン マッチ式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="39d01-118">You can use pattern match expressions on variables whose type is a generic type parameter.</span></span>

<span data-ttu-id="39d01-119">最後に、コンパイラには、[参照アセンブリ生成](#reference-assembly-generation)を制御する 2 つのオプション、`-refout` と `-refonly` があります。</span><span class="sxs-lookup"><span data-stu-id="39d01-119">Finally, the compiler has two options `-refout` and `-refonly` that control [reference assembly generation](#reference-assembly-generation).</span></span>

<span data-ttu-id="39d01-120">ポイント リリースで最新の機能を使用するには、[コンパイラ言語バージョンを構成](../language-reference/configure-language-version.md)し、バージョンを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39d01-120">To use the latest features in a point release, you need to [configure the compiler language version](../language-reference/configure-language-version.md) and select the version.</span></span>

## <a name="async-main"></a><span data-ttu-id="39d01-121">async main</span><span class="sxs-lookup"><span data-stu-id="39d01-121">Async main</span></span>

<span data-ttu-id="39d01-122">*async main* メソッドにより、`Main` メソッドで `await` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="39d01-122">An *async main* method enables you to use `await` in your `Main` method.</span></span>
<span data-ttu-id="39d01-123">以前は次のように記述する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="39d01-123">Previously you would need to write:</span></span>

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

<span data-ttu-id="39d01-124">それが次のように記述できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="39d01-124">You can now write:</span></span>

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

<span data-ttu-id="39d01-125">プログラムによって終了コードが返されない場合、<xref:System.Threading.Tasks.Task> を返す `Main` メソッドを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="39d01-125">If your program doesn't return an exit code, you can declare a `Main` method that returns a <xref:System.Threading.Tasks.Task>:</span></span>

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

<span data-ttu-id="39d01-126">プログラミング ガイドの [async main](../programming-guide/main-and-command-args/index.md) の記事に詳細があります。</span><span class="sxs-lookup"><span data-stu-id="39d01-126">You can read more about the details in the [async main](../programming-guide/main-and-command-args/index.md) article in the programming guide.</span></span>

## <a name="default-literal-expressions"></a><span data-ttu-id="39d01-127">既定のリテラル式</span><span class="sxs-lookup"><span data-stu-id="39d01-127">Default literal expressions</span></span>

<span data-ttu-id="39d01-128">既定のリテラル式は既定の値式の拡張版です。</span><span class="sxs-lookup"><span data-stu-id="39d01-128">Default literal expressions are an enhancement to default value expressions.</span></span>
<span data-ttu-id="39d01-129">これらの式によって変数が初期化され、既定値になります。</span><span class="sxs-lookup"><span data-stu-id="39d01-129">These expressions initialize a variable to the default value.</span></span> <span data-ttu-id="39d01-130">以前は次のように記述していました。</span><span class="sxs-lookup"><span data-stu-id="39d01-130">Where you previously would write:</span></span>

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

<span data-ttu-id="39d01-131">それが今では、初期化の右項で種類を省略できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="39d01-131">You can now omit the type on the right-hand side of the initialization:</span></span>

```csharp
Func<string, bool> whereClause = default;
```

<span data-ttu-id="39d01-132">この拡張の詳細は、C# プログラミング ガイドの[既定の値式](../programming-guide/statements-expressions-operators/default-value-expressions.md)に関する記事にあります。</span><span class="sxs-lookup"><span data-stu-id="39d01-132">You can learn more about this enhancement in the C# Programming Guide article on [default value expressions](../programming-guide/statements-expressions-operators/default-value-expressions.md).</span></span>

<span data-ttu-id="39d01-133">この拡張では、[既定のキーワード](../language-reference/keywords/default.md)の解析ルールも一部変更されています。</span><span class="sxs-lookup"><span data-stu-id="39d01-133">This enhancement also changes some of the parsing rules for the [default keyword](../language-reference/keywords/default.md).</span></span>

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="39d01-134">推論されたタプル要素の名前</span><span class="sxs-lookup"><span data-stu-id="39d01-134">Inferred tuple element names</span></span>

<span data-ttu-id="39d01-135">この機能は、C# 7.0 で導入されたタプル機能の小規模拡張です。</span><span class="sxs-lookup"><span data-stu-id="39d01-135">This feature is a small enhancement to the tuples feature introduced in C# 7.0.</span></span> <span data-ttu-id="39d01-136">タプルを何度初期化しても、代入の右項に使用される変数は、タプル要素に使用するものと同じ名前になります。</span><span class="sxs-lookup"><span data-stu-id="39d01-136">Many times when you initialize a tuple, the variables used for the right side of the assignment are the same as the names you'd like for the tuple elements:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

<span data-ttu-id="39d01-137">タプル要素の名前は、C# 7.1 でタプルの初期化に使用される変数から推測できます。</span><span class="sxs-lookup"><span data-stu-id="39d01-137">The names of tuple elements can be inferred from the variables used to initialize the tuple in C# 7.1:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

<span data-ttu-id="39d01-138">この機能の詳細については、[タプル](../tuples.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39d01-138">You can learn more about this feature in the [Tuples](../tuples.md) article.</span></span>

## <a name="pattern-matching-on-generic-type-parameters"></a><span data-ttu-id="39d01-139">ジェネリック型パラメーターのパターン マッチ</span><span class="sxs-lookup"><span data-stu-id="39d01-139">Pattern matching on generic type parameters</span></span>

<span data-ttu-id="39d01-140">C#7.1 以降では、`is` 型パターンと `switch` 型パターンのパターン式は、ジェネリック型パラメーターの型を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="39d01-140">Beginning with C# 7.1, the pattern expression for `is` and the `switch` type pattern may have the type of a generic type parameter.</span></span> <span data-ttu-id="39d01-141">これは `struct` 型か `class` 型のいずれかである可能性がある型を確認し、ボックス化を回避するときに最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="39d01-141">This can be most useful when checking types that may be either `struct` or `class` types, and you want to avoid boxing.</span></span>

## <a name="reference-assembly-generation"></a><span data-ttu-id="39d01-142">参照アセンブリ生成</span><span class="sxs-lookup"><span data-stu-id="39d01-142">Reference assembly generation</span></span>

<span data-ttu-id="39d01-143">"*参照専用アセンブリ*" を生成する新しい 2 つのコンパイラ オプション [-refout](../language-reference/compiler-options/refout-compiler-option.md) と [-refonly](../language-reference/compiler-options/refonly-compiler-option.md) があります。</span><span class="sxs-lookup"><span data-stu-id="39d01-143">There are two new compiler options that generate *reference-only assemblies*: [-refout](../language-reference/compiler-options/refout-compiler-option.md) and [-refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span></span>
<span data-ttu-id="39d01-144">リンク先の記事には、オプションと参照アセンブリに関する詳細があります。</span><span class="sxs-lookup"><span data-stu-id="39d01-144">The linked articles explain these options and reference assemblies in more detail.</span></span>
