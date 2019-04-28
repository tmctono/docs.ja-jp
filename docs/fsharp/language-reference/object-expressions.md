---
title: オブジェクト式
description: 名前付きの型コードを追加し、新たに作成するために必要なオーバーヘッドを回避するときに、F# オブジェクト式を使用する方法をについて説明します。
ms.date: 02/08/2019
ms.openlocfilehash: 63f2c1d7128721b7b8c744e4cf02d73c2a8b4a07
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666294"
---
# <a name="object-expressions"></a><span data-ttu-id="f45dc-103">オブジェクト式</span><span class="sxs-lookup"><span data-stu-id="f45dc-103">Object Expressions</span></span>

<span data-ttu-id="f45dc-104">*オブジェクト式*は動的に作成された、匿名のオブジェクトの種類の新しいインスタンスを作成する式が、既存の基本型、インターフェイス、またはインターフェイスのセットに基づいてです。</span><span class="sxs-lookup"><span data-stu-id="f45dc-104">An *object expression* is an expression that creates a new instance of a dynamically created, anonymous object type that is based on an existing base type, interface, or set of interfaces.</span></span>

## <a name="syntax"></a><span data-ttu-id="f45dc-105">構文</span><span class="sxs-lookup"><span data-stu-id="f45dc-105">Syntax</span></span>

```fsharp
// When typename is a class:
{ new typename [type-params]arguments with
    member-definitions
    [ additional-interface-definitions ]
}
// When typename is not a class:
{ new typename [generic-type-args] with
    member-definitions
    [ additional-interface-definitions ]
}
```

## <a name="remarks"></a><span data-ttu-id="f45dc-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="f45dc-106">Remarks</span></span>

<span data-ttu-id="f45dc-107">前の構文で、 *typename*既存のクラス型またはインターフェイス型を表します。</span><span class="sxs-lookup"><span data-stu-id="f45dc-107">In the previous syntax, the *typename* represents an existing class type or interface type.</span></span> <span data-ttu-id="f45dc-108">*型 params*省略可能なジェネリック型パラメーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f45dc-108">*type-params* describes the optional generic type parameters.</span></span> <span data-ttu-id="f45dc-109">*引数*コンス トラクターのパラメーターを必要とするクラス型にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="f45dc-109">The *arguments* are used only for class types, which require constructor parameters.</span></span> <span data-ttu-id="f45dc-110">*メンバー定義*は基底クラスのメソッドのオーバーライドまたは基底クラスまたはインターフェイスのいずれかの抽象メソッドの実装。</span><span class="sxs-lookup"><span data-stu-id="f45dc-110">The *member-definitions* are overrides of base class methods, or implementations of abstract methods from either a base class or an interface.</span></span>

<span data-ttu-id="f45dc-111">次の例は、さまざまな種類のオブジェクト式を示しています。</span><span class="sxs-lookup"><span data-stu-id="f45dc-111">The following example illustrates several different types of object expressions.</span></span>

```fsharp
// This object expression specifies a System.Object but overrides the
// ToString method.
let obj1 = { new System.Object() with member x.ToString() = "F#" }
printfn "%A" obj1

// This object expression implements the IFormattable interface.
let delimiter(delim1: string, delim2: string, value: string) =
    { new System.IFormattable with
        member x.ToString(format: string, provider: System.IFormatProvider) =
            if format = "D" then
                delim1 + value + delim2
            else
                value }

let obj2 = delimiter("{","}", "Bananas!");

printfn "%A" (System.String.Format("{0:D}", obj2))

// Define two interfaces
type IFirst =
  abstract F : unit -> unit
  abstract G : unit -> unit

type ISecond =
  inherit IFirst
  abstract H : unit -> unit
  abstract J : unit -> unit

// This object expression implements both interfaces.
let implementer() =
    { new ISecond with
        member this.H() = ()
        member this.J() = ()
      interface IFirst with
        member this.F() = ()
        member this.G() = () }
```

## <a name="using-object-expressions"></a><span data-ttu-id="f45dc-112">オブジェクトの式の使用</span><span class="sxs-lookup"><span data-stu-id="f45dc-112">Using Object Expressions</span></span>

<span data-ttu-id="f45dc-113">余分なコードと名前付きの型を新しく作成する必要なオーバーヘッドを回避する場合に、オブジェクトの式を使用します。</span><span class="sxs-lookup"><span data-stu-id="f45dc-113">You use object expressions when you want to avoid the extra code and overhead that is required to create a new, named type.</span></span> <span data-ttu-id="f45dc-114">プログラムで作成された型の数を最小限に抑えるには、オブジェクト表現を使用する場合のコード行の数を削減し、型の不要な急増を回避できます。</span><span class="sxs-lookup"><span data-stu-id="f45dc-114">If you use object expressions to minimize the number of types created in a program, you can reduce the number of lines of code and prevent the unnecessary proliferation of types.</span></span> <span data-ttu-id="f45dc-115">特定の状況に対処するためだけに多くの種類を作成する代わりには、既存の種類をカスタマイズできます。 または、特定の状況に適切なインターフェイスの実装を提供するオブジェクト式を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="f45dc-115">Instead of creating many types just to handle specific situations, you can use an object expression that customizes an existing type or provides an appropriate implementation of an interface for the specific case at hand.</span></span>

## <a name="see-also"></a><span data-ttu-id="f45dc-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="f45dc-116">See also</span></span>

- [<span data-ttu-id="f45dc-117">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="f45dc-117">F# Language Reference</span></span>](index.md)
