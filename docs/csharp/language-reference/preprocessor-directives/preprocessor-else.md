---
description: '#else - C# リファレンス'
title: '#else - C# リファレンス'
ms.date: 07/20/2015
f1_keywords:
- '#else'
helpviewer_keywords:
- '#else directive [C#]'
ms.assetid: 6a347322-cfa2-4a86-98f8-ddfa2cb7d4db
ms.openlocfilehash: fb1a9f30a42c78b5c4c7323ec213ab8c20b9bb76
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138177"
---
# <a name="else-c-reference"></a><span data-ttu-id="d19af-103">#else (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="d19af-103">#else (C# Reference)</span></span>
<span data-ttu-id="d19af-104">`#else` を使用すると、複合条件付きディレクティブを作成できるため、先行する [#if](./preprocessor-if.md) または (省略可能な) [#elif](./preprocessor-elif.md) ディレクティブの式がいずれも `true` に評価されない場合は、コンパイラが `#else` と以降の `#endif` の間のすべてのコードを評価します。</span><span class="sxs-lookup"><span data-stu-id="d19af-104">`#else` lets you create a compound conditional directive, so that, if none of the expressions in the preceding [#if](./preprocessor-if.md) or (optional) [#elif](./preprocessor-elif.md) directives evaluate to `true`, the compiler will evaluate all code between `#else` and the subsequent `#endif`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d19af-105">注釈</span><span class="sxs-lookup"><span data-stu-id="d19af-105">Remarks</span></span>  
 <span data-ttu-id="d19af-106">[#endif](./preprocessor-endif.md) が、`#else` の後の次のプリプロセッサ ディレクティブになる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d19af-106">[#endif](./preprocessor-endif.md) must be the next preprocessor directive after `#else`.</span></span> <span data-ttu-id="d19af-107">`#else` の使用例については、「[#if](./preprocessor-if.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d19af-107">See [#if](./preprocessor-if.md) for an example of how to use `#else`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d19af-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="d19af-108">See also</span></span>

- [<span data-ttu-id="d19af-109">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="d19af-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d19af-110">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="d19af-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d19af-111">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="d19af-111">C# Preprocessor Directives</span></span>](./index.md)
