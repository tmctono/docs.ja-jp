---
title: ReadOnly
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 48261e27de302c1809c9725e6e2fc0705a803930
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84386777"
---
# <a name="withevents-visual-basic"></a><span data-ttu-id="dbdae-102">WithEvents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dbdae-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="dbdae-103">1 つ以上の宣言されたメンバー変数が、イベントを発生させる可能性のあるクラスのインスタンスを参照していることを示します。</span><span class="sxs-lookup"><span data-stu-id="dbdae-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>

## <a name="remarks"></a><span data-ttu-id="dbdae-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="dbdae-104">Remarks</span></span>

<span data-ttu-id="dbdae-105">変数が `WithEvents` を使用して定義されている場合は、メソッドが `Handles` キーワードを使用して変数のイベントを処理するように、宣言によって指定できます。</span><span class="sxs-lookup"><span data-stu-id="dbdae-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>

<span data-ttu-id="dbdae-106">`WithEvents` は、クラスまたはモジュール レベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="dbdae-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="dbdae-107">つまり、`WithEvents` 変数の宣言コンテキストはクラスまたはモジュールにする必要があり、ソース ファイル、名前空間、構造体、またはプロシージャにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="dbdae-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>

<span data-ttu-id="dbdae-108">構造体メンバーでは `WithEvents` は使用できません。</span><span class="sxs-lookup"><span data-stu-id="dbdae-108">You cannot use `WithEvents` on a structure member.</span></span>

<span data-ttu-id="dbdae-109">`WithEvents` では、配列ではなく個々の変数のみを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="dbdae-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>

## <a name="rules"></a><span data-ttu-id="dbdae-110">ルール</span><span class="sxs-lookup"><span data-stu-id="dbdae-110">Rules</span></span>

<span data-ttu-id="dbdae-111">**要素型。**</span><span class="sxs-lookup"><span data-stu-id="dbdae-111">**Element Types.**</span></span> <span data-ttu-id="dbdae-112">オブジェクト変数として `WithEvents` 変数を宣言して、クラス インスタンスを受け入れられるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbdae-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="dbdae-113">C++ では、これらを `Object` として宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="dbdae-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="dbdae-114">イベントを発生可能な特定のクラスとして宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbdae-114">You must declare them as the specific class that can raise the events.</span></span>

<span data-ttu-id="dbdae-115">`WithEvents` 修飾子は、次のコンテキストで使用できます。[Dim ステートメント](../statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="dbdae-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../statements/dim-statement.md)</span></span>

## <a name="example"></a><span data-ttu-id="dbdae-116">例</span><span class="sxs-lookup"><span data-stu-id="dbdae-116">Example</span></span>

```vb
Dim WithEvents app As Application
```

## <a name="see-also"></a><span data-ttu-id="dbdae-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="dbdae-117">See also</span></span>

- [<span data-ttu-id="dbdae-118">Handles</span><span class="sxs-lookup"><span data-stu-id="dbdae-118">Handles</span></span>](../statements/handles-clause.md)
- [<span data-ttu-id="dbdae-119">キーワード</span><span class="sxs-lookup"><span data-stu-id="dbdae-119">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="dbdae-120">イベント</span><span class="sxs-lookup"><span data-stu-id="dbdae-120">Events</span></span>](../../programming-guide/language-features/events/index.md)
