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
ms.openlocfilehash: 729d0710d65c0cda750061e72309ced527bbcfe7
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582060"
---
# <a name="rem-statement-visual-basic"></a><span data-ttu-id="532b3-102">REM ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="532b3-102">REM Statement (Visual Basic)</span></span>
<span data-ttu-id="532b3-103">プログラムのソースコードに説明の解説を含めるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="532b3-103">Used to include explanatory remarks in the source code of a program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="532b3-104">構文</span><span class="sxs-lookup"><span data-stu-id="532b3-104">Syntax</span></span>  
  
```vb  
REM comment  
' comment  
```  
  
## <a name="parts"></a><span data-ttu-id="532b3-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="532b3-105">Parts</span></span>  
 `comment`  
 <span data-ttu-id="532b3-106">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="532b3-106">Optional.</span></span> <span data-ttu-id="532b3-107">追加するコメントのテキスト。</span><span class="sxs-lookup"><span data-stu-id="532b3-107">The text of any comment you want to include.</span></span> <span data-ttu-id="532b3-108">@No__t_0 キーワードと `comment` の間にはスペースが必要です。</span><span class="sxs-lookup"><span data-stu-id="532b3-108">A space is required between the `REM` keyword and `comment`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="532b3-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="532b3-109">Remarks</span></span>  
 <span data-ttu-id="532b3-110">@No__t_0 ステートメントを1行に単独で配置することも、別のステートメントの後の行に配置することもできます。</span><span class="sxs-lookup"><span data-stu-id="532b3-110">You can put a `REM` statement alone on a line, or you can put it on a line following another statement.</span></span> <span data-ttu-id="532b3-111">@No__t_0 ステートメントは、行の最後のステートメントである必要があります。</span><span class="sxs-lookup"><span data-stu-id="532b3-111">The `REM` statement must be the last statement on the line.</span></span> <span data-ttu-id="532b3-112">別のステートメントの後に続く場合、`REM` は、そのステートメントからスペースで区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="532b3-112">If it follows another statement, the `REM` must be separated from that statement by a space.</span></span>  
  
 <span data-ttu-id="532b3-113">@No__t_1 ではなく、単一引用符 (`'`) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="532b3-113">You can use a single quotation mark (`'`) instead of `REM`.</span></span> <span data-ttu-id="532b3-114">これは、コメントが同じ行で別のステートメントに続くか、または行に単独で存在するかにかかわらず当てはまります。</span><span class="sxs-lookup"><span data-stu-id="532b3-114">This is true whether your comment follows another statement on the same line or sits alone on a line.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="532b3-115">行連結シーケンス (`_`) を使用して、`REM` ステートメントを続行することはできません。</span><span class="sxs-lookup"><span data-stu-id="532b3-115">You cannot continue a `REM` statement by using a line-continuation sequence (`_`).</span></span> <span data-ttu-id="532b3-116">コメントが開始されると、コンパイラは文字が特別な意味を持つかどうかを検査しません。</span><span class="sxs-lookup"><span data-stu-id="532b3-116">Once a comment begins, the compiler does not examine the characters for special meaning.</span></span> <span data-ttu-id="532b3-117">複数行のコメントの場合は、各行に別の `REM` ステートメントまたはコメントシンボル (`'`) を使用します。</span><span class="sxs-lookup"><span data-stu-id="532b3-117">For a multiple-line comment, use another `REM` statement or a comment symbol (`'`) on each line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="532b3-118">例</span><span class="sxs-lookup"><span data-stu-id="532b3-118">Example</span></span>  
 <span data-ttu-id="532b3-119">次の例は、プログラムに説明の解説を含めるために使用される `REM` ステートメントを示しています。</span><span class="sxs-lookup"><span data-stu-id="532b3-119">The following example illustrates the `REM` statement, which is used to include explanatory remarks in a program.</span></span> <span data-ttu-id="532b3-120">また、`REM` の代わりに単一引用符文字 (`'`) を使用する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="532b3-120">It also shows the alternative of using the single quotation-mark character (`'`) instead of `REM`.</span></span>  
  
 [!code-vb[VbVbalrStatements#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="532b3-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="532b3-121">See also</span></span>

- [<span data-ttu-id="532b3-122">コード内のコメント</span><span class="sxs-lookup"><span data-stu-id="532b3-122">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)
- [<span data-ttu-id="532b3-123">方法 : コード内でステートメントを分割および連結する</span><span class="sxs-lookup"><span data-stu-id="532b3-123">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
