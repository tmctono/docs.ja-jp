---
title: WithEvents
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 2309c675b50a2025d73841a47fe8e30e7cecd522
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350748"
---
# <a name="withevents-visual-basic"></a><span data-ttu-id="a2b40-102">WithEvents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2b40-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="a2b40-103">1つ以上の宣言されたメンバー変数が、イベントを発生させることができるクラスのインスタンスを参照することを指定します。</span><span class="sxs-lookup"><span data-stu-id="a2b40-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>

## <a name="remarks"></a><span data-ttu-id="a2b40-104">コメント</span><span class="sxs-lookup"><span data-stu-id="a2b40-104">Remarks</span></span>

<span data-ttu-id="a2b40-105">`WithEvents`を使用して変数が定義されている場合は、メソッドが `Handles` キーワードを使用して変数のイベントを処理するように、宣言によって指定できます。</span><span class="sxs-lookup"><span data-stu-id="a2b40-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>

<span data-ttu-id="a2b40-106">`WithEvents` は、クラスレベルまたはモジュールレベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a2b40-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="a2b40-107">つまり、`WithEvents` 変数の宣言コンテキストは、クラスまたはモジュールである必要があり、ソースファイル、名前空間、構造体、またはプロシージャにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a2b40-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>

<span data-ttu-id="a2b40-108">構造体メンバーで `WithEvents` を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="a2b40-108">You cannot use `WithEvents` on a structure member.</span></span>

<span data-ttu-id="a2b40-109">`WithEvents`では、配列ではなく個々の変数のみを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="a2b40-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>

## <a name="rules"></a><span data-ttu-id="a2b40-110">ルール</span><span class="sxs-lookup"><span data-stu-id="a2b40-110">Rules</span></span>

<span data-ttu-id="a2b40-111">**要素の型。**</span><span class="sxs-lookup"><span data-stu-id="a2b40-111">**Element Types.**</span></span> <span data-ttu-id="a2b40-112">オブジェクト変数として `WithEvents` 変数を宣言して、クラスのインスタンスを受け入れるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2b40-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="a2b40-113">ただし、`Object`として宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="a2b40-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="a2b40-114">これらのクラスは、イベントを発生させることができる特定のクラスとして宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2b40-114">You must declare them as the specific class that can raise the events.</span></span>

<span data-ttu-id="a2b40-115">`WithEvents` 修飾子は、次のコンテキストで使用できます: [Dim ステートメント](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="a2b40-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>

## <a name="example"></a><span data-ttu-id="a2b40-116">例</span><span class="sxs-lookup"><span data-stu-id="a2b40-116">Example</span></span>

```vb
Dim WithEvents app As Application
```

## <a name="see-also"></a><span data-ttu-id="a2b40-117">参照</span><span class="sxs-lookup"><span data-stu-id="a2b40-117">See also</span></span>

- <span data-ttu-id="a2b40-118">[!](../../../visual-basic/language-reference/statements/handles-clause.md)</span><span class="sxs-lookup"><span data-stu-id="a2b40-118">[Handles](../../../visual-basic/language-reference/statements/handles-clause.md)</span></span>
- [<span data-ttu-id="a2b40-119">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b40-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="a2b40-120">イベント</span><span class="sxs-lookup"><span data-stu-id="a2b40-120">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
