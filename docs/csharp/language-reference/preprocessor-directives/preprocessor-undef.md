---
description: '#undef - C# リファレンス'
title: '#undef - C# リファレンス'
ms.date: 06/30/2018
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
ms.openlocfilehash: 7db79be7ea9d8462e09b6ae874bf0ae7d265afe2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150558"
---
# <a name="undef-c-reference"></a><span data-ttu-id="a6cab-103">#undef (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="a6cab-103">#undef (C# Reference)</span></span>

<span data-ttu-id="a6cab-104">`#undef` を使用すると、シンボルを未定義にすることができます。未定義のシンボルを [#if](./preprocessor-if.md) ディレクティブで式として使用すると、その式は `false` と評価されます。</span><span class="sxs-lookup"><span data-stu-id="a6cab-104">`#undef` lets you undefine a symbol, such that, by using the symbol as the expression in a [#if](./preprocessor-if.md) directive, the expression will evaluate to `false`.</span></span>  
  
 <span data-ttu-id="a6cab-105">シンボルは、[#define](./preprocessor-define.md) ディレクティブまたは [-define](../compiler-options/define-compiler-option.md) コンパイラ オプションのいずれかで定義できます。</span><span class="sxs-lookup"><span data-stu-id="a6cab-105">A symbol can be defined either with the [#define](./preprocessor-define.md) directive or the [-define](../compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="a6cab-106">`#undef` ディレクティブは、ファイル内で、ディレクティブではない他のステートメントよりも前に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6cab-106">The `#undef` directive must appear in the file before you use any statements that are not also directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6cab-107">例</span><span class="sxs-lookup"><span data-stu-id="a6cab-107">Example</span></span>  

```csharp
// preprocessor_undef.cs  
// compile with: /d:DEBUG  
#undef DEBUG  
using System;  
class MyClass
{  
    static void Main()
    {  
#if DEBUG  
        Console.WriteLine("DEBUG is defined");  
#else  
        Console.WriteLine("DEBUG is not defined");  
#endif  
    }  
}  
```

<span data-ttu-id="a6cab-108">**DEBUG が定義されていません**</span><span class="sxs-lookup"><span data-stu-id="a6cab-108">**DEBUG is not defined**</span></span>

## <a name="see-also"></a><span data-ttu-id="a6cab-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6cab-109">See also</span></span>

- [<span data-ttu-id="a6cab-110">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="a6cab-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a6cab-111">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="a6cab-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a6cab-112">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="a6cab-112">C# Preprocessor Directives</span></span>](./index.md)
