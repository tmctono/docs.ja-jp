---
title: Optional
ms.date: 07/20/2015
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
ms.openlocfilehash: c46d06dba61158d7362d736731161be306af3f10
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392146"
---
# <a name="optional-visual-basic"></a><span data-ttu-id="f1d34-102">Optional (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f1d34-102">Optional (Visual Basic)</span></span>

<span data-ttu-id="f1d34-103">プロシージャが呼び出されるときにプロシージャ引数が省略可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="f1d34-103">Specifies that a procedure argument can be omitted when the procedure is called.</span></span>

## <a name="remarks"></a><span data-ttu-id="f1d34-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="f1d34-104">Remarks</span></span>

<span data-ttu-id="f1d34-105">省略可能なパラメーターごとに、そのパラメーターの既定値として定数式を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1d34-105">For each optional parameter, you must specify a constant expression as the default value of that parameter.</span></span> <span data-ttu-id="f1d34-106">式が [Nothing](../nothing.md) に評価される場合は、値データ型の既定値がパラメーターの既定値として使用されます。</span><span class="sxs-lookup"><span data-stu-id="f1d34-106">If the expression evaluates to [Nothing](../nothing.md), the default value of the value data type is used as the default value of the parameter.</span></span>

<span data-ttu-id="f1d34-107">パラメーター リストに省略可能なパラメーターが含まれている場合は、その後に続くすべてのパラメーターも省略可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1d34-107">If the parameter list contains an optional parameter, every parameter that follows it must also be optional.</span></span>

<span data-ttu-id="f1d34-108">`Optional` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="f1d34-108">The `Optional` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="f1d34-109">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="f1d34-109">Declare Statement</span></span>](../statements/declare-statement.md)

- [<span data-ttu-id="f1d34-110">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="f1d34-110">Function Statement</span></span>](../statements/function-statement.md)

- [<span data-ttu-id="f1d34-111">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="f1d34-111">Property Statement</span></span>](../statements/property-statement.md)

- [<span data-ttu-id="f1d34-112">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="f1d34-112">Sub Statement</span></span>](../statements/sub-statement.md)

> [!NOTE]
> <span data-ttu-id="f1d34-113">省略可能なパラメーターの有無にかかわらず、プロシージャを呼び出すときは、位置または名前によって引数を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="f1d34-113">When calling a procedure with or without optional parameters, you can pass arguments by position or by name.</span></span> <span data-ttu-id="f1d34-114">詳細については、「[位置と名前による引数渡し](../../programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1d34-114">For more information, see [Passing Arguments by Position and by Name](../../programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f1d34-115">オーバーロードを使用して省略可能なパラメーターを持つプロシージャを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="f1d34-115">You can also define a procedure with optional parameters by using overloading.</span></span> <span data-ttu-id="f1d34-116">省略可能なパラメーターが 1 つあるとすると、パラメーターを受け取る場合と受け取らない場合の、2 つのオーバーロードされたバージョンのプロシージャを定義できます。</span><span class="sxs-lookup"><span data-stu-id="f1d34-116">If you have one optional parameter, you can define two overloaded versions of the procedure, one that accepts the parameter and one that doesn’t.</span></span> <span data-ttu-id="f1d34-117">詳細については、「 [Procedure Overloading](../../programming-guide/language-features/procedures/procedure-overloading.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1d34-117">For more information, see [Procedure Overloading](../../programming-guide/language-features/procedures/procedure-overloading.md).</span></span>

## <a name="example"></a><span data-ttu-id="f1d34-118">例</span><span class="sxs-lookup"><span data-stu-id="f1d34-118">Example</span></span>

<span data-ttu-id="f1d34-119">次の例では、省略可能なパラメーターがあるプロシージャを定義しています。</span><span class="sxs-lookup"><span data-stu-id="f1d34-119">The following example defines a procedure that has an optional parameter.</span></span>

```vb
Public Function FindMatches(ByRef values As List(Of String),
                            ByVal searchString As String,
                            Optional ByVal matchCase As Boolean = False) As List(Of String)

    Dim results As IEnumerable(Of String)

    If matchCase Then
        results = From v In values
                  Where v.Contains(searchString)
    Else
        results = From v In values
                  Where UCase(v).Contains(UCase(searchString))
    End If

    Return results.ToList()
End Function
```

## <a name="example"></a><span data-ttu-id="f1d34-120">例</span><span class="sxs-lookup"><span data-stu-id="f1d34-120">Example</span></span>

<span data-ttu-id="f1d34-121">次の例では、位置で渡される引数と名前で渡される引数を使用してプロシージャを呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f1d34-121">The following example demonstrates how to call a procedure with arguments passed by position and with arguments passed by name.</span></span> <span data-ttu-id="f1d34-122">このプロシージャには、2 つの省略可能なパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="f1d34-122">The procedure has two optional parameters.</span></span>

[!code-vb[VbVbalrKeywords#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class8.vb#21)]

## <a name="see-also"></a><span data-ttu-id="f1d34-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1d34-123">See also</span></span>

- [<span data-ttu-id="f1d34-124">パラメーター リスト</span><span class="sxs-lookup"><span data-stu-id="f1d34-124">Parameter List</span></span>](../statements/parameter-list.md)
- [<span data-ttu-id="f1d34-125">省略可能なパラメーター</span><span class="sxs-lookup"><span data-stu-id="f1d34-125">Optional Parameters</span></span>](../../programming-guide/language-features/procedures/optional-parameters.md)
- [<span data-ttu-id="f1d34-126">キーワード</span><span class="sxs-lookup"><span data-stu-id="f1d34-126">Keywords</span></span>](../keywords/index.md)
