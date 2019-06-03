---
title: '#if プリプロセッサ ディレクティブ - C# リファレンス'
ms.custom: seodec18
ms.date: 06/30/2018
f1_keywords:
- '#if'
helpviewer_keywords:
- '#if directive [C#]'
ms.assetid: 48cabbff-ca82-491f-a56a-eeccd528c7c2
ms.openlocfilehash: 12ef0926665103e739ed4a8ee83ff895b439fffc
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300075"
---
# <a name="if-c-reference"></a><span data-ttu-id="dda19-102">#if (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="dda19-102">#if (C# Reference)</span></span>

<span data-ttu-id="dda19-103">C# コンパイラでは、`#if` ディレクティブ、次いで [#endif](preprocessor-endif.md) ディレクティブが検出されると、これらのディレクティブ間のコードがコンパイルされます (指定されたシンボルが定義されている場合に限る)。</span><span class="sxs-lookup"><span data-stu-id="dda19-103">When the C# compiler encounters an `#if` directive, followed eventually by an [#endif](preprocessor-endif.md) directive, it compiles the code between the directives only if the specified symbol is defined.</span></span> <span data-ttu-id="dda19-104">C および C++ とは異なり、シンボルに数値を割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="dda19-104">Unlike C and C++, you cannot assign a numeric value to a symbol.</span></span> <span data-ttu-id="dda19-105">C# の #if ステートメントはブール値で、シンボルが定義されているかどうかのみをテストします。</span><span class="sxs-lookup"><span data-stu-id="dda19-105">The #if statement in C# is Boolean and only tests whether the symbol has been defined or not.</span></span> <span data-ttu-id="dda19-106">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="dda19-106">For example:</span></span>

```csharp
#if DEBUG
    Console.WriteLine("Debug version");
#endif
```

<span data-ttu-id="dda19-107">[==](../operators/equality-operators.md#equality-operator-) (等しい) および [!=](../operators/equality-operators.md#inequality-operator-) (等しくない) の各演算子は、[true](../keywords/true-literal.md) か [false](../keywords/false-literal.md) のどちらであるかのテストにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="dda19-107">You can use the operators [==](../operators/equality-operators.md#equality-operator-) (equality) and [!=](../operators/equality-operators.md#inequality-operator-) (inequality) only to test for [true](../keywords/true-literal.md) or [false](../keywords/false-literal.md).</span></span> <span data-ttu-id="dda19-108">true は、シンボルが定義されていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="dda19-108">True means the symbol is defined.</span></span> <span data-ttu-id="dda19-109">ステートメント `#if DEBUG` と `#if (DEBUG == true)` の意味は同じです。</span><span class="sxs-lookup"><span data-stu-id="dda19-109">The statement `#if DEBUG` has the same meaning as `#if (DEBUG == true)`.</span></span> <span data-ttu-id="dda19-110">[&&](../operators/boolean-logical-operators.md#conditional-logical-and-operator-) (かつ)、[&#124;&#124;](../operators/boolean-logical-operators.md#conditional-logical-or-operator-) (または)、および [!](../operators/boolean-logical-operators.md#logical-negation-operator-)</span><span class="sxs-lookup"><span data-stu-id="dda19-110">You can use the operators [&&](../operators/boolean-logical-operators.md#conditional-logical-and-operator-) (and), [&#124;&#124;](../operators/boolean-logical-operators.md#conditional-logical-or-operator-) (or), and [!](../operators/boolean-logical-operators.md#logical-negation-operator-)</span></span> <span data-ttu-id="dda19-111">(not) の各演算子を使用すると、複数のシンボルが定義されているかどうかを評価できます。</span><span class="sxs-lookup"><span data-stu-id="dda19-111">(not) to evaluate whether multiple symbols have been defined.</span></span> <span data-ttu-id="dda19-112">シンボルと演算子は、かっこを使用してグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="dda19-112">You can also group symbols and operators with parentheses.</span></span>

## <a name="remarks"></a><span data-ttu-id="dda19-113">解説</span><span class="sxs-lookup"><span data-stu-id="dda19-113">Remarks</span></span>

<span data-ttu-id="dda19-114">`#if` と [#else](preprocessor-else.md)、[#elif](preprocessor-elif.md)、[#endif](preprocessor-endif.md)、[#define](preprocessor-define.md)、[#undef](preprocessor-undef.md) の各ディレクティブを組み合わせると、1 つ以上のシンボルが存在するかどうかに応じてコードを含めたり除外したりできます。</span><span class="sxs-lookup"><span data-stu-id="dda19-114">`#if`, along with the [#else](preprocessor-else.md), [#elif](preprocessor-elif.md), [#endif](preprocessor-endif.md), [#define](preprocessor-define.md), and [#undef](preprocessor-undef.md) directives, lets you include or exclude code based on the existence of one or more symbols.</span></span> <span data-ttu-id="dda19-115">これは、デバッグ ビルドのコードをコンパイルする場合や、特定の構成でコンパイルを行う場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="dda19-115">This can be useful when compiling code for a debug build or when compiling for a specific configuration.</span></span>

<span data-ttu-id="dda19-116">`#if` ディレクティブで始まる条件付きディレクティブは、`#endif` ディレクティブで明示的に終了させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="dda19-116">A conditional directive beginning with a `#if` directive must explicitly be terminated with a `#endif` directive.</span></span>

<span data-ttu-id="dda19-117">`#define` を使用するとシンボルを定義できます。</span><span class="sxs-lookup"><span data-stu-id="dda19-117">`#define` lets you define a symbol.</span></span> <span data-ttu-id="dda19-118">定義したシンボルを `#if` ディレクティブに渡す式として使用すると、この式は `true` と評価されます。</span><span class="sxs-lookup"><span data-stu-id="dda19-118">By then using the symbol as the expression passed to the `#if` directive, the expression evaluates to `true`.</span></span>

<span data-ttu-id="dda19-119">シンボルは、[-define](../compiler-options/define-compiler-option.md) コンパイラ オプションでも定義できます。</span><span class="sxs-lookup"><span data-stu-id="dda19-119">You can also define a symbol with the [-define](../compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="dda19-120">[#undef](preprocessor-undef.md) を使うと、シンボルを未定義状態にできます。</span><span class="sxs-lookup"><span data-stu-id="dda19-120">You can undefine a symbol with [#undef](preprocessor-undef.md).</span></span>

<span data-ttu-id="dda19-121">`-define` または `#define` で定義されたシンボルは、同じ名前の変数とは競合しません。</span><span class="sxs-lookup"><span data-stu-id="dda19-121">A symbol that you define with `-define` or with `#define` doesn't conflict with a variable of the same name.</span></span> <span data-ttu-id="dda19-122">変数名をプリプロセッサ ディレクティブに渡すことはできません。シンボルはプリプロセッサ ディレクティブだけで評価されます。</span><span class="sxs-lookup"><span data-stu-id="dda19-122">That is, a variable name should not be passed to a preprocessor directive, and a symbol can only be evaluated by a preprocessor directive.</span></span>

<span data-ttu-id="dda19-123">`#define` を使用して作成したシンボルのスコープは、そのシンボルが定義されているファイルです。</span><span class="sxs-lookup"><span data-stu-id="dda19-123">The scope of a symbol created with `#define` is the file in which it was defined.</span></span>

<span data-ttu-id="dda19-124">また、ビルド システムも、各種[ターゲット フレームワーク](../../../standard/frameworks.md)を表す、定義済みプリプロセッサ シンボルを認識します。</span><span class="sxs-lookup"><span data-stu-id="dda19-124">The build system is also aware of predefined preprocessor symbols representing different [target frameworks](../../../standard/frameworks.md).</span></span> <span data-ttu-id="dda19-125">これは、複数の .NET の実装やバージョンをターゲットとできるアプリケーションを作成する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="dda19-125">They're useful when creating applications that can target more than one .NET implementation or version.</span></span>

[!INCLUDE [Preprocessor symbols](~/includes/preprocessor-symbols.md)]

<span data-ttu-id="dda19-126">他の定義済みシンボルとしては、DEBUG 定数と TRACE 定数があります。</span><span class="sxs-lookup"><span data-stu-id="dda19-126">Other predefined symbols include the DEBUG and TRACE constants.</span></span> <span data-ttu-id="dda19-127">`#define` を使用して、プロジェクトに設定された値をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="dda19-127">You can override the values set for the project using `#define`.</span></span> <span data-ttu-id="dda19-128">たとえば、DEBUG シンボルは、ビルド構成プロパティ ("デバッグ" モードまたは "リリース" モード) に応じて自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="dda19-128">The DEBUG symbol, for example, is automatically set depending on your build configuration properties ("Debug" or "Release" mode).</span></span>

## <a name="examples"></a><span data-ttu-id="dda19-129">使用例</span><span class="sxs-lookup"><span data-stu-id="dda19-129">Examples</span></span>

<span data-ttu-id="dda19-130">次の例は、ファイルで MYTEST シンボルを定義し、MYTEST シンボルと DEBUG シンボルの値をテストする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="dda19-130">The following example shows you how to define a MYTEST symbol on a file and then test the values of the MYTEST and DEBUG symbols.</span></span> <span data-ttu-id="dda19-131">この例の出力は、プロジェクトをデバッグとリリースのどちらの構成モードでビルドするかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="dda19-131">The output of this example depends on whether you built the project on Debug or Release configuration mode.</span></span>

```csharp
#define MYTEST
using System;
public class MyClass
{
    static void Main()
    {
#if (DEBUG && !MYTEST)
        Console.WriteLine("DEBUG is defined");
#elif (!DEBUG && MYTEST)
        Console.WriteLine("MYTEST is defined");
#elif (DEBUG && MYTEST)
        Console.WriteLine("DEBUG and MYTEST are defined");  
#else
        Console.WriteLine("DEBUG and MYTEST are not defined");
#endif
    }
}
```

<span data-ttu-id="dda19-132">次の例は、各種ターゲット フレームワークをテストし、可能な場合には新しい API を使用できるようにする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="dda19-132">The following example shows you how to test for different target frameworks so you can use newer APIs when possible:</span></span>

```csharp
public class MyClass
{
    static void Main()
    {
#if NET40
        WebClient _client = new WebClient();
#else
        HttpClient _client = new HttpClient();
#endif
    }
    //...
}
```

## <a name="see-also"></a><span data-ttu-id="dda19-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="dda19-133">See also</span></span>

- [<span data-ttu-id="dda19-134">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="dda19-134">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="dda19-135">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="dda19-135">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="dda19-136">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="dda19-136">C# Preprocessor Directives</span></span>](index.md)
- [<span data-ttu-id="dda19-137">方法: トレースとデバッグを指定して条件付きコンパイルを実行する</span><span class="sxs-lookup"><span data-stu-id="dda19-137">How to: Compile Conditionally with Trace and Debug</span></span>](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)
