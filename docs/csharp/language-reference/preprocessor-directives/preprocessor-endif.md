---
title: '#endif - C# リファレンス'
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: cc344a224e2308e843328b228dd5e2466d02069f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712547"
---
# <a name="endif-c-reference"></a><span data-ttu-id="8812b-102">#endif (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="8812b-102">#endif (C# Reference)</span></span>
<span data-ttu-id="8812b-103">`#endif` は [#if](./preprocessor-if.md)ディレクティブで始まる、条件付きディレクティブの終了を指定します。</span><span class="sxs-lookup"><span data-stu-id="8812b-103">`#endif` specifies the end of a conditional directive, which began with the [#if](./preprocessor-if.md) directive.</span></span> <span data-ttu-id="8812b-104">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8812b-104">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="8812b-105">解説</span><span class="sxs-lookup"><span data-stu-id="8812b-105">Remarks</span></span>  
 <span data-ttu-id="8812b-106">`#if` ディレクティブで始まる条件付きディレクティブは、`#endif` ディレクティブで明示的に終了させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="8812b-106">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="8812b-107">[ の使用例については、「](./preprocessor-if.md)#if`#endif`」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8812b-107">See [#if](./preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8812b-108">参照</span><span class="sxs-lookup"><span data-stu-id="8812b-108">See also</span></span>

- [<span data-ttu-id="8812b-109">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="8812b-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="8812b-110">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="8812b-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="8812b-111">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="8812b-111">C# Preprocessor Directives</span></span>](./index.md)
