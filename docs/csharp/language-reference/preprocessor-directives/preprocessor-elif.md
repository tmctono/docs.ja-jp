---
title: '#elif - C# リファレンス'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#elif'
helpviewer_keywords:
- '#elif directive [C#]'
ms.assetid: 731d78df-08e0-4d51-b8c8-f193c27de13f
ms.openlocfilehash: b04db4bd23a459043efec59b8ebf9d322defbcf7
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69608587"
---
# <a name="elif-c-reference"></a><span data-ttu-id="31a8d-102">#elif (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="31a8d-102">#elif (C# Reference)</span></span>
<span data-ttu-id="31a8d-103">`#elif` を使用すると、複合条件付きディレクティブを作成できます。</span><span class="sxs-lookup"><span data-stu-id="31a8d-103">`#elif` lets you create a compound conditional directive.</span></span> <span data-ttu-id="31a8d-104">`#elif` 式が評価されるのは、先行するディレクティブ式 [#if](./preprocessor-if.md) および `#elif` (オプション) が `true` と評価されなかった場合です。</span><span class="sxs-lookup"><span data-stu-id="31a8d-104">The `#elif` expression will be evaluated if neither the preceding [#if](./preprocessor-if.md) nor any preceding, optional, `#elif` directive expressions evaluate to `true`.</span></span> <span data-ttu-id="31a8d-105">`#elif` 式が `true` と評価された場合は、`#elif` と次の条件付きディレクティブの間にあるすべてのコードが、コンパイラによって評価されます。</span><span class="sxs-lookup"><span data-stu-id="31a8d-105">If a `#elif` expression evaluates to `true`, the compiler evaluates all the code between the `#elif` and the next conditional directive.</span></span> <span data-ttu-id="31a8d-106">例:</span><span class="sxs-lookup"><span data-stu-id="31a8d-106">For example:</span></span>  
  
```csharp
#define VC7  
//...  
#if debug  
    Console.WriteLine("Debug build");  
#elif VC7  
    Console.WriteLine("Visual Studio 7");  
#endif  
```  
  
 <span data-ttu-id="31a8d-107">複数のシンボルを評価するときには、`==` (等値)、`!=` (非等値)、`&&` (AND)、および `||` (OR) の演算子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="31a8d-107">You can use the operators `==` (equality), `!=` (inequality), `&&` (and), and `||` (or), to evaluate multiple symbols.</span></span> <span data-ttu-id="31a8d-108">シンボルと演算子は、かっこを使用してグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="31a8d-108">You can also group symbols and operators with parentheses.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31a8d-109">解説</span><span class="sxs-lookup"><span data-stu-id="31a8d-109">Remarks</span></span>  
 <span data-ttu-id="31a8d-110">`#elif` では、次のように記述した場合と同じ結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="31a8d-110">`#elif` is equivalent to using:</span></span>  
  
```csharp
#else  
#if  
```  
  
 <span data-ttu-id="31a8d-111">`#elif` を使用する方が簡単です。`#if` には対になる [#endif](./preprocessor-endif.md) が必要ですが、`#elif` では対応する `#endif` が不要なためです。</span><span class="sxs-lookup"><span data-stu-id="31a8d-111">Using `#elif` is simpler, because each `#if` requires a [#endif](./preprocessor-endif.md), whereas a `#elif` can be used without a matching `#endif`.</span></span>  
  
 <span data-ttu-id="31a8d-112">`#elif` の使用例については、「[#if](./preprocessor-if.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31a8d-112">See [#if](./preprocessor-if.md) for an example of how to use `#elif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31a8d-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="31a8d-113">See also</span></span>

- [<span data-ttu-id="31a8d-114">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="31a8d-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="31a8d-115">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="31a8d-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="31a8d-116">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="31a8d-116">C# Preprocessor Directives</span></span>](./index.md)
