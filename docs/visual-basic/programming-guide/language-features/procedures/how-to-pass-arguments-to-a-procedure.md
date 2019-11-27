---
title: '方法: プロシージャに引数を渡す'
ms.date: 07/20/2015
helpviewer_keywords:
- arguments [Visual Basic], passing to procedures
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], calling
- argument passing [Visual Basic], procedures
ms.assetid: 08723588-3890-4ddc-8249-79e049e0f241
ms.openlocfilehash: 0267eed7c145988d61de715fd661bd4906d8d57d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344844"
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a><span data-ttu-id="8e3f3-102">方法: プロシージャに引数を渡す (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8e3f3-102">How to: Pass Arguments to a Procedure (Visual Basic)</span></span>
<span data-ttu-id="8e3f3-103">プロシージャを呼び出すときは、かっこで囲んだ引数リストを使用してプロシージャ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="8e3f3-103">When you call a procedure, you follow the procedure name with an argument list in parentheses.</span></span> <span data-ttu-id="8e3f3-104">プロシージャで定義されているすべての必須パラメーターに対応する引数を指定します。また、必要に応じて `Optional` パラメーターに引数を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="8e3f3-104">You supply an argument corresponding to every required parameter the procedure defines, and you can optionally supply arguments to the `Optional` parameters.</span></span> <span data-ttu-id="8e3f3-105">呼び出しに `Optional` パラメーターを指定しない場合は、後続の引数を指定する場合に、引数リスト内でその位置をマークするためにコンマを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e3f3-105">If you do not supply an `Optional` parameter in the call, you must include a comma to mark its place in the argument list if you are supplying any subsequent arguments.</span></span>  
  
 <span data-ttu-id="8e3f3-106">`Byte` など、対応するパラメーターとは異なるデータ型の引数を `String`に渡す場合は、型チェックスイッチ ([Option Strict ステートメント](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) を `Off`に設定できます。</span><span class="sxs-lookup"><span data-stu-id="8e3f3-106">If you intend to pass an argument of a data type different from that of its corresponding parameter, such as `Byte` to `String`, you can set the type-checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) to `Off`.</span></span> <span data-ttu-id="8e3f3-107">`Option Strict` が `On`場合は、拡大変換または明示的な変換キーワードのいずれかを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e3f3-107">If `Option Strict` is `On`, you must use either widening conversions or explicit conversion keywords.</span></span> <span data-ttu-id="8e3f3-108">詳細については、「[拡大および縮小変換](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)」と「[型変換関数](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e3f3-108">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="8e3f3-109">詳細については、「[プロシージャのパラメーターと引数](./procedure-parameters-and-arguments.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e3f3-109">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a><span data-ttu-id="8e3f3-110">プロシージャに1つ以上の引数を渡すには</span><span class="sxs-lookup"><span data-stu-id="8e3f3-110">To pass one or more arguments to a procedure</span></span>  
  
1. <span data-ttu-id="8e3f3-111">呼び出し元のステートメントで、プロシージャ名の後にかっこを付けます。</span><span class="sxs-lookup"><span data-stu-id="8e3f3-111">In the calling statement, follow the procedure name with parentheses.</span></span>  
  
2. <span data-ttu-id="8e3f3-112">かっこ内に引数リストを入力します。</span><span class="sxs-lookup"><span data-stu-id="8e3f3-112">Inside the parentheses, put an argument list.</span></span> <span data-ttu-id="8e3f3-113">プロシージャが定義する必須パラメーターごとに引数を含め、引数をコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="8e3f3-113">Include an argument for each required parameter the procedure defines, and separate the arguments with commas.</span></span>  
  
3. <span data-ttu-id="8e3f3-114">各引数が、対応するパラメーターに対して定義されている型に変換できるデータ型に評価される有効な式であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8e3f3-114">Make sure each argument is a valid expression that evaluates to a data type convertible to the type the procedure defines for the corresponding parameter.</span></span>  
  
4. <span data-ttu-id="8e3f3-115">パラメーターが[省略可能](../../../../visual-basic/language-reference/modifiers/optional.md)として定義されている場合は、引数リストに含めるか、または省略することができます。</span><span class="sxs-lookup"><span data-stu-id="8e3f3-115">If a parameter is defined as [Optional](../../../../visual-basic/language-reference/modifiers/optional.md), you can either include it in the argument list or omit it.</span></span> <span data-ttu-id="8e3f3-116">省略した場合、プロシージャは、そのパラメーターに対して定義されている既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="8e3f3-116">If you omit it, the procedure uses the default value defined for that parameter.</span></span>  
  
5. <span data-ttu-id="8e3f3-117">`Optional` パラメーターの引数を省略していて、パラメーターリスト内に別のパラメーターがある場合は、引数リストで省略された引数の代わりにコンマを追加してマークできます。</span><span class="sxs-lookup"><span data-stu-id="8e3f3-117">If you omit an argument for an `Optional` parameter and there is another parameter after it in the parameter list, you can mark the place of the omitted argument by an extra comma in the argument list.</span></span>  
  
     <span data-ttu-id="8e3f3-118">次の例では、Visual Basic <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8e3f3-118">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function.</span></span>  
  
     [!code-vb[VbVbcnProcedures#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#34)]  
  
     <span data-ttu-id="8e3f3-119">前の例では、必要な最初の引数が指定されています。これは、表示されるメッセージ文字列です。</span><span class="sxs-lookup"><span data-stu-id="8e3f3-119">The preceding example supplies the required first argument, which is the message string to be displayed.</span></span> <span data-ttu-id="8e3f3-120">省略可能な2番目のパラメーターの引数を省略して、メッセージボックスに表示するボタンを指定します。</span><span class="sxs-lookup"><span data-stu-id="8e3f3-120">It omits an argument for the optional second parameter, which specifies the buttons to be displayed on the message box.</span></span> <span data-ttu-id="8e3f3-121">呼び出しで値が指定されていないため、`MsgBox` は既定値の `MsgBoxStyle.OKOnly`を使用し、 **[OK** ] ボタンのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="8e3f3-121">Because the call does not supply a value, `MsgBox` uses the default value, `MsgBoxStyle.OKOnly`, which displays only an **OK** button.</span></span>  
  
     <span data-ttu-id="8e3f3-122">引数リストの2番目のコンマは省略された2番目の引数の位置をマークし、最後の文字列は `MsgBox`の3番目のパラメーター (タイトルバーに表示されるテキスト) に渡されます。</span><span class="sxs-lookup"><span data-stu-id="8e3f3-122">The second comma in the argument list marks the place of the omitted second argument, and the last string is passed to the optional third parameter of `MsgBox`, which is the text to be displayed in the title bar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e3f3-123">参照</span><span class="sxs-lookup"><span data-stu-id="8e3f3-123">See also</span></span>

- [<span data-ttu-id="8e3f3-124">Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="8e3f3-124">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="8e3f3-125">Function プロシージャ</span><span class="sxs-lookup"><span data-stu-id="8e3f3-125">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="8e3f3-126">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="8e3f3-126">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="8e3f3-127">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="8e3f3-127">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="8e3f3-128">方法 : プロシージャにパラメーターを定義する</span><span class="sxs-lookup"><span data-stu-id="8e3f3-128">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)
- [<span data-ttu-id="8e3f3-129">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="8e3f3-129">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="8e3f3-130">再帰プロシージャ</span><span class="sxs-lookup"><span data-stu-id="8e3f3-130">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="8e3f3-131">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="8e3f3-131">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="8e3f3-132">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="8e3f3-132">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="8e3f3-133">オブジェクト指向プログラミング (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8e3f3-133">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
