---
description: '#endif - C# リファレンス'
title: '#endif - C# リファレンス'
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: 0ccc00ceab2aa67c77140e3ef09907ba260d7e9b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168635"
---
# <a name="endif-c-reference"></a><span data-ttu-id="40e79-103">#endif (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="40e79-103">#endif (C# Reference)</span></span>

<span data-ttu-id="40e79-104">`#endif` は [#if](./preprocessor-if.md)ディレクティブで始まる、条件付きディレクティブの終了を指定します。</span><span class="sxs-lookup"><span data-stu-id="40e79-104">`#endif` specifies the end of a conditional directive, which began with the [#if](./preprocessor-if.md) directive.</span></span> <span data-ttu-id="40e79-105">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="40e79-105">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="40e79-106">解説</span><span class="sxs-lookup"><span data-stu-id="40e79-106">Remarks</span></span>  

 <span data-ttu-id="40e79-107">`#if` ディレクティブで始まる条件付きディレクティブは、`#endif` ディレクティブで明示的に終了させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="40e79-107">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="40e79-108">`#endif` の使用例については、「[#if](./preprocessor-if.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40e79-108">See [#if](./preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40e79-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="40e79-109">See also</span></span>

- [<span data-ttu-id="40e79-110">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="40e79-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="40e79-111">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="40e79-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="40e79-112">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="40e79-112">C# Preprocessor Directives</span></span>](./index.md)
