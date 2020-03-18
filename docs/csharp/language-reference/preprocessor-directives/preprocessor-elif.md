---
title: '#elif - C# リファレンス'
ms.date: 07/20/2015
f1_keywords:
- '#elif'
helpviewer_keywords:
- '#elif directive [C#]'
ms.assetid: 731d78df-08e0-4d51-b8c8-f193c27de13f
ms.openlocfilehash: c78818f40b76414d289af6c704ff019b63befe37
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712573"
---
# <a name="elif-c-reference"></a><span data-ttu-id="529c5-102">#elif (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="529c5-102">#elif (C# Reference)</span></span>
<span data-ttu-id="529c5-103">`#elif` を使用すると、複合条件付きディレクティブを作成できます。</span><span class="sxs-lookup"><span data-stu-id="529c5-103">`#elif` lets you create a compound conditional directive.</span></span> <span data-ttu-id="529c5-104">`#elif` 式が評価されるのは、先行するディレクティブ式 [#if](./preprocessor-if.md) および `#elif` (オプション) が `true` と評価されなかった場合です。</span><span class="sxs-lookup"><span data-stu-id="529c5-104">The `#elif` expression will be evaluated if neither the preceding [#if](./preprocessor-if.md) nor any preceding, optional, `#elif` directive expressions evaluate to `true`.</span></span> <span data-ttu-id="529c5-105">`#elif` 式が `true` と評価された場合は、`#elif` と次の条件付きディレクティブの間にあるすべてのコードが、コンパイラによって評価されます。</span><span class="sxs-lookup"><span data-stu-id="529c5-105">If a `#elif` expression evaluates to `true`, the compiler evaluates all the code between the `#elif` and the next conditional directive.</span></span> <span data-ttu-id="529c5-106">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="529c5-106">For example:</span></span>  
  
```csharp
#define VC7  
//...  
#if debug  
    Console.WriteLine("Debug build");  
#elif VC7  
    Console.WriteLine("Visual Studio 7");  
#endif  
```  
  
 <span data-ttu-id="529c5-107">複数のシンボルを評価するときには、`==` (等値)、`!=` (非等値)、`&&` (AND)、および `||` (OR) の演算子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="529c5-107">You can use the operators `==` (equality), `!=` (inequality), `&&` (and), and `||` (or), to evaluate multiple symbols.</span></span> <span data-ttu-id="529c5-108">シンボルと演算子は、かっこを使用してグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="529c5-108">You can also group symbols and operators with parentheses.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="529c5-109">解説</span><span class="sxs-lookup"><span data-stu-id="529c5-109">Remarks</span></span>  
 <span data-ttu-id="529c5-110">`#elif` では、次のように記述した場合と同じ結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="529c5-110">`#elif` is equivalent to using:</span></span>  
  
```csharp
#else  
#if  
```  
  
 <span data-ttu-id="529c5-111">`#elif` を使用する方が簡単です。`#if` には対になる [#endif](./preprocessor-endif.md) が必要ですが、`#elif` では対応する `#endif` が不要なためです。</span><span class="sxs-lookup"><span data-stu-id="529c5-111">Using `#elif` is simpler, because each `#if` requires a [#endif](./preprocessor-endif.md), whereas a `#elif` can be used without a matching `#endif`.</span></span>  
  
 <span data-ttu-id="529c5-112">[ の使用例については、「](./preprocessor-if.md)#if`#elif`」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="529c5-112">See [#if](./preprocessor-if.md) for an example of how to use `#elif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="529c5-113">参照</span><span class="sxs-lookup"><span data-stu-id="529c5-113">See also</span></span>

- [<span data-ttu-id="529c5-114">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="529c5-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="529c5-115">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="529c5-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="529c5-116">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="529c5-116">C# Preprocessor Directives</span></span>](./index.md)
