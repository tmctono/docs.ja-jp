---
title: '#warning - C# リファレンス'
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: 38c3807a696599390667060d3bf374c68845fed0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715071"
---
# <a name="warning-c-reference"></a><span data-ttu-id="2be3c-102">#warning (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="2be3c-102">#warning (C# Reference)</span></span>
<span data-ttu-id="2be3c-103">`#warning` を使用すると、コード内の特定の場所から [CS1030](../../misc/cs1030.md) レベル 1 のコンパイラの警告を生成できます。</span><span class="sxs-lookup"><span data-stu-id="2be3c-103">`#warning` lets you generate a [CS1030](../../misc/cs1030.md) level one compiler warning from a specific location in your code.</span></span> <span data-ttu-id="2be3c-104">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2be3c-104">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="2be3c-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="2be3c-105">Remarks</span></span>
 <span data-ttu-id="2be3c-106">`#warning` は条件付きディレクティブ内で一般的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="2be3c-106">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="2be3c-107">[#error](./preprocessor-error.md) を使用してユーザー定義のエラーを生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="2be3c-107">It is also possible to generate a user-defined error with [#error](./preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2be3c-108">例</span><span class="sxs-lookup"><span data-stu-id="2be3c-108">Example</span></span>  

```csharp
// preprocessor_warning.cs  
// CS1030 expected  
#define DEBUG  
class MainClass
{  
    static void Main()
    {  
#if DEBUG  
#warning DEBUG is defined  
#endif  
    }  
}  
```  

## <a name="see-also"></a><span data-ttu-id="2be3c-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="2be3c-109">See also</span></span>

- [<span data-ttu-id="2be3c-110">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="2be3c-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2be3c-111">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="2be3c-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2be3c-112">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="2be3c-112">C# Preprocessor Directives</span></span>](./index.md)
