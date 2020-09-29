---
description: '#warning - C# リファレンス'
title: '#warning - C# リファレンス'
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: 9ade723bdca17597dcd56240f506e60f2debf6be
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186420"
---
# <a name="warning-c-reference"></a><span data-ttu-id="f563b-103">#warning (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="f563b-103">#warning (C# Reference)</span></span>

<span data-ttu-id="f563b-104">`#warning` を使用すると、コード内の特定の場所から [CS1030](../../misc/cs1030.md) レベル 1 のコンパイラの警告を生成できます。</span><span class="sxs-lookup"><span data-stu-id="f563b-104">`#warning` lets you generate a [CS1030](../../misc/cs1030.md) level one compiler warning from a specific location in your code.</span></span> <span data-ttu-id="f563b-105">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f563b-105">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="f563b-106">解説</span><span class="sxs-lookup"><span data-stu-id="f563b-106">Remarks</span></span>

 <span data-ttu-id="f563b-107">`#warning` は条件付きディレクティブ内で一般的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f563b-107">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="f563b-108">[#error](./preprocessor-error.md) を使用してユーザー定義のエラーを生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="f563b-108">It is also possible to generate a user-defined error with [#error](./preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f563b-109">例</span><span class="sxs-lookup"><span data-stu-id="f563b-109">Example</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="f563b-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="f563b-110">See also</span></span>

- [<span data-ttu-id="f563b-111">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="f563b-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f563b-112">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="f563b-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f563b-113">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="f563b-113">C# Preprocessor Directives</span></span>](./index.md)
