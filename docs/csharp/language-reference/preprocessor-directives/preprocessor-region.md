---
description: '#region - C# リファレンス'
title: '#region - C# リファレンス'
ms.date: 07/20/2015
f1_keywords:
- '#region'
helpviewer_keywords:
- '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
ms.openlocfilehash: ed40d895fedb9be271bb389a4f8de69d7ae3f266
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137943"
---
# <a name="region-c-reference"></a><span data-ttu-id="1c9c4-103">#region (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="1c9c4-103">#region (C# Reference)</span></span>
<span data-ttu-id="1c9c4-104">`#region` を使用すると、コード ブロックを指定できます。このブロックは、コード エディターの[アウトライン](/visualstudio/ide/outlining)機能を使用して、展開や折りたたみを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1c9c4-104">`#region` lets you specify a block of code that you can expand or collapse when using the [outlining](/visualstudio/ide/outlining) feature of the code editor.</span></span> <span data-ttu-id="1c9c4-105">コード ファイルが長い場合は、現在操作している部分に集中できるように 1 つ以上の領域を折りたたむ (非表示にする) ことができると便利です。</span><span class="sxs-lookup"><span data-stu-id="1c9c4-105">In longer code files, it is convenient to be able to collapse or hide one or more regions so that you can focus on the part of the file that you are currently working on.</span></span> <span data-ttu-id="1c9c4-106">次の例では、領域を定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1c9c4-106">The following example shows how to define a region:</span></span>  
  
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
  
## <a name="remarks"></a><span data-ttu-id="1c9c4-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="1c9c4-107">Remarks</span></span>  
 <span data-ttu-id="1c9c4-108">`#region` ブロックは、[#endregion](./preprocessor-endregion.md) ディレクティブで終了させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c9c4-108">A `#region` block must be terminated with a [#endregion](./preprocessor-endregion.md) directive.</span></span>  
  
 <span data-ttu-id="1c9c4-109">`#region` ブロックは、[#if](./preprocessor-if.md) ブロックと重複することはできません。</span><span class="sxs-lookup"><span data-stu-id="1c9c4-109">A `#region` block cannot overlap with a [#if](./preprocessor-if.md) block.</span></span> <span data-ttu-id="1c9c4-110">ただし、`#region` ブロックを `#if` ブロック内に入れ子にしたり、`#if` ブロックを `#region` ブロック内に入れ子にしたりすることはできます。</span><span class="sxs-lookup"><span data-stu-id="1c9c4-110">However, a `#region` block can be nested in a `#if` block, and a `#if` block can be nested in a `#region` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c9c4-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c9c4-111">See also</span></span>

- [<span data-ttu-id="1c9c4-112">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="1c9c4-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1c9c4-113">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="1c9c4-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1c9c4-114">C# プリプロセッサ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="1c9c4-114">C# Preprocessor Directives</span></span>](./index.md)
