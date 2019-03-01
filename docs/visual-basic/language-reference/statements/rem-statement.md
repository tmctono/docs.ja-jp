---
title: REM ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.'
- vb.Rem
- Rem
- "'"
helpviewer_keywords:
- REM statement [Visual Basic]
- comments, Visual Basic code
- code comments, Visual Basic
- Visual Basic code, comments
- "' comment marker character [Visual Basic]"
ms.assetid: 34126d7f-e0f9-476d-91e6-b31b398615dc
ms.openlocfilehash: b25910f5215585914094b7bc4420f537a400934b
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967999"
---
# <a name="rem-statement-visual-basic"></a><span data-ttu-id="28790-102">REM ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="28790-102">REM Statement (Visual Basic)</span></span>
<span data-ttu-id="28790-103">プログラムのソース コードにコメントを記述するために使用します。</span><span class="sxs-lookup"><span data-stu-id="28790-103">Used to include explanatory remarks in the source code of a program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28790-104">構文</span><span class="sxs-lookup"><span data-stu-id="28790-104">Syntax</span></span>  
  
```  
REM comment  
' comment  
```  
  
## <a name="parts"></a><span data-ttu-id="28790-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="28790-105">Parts</span></span>  
 `comment`  
 <span data-ttu-id="28790-106">任意。</span><span class="sxs-lookup"><span data-stu-id="28790-106">Optional.</span></span> <span data-ttu-id="28790-107">含めるコメントのテキスト。</span><span class="sxs-lookup"><span data-stu-id="28790-107">The text of any comment you want to include.</span></span> <span data-ttu-id="28790-108">スペースは間で必要な`REM`キーワードと`comment`します。</span><span class="sxs-lookup"><span data-stu-id="28790-108">A space is required between the `REM` keyword and `comment`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28790-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="28790-109">Remarks</span></span>  
 <span data-ttu-id="28790-110">配置することができます、`REM`ステートメントまたは行に単独では別のステートメントの後にそれを配置できます。</span><span class="sxs-lookup"><span data-stu-id="28790-110">You can put a `REM` statement alone on a line, or you can put it on a line following another statement.</span></span> <span data-ttu-id="28790-111">`REM`ステートメントは、行の最後のステートメントである必要があります。</span><span class="sxs-lookup"><span data-stu-id="28790-111">The `REM` statement must be the last statement on the line.</span></span> <span data-ttu-id="28790-112">別のステートメントが続く場合、`REM`からそのステートメントをスペースで区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="28790-112">If it follows another statement, the `REM` must be separated from that statement by a space.</span></span>  
  
 <span data-ttu-id="28790-113">単一引用符を使用することができます (`'`) の代わりに`REM`します。</span><span class="sxs-lookup"><span data-stu-id="28790-113">You can use a single quotation mark (`'`) instead of `REM`.</span></span> <span data-ttu-id="28790-114">これはコメントが同じ行に依存して別のステートメントまたは行に単独ではかどうかに当てはまります。</span><span class="sxs-lookup"><span data-stu-id="28790-114">This is true whether your comment follows another statement on the same line or sits alone on a line.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28790-115">続行することはできません、`REM`行連結シーケンスを使用してステートメント (`_`)。</span><span class="sxs-lookup"><span data-stu-id="28790-115">You cannot continue a `REM` statement by using a line-continuation sequence (`_`).</span></span> <span data-ttu-id="28790-116">コメントが開始されると、コンパイラは特別な意味の文字をチェックしません。</span><span class="sxs-lookup"><span data-stu-id="28790-116">Once a comment begins, the compiler does not examine the characters for special meaning.</span></span> <span data-ttu-id="28790-117">複数行にコメントを記述する場合は、別の操作を使用して`REM`ステートメントまたはコメント記号 (`'`) 行ごとにします。</span><span class="sxs-lookup"><span data-stu-id="28790-117">For a multiple-line comment, use another `REM` statement or a comment symbol (`'`) on each line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28790-118">例</span><span class="sxs-lookup"><span data-stu-id="28790-118">Example</span></span>  
 <span data-ttu-id="28790-119">次の例を示しています、`REM`ステートメントでは、プログラムにコメントを記述するために使用します。</span><span class="sxs-lookup"><span data-stu-id="28790-119">The following example illustrates the `REM` statement, which is used to include explanatory remarks in a program.</span></span> <span data-ttu-id="28790-120">単一引用符文字を使用する方法も示しています (`'`) の代わりに`REM`します。</span><span class="sxs-lookup"><span data-stu-id="28790-120">It also shows the alternative of using the single quotation-mark character (`'`) instead of `REM`.</span></span>  
  
 [!code-vb[VbVbalrStatements#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="28790-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="28790-121">See also</span></span>
- [<span data-ttu-id="28790-122">コード内のコメント</span><span class="sxs-lookup"><span data-stu-id="28790-122">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)
- [<span data-ttu-id="28790-123">方法: コード内でステートメントを分割および連結する</span><span class="sxs-lookup"><span data-stu-id="28790-123">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
