---
description: '#warning - C# リファレンス'
title: '#warning - C# リファレンス'
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: ab2cc5120492fc2a4b94296eb85e563c0a1d5ad3
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137839"
---
# <a name="warning-c-reference"></a><span data-ttu-id="0755a-103">#warning (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="0755a-103">#warning (C# Reference)</span></span>
<span data-ttu-id="0755a-104">`#warning` を使用すると、コード内の特定の場所から [CS1030](../../misc/cs1030.md) レベル 1 のコンパイラの警告を生成できます。</span><span class="sxs-lookup"><span data-stu-id="0755a-104">`#warning` lets you generate a [CS1030](../../misc/cs1030.md) level one compiler warning from a specific location in your code.</span></span> <span data-ttu-id="0755a-105">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0755a-105">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="0755a-106">解説</span><span class="sxs-lookup"><span data-stu-id="0755a-106">Remarks</span></span>
 <span data-ttu-id="0755a-107">`#warning` は条件付きディレクティブ内で一般的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="0755a-107">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="0755a-108">[#error](./preprocessor-error.md) を使用してユーザー定義のエラーを生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="0755a-108">It is also possible to generate a user-defined error with [#error](./preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0755a-109">例</span><span class="sxs-lookup"><span data-stu-id="0755a-109">Example</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="0755a-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="0755a-110">See also</span></span>

- [<span data-ttu-id="0755a-111">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="0755a-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0755a-112">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="0755a-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0755a-113">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="0755a-113">C# Preprocessor Directives</span></span>](./index.md)
