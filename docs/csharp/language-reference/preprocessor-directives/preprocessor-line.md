---
title: '#line - C# リファレンス'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#line'
helpviewer_keywords:
- '#line directive [C#]'
ms.assetid: 6439e525-5dd5-4acb-b8ea-efabb32ff95b
ms.openlocfilehash: b4ac4fd3277fb53251e87321500d1b8007458037
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69608540"
---
# <a name="line-c-reference"></a><span data-ttu-id="799cf-102">#line (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="799cf-102">#line (C# Reference)</span></span>

<span data-ttu-id="799cf-103">`#line` を使用すると、コンパイラの行番号および (必要に応じて) エラーと警告に出力されるファイル名を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="799cf-103">`#line` lets you modify the compiler's line numbering and (optionally) the file name output for errors and warnings.</span></span>

<span data-ttu-id="799cf-104">次の例では、行番号に関連付けられている 2 つの警告を報告する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="799cf-104">The following example shows how to report two warnings associated with line numbers.</span></span> <span data-ttu-id="799cf-105">`#line 200` ディレクティブは次の行番号が 200 (既定では #6) になるように強制し、次の `#line` ディレクティブまでファイル名を "Special" として報告します。</span><span class="sxs-lookup"><span data-stu-id="799cf-105">The `#line 200` directive forces the next line's number to be 200 (although the default is #6), and until the next `#line` directive, the filename will be reported as "Special".</span></span> <span data-ttu-id="799cf-106">`#line default` ディレクティブは、行の番号付けをその既定の番号付けに戻します。つまり、前のディレクティブで番号が付け直された行をカウントします。</span><span class="sxs-lookup"><span data-stu-id="799cf-106">The `#line default` directive returns the line numbering to its default numbering, which counts the lines that were renumbered by the previous directive.</span></span>

```csharp
class MainClass
{
    static void Main()
    {
#line 200 "Special"
        int i;
        int j;
#line default
        char c;
        float f;
#line hidden // numbering not affected
        string s;
        double d;
    }
}
```

<span data-ttu-id="799cf-107">コンパイルで生成される出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="799cf-107">Compilation produces the following output:</span></span>

```console
Special(200,13): warning CS0168: The variable 'i' is declared but never used
Special(201,13): warning CS0168: The variable 'j' is declared but never used
MainClass.cs(9,14): warning CS0168: The variable 'c' is declared but never used
MainClass.cs(10,15): warning CS0168: The variable 'f' is declared but never used
MainClass.cs(12,16): warning CS0168: The variable 's' is declared but never used
MainClass.cs(13,16): warning CS0168: The variable 'd' is declared but never used
```

## <a name="remarks"></a><span data-ttu-id="799cf-108">解説</span><span class="sxs-lookup"><span data-stu-id="799cf-108">Remarks</span></span>

<span data-ttu-id="799cf-109">`#line` ディレクティブは、ビルド プロセスで自動化された中間ステップで使用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="799cf-109">The `#line` directive might be used in an automated, intermediate step in the build process.</span></span> <span data-ttu-id="799cf-110">たとえば、行が元のソース コード ファイルから削除されても、ファイル内の元の行番号付けに基づいてコンパイラに引き続き出力を生成させる場合は、行を削除してから `#line` を使用して元の行番号付けをシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="799cf-110">For example, if lines were removed from the original source code file, but you still wanted the compiler to generate output based on the original line numbering in the file, you could remove lines and then simulate the original line numbering with `#line`.</span></span>

<span data-ttu-id="799cf-111">開発者がコードをステップ実行すると、`#line hidden` と次の `#line` ディレクティブ (別の `#line hidden` ディレクティブではないと仮定) の間のすべての行がステップ オーバーされるように、`#line hidden` ディレクティブは、連続する行をデバッガーから隠します。</span><span class="sxs-lookup"><span data-stu-id="799cf-111">The `#line hidden` directive hides the successive lines from the debugger, such that when the developer steps through the code, any lines between a `#line hidden` and the next `#line` directive (assuming that it is not another `#line hidden` directive) will be stepped over.</span></span> <span data-ttu-id="799cf-112">このオプションは、ユーザー定義のコードとコンピューターによって生成されたコードを ASP.NET が区別できるようするために使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="799cf-112">This option can also be used to allow ASP.NET to differentiate between user-defined and machine-generated code.</span></span> <span data-ttu-id="799cf-113">この機能を主に使用しているのは ASP.NET ですが、より多くのソース ジェネレーターが利用できる可能性はあります。</span><span class="sxs-lookup"><span data-stu-id="799cf-113">Although ASP.NET is the primary consumer of this feature, it is likely that more source generators will make use of it.</span></span>

<span data-ttu-id="799cf-114">`#line hidden` ディレクティブはエラーの報告でのファイル名や行番号には影響しません。</span><span class="sxs-lookup"><span data-stu-id="799cf-114">A `#line hidden` directive does not affect file names or line numbers in error reporting.</span></span> <span data-ttu-id="799cf-115">つまり、非表示のブロックでエラーが発生した場合、コンパイラはエラーの現在のファイル名と行番号を報告します。</span><span class="sxs-lookup"><span data-stu-id="799cf-115">That is, if an error is encountered in a hidden block, the compiler will report the current file name and line number of the error.</span></span>

<span data-ttu-id="799cf-116">`#line filename` ディレクティブは、コンパイラ出力に表示するファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="799cf-116">The `#line filename` directive specifies the file name you want to appear in the compiler output.</span></span> <span data-ttu-id="799cf-117">既定では、ソース コード ファイルの実際の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="799cf-117">By default, the actual name of the source code file is used.</span></span> <span data-ttu-id="799cf-118">ファイル名は、二重引用符 ("") で囲み、前に行番号を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="799cf-118">The file name must be in double quotation marks ("") and must be preceded by a line number.</span></span>

<span data-ttu-id="799cf-119">ソース コード ファイルは、任意の数の `#line` ディレクティブを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="799cf-119">A source code file can have any number of `#line` directives.</span></span>

## <a name="example-1"></a><span data-ttu-id="799cf-120">例 1</span><span class="sxs-lookup"><span data-stu-id="799cf-120">Example 1</span></span>

<span data-ttu-id="799cf-121">次の例では、デバッガーがコード内の非表示の行を無視する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="799cf-121">The following example shows how the debugger ignores the hidden lines in the code.</span></span> <span data-ttu-id="799cf-122">例を実行すると、次の 3 行のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="799cf-122">When you run the example, it will display three lines of text.</span></span> <span data-ttu-id="799cf-123">しかし、例に示されているようにブレークポイントを設定し、F10 キーを押してコードをステップ実行すると、デバッガーが非表示の行を無視することがわかります。</span><span class="sxs-lookup"><span data-stu-id="799cf-123">However, when you set a break point, as shown in the example, and hit F10 to step through the code, you will notice that the debugger ignores the hidden line.</span></span> <span data-ttu-id="799cf-124">非表示の行にブレークポイントを設定した場合でも、デバッガーは無視することに注目してください。</span><span class="sxs-lookup"><span data-stu-id="799cf-124">Notice also that even if you set a break point at the hidden line, the debugger will still ignore it.</span></span>

```csharp
// preprocessor_linehidden.cs
using System;
class MainClass
{
    static void Main()
    {
        Console.WriteLine("Normal line #1."); // Set break point here.
#line hidden
        Console.WriteLine("Hidden line.");
#line default
        Console.WriteLine("Normal line #2.");
    }
}
```

## <a name="see-also"></a><span data-ttu-id="799cf-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="799cf-125">See also</span></span>

- [<span data-ttu-id="799cf-126">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="799cf-126">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="799cf-127">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="799cf-127">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="799cf-128">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="799cf-128">C# Preprocessor Directives</span></span>](./index.md)
