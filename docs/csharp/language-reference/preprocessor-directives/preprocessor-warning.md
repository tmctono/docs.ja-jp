---
title: '#warning - C# リファレンス'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: 3d09cd95ef4d53e3f11d9feb9675ebba22d6f857
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69608526"
---
# <a name="warning-c-reference"></a><span data-ttu-id="0f334-102">#warning (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="0f334-102">#warning (C# Reference)</span></span>
<span data-ttu-id="0f334-103">`#warning` を使用すると、コード内の特定の場所から [CS1030](../../misc/cs1030.md) レベル 1 のコンパイラの警告を生成できます。</span><span class="sxs-lookup"><span data-stu-id="0f334-103">`#warning` lets you generate a [CS1030](../../misc/cs1030.md) level one compiler warning from a specific location in your code.</span></span> <span data-ttu-id="0f334-104">例:</span><span class="sxs-lookup"><span data-stu-id="0f334-104">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="0f334-105">解説</span><span class="sxs-lookup"><span data-stu-id="0f334-105">Remarks</span></span>
 <span data-ttu-id="0f334-106">`#warning` は条件付きディレクティブ内で一般的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="0f334-106">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="0f334-107">[#error](./preprocessor-error.md) を使用してユーザー定義のエラーを生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="0f334-107">It is also possible to generate a user-defined error with [#error](./preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f334-108">例</span><span class="sxs-lookup"><span data-stu-id="0f334-108">Example</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="0f334-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f334-109">See also</span></span>

- [<span data-ttu-id="0f334-110">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="0f334-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0f334-111">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="0f334-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0f334-112">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="0f334-112">C# Preprocessor Directives</span></span>](./index.md)
