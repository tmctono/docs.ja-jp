---
title: '方法: (Visual Basic)、プロシージャに引数を渡す'
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
ms.openlocfilehash: 012ad8e6229958575030ee820a3b0b79cc50facc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59333913"
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a><span data-ttu-id="d41dc-102">方法: (Visual Basic)、プロシージャに引数を渡す</span><span class="sxs-lookup"><span data-stu-id="d41dc-102">How to: Pass Arguments to a Procedure (Visual Basic)</span></span>
<span data-ttu-id="d41dc-103">プロシージャを呼び出すときに、引数リストをかっこで、プロシージャ名に従ってください。</span><span class="sxs-lookup"><span data-stu-id="d41dc-103">When you call a procedure, you follow the procedure name with an argument list in parentheses.</span></span> <span data-ttu-id="d41dc-104">プロシージャに定義されたすべての必須パラメーターに対応する引数を指定して、引数を指定することができます必要に応じて、`Optional`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="d41dc-104">You supply an argument corresponding to every required parameter the procedure defines, and you can optionally supply arguments to the `Optional` parameters.</span></span> <span data-ttu-id="d41dc-105">指定しない場合、`Optional`呼び出しのパラメーターは、すべての後続の引数を指定している場合、引数リスト内の場所をマークする、コンマを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d41dc-105">If you do not supply an `Optional` parameter in the call, you must include a comma to mark its place in the argument list if you are supplying any subsequent arguments.</span></span>  
  
 <span data-ttu-id="d41dc-106">など、対応するパラメーターの異なるに渡すには、データ型の引数にするかどうかに`Byte`に`String`、型チェック スイッチを設定することができます ([Option Strict ステートメント](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) に`Off`します。</span><span class="sxs-lookup"><span data-stu-id="d41dc-106">If you intend to pass an argument of a data type different from that of its corresponding parameter, such as `Byte` to `String`, you can set the type-checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) to `Off`.</span></span> <span data-ttu-id="d41dc-107">場合`Option Strict`は`On`、いずれかを使用する必要がありますまたはキーワードの明示的な変換の変換を拡大します。</span><span class="sxs-lookup"><span data-stu-id="d41dc-107">If `Option Strict` is `On`, you must use either widening conversions or explicit conversion keywords.</span></span> <span data-ttu-id="d41dc-108">詳細については、次を参照してください。 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)と[型変換関数](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)します。</span><span class="sxs-lookup"><span data-stu-id="d41dc-108">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="d41dc-109">詳細については、次を参照してください。[プロシージャのパラメーターと引数](./procedure-parameters-and-arguments.md)します。</span><span class="sxs-lookup"><span data-stu-id="d41dc-109">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a><span data-ttu-id="d41dc-110">プロシージャに 1 つまたは複数の引数を渡す</span><span class="sxs-lookup"><span data-stu-id="d41dc-110">To pass one or more arguments to a procedure</span></span>  
  
1. <span data-ttu-id="d41dc-111">呼び出し元のステートメントをかっこでプロシージャ名に従います。</span><span class="sxs-lookup"><span data-stu-id="d41dc-111">In the calling statement, follow the procedure name with parentheses.</span></span>  
  
2. <span data-ttu-id="d41dc-112">かっこの内側に、引数リストを配置します。</span><span class="sxs-lookup"><span data-stu-id="d41dc-112">Inside the parentheses, put an argument list.</span></span> <span data-ttu-id="d41dc-113">プロシージャの定義、必要な各パラメーターの引数を含むし、引数をコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="d41dc-113">Include an argument for each required parameter the procedure defines, and separate the arguments with commas.</span></span>  
  
3. <span data-ttu-id="d41dc-114">各引数は、対応するパラメーターの型、プロシージャに変換できるデータ型に評価される有効な式を定義することを確認します。</span><span class="sxs-lookup"><span data-stu-id="d41dc-114">Make sure each argument is a valid expression that evaluates to a data type convertible to the type the procedure defines for the corresponding parameter.</span></span>  
  
4. <span data-ttu-id="d41dc-115">パラメーターとして定義されている場合[(省略可能)](../../../../visual-basic/language-reference/modifiers/optional.md)、引数リストに含めるか、これを省略します。</span><span class="sxs-lookup"><span data-stu-id="d41dc-115">If a parameter is defined as [Optional](../../../../visual-basic/language-reference/modifiers/optional.md), you can either include it in the argument list or omit it.</span></span> <span data-ttu-id="d41dc-116">を省略した場合、手順は、そのパラメーターの定義された既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="d41dc-116">If you omit it, the procedure uses the default value defined for that parameter.</span></span>  
  
5. <span data-ttu-id="d41dc-117">引数を省略した場合、`Optional`パラメーターとパラメーター リストで別のパラメーター後に、引数リスト内の余分なコンマが省略された引数の代わりをマークすることができます。</span><span class="sxs-lookup"><span data-stu-id="d41dc-117">If you omit an argument for an `Optional` parameter and there is another parameter after it in the parameter list, you can mark the place of the omitted argument by an extra comma in the argument list.</span></span>  
  
     <span data-ttu-id="d41dc-118">次の例では、Visual Basic<xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>関数。</span><span class="sxs-lookup"><span data-stu-id="d41dc-118">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function.</span></span>  
  
     [!code-vb[VbVbcnProcedures#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#34)]  
  
     <span data-ttu-id="d41dc-119">前の例では、必要な最初の引数は表示されるメッセージ文字列を提供します。</span><span class="sxs-lookup"><span data-stu-id="d41dc-119">The preceding example supplies the required first argument, which is the message string to be displayed.</span></span> <span data-ttu-id="d41dc-120">メッセージ ボックスに表示するボタンを指定する省略可能な第 2 パラメーターの引数が省略されます。</span><span class="sxs-lookup"><span data-stu-id="d41dc-120">It omits an argument for the optional second parameter, which specifies the buttons to be displayed on the message box.</span></span> <span data-ttu-id="d41dc-121">呼び出しは、値を指定していないため、 `MsgBox` 、既定値を使用して`MsgBoxStyle.OKOnly`、のみが表示されます、 **[ok]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d41dc-121">Because the call does not supply a value, `MsgBox` uses the default value, `MsgBoxStyle.OKOnly`, which displays only an **OK** button.</span></span>  
  
     <span data-ttu-id="d41dc-122">引数リスト内の 2 つ目のコンマは省略すると 2 番目の引数の場所をマークし、最後の文字列の省略可能な 3 番目のパラメーターに渡された`MsgBox`、これは、タイトル バーに表示されるテキスト。</span><span class="sxs-lookup"><span data-stu-id="d41dc-122">The second comma in the argument list marks the place of the omitted second argument, and the last string is passed to the optional third parameter of `MsgBox`, which is the text to be displayed in the title bar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d41dc-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="d41dc-123">See also</span></span>

- [<span data-ttu-id="d41dc-124">Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="d41dc-124">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="d41dc-125">Function プロシージャ</span><span class="sxs-lookup"><span data-stu-id="d41dc-125">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="d41dc-126">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="d41dc-126">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="d41dc-127">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="d41dc-127">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="d41dc-128">方法: プロシージャのパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="d41dc-128">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)
- [<span data-ttu-id="d41dc-129">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="d41dc-129">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="d41dc-130">再帰プロシージャ</span><span class="sxs-lookup"><span data-stu-id="d41dc-130">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="d41dc-131">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="d41dc-131">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="d41dc-132">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="d41dc-132">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="d41dc-133">オブジェクト指向プログラミング (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d41dc-133">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
