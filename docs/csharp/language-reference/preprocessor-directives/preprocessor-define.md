---
description: '#define - C# リファレンス'
title: '#define - C# リファレンス'
ms.date: 06/30/2018
f1_keywords:
- '#define'
helpviewer_keywords:
- '#define directive [C#]'
ms.assetid: 23638b8f-779c-450e-b600-d55682de7d01
ms.openlocfilehash: a37f883a249ec74b66769ee40b84b20e8568c451
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89132340"
---
# <a name="define-c-reference"></a><span data-ttu-id="49095-103">#define (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="49095-103">#define (C# Reference)</span></span>
<span data-ttu-id="49095-104">`#define` は、シンボルを定義するために使用します。</span><span class="sxs-lookup"><span data-stu-id="49095-104">You use `#define` to define a symbol.</span></span> <span data-ttu-id="49095-105">次の例に示すように、定義したシンボルを式として [#if](./preprocessor-if.md) ディレクティブに渡すと、式は `true` と評価されます。</span><span class="sxs-lookup"><span data-stu-id="49095-105">When you use the symbol as the expression that's passed to the [#if](./preprocessor-if.md) directive, the expression will evaluate to `true`, as the following example shows:</span></span>  

 ```csharp
 #define DEBUG
 ```
  
## <a name="remarks"></a><span data-ttu-id="49095-106">注釈</span><span class="sxs-lookup"><span data-stu-id="49095-106">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="49095-107">`#define` ディレクティブを使用して、通常 C および C++ で行うように定数値を宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="49095-107">The `#define` directive cannot be used to declare constant values as is typically done in C and C++.</span></span> <span data-ttu-id="49095-108">C# の定数は、クラスまたは構造体の静的メンバーとして定義することができます。</span><span class="sxs-lookup"><span data-stu-id="49095-108">Constants in C# are best defined as static members of a class or struct.</span></span> <span data-ttu-id="49095-109">そのような定数がいくつかある場合は、それを保持するための "Constants" クラスを個別に作成することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="49095-109">If you have several such constants, consider creating a separate "Constants" class to hold them.</span></span>  
  
 <span data-ttu-id="49095-110">シンボルを使用して、コンパイル条件を指定できます。</span><span class="sxs-lookup"><span data-stu-id="49095-110">Symbols can be used to specify conditions for compilation.</span></span> <span data-ttu-id="49095-111">シンボルは、[#if](./preprocessor-if.md) または [#elif](./preprocessor-elif.md) で評価できます。</span><span class="sxs-lookup"><span data-stu-id="49095-111">You can test for the symbol with either [#if](./preprocessor-if.md) or [#elif](./preprocessor-elif.md).</span></span> <span data-ttu-id="49095-112">また、<xref:System.Diagnostics.ConditionalAttribute> を使用して、条件付きコンパイルを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="49095-112">You can also use the <xref:System.Diagnostics.ConditionalAttribute> to perform conditional compilation.</span></span>  
  
 <span data-ttu-id="49095-113">シンボルを定義することはできますが、シンボルに値は代入できません。</span><span class="sxs-lookup"><span data-stu-id="49095-113">You can define a symbol, but you cannot assign a value to a symbol.</span></span> <span data-ttu-id="49095-114">`#define` ディレクティブは、ファイル内で、プリプロセッサ ディレクティブではない他の命令よりも前に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49095-114">The `#define` directive must appear in the file before you use any instructions that aren't also preprocessor directives.</span></span>  
  
 <span data-ttu-id="49095-115">シンボルは、[-define](../compiler-options/define-compiler-option.md) コンパイラ オプションでも定義できます。</span><span class="sxs-lookup"><span data-stu-id="49095-115">You can also define a symbol with the [-define](../compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="49095-116">[#undef](./preprocessor-undef.md) を使うと、シンボルを未定義状態にできます。</span><span class="sxs-lookup"><span data-stu-id="49095-116">You can undefine a symbol with [#undef](./preprocessor-undef.md).</span></span>  
  
 <span data-ttu-id="49095-117">`-define` または `#define` で定義されたシンボルは、同じ名前の変数とは競合しません。</span><span class="sxs-lookup"><span data-stu-id="49095-117">A symbol that you define with `-define` or with `#define` does not conflict with a variable of the same name.</span></span> <span data-ttu-id="49095-118">変数名をプリプロセッサ ディレクティブに渡すことはできません。シンボルはプリプロセッサ ディレクティブだけで評価されます。</span><span class="sxs-lookup"><span data-stu-id="49095-118">That is, a variable name should not be passed to a preprocessor directive and a symbol can only be evaluated by a preprocessor directive.</span></span>  
  
 <span data-ttu-id="49095-119">`#define` で定義されたシンボルのスコープは、そのシンボルが定義されたファイル内だけです。</span><span class="sxs-lookup"><span data-stu-id="49095-119">The scope of a symbol that was created by using `#define` is the file in which the symbol was defined.</span></span>  
  
 <span data-ttu-id="49095-120">次の例に示すように、`#define` ディレクティブは、ファイルの先頭で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49095-120">As the following example shows, you must put `#define` directives at the top of the file.</span></span>  
  
```csharp  
#define DEBUG  
//#define TRACE  
#undef TRACE  
  
using System;  
  
public class TestDefine  
{  
    static void Main()  
    {  
#if (DEBUG)  
        Console.WriteLine("Debugging is enabled.");  
#endif  
  
#if (TRACE)  
     Console.WriteLine("Tracing is enabled.");  
#endif  
    }  
}  
// Output:  
// Debugging is enabled.  
```  
  
 <span data-ttu-id="49095-121">シンボルの定義を解除する方法の例については、「[#undef](./preprocessor-undef.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49095-121">For an example of how to undefine a symbol, see [#undef](./preprocessor-undef.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49095-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="49095-122">See also</span></span>

- [<span data-ttu-id="49095-123">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="49095-123">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="49095-124">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="49095-124">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="49095-125">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="49095-125">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="49095-126">const</span><span class="sxs-lookup"><span data-stu-id="49095-126">const</span></span>](../keywords/const.md)
- [<span data-ttu-id="49095-127">方法: トレースとデバッグを指定して条件付きコンパイルを実行する</span><span class="sxs-lookup"><span data-stu-id="49095-127">How to: Compile Conditionally with Trace and Debug</span></span>](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)
- [<span data-ttu-id="49095-128">#undef</span><span class="sxs-lookup"><span data-stu-id="49095-128">#undef</span></span>](./preprocessor-undef.md)
- [<span data-ttu-id="49095-129">#if</span><span class="sxs-lookup"><span data-stu-id="49095-129">#if</span></span>](./preprocessor-if.md)
