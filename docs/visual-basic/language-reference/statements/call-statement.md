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
ms.openlocfilehash: af0b62d6cfacbcf94f527e049e07e51bf496a6cf
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "71392760"
---
# <a name="call-statement-visual-basic"></a><span data-ttu-id="7fa36-102">Call ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7fa36-102">Call Statement (Visual Basic)</span></span>

<span data-ttu-id="7fa36-103">@No__t-0、@no__t 1、またはダイナミックリンクライブラリ (DLL) プロシージャに制御を転送します。</span><span class="sxs-lookup"><span data-stu-id="7fa36-103">Transfers control to a `Function`, `Sub`, or dynamic-link library (DLL) procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="7fa36-104">構文</span><span class="sxs-lookup"><span data-stu-id="7fa36-104">Syntax</span></span>

```vb
[ Call ] procedureName [ (argumentList) ]
```

## <a name="parts"></a><span data-ttu-id="7fa36-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="7fa36-105">Parts</span></span>

|||
|---|---|
|`procedureName`|<span data-ttu-id="7fa36-106">必須。</span><span class="sxs-lookup"><span data-stu-id="7fa36-106">Required.</span></span> <span data-ttu-id="7fa36-107">呼び出すプロシージャの名前。</span><span class="sxs-lookup"><span data-stu-id="7fa36-107">Name of the procedure to call.</span></span>|
|`argumentList`|<span data-ttu-id="7fa36-108">任意。</span><span class="sxs-lookup"><span data-stu-id="7fa36-108">Optional.</span></span> <span data-ttu-id="7fa36-109">プロシージャが呼び出されたときにプロシージャに渡される引数を表す変数または式のリスト。</span><span class="sxs-lookup"><span data-stu-id="7fa36-109">List of variables or expressions representing arguments that are passed to the procedure when it is called.</span></span> <span data-ttu-id="7fa36-110">複数の引数は、コンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="7fa36-110">Multiple arguments are separated by commas.</span></span> <span data-ttu-id="7fa36-111">@No__t-0 を指定する場合は、かっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fa36-111">If you include `argumentList`, you must enclose it in parentheses.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="7fa36-112">コメント</span><span class="sxs-lookup"><span data-stu-id="7fa36-112">Remarks</span></span>

 <span data-ttu-id="7fa36-113">プロシージャを呼び出すときには、`Call` キーワードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7fa36-113">You can use the `Call` keyword when you call a procedure.</span></span> <span data-ttu-id="7fa36-114">ほとんどのプロシージャ呼び出しでは、このキーワードを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7fa36-114">For most procedure calls, you aren’t required to use this  keyword.</span></span>

 <span data-ttu-id="7fa36-115">通常、呼び出された式が識別子で始まらない場合は、`Call` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="7fa36-115">You typically use the `Call` keyword when the called expression doesn’t start with an identifier.</span></span> <span data-ttu-id="7fa36-116">他の用途には `Call` キーワードを使用しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7fa36-116">Use of the `Call` keyword for other uses isn't recommended.</span></span>

 <span data-ttu-id="7fa36-117">プロシージャが値を返す場合、`Call` ステートメントはそれを破棄します。</span><span class="sxs-lookup"><span data-stu-id="7fa36-117">If the procedure returns a value, the `Call` statement discards it.</span></span>

## <a name="example"></a><span data-ttu-id="7fa36-118">例</span><span class="sxs-lookup"><span data-stu-id="7fa36-118">Example</span></span>

 <span data-ttu-id="7fa36-119">次のコードは、プロシージャを呼び出すために @no__t 0 キーワードが必要な2つの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="7fa36-119">The following code shows two examples where the `Call` keyword is necessary to call a procedure.</span></span> <span data-ttu-id="7fa36-120">どちらの例でも、呼び出された式の先頭が識別子ではありません。</span><span class="sxs-lookup"><span data-stu-id="7fa36-120">In both examples, the called expression doesn't start with an identifier.</span></span>

 [!code-vb[VbVbalrStatements#97](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#97)]  
  
## <a name="see-also"></a><span data-ttu-id="7fa36-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="7fa36-121">See also</span></span>

- [<span data-ttu-id="7fa36-122">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="7fa36-122">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="7fa36-123">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="7fa36-123">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="7fa36-124">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="7fa36-124">Declare Statement</span></span>](declare-statement.md)
- [<span data-ttu-id="7fa36-125">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="7fa36-125">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
