---
title: Call ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
ms.openlocfilehash: 755443a99a1ad8b0430a76d2dba1ff27472d4c9d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945068"
---
# <a name="call-statement-visual-basic"></a><span data-ttu-id="d5589-102">Call ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5589-102">Call Statement (Visual Basic)</span></span>
<span data-ttu-id="d5589-103">転送コントロールを`Function`、 `Sub`、またはダイナミック リンク ライブラリ (DLL) プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="d5589-103">Transfers control to a `Function`, `Sub`, or dynamic-link library (DLL) procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5589-104">構文</span><span class="sxs-lookup"><span data-stu-id="d5589-104">Syntax</span></span>  
  
```  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="d5589-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="d5589-105">Parts</span></span>  
|||
|---|---|
|`procedureName`|<span data-ttu-id="d5589-106">必須。</span><span class="sxs-lookup"><span data-stu-id="d5589-106">Required.</span></span> <span data-ttu-id="d5589-107">呼び出すプロシージャの名前。</span><span class="sxs-lookup"><span data-stu-id="d5589-107">Name of the procedure to call.</span></span>|
|`argumentList`|<span data-ttu-id="d5589-108">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="d5589-108">Optional.</span></span> <span data-ttu-id="d5589-109">変数または呼び出された場合、プロシージャに渡される引数を表す式の一覧です。</span><span class="sxs-lookup"><span data-stu-id="d5589-109">List of variables or expressions representing arguments that are passed to the procedure when it is called.</span></span> <span data-ttu-id="d5589-110">複数の引数は、コンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="d5589-110">Multiple arguments are separated by commas.</span></span> <span data-ttu-id="d5589-111">含める場合`argumentList`かっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5589-111">If you include `argumentList`, you must enclose it in parentheses.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="d5589-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="d5589-112">Remarks</span></span>  
 <span data-ttu-id="d5589-113">使用することができます、`Call`プロシージャを呼び出すときに、キーワード。</span><span class="sxs-lookup"><span data-stu-id="d5589-113">You can use the `Call` keyword when you call a procedure.</span></span> <span data-ttu-id="d5589-114">ほとんどのプロシージャ呼び出しについては、このキーワードを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d5589-114">For most procedure calls, you aren’t required to use this  keyword.</span></span>  
  
 <span data-ttu-id="d5589-115">通常、使用、`Call`キーワード、識別子で呼び出された式が開始しない場合。</span><span class="sxs-lookup"><span data-stu-id="d5589-115">You typically use the `Call` keyword when the called expression doesn’t start with an identifier.</span></span> <span data-ttu-id="d5589-116">使用、`Call`キーワードの他の使用はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="d5589-116">Use of the `Call` keyword for other uses isn’t recommended.</span></span>  
  
 <span data-ttu-id="d5589-117">プロシージャは、値を返す場合、`Call`ステートメントでは、それを破棄します。</span><span class="sxs-lookup"><span data-stu-id="d5589-117">If the procedure returns a value, the `Call` statement discards it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5589-118">例</span><span class="sxs-lookup"><span data-stu-id="d5589-118">Example</span></span>  
 <span data-ttu-id="d5589-119">次のコードは 2 つの例で、`Call`キーワードは、プロシージャを呼び出すために必要な。</span><span class="sxs-lookup"><span data-stu-id="d5589-119">The following code shows two examples where the `Call` keyword is necessary to call a procedure.</span></span> <span data-ttu-id="d5589-120">どちらの例では、呼び出された式が識別子で開始しません。</span><span class="sxs-lookup"><span data-stu-id="d5589-120">In both examples, the called expression doesn't start with an identifier.</span></span>  
  
 [!code-vb[VbVbalrStatements#97](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#97)]  
  
## <a name="see-also"></a><span data-ttu-id="d5589-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5589-121">See also</span></span>

- [<span data-ttu-id="d5589-122">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="d5589-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="d5589-123">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="d5589-123">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="d5589-124">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="d5589-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="d5589-125">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="d5589-125">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
