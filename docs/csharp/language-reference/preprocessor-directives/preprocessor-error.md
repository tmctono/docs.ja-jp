---
title: '#error - C# リファレンス'
ms.date: 07/20/2015
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: 28e77304edee617adc1422e6a52d0a617cd9b3bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173407"
---
# <a name="error-c-reference"></a><span data-ttu-id="c5095-102">#error (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="c5095-102">#error (C# Reference)</span></span>
<span data-ttu-id="c5095-103">`#error` を使用すると、コード内の特定の場所からユーザー定義の [CS1029](../compiler-messages/cs1029.md) エラーを生成できます。</span><span class="sxs-lookup"><span data-stu-id="c5095-103">`#error` lets you generate a [CS1029](../compiler-messages/cs1029.md) user-defined error from a specific location in your code.</span></span> <span data-ttu-id="c5095-104">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c5095-104">For example:</span></span>  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="c5095-105">解説</span><span class="sxs-lookup"><span data-stu-id="c5095-105">Remarks</span></span>  
 <span data-ttu-id="c5095-106">`#error` は条件付きディレクティブ内で一般的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c5095-106">A common use of `#error` is in a conditional directive.</span></span>  
  
 <span data-ttu-id="c5095-107">[#warning](./preprocessor-warning.md) を使用してユーザー定義の警告を生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="c5095-107">It is also possible to generate a user-defined warning with [#warning](./preprocessor-warning.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5095-108">例</span><span class="sxs-lookup"><span data-stu-id="c5095-108">Example</span></span>  
  
```csharp
// preprocessor_error.cs  
// CS1029 expected  
#define DEBUG  
class MainClass
{  
    static void Main()
    {  
#if DEBUG  
#error DEBUG is defined  
#endif  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c5095-109">参照</span><span class="sxs-lookup"><span data-stu-id="c5095-109">See also</span></span>

- [<span data-ttu-id="c5095-110">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="c5095-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c5095-111">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="c5095-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c5095-112">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="c5095-112">C# Preprocessor Directives</span></span>](./index.md)
