---
title: Throw ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Throw
helpviewer_keywords:
- structured exception handling, throw statements
- try-catch exception handling, throw statements
- throw statement [Visual Basic], about throw statements
- throwing exceptions, throw statement
- exception handling, throw statement
- On Error statement [Visual Basic], throwing exceptions
- throwing exceptions
- exception handling, unstructured
- throw statement [Visual Basic]
ms.assetid: a6e07406-5c8a-4498-87a2-8339f3651d62
ms.openlocfilehash: 9680700267f17c8e316de351fead61f1dc4aded0
ms.sourcegitcommit: 9ee6cd851b6e176a5811ea28ed0d5935c71950f9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68869019"
---
# <a name="throw-statement-visual-basic"></a><span data-ttu-id="8e2bb-102">Throw ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8e2bb-102">Throw Statement (Visual Basic)</span></span>

<span data-ttu-id="8e2bb-103">プロシージャ内で例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="8e2bb-103">Throws an exception within a procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="8e2bb-104">構文</span><span class="sxs-lookup"><span data-stu-id="8e2bb-104">Syntax</span></span>

```vb
Throw [ expression ]
```

## <a name="part"></a><span data-ttu-id="8e2bb-105">パーツ</span><span class="sxs-lookup"><span data-stu-id="8e2bb-105">Part</span></span>

`expression`\
<span data-ttu-id="8e2bb-106">スローされる例外に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="8e2bb-106">Provides information about the exception to be thrown.</span></span> <span data-ttu-id="8e2bb-107">`Catch`ステートメント内に存在する場合は省略可能。それ以外の場合は必須。</span><span class="sxs-lookup"><span data-stu-id="8e2bb-107">Optional when residing in a `Catch` statement, otherwise required.</span></span>

## <a name="remarks"></a><span data-ttu-id="8e2bb-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="8e2bb-108">Remarks</span></span>

<span data-ttu-id="8e2bb-109">ステートメント`Throw`によって例外がスローされ、構造化された例外処理`Try`コード (...`Catch`...) または非構造化例外処理コード`On Error GoTo`() があります。 `Finally`</span><span class="sxs-lookup"><span data-stu-id="8e2bb-109">The `Throw` statement throws an exception that you can handle with structured exception-handling code (`Try`...`Catch`...`Finally`) or unstructured exception-handling code (`On Error GoTo`).</span></span> <span data-ttu-id="8e2bb-110">`Throw`ステートメントを使用すると、適切な例外処理コードが見つかるまで呼び出し履歴が上に移動するの Visual Basic で、コード内でエラーをトラップすることができます。</span><span class="sxs-lookup"><span data-stu-id="8e2bb-110">You can use the `Throw` statement to trap errors within your code because Visual Basic moves up the call stack until it finds the appropriate exception-handling code.</span></span>

<span data-ttu-id="8e2bb-111">式が指定されていない`Catch` `Catch`ステートメントは、ステートメント内でのみ使用できます。この場合、ステートメントは、ステートメントによって現在処理されている例外を再スローします。 `Throw`</span><span class="sxs-lookup"><span data-stu-id="8e2bb-111">A `Throw` statement with no expression can only be used in a `Catch` statement, in which case the statement rethrows the exception currently being handled by the `Catch` statement.</span></span>

<span data-ttu-id="8e2bb-112">ステートメント`Throw`は、 `expression`例外の呼び出し履歴をリセットします。</span><span class="sxs-lookup"><span data-stu-id="8e2bb-112">The `Throw` statement resets the call stack for the `expression` exception.</span></span> <span data-ttu-id="8e2bb-113">が`expression`指定されていない場合、呼び出し履歴は変更されません。</span><span class="sxs-lookup"><span data-stu-id="8e2bb-113">If `expression` is not provided, the call stack is left unchanged.</span></span> <span data-ttu-id="8e2bb-114"><xref:System.Exception.StackTrace%2A>プロパティを使用して、例外の呼び出し履歴にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8e2bb-114">You can access the call stack for the exception through the <xref:System.Exception.StackTrace%2A> property.</span></span>

## <a name="example"></a><span data-ttu-id="8e2bb-115">例</span><span class="sxs-lookup"><span data-stu-id="8e2bb-115">Example</span></span>

<span data-ttu-id="8e2bb-116">次のコードでは`Throw` 、ステートメントを使用して例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="8e2bb-116">The following code uses the `Throw` statement to throw an exception:</span></span>

[!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]

## <a name="see-also"></a><span data-ttu-id="8e2bb-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e2bb-117">See also</span></span>

- [<span data-ttu-id="8e2bb-118">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="8e2bb-118">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="8e2bb-119">On Error ステートメント</span><span class="sxs-lookup"><span data-stu-id="8e2bb-119">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
