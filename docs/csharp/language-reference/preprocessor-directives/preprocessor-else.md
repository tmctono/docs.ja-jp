---
title: '#else - C# リファレンス'
ms.date: 07/20/2015
f1_keywords:
- '#else'
helpviewer_keywords:
- '#else directive [C#]'
ms.assetid: 6a347322-cfa2-4a86-98f8-ddfa2cb7d4db
ms.openlocfilehash: 967ef38687b739ef3bea3f8923ab26bba0b6cea9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712560"
---
# <a name="else-c-reference"></a><span data-ttu-id="53039-102">#else (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="53039-102">#else (C# Reference)</span></span>
<span data-ttu-id="53039-103">`#else` を使用すると、複合条件付きディレクティブを作成できるため、先行する [#if](./preprocessor-if.md) または (省略可能な) [#elif](./preprocessor-elif.md) ディレクティブの式がいずれも `true` に評価されない場合は、コンパイラが `#else` と以降の `#endif` の間のすべてのコードを評価します。</span><span class="sxs-lookup"><span data-stu-id="53039-103">`#else` lets you create a compound conditional directive, so that, if none of the expressions in the preceding [#if](./preprocessor-if.md) or (optional) [#elif](./preprocessor-elif.md) directives evaluate to `true`, the compiler will evaluate all code between `#else` and the subsequent `#endif`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53039-104">解説</span><span class="sxs-lookup"><span data-stu-id="53039-104">Remarks</span></span>  
 <span data-ttu-id="53039-105">[#endif](./preprocessor-endif.md) が、`#else` の後の次のプリプロセッサ ディレクティブになる必要があります。</span><span class="sxs-lookup"><span data-stu-id="53039-105">[#endif](./preprocessor-endif.md) must be the next preprocessor directive after `#else`.</span></span> <span data-ttu-id="53039-106">[ の使用例については、「](./preprocessor-if.md)#if`#else`」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53039-106">See [#if](./preprocessor-if.md) for an example of how to use `#else`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53039-107">参照</span><span class="sxs-lookup"><span data-stu-id="53039-107">See also</span></span>

- [<span data-ttu-id="53039-108">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="53039-108">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="53039-109">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="53039-109">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="53039-110">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="53039-110">C# Preprocessor Directives</span></span>](./index.md)
