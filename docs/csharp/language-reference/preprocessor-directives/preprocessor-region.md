---
title: '#region - C# リファレンス'
ms.date: 07/20/2015
f1_keywords:
- '#region'
helpviewer_keywords:
- '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
ms.openlocfilehash: 66583d6e067b006b03130d8ff842b56bf57bcebc
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83802770"
---
# <a name="region-c-reference"></a><span data-ttu-id="28ab5-102">#region (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="28ab5-102">#region (C# Reference)</span></span>
<span data-ttu-id="28ab5-103">`#region` を使用すると、コード ブロックを指定できます。このブロックは、コード エディターの[アウトライン](/visualstudio/ide/outlining)機能を使用して、展開や折りたたみを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="28ab5-103">`#region` lets you specify a block of code that you can expand or collapse when using the [outlining](/visualstudio/ide/outlining) feature of the code editor.</span></span> <span data-ttu-id="28ab5-104">コード ファイルが長い場合は、現在操作している部分に集中できるように 1 つ以上の領域を折りたたむ (非表示にする) ことができると便利です。</span><span class="sxs-lookup"><span data-stu-id="28ab5-104">In longer code files, it is convenient to be able to collapse or hide one or more regions so that you can focus on the part of the file that you are currently working on.</span></span> <span data-ttu-id="28ab5-105">次の例では、領域を定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="28ab5-105">The following example shows how to define a region:</span></span>  
  
```csharp
#region MyClass definition  
public class MyClass
{  
    static void Main()
    {  
    }  
}  
#endregion  
```  
  
## <a name="remarks"></a><span data-ttu-id="28ab5-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="28ab5-106">Remarks</span></span>  
 <span data-ttu-id="28ab5-107">`#region` ブロックは、[#endregion](./preprocessor-endregion.md) ディレクティブで終了させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="28ab5-107">A `#region` block must be terminated with a [#endregion](./preprocessor-endregion.md) directive.</span></span>  
  
 <span data-ttu-id="28ab5-108">`#region` ブロックは、[#if](./preprocessor-if.md) ブロックと重複することはできません。</span><span class="sxs-lookup"><span data-stu-id="28ab5-108">A `#region` block cannot overlap with a [#if](./preprocessor-if.md) block.</span></span> <span data-ttu-id="28ab5-109">ただし、`#region` ブロックを `#if` ブロック内に入れ子にしたり、`#if` ブロックを `#region` ブロック内に入れ子にしたりすることはできます。</span><span class="sxs-lookup"><span data-stu-id="28ab5-109">However, a `#region` block can be nested in a `#if` block, and a `#if` block can be nested in a `#region` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28ab5-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="28ab5-110">See also</span></span>

- [<span data-ttu-id="28ab5-111">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="28ab5-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="28ab5-112">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="28ab5-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="28ab5-113">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="28ab5-113">C# Preprocessor Directives</span></span>](./index.md)
