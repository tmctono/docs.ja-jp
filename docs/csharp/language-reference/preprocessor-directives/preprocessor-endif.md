---
title: '#endif - C# リファレンス'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: 74205c836b4eeb2d8b17b907bb13708f3225df08
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69608569"
---
# <a name="endif-c-reference"></a><span data-ttu-id="d027f-102">#endif (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="d027f-102">#endif (C# Reference)</span></span>
<span data-ttu-id="d027f-103">`#endif` は [#if](./preprocessor-if.md)ディレクティブで始まる、条件付きディレクティブの終了を指定します。</span><span class="sxs-lookup"><span data-stu-id="d027f-103">`#endif` specifies the end of a conditional directive, which began with the [#if](./preprocessor-if.md) directive.</span></span> <span data-ttu-id="d027f-104">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d027f-104">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="d027f-105">解説</span><span class="sxs-lookup"><span data-stu-id="d027f-105">Remarks</span></span>  
 <span data-ttu-id="d027f-106">`#if` ディレクティブで始まる条件付きディレクティブは、`#endif` ディレクティブで明示的に終了させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d027f-106">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="d027f-107">`#endif` の使用例については、「[#if](./preprocessor-if.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d027f-107">See [#if](./preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d027f-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="d027f-108">See also</span></span>

- [<span data-ttu-id="d027f-109">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="d027f-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d027f-110">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="d027f-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d027f-111">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="d027f-111">C# Preprocessor Directives</span></span>](./index.md)
