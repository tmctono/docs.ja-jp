---
title: '#define - C# リファレンス'
ms.date: 06/30/2018
f1_keywords:
- '#define'
helpviewer_keywords:
- '#define directive [C#]'
ms.assetid: 23638b8f-779c-450e-b600-d55682de7d01
ms.openlocfilehash: 7457b05ae827675969398792bcb02f025f3028fb
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712586"
---
# <a name="define-c-reference"></a><span data-ttu-id="7eb15-102">#define (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="7eb15-102">#define (C# Reference)</span></span>
<span data-ttu-id="7eb15-103">`#define` は、シンボルを定義するために使用します。</span><span class="sxs-lookup"><span data-stu-id="7eb15-103">You use `#define` to define a symbol.</span></span> <span data-ttu-id="7eb15-104">次の例に示すように、定義したシンボルを式として [#if](./preprocessor-if.md) ディレクティブに渡すと、式は `true` と評価されます。</span><span class="sxs-lookup"><span data-stu-id="7eb15-104">When you use the symbol as the expression that's passed to the [#if](./preprocessor-if.md) directive, the expression will evaluate to `true`, as the following example shows:</span></span>  
 
 ```csharp
 #define DEBUG
 ```
  
## <a name="remarks"></a><span data-ttu-id="7eb15-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="7eb15-105">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7eb15-106">`#define` ディレクティブを使用して、通常 C および C++ で行うように定数値を宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="7eb15-106">The `#define` directive cannot be used to declare constant values as is typically done in C and C++.</span></span> <span data-ttu-id="7eb15-107">C# の定数は、クラスまたは構造体の静的メンバーとして定義することができます。</span><span class="sxs-lookup"><span data-stu-id="7eb15-107">Constants in C# are best defined as static members of a class or struct.</span></span> <span data-ttu-id="7eb15-108">そのような定数がいくつかある場合は、それを保持するための "Constants" クラスを個別に作成することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="7eb15-108">If you have several such constants, consider creating a separate "Constants" class to hold them.</span></span>  
  
 <span data-ttu-id="7eb15-109">シンボルを使用して、コンパイル条件を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7eb15-109">Symbols can be used to specify conditions for compilation.</span></span> <span data-ttu-id="7eb15-110">シンボルは、[#if](./preprocessor-if.md) または [#elif](./preprocessor-elif.md) で評価できます。</span><span class="sxs-lookup"><span data-stu-id="7eb15-110">You can test for the symbol with either [#if](./preprocessor-if.md) or [#elif](./preprocessor-elif.md).</span></span> <span data-ttu-id="7eb15-111">また、<xref:System.Diagnostics.ConditionalAttribute> を使用して、条件付きコンパイルを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="7eb15-111">You can also use the <xref:System.Diagnostics.ConditionalAttribute> to perform conditional compilation.</span></span>  
  
 <span data-ttu-id="7eb15-112">シンボルを定義することはできますが、シンボルに値は代入できません。</span><span class="sxs-lookup"><span data-stu-id="7eb15-112">You can define a symbol, but you cannot assign a value to a symbol.</span></span> <span data-ttu-id="7eb15-113">`#define` ディレクティブは、ファイル内で、プリプロセッサ ディレクティブではない他の命令よりも前に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7eb15-113">The `#define` directive must appear in the file before you use any instructions that aren't also preprocessor directives.</span></span>  
  
 <span data-ttu-id="7eb15-114">シンボルは、[-define](../compiler-options/define-compiler-option.md) コンパイラ オプションでも定義できます。</span><span class="sxs-lookup"><span data-stu-id="7eb15-114">You can also define a symbol with the [-define](../compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="7eb15-115">[#undef](./preprocessor-undef.md) を使うと、シンボルを未定義状態にできます。</span><span class="sxs-lookup"><span data-stu-id="7eb15-115">You can undefine a symbol with [#undef](./preprocessor-undef.md).</span></span>  
  
 <span data-ttu-id="7eb15-116">`-define` または `#define` で定義されたシンボルは、同じ名前の変数とは競合しません。</span><span class="sxs-lookup"><span data-stu-id="7eb15-116">A symbol that you define with `-define` or with `#define` does not conflict with a variable of the same name.</span></span> <span data-ttu-id="7eb15-117">変数名をプリプロセッサ ディレクティブに渡すことはできません。シンボルはプリプロセッサ ディレクティブだけで評価されます。</span><span class="sxs-lookup"><span data-stu-id="7eb15-117">That is, a variable name should not be passed to a preprocessor directive and a symbol can only be evaluated by a preprocessor directive.</span></span>  
  
 <span data-ttu-id="7eb15-118">`#define` で定義されたシンボルのスコープは、そのシンボルが定義されたファイル内だけです。</span><span class="sxs-lookup"><span data-stu-id="7eb15-118">The scope of a symbol that was created by using `#define` is the file in which the symbol was defined.</span></span>  
  
 <span data-ttu-id="7eb15-119">次の例に示すように、`#define` ディレクティブは、ファイルの先頭で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7eb15-119">As the following example shows, you must put `#define` directives at the top of the file.</span></span>  
  
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
  
 <span data-ttu-id="7eb15-120">シンボルの定義を解除する方法の例については、「[#undef](./preprocessor-undef.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7eb15-120">For an example of how to undefine a symbol, see [#undef](./preprocessor-undef.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eb15-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="7eb15-121">See also</span></span>

- [<span data-ttu-id="7eb15-122">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="7eb15-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="7eb15-123">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="7eb15-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7eb15-124">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="7eb15-124">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="7eb15-125">const</span><span class="sxs-lookup"><span data-stu-id="7eb15-125">const</span></span>](../keywords/const.md)
- [<span data-ttu-id="7eb15-126">方法: トレースとデバッグを指定して条件付きコンパイルを実行する</span><span class="sxs-lookup"><span data-stu-id="7eb15-126">How to: Compile Conditionally with Trace and Debug</span></span>](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)
- [<span data-ttu-id="7eb15-127">#undef</span><span class="sxs-lookup"><span data-stu-id="7eb15-127">#undef</span></span>](./preprocessor-undef.md)
- [<span data-ttu-id="7eb15-128">#if</span><span class="sxs-lookup"><span data-stu-id="7eb15-128">#if</span></span>](./preprocessor-if.md)
