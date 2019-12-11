---
title: Call ステートメント
ms.date: 07/20/2015
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
ms.openlocfilehash: 7de194ea23827e08c49f4519c1000708a4bd91b4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350158"
---
# <a name="call-statement-visual-basic"></a><span data-ttu-id="220df-102">Call ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="220df-102">Call Statement (Visual Basic)</span></span>

<span data-ttu-id="220df-103">`Function`、`Sub`、またはダイナミックリンクライブラリ (DLL) プロシージャに制御を転送します。</span><span class="sxs-lookup"><span data-stu-id="220df-103">Transfers control to a `Function`, `Sub`, or dynamic-link library (DLL) procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="220df-104">構文</span><span class="sxs-lookup"><span data-stu-id="220df-104">Syntax</span></span>  
  
```vb  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="220df-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="220df-105">Parts</span></span>  

|||
|---|---|
|`procedureName`|<span data-ttu-id="220df-106">必須。</span><span class="sxs-lookup"><span data-stu-id="220df-106">Required.</span></span> <span data-ttu-id="220df-107">呼び出すプロシージャの名前。</span><span class="sxs-lookup"><span data-stu-id="220df-107">Name of the procedure to call.</span></span>|
|`argumentList`|<span data-ttu-id="220df-108">省略可。</span><span class="sxs-lookup"><span data-stu-id="220df-108">Optional.</span></span> <span data-ttu-id="220df-109">プロシージャが呼び出されたときにプロシージャに渡される引数を表す変数または式のリスト。</span><span class="sxs-lookup"><span data-stu-id="220df-109">List of variables or expressions representing arguments that are passed to the procedure when it is called.</span></span> <span data-ttu-id="220df-110">複数の引数は、コンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="220df-110">Multiple arguments are separated by commas.</span></span> <span data-ttu-id="220df-111">`argumentList`を含める場合は、かっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="220df-111">If you include `argumentList`, you must enclose it in parentheses.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="220df-112">コメント</span><span class="sxs-lookup"><span data-stu-id="220df-112">Remarks</span></span>

 <span data-ttu-id="220df-113">プロシージャを呼び出すときに、`Call` キーワードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="220df-113">You can use the `Call` keyword when you call a procedure.</span></span> <span data-ttu-id="220df-114">ほとんどのプロシージャ呼び出しでは、このキーワードを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="220df-114">For most procedure calls, you aren’t required to use this  keyword.</span></span>

 <span data-ttu-id="220df-115">通常、呼び出された式が識別子で始まらない場合は、`Call` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="220df-115">You typically use the `Call` keyword when the called expression doesn’t start with an identifier.</span></span> <span data-ttu-id="220df-116">他の用途には `Call` キーワードを使用しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="220df-116">Use of the `Call` keyword for other uses isn't recommended.</span></span>

 <span data-ttu-id="220df-117">プロシージャが値を返す場合、`Call` ステートメントによって値が破棄されます。</span><span class="sxs-lookup"><span data-stu-id="220df-117">If the procedure returns a value, the `Call` statement discards it.</span></span>

## <a name="example"></a><span data-ttu-id="220df-118">例</span><span class="sxs-lookup"><span data-stu-id="220df-118">Example</span></span>

 <span data-ttu-id="220df-119">次のコードは、プロシージャを呼び出すために `Call` キーワードが必要な2つの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="220df-119">The following code shows two examples where the `Call` keyword is necessary to call a procedure.</span></span> <span data-ttu-id="220df-120">どちらの例でも、呼び出された式の先頭が識別子ではありません。</span><span class="sxs-lookup"><span data-stu-id="220df-120">In both examples, the called expression doesn't start with an identifier.</span></span>

 [!code-vb[VbVbalrStatements#97](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#97)]  
  
## <a name="see-also"></a><span data-ttu-id="220df-121">参照</span><span class="sxs-lookup"><span data-stu-id="220df-121">See also</span></span>

- [<span data-ttu-id="220df-122">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="220df-122">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="220df-123">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="220df-123">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="220df-124">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="220df-124">Declare Statement</span></span>](declare-statement.md)
- [<span data-ttu-id="220df-125">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="220df-125">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
