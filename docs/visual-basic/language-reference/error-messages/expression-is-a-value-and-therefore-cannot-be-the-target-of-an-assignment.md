---
title: Expression は値であるため、代入式のターゲットにすることはできません。
ms.date: 07/20/2015
f1_keywords:
- bc30068
- vbc30068
helpviewer_keywords:
- BC30068
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
ms.openlocfilehash: 1c7fb92c963ea7fa4129cddf060fe7c0b0261fc7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665142"
---
# <a name="expression-is-a-value-and-therefore-cannot-be-the-target-of-an-assignment"></a><span data-ttu-id="390c0-102">Expression は値であるため、代入式のターゲットにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="390c0-102">Expression is a value and therefore cannot be the target of an assignment</span></span>
<span data-ttu-id="390c0-103">ステートメントは、式に値を代入しようとします。</span><span class="sxs-lookup"><span data-stu-id="390c0-103">A statement attempts to assign a value to an expression.</span></span> <span data-ttu-id="390c0-104">実行時に、書き込み可能な変数、プロパティ、または配列要素にのみ値を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="390c0-104">You can assign a value only to a writable variable, property, or array element at run time.</span></span> <span data-ttu-id="390c0-105">次の例では、このエラーは発生する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="390c0-105">The following example illustrates how this error can occur.</span></span>  
  
```  
Dim yesterday As Integer  
ReadOnly maximum As Integer = 45  
yesterday + 1 = DatePart(DateInterval.Day, Now)  
' The preceding line is an ERROR because of an expression on the left.  
maximum = 50  
' The preceding line is an ERROR because maximum is declared ReadOnly.  
```  
  
 <span data-ttu-id="390c0-106">類似した例は、プロパティおよび配列の要素に適用できます。</span><span class="sxs-lookup"><span data-stu-id="390c0-106">Similar examples could apply to properties and array elements.</span></span>  
  
 <span data-ttu-id="390c0-107">**間接的にアクセスします。**</span><span class="sxs-lookup"><span data-stu-id="390c0-107">**Indirect Access.**</span></span> <span data-ttu-id="390c0-108">値の型を間接的にアクセスでは、このエラーを生成できます。</span><span class="sxs-lookup"><span data-stu-id="390c0-108">Indirect access through a value type can also generate this error.</span></span> <span data-ttu-id="390c0-109">値を設定しようとしています。 次のコード例を検討してください。<xref:System.Drawing.Point>を通じて間接的にアクセスして<xref:System.Windows.Forms.Control.Location%2A>します。</span><span class="sxs-lookup"><span data-stu-id="390c0-109">Consider the following code example, which attempts to set the value of <xref:System.Drawing.Point> by accessing it indirectly through <xref:System.Windows.Forms.Control.Location%2A>.</span></span>  
  
```  
' Assume this code runs inside Form1.  
Dim exitButton As New System.Windows.Forms.Button()  
exitButton.Text = "Exit this form"  
exitButton.Location.X = 140  
' The preceding line is an ERROR because of no storage for Location.  
```  
  
 <span data-ttu-id="390c0-110">前の例の最後のステートメントは失敗の一時的な割り当てのみを作成するため、<xref:System.Drawing.Point>によって返される構造体、<xref:System.Windows.Forms.Control.Location%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="390c0-110">The last statement of the preceding example fails because it creates only a temporary allocation for the <xref:System.Drawing.Point> structure returned by the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span> <span data-ttu-id="390c0-111">構造体は値の型と、ステートメントの実行後、一時的な構造は保持されません。</span><span class="sxs-lookup"><span data-stu-id="390c0-111">A structure is a value type, and the temporary structure is not retained after the statement runs.</span></span> <span data-ttu-id="390c0-112">宣言の変数を使用して、問題が解決<xref:System.Windows.Forms.Control.Location%2A>より永続的な割り当てを作成する、<xref:System.Drawing.Point>構造体。</span><span class="sxs-lookup"><span data-stu-id="390c0-112">The problem is resolved by declaring and using a variable for <xref:System.Windows.Forms.Control.Location%2A>, which creates a more permanent allocation for the <xref:System.Drawing.Point> structure.</span></span> <span data-ttu-id="390c0-113">次の例では、前の例の最後のステートメントを置き換えることができるコードを示します。</span><span class="sxs-lookup"><span data-stu-id="390c0-113">The following example shows code that can replace the last statement of the preceding example.</span></span>  
  
```  
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)  
exitButton.Location = exitLocation  
```  
  
 <span data-ttu-id="390c0-114">**エラー ID:** BC30068</span><span class="sxs-lookup"><span data-stu-id="390c0-114">**Error ID:** BC30068</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="390c0-115">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="390c0-115">To correct this error</span></span>  
  
- <span data-ttu-id="390c0-116">ステートメントは、式に値を割り当てます場合、は、書き込み可能な 1 つの変数、プロパティ、または配列要素で式を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="390c0-116">If the statement assigns a value to an expression, replace the expression with a single writable variable, property, or array element.</span></span>  
  
- <span data-ttu-id="390c0-117">ステートメントが値型 (通常は構造体) を通じて間接的にアクセスする場合、値の型を保持する変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="390c0-117">If the statement makes indirect access through a value type (usually a structure), create a variable to hold the value type.</span></span>  
  
- <span data-ttu-id="390c0-118">適切な構造体 (またはその他の値の型) を変数に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="390c0-118">Assign the appropriate structure (or other value type) to the variable.</span></span>  
  
- <span data-ttu-id="390c0-119">値を代入するのにプロパティにアクセスするのにには、変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="390c0-119">Use the variable to access the property to assign it a value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="390c0-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="390c0-120">See also</span></span>

- [<span data-ttu-id="390c0-121">演算子および式</span><span class="sxs-lookup"><span data-stu-id="390c0-121">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="390c0-122">ステートメント</span><span class="sxs-lookup"><span data-stu-id="390c0-122">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="390c0-123">プロシージャのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="390c0-123">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
