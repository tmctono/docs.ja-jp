---
title: '#else - C# リファレンス'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#else'
helpviewer_keywords:
- '#else directive [C#]'
ms.assetid: 6a347322-cfa2-4a86-98f8-ddfa2cb7d4db
ms.openlocfilehash: d6a514f71b3526b2ffe347cdd971b81907fb0aad
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69605720"
---
# <a name="else-c-reference"></a><span data-ttu-id="acb23-102">#else (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="acb23-102">#else (C# Reference)</span></span>
<span data-ttu-id="acb23-103">`#else` を使用すると、複合条件付きディレクティブを作成できるため、先行する [#if](./preprocessor-if.md) または (省略可能な) [#elif](./preprocessor-elif.md) ディレクティブの式がいずれも `true` に評価されない場合は、コンパイラが `#else` と以降の `#endif` の間のすべてのコードを評価します。</span><span class="sxs-lookup"><span data-stu-id="acb23-103">`#else` lets you create a compound conditional directive, so that, if none of the expressions in the preceding [#if](./preprocessor-if.md) or (optional) [#elif](./preprocessor-elif.md) directives evaluate to `true`, the compiler will evaluate all code between `#else` and the subsequent `#endif`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="acb23-104">解説</span><span class="sxs-lookup"><span data-stu-id="acb23-104">Remarks</span></span>  
 <span data-ttu-id="acb23-105">[#endif](./preprocessor-endif.md) が、`#else` の後の次のプリプロセッサ ディレクティブになる必要があります。</span><span class="sxs-lookup"><span data-stu-id="acb23-105">[#endif](./preprocessor-endif.md) must be the next preprocessor directive after `#else`.</span></span> <span data-ttu-id="acb23-106">`#else` の使用例については、「[#if](./preprocessor-if.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acb23-106">See [#if](./preprocessor-if.md) for an example of how to use `#else`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acb23-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="acb23-107">See also</span></span>

- [<span data-ttu-id="acb23-108">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="acb23-108">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="acb23-109">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="acb23-109">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="acb23-110">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="acb23-110">C# Preprocessor Directives</span></span>](./index.md)
