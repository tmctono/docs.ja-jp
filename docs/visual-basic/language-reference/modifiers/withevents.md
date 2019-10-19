---
title: WithEvents (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 50d5a768393e90d28d150b451405e35e6f4c7953
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583041"
---
# <a name="withevents-visual-basic"></a><span data-ttu-id="0dcce-102">WithEvents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0dcce-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="0dcce-103">1つ以上の宣言されたメンバー変数が、イベントを発生させることができるクラスのインスタンスを参照することを指定します。</span><span class="sxs-lookup"><span data-stu-id="0dcce-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>

## <a name="remarks"></a><span data-ttu-id="0dcce-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="0dcce-104">Remarks</span></span>

<span data-ttu-id="0dcce-105">@No__t_0 を使用して変数が定義されている場合は、メソッドが `Handles` キーワードを使用して変数のイベントを処理するように、宣言によって指定できます。</span><span class="sxs-lookup"><span data-stu-id="0dcce-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>

<span data-ttu-id="0dcce-106">@No__t_0 は、クラスレベルまたはモジュールレベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="0dcce-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="0dcce-107">つまり、`WithEvents` 変数の宣言コンテキストは、クラスまたはモジュールである必要があり、ソースファイル、名前空間、構造体、またはプロシージャにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="0dcce-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>

<span data-ttu-id="0dcce-108">構造体メンバーで `WithEvents` を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="0dcce-108">You cannot use `WithEvents` on a structure member.</span></span>

<span data-ttu-id="0dcce-109">@No__t_0 では、配列ではなく個々の変数のみを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="0dcce-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>

## <a name="rules"></a><span data-ttu-id="0dcce-110">ルール</span><span class="sxs-lookup"><span data-stu-id="0dcce-110">Rules</span></span>

<span data-ttu-id="0dcce-111">**要素の型。**</span><span class="sxs-lookup"><span data-stu-id="0dcce-111">**Element Types.**</span></span> <span data-ttu-id="0dcce-112">オブジェクト変数として `WithEvents` 変数を宣言して、クラスのインスタンスを受け入れるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0dcce-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="0dcce-113">ただし、`Object` として宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="0dcce-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="0dcce-114">これらのクラスは、イベントを発生させることができる特定のクラスとして宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0dcce-114">You must declare them as the specific class that can raise the events.</span></span>

<span data-ttu-id="0dcce-115">@No__t_0 修飾子は、次のコンテキストで使用できます: [Dim ステートメント](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="0dcce-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>

## <a name="example"></a><span data-ttu-id="0dcce-116">例</span><span class="sxs-lookup"><span data-stu-id="0dcce-116">Example</span></span>

```vb
Dim WithEvents app As Application
```

## <a name="see-also"></a><span data-ttu-id="0dcce-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="0dcce-117">See also</span></span>

- [<span data-ttu-id="0dcce-118">Handles</span><span class="sxs-lookup"><span data-stu-id="0dcce-118">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="0dcce-119">キーワード</span><span class="sxs-lookup"><span data-stu-id="0dcce-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="0dcce-120">イベント</span><span class="sxs-lookup"><span data-stu-id="0dcce-120">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
