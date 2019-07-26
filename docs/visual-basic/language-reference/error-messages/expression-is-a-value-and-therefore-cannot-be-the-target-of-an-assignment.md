---
title: Expression は値であるため、代入式のターゲットにすることはできません。
ms.date: 07/20/2015
f1_keywords:
- bc30068
- vbc30068
helpviewer_keywords:
- BC30068
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
ms.openlocfilehash: d5aae4d30abbf9ed2af260412352a5e0452e0dcc
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2019
ms.locfileid: "68513033"
---
# <a name="expression-is-a-value-and-therefore-cannot-be-the-target-of-an-assignment"></a><span data-ttu-id="3720a-102">Expression は値であるため、代入式のターゲットにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3720a-102">Expression is a value and therefore cannot be the target of an assignment</span></span>

<span data-ttu-id="3720a-103">ステートメントが式に値を代入しようとしています。</span><span class="sxs-lookup"><span data-stu-id="3720a-103">A statement attempts to assign a value to an expression.</span></span> <span data-ttu-id="3720a-104">実行時には、書き込み可能な変数、プロパティ、または配列要素にのみ値を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3720a-104">You can assign a value only to a writable variable, property, or array element at run time.</span></span> <span data-ttu-id="3720a-105">次の例は、このエラーがどのように発生するかを示しています。</span><span class="sxs-lookup"><span data-stu-id="3720a-105">The following example illustrates how this error can occur.</span></span>

```vb
Dim yesterday As Integer
ReadOnly maximum As Integer = 45
yesterday + 1 = DatePart(DateInterval.Day, Now)
' The preceding line is an ERROR because of an expression on the left.
maximum = 50
' The preceding line is an ERROR because maximum is declared ReadOnly.
```

<span data-ttu-id="3720a-106">同様の例は、プロパティや配列要素にも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="3720a-106">Similar examples could apply to properties and array elements.</span></span>

<span data-ttu-id="3720a-107">**間接アクセス。**</span><span class="sxs-lookup"><span data-stu-id="3720a-107">**Indirect Access.**</span></span> <span data-ttu-id="3720a-108">値型を使用して間接的にアクセスすると、このエラーが発生することもあります。</span><span class="sxs-lookup"><span data-stu-id="3720a-108">Indirect access through a value type can also generate this error.</span></span> <span data-ttu-id="3720a-109">を通じ<xref:System.Drawing.Point> <xref:System.Windows.Forms.Control.Location%2A>て間接的にアクセスすることによっての値を設定しようとする次のコード例について考えてみます。</span><span class="sxs-lookup"><span data-stu-id="3720a-109">Consider the following code example, which attempts to set the value of <xref:System.Drawing.Point> by accessing it indirectly through <xref:System.Windows.Forms.Control.Location%2A>.</span></span>

```vb
' Assume this code runs inside Form1.
Dim exitButton As New System.Windows.Forms.Button()
exitButton.Text = "Exit this form"
exitButton.Location.X = 140
' The preceding line is an ERROR because of no storage for Location.
```

<span data-ttu-id="3720a-110">前の例の最後のステートメントは、 <xref:System.Drawing.Point> <xref:System.Windows.Forms.Control.Location%2A>プロパティによって返される構造体の一時的な割り当てのみを作成するため、失敗します。</span><span class="sxs-lookup"><span data-stu-id="3720a-110">The last statement of the preceding example fails because it creates only a temporary allocation for the <xref:System.Drawing.Point> structure returned by the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span> <span data-ttu-id="3720a-111">構造体は値型であり、ステートメントの実行後は、一時的な構造体は保持されません。</span><span class="sxs-lookup"><span data-stu-id="3720a-111">A structure is a value type, and the temporary structure is not retained after the statement runs.</span></span> <span data-ttu-id="3720a-112">この問題を解決するには、の<xref:System.Windows.Forms.Control.Location%2A>変数を宣言して使用します。これにより、 <xref:System.Drawing.Point>構造体に対してより永続的な割り当てが作成されます。</span><span class="sxs-lookup"><span data-stu-id="3720a-112">The problem is resolved by declaring and using a variable for <xref:System.Windows.Forms.Control.Location%2A>, which creates a more permanent allocation for the <xref:System.Drawing.Point> structure.</span></span> <span data-ttu-id="3720a-113">次の例は、前の例の最後のステートメントを置き換えることができるコードを示しています。</span><span class="sxs-lookup"><span data-stu-id="3720a-113">The following example shows code that can replace the last statement of the preceding example.</span></span>

```vb
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)
exitButton.Location = exitLocation
```

<span data-ttu-id="3720a-114">**エラー ID:** BC30068</span><span class="sxs-lookup"><span data-stu-id="3720a-114">**Error ID:** BC30068</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="3720a-115">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="3720a-115">To correct this error</span></span>

- <span data-ttu-id="3720a-116">ステートメントによって式に値が割り当てられた場合は、式を1つの書き込み可能な変数、プロパティ、または配列要素に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3720a-116">If the statement assigns a value to an expression, replace the expression with a single writable variable, property, or array element.</span></span>

- <span data-ttu-id="3720a-117">ステートメントが値型 (通常は構造体) を介して間接的にアクセスする場合は、値型を保持する変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="3720a-117">If the statement makes indirect access through a value type (usually a structure), create a variable to hold the value type.</span></span>

- <span data-ttu-id="3720a-118">変数に適切な構造 (またはその他の値型) を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3720a-118">Assign the appropriate structure (or other value type) to the variable.</span></span>

- <span data-ttu-id="3720a-119">変数を使用してプロパティにアクセスし、値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3720a-119">Use the variable to access the property to assign it a value.</span></span>

## <a name="see-also"></a><span data-ttu-id="3720a-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="3720a-120">See also</span></span>

- [<span data-ttu-id="3720a-121">演算子および式</span><span class="sxs-lookup"><span data-stu-id="3720a-121">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="3720a-122">ステートメント</span><span class="sxs-lookup"><span data-stu-id="3720a-122">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="3720a-123">プロシージャのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="3720a-123">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
