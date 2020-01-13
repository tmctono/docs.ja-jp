---
title: '#undef - C# リファレンス'
ms.date: 06/30/2018
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
ms.openlocfilehash: 21923412aa178c3b86e94a54bd911130e48e4deb
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712443"
---
# <a name="undef-c-reference"></a><span data-ttu-id="7e37d-102">#undef (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="7e37d-102">#undef (C# Reference)</span></span>
<span data-ttu-id="7e37d-103">`#undef` を使用すると、シンボルを未定義にすることができます。未定義のシンボルを [#if](./preprocessor-if.md) ディレクティブで式として使用すると、その式は `false` と評価されます。</span><span class="sxs-lookup"><span data-stu-id="7e37d-103">`#undef` lets you undefine a symbol, such that, by using the symbol as the expression in a [#if](./preprocessor-if.md) directive, the expression will evaluate to `false`.</span></span>  
  
 <span data-ttu-id="7e37d-104">シンボルは、[#define](./preprocessor-define.md) ディレクティブまたは [-define](../compiler-options/define-compiler-option.md) コンパイラ オプションのいずれかで定義できます。</span><span class="sxs-lookup"><span data-stu-id="7e37d-104">A symbol can be defined either with the [#define](./preprocessor-define.md) directive or the [-define](../compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="7e37d-105">`#undef` ディレクティブは、ファイル内で、ディレクティブではない他のステートメントよりも前に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e37d-105">The `#undef` directive must appear in the file before you use any statements that are not also directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e37d-106">例</span><span class="sxs-lookup"><span data-stu-id="7e37d-106">Example</span></span>  

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

<span data-ttu-id="7e37d-107">**DEBUG が定義されていません**</span><span class="sxs-lookup"><span data-stu-id="7e37d-107">**DEBUG is not defined**</span></span>

## <a name="see-also"></a><span data-ttu-id="7e37d-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e37d-108">See also</span></span>

- [<span data-ttu-id="7e37d-109">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="7e37d-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="7e37d-110">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="7e37d-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7e37d-111">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="7e37d-111">C# Preprocessor Directives</span></span>](./index.md)
