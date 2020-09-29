---
description: '#else - C# リファレンス'
title: '#else - C# リファレンス'
ms.date: 07/20/2015
f1_keywords:
- '#else'
helpviewer_keywords:
- '#else directive [C#]'
ms.assetid: 6a347322-cfa2-4a86-98f8-ddfa2cb7d4db
ms.openlocfilehash: f0dc8c34672c3e9e5a2207211794fbc8099640c5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168674"
---
# <a name="else-c-reference"></a><span data-ttu-id="23707-103">#else (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="23707-103">#else (C# Reference)</span></span>

<span data-ttu-id="23707-104">`#else` を使用すると、複合条件付きディレクティブを作成できるため、先行する [#if](./preprocessor-if.md) または (省略可能な) [#elif](./preprocessor-elif.md) ディレクティブの式がいずれも `true` に評価されない場合は、コンパイラが `#else` と以降の `#endif` の間のすべてのコードを評価します。</span><span class="sxs-lookup"><span data-stu-id="23707-104">`#else` lets you create a compound conditional directive, so that, if none of the expressions in the preceding [#if](./preprocessor-if.md) or (optional) [#elif](./preprocessor-elif.md) directives evaluate to `true`, the compiler will evaluate all code between `#else` and the subsequent `#endif`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23707-105">解説</span><span class="sxs-lookup"><span data-stu-id="23707-105">Remarks</span></span>  

 <span data-ttu-id="23707-106">[#endif](./preprocessor-endif.md) が、`#else` の後の次のプリプロセッサ ディレクティブになる必要があります。</span><span class="sxs-lookup"><span data-stu-id="23707-106">[#endif](./preprocessor-endif.md) must be the next preprocessor directive after `#else`.</span></span> <span data-ttu-id="23707-107">`#else` の使用例については、「[#if](./preprocessor-if.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23707-107">See [#if](./preprocessor-if.md) for an example of how to use `#else`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23707-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="23707-108">See also</span></span>

- [<span data-ttu-id="23707-109">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="23707-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="23707-110">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="23707-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="23707-111">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="23707-111">C# Preprocessor Directives</span></span>](./index.md)
