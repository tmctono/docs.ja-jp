---
title: 固定キーワード
description: 方法について説明します。 'pin' を使用して、コレクションを防ぐために、スタック上にローカル、 F# 'fixed' キーワード。
ms.date: 04/24/2017
ms.openlocfilehash: 7fdf66560f3e2ab7584b00c7e4584d7f6c161858
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772659"
---
# <a name="the-fixed-keyword"></a><span data-ttu-id="8b630-103">固定キーワード</span><span class="sxs-lookup"><span data-stu-id="8b630-103">The fixed keyword</span></span>

<span data-ttu-id="8b630-104">F#4.1 が導入されています、`fixed`キーワードで、収集またはガベージ コレクション中に移動されないようにするには、スタックにローカルを「ピン留め」することができます。</span><span class="sxs-lookup"><span data-stu-id="8b630-104">F# 4.1 introduces the `fixed` keyword, which allows you to "pin" a local onto the stack to prevent it from being collected or moved during garbage-collection.</span></span>  <span data-ttu-id="8b630-105">低レベルのプログラミング シナリオに使用されます。</span><span class="sxs-lookup"><span data-stu-id="8b630-105">It is used for low-level programming scenarios.</span></span>

## <a name="syntax"></a><span data-ttu-id="8b630-106">構文</span><span class="sxs-lookup"><span data-stu-id="8b630-106">Syntax</span></span>

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a><span data-ttu-id="8b630-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="8b630-107">Remarks</span></span>

<span data-ttu-id="8b630-108">これは、ポインターを抽出し、収集されたり、ガベージ コレクション中に移動できない名前にバインドすることを許可する式の構文を拡張します。</span><span class="sxs-lookup"><span data-stu-id="8b630-108">This extends the syntax of expressions to allow extracting a pointer and binding it to a name which is prevented from being collected or moved during garbage-collection.</span></span>  

<span data-ttu-id="8b630-109">使用して式からのポインターが固定されて、`fixed`キーワードは、識別子を使用してにバインドされて、`use`キーワード。</span><span class="sxs-lookup"><span data-stu-id="8b630-109">A pointer from an expression is fixed via the `fixed` keyword is bound to an identifier via the `use` keyword.</span></span>  <span data-ttu-id="8b630-110">これのセマンティクスを使用したリソース管理に似ています、`use`キーワード。</span><span class="sxs-lookup"><span data-stu-id="8b630-110">The semantics of this are similar to resource management via the `use` keyword.</span></span>  <span data-ttu-id="8b630-111">ポインターは、スコープ内にあるし、修正が不要になったスコープ外に出ることが、中に固定されています。</span><span class="sxs-lookup"><span data-stu-id="8b630-111">The pointer is fixed while it is in scope, and once it is out of scope, it is no longer fixed.</span></span>  <span data-ttu-id="8b630-112">`fixed` コンテキストの外部で使用することはできません、`use`バインドします。</span><span class="sxs-lookup"><span data-stu-id="8b630-112">`fixed` cannot be used outside the context of a `use` binding.</span></span>  <span data-ttu-id="8b630-113">名前に、ポインターをバインドする必要があります`use`します。</span><span class="sxs-lookup"><span data-stu-id="8b630-113">You must bind the pointer to a name with `use`.</span></span>

<span data-ttu-id="8b630-114">使用`fixed`関数またはメソッドの式内で発生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b630-114">Use of `fixed` must occur within an expression in a function or a method.</span></span>  <span data-ttu-id="8b630-115">これは、スクリプト レベルまたはモジュール レベルのスコープで使用できません。</span><span class="sxs-lookup"><span data-stu-id="8b630-115">It cannot be used at a script-level or module-level scope.</span></span>

<span data-ttu-id="8b630-116">ポインターのすべてのコードのようにこれは安全でない機能で、使用時に警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="8b630-116">Like all pointer code, this is an unsafe feature and will emit a warning when used.</span></span>

## <a name="example"></a><span data-ttu-id="8b630-117">例</span><span class="sxs-lookup"><span data-stu-id="8b630-117">Example</span></span>

```fsharp
open Microsoft.FSharp.NativeInterop

type Point = { mutable X: int; mutable Y: int}

let squareWithPointer (p: nativeptr<int>) =
    // Dereference the pointer at the 0th address.
    let mutable value = NativePtr.get p 0

    // Perform some work
    value <- value * value

    // Set the value in the pointer at the 0th address.
    NativePtr.set p 0 value

let pnt = { X = 1; Y = 2 }
printfn "pnt before - X: %d Y: %d" pnt.X pnt.Y // prints 1 and 2

// Note that the use of 'fixed' is inside a function.
// You cannot fix a pointer at a script-level or module-level scope.
let doPointerWork() =
    use ptr = fixed &pnt.Y

    // Square the Y value
    squareWithPointer ptr
    printfn "pnt after - X: %d Y: %d" pnt.X pnt.Y // prints 1 and 4

doPointerWork()
```

## <a name="see-also"></a><span data-ttu-id="8b630-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="8b630-118">See also</span></span>

- [<span data-ttu-id="8b630-119">NativePtr モジュール</span><span class="sxs-lookup"><span data-stu-id="8b630-119">NativePtr Module</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/nativeinterop.nativeptr-module-%5Bfsharp%5D)
