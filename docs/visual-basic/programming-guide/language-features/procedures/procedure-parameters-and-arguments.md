---
title: プロシージャのパラメーターと引数 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], argument lists
- values [Visual Basic], passing to procedures
- arguments [Visual Basic], passing
- procedures [Visual Basic], parameters
- Visual Basic code, argument lists
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic procedures
- parameters [Visual Basic], lists
- arguments [Visual Basic], Visual Basic procedures
- arguments [Visual Basic], procedures
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- argument lists [Visual Basic]
- procedures [Visual Basic], parameter lists
ms.assetid: ff275aff-aa13-40df-bd4c-63486db8c1e9
ms.openlocfilehash: f7291d809c754249c155eb9382f3fcd8a63c20c7
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56972550"
---
# <a name="procedure-parameters-and-arguments-visual-basic"></a><span data-ttu-id="a7d5b-102">プロシージャのパラメーターと引数 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7d5b-102">Procedure Parameters and Arguments (Visual Basic)</span></span>
<span data-ttu-id="a7d5b-103">ほとんどの場合、プロシージャには、呼び出されたときの状況に関する情報が必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7d5b-103">In most cases, a procedure needs some information about the circumstances in which it has been called.</span></span> <span data-ttu-id="a7d5b-104">繰り返される、または共有のタスクを実行する手順では、呼び出しごとに異なる情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="a7d5b-104">A procedure that performs repeated or shared tasks uses different information for each call.</span></span> <span data-ttu-id="a7d5b-105">この情報は、変数、定数、および呼び出しでは、プロシージャに渡す式で構成されます。</span><span class="sxs-lookup"><span data-stu-id="a7d5b-105">This information consists of variables, constants, and expressions that you pass to the procedure when you call it.</span></span>  
  
 <span data-ttu-id="a7d5b-106">A*パラメーター*プロシージャには、このメソッドを呼び出すときに指定することが期待される値を表します。</span><span class="sxs-lookup"><span data-stu-id="a7d5b-106">A *parameter* represents a value that the procedure expects you to supply when you call it.</span></span> <span data-ttu-id="a7d5b-107">プロシージャの宣言では、そのパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="a7d5b-107">The procedure's declaration defines its parameters.</span></span>  
  
 <span data-ttu-id="a7d5b-108">パラメーターなし、1 つのパラメーター、または 1 つ以上のプロシージャを定義できます。</span><span class="sxs-lookup"><span data-stu-id="a7d5b-108">You can define a procedure with no parameters, one parameter, or more than one.</span></span> <span data-ttu-id="a7d5b-109">パラメーターを指定するプロシージャの定義の一部と呼ばれる、*パラメーター リスト*します。</span><span class="sxs-lookup"><span data-stu-id="a7d5b-109">The part of the procedure definition that specifies the parameters is called the *parameter list*.</span></span>  
  
 <span data-ttu-id="a7d5b-110">*引数*プロシージャを呼び出すときにプロシージャのパラメーターに指定した値を表します。</span><span class="sxs-lookup"><span data-stu-id="a7d5b-110">An *argument* represents the value you supply to a procedure parameter when you call the procedure.</span></span> <span data-ttu-id="a7d5b-111">プロシージャを呼び出すときに、呼び出し元のコードは、引数を提供します。</span><span class="sxs-lookup"><span data-stu-id="a7d5b-111">The calling code supplies the arguments when it calls the procedure.</span></span> <span data-ttu-id="a7d5b-112">引数を指定するプロシージャの呼び出しの一部と呼ばれる、*引数リスト*します。</span><span class="sxs-lookup"><span data-stu-id="a7d5b-112">The part of the procedure call that specifies the arguments is called the *argument list*.</span></span>  
  
 <span data-ttu-id="a7d5b-113">次の図は、プロシージャを呼び出すコード`safeSquareRoot`2 つの異なる場所からします。</span><span class="sxs-lookup"><span data-stu-id="a7d5b-113">The following illustration shows code calling the procedure `safeSquareRoot` from two different places.</span></span> <span data-ttu-id="a7d5b-114">最初の呼び出しは、変数の値を渡します`x`(4.0) パラメーターに`number`とで戻り値`root`(2.0)、変数に割り当てられている`y`します。</span><span class="sxs-lookup"><span data-stu-id="a7d5b-114">The first call passes the value of the variable `x` (4.0) to the parameter `number`, and the return value in `root` (2.0) is assigned to the variable `y`.</span></span> <span data-ttu-id="a7d5b-115">2 番目の呼び出しにリテラル値 9.0 を通過する`number`、戻り値 (3.0) を変数に代入と`z`します。</span><span class="sxs-lookup"><span data-stu-id="a7d5b-115">The second call passes the literal value 9.0 to `number`, and assigns the return value (3.0) to variable `z`.</span></span>  
  
 <span data-ttu-id="a7d5b-116">![パラメーターに引数を渡すグラフィック ダイアグラム](./media/parametersargue.gif "ParametersArgue")</span><span class="sxs-lookup"><span data-stu-id="a7d5b-116">![Graphic diagram of passing argument to parameter](./media/parametersargue.gif "ParametersArgue")</span></span>  
<span data-ttu-id="a7d5b-117">パラメーターに引数を渡す</span><span class="sxs-lookup"><span data-stu-id="a7d5b-117">Passing an argument to a parameter</span></span>  
  
 <span data-ttu-id="a7d5b-118">詳細については、次を参照してください。[の相違点の間でパラメーターと引数](./differences-between-parameters-and-arguments.md)します。</span><span class="sxs-lookup"><span data-stu-id="a7d5b-118">For more information, see [Differences Between Parameters and Arguments](./differences-between-parameters-and-arguments.md).</span></span>  
  
## <a name="parameter-data-type"></a><span data-ttu-id="a7d5b-119">パラメーターのデータ型</span><span class="sxs-lookup"><span data-stu-id="a7d5b-119">Parameter Data Type</span></span>  
 <span data-ttu-id="a7d5b-120">使用して、パラメーターのデータ型を定義する、`As`宣言内の句。</span><span class="sxs-lookup"><span data-stu-id="a7d5b-120">You define a data type for a parameter by using the `As` clause in its declaration.</span></span> <span data-ttu-id="a7d5b-121">たとえば、次の関数は、文字列と整数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a7d5b-121">For example, the following function accepts a string and an integer.</span></span>  
  
 [!code-vb[VbVbcnProcedures#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#32)]  
  
 <span data-ttu-id="a7d5b-122">型チェック スイッチの場合 ([Option Strict ステートメント](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) は`Off,`、`As`する点を除いて、すべてのパラメーターがそれを使用する必要があります、1 つのパラメーターで使用する場合、句は省略可能でします。</span><span class="sxs-lookup"><span data-stu-id="a7d5b-122">If the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `Off,` the `As` clause is optional, except that if any one parameter uses it, all parameters must use it.</span></span> <span data-ttu-id="a7d5b-123">型チェックが場合`On`、`As`句がすべてのプロシージャのパラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="a7d5b-123">If type checking is `On`, the `As` clause is required for all procedure parameters.</span></span>  
  
 <span data-ttu-id="a7d5b-124">呼び出し元のコードがなど、対応するパラメーターの異なるデータ型の引数を指定するかどうかは`Byte`を`String`パラメーターを次のいずれかの操作にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7d5b-124">If the calling code expects to supply an argument with a data type different from that of its corresponding parameter, such as `Byte` to a `String` parameter, it must do one of the following:</span></span>  
  
-   <span data-ttu-id="a7d5b-125">パラメーターのデータ型に拡大変換するデータ型の引数だけを渡す</span><span class="sxs-lookup"><span data-stu-id="a7d5b-125">Supply only arguments with data types that widen to the parameter data type;</span></span>  
  
-   <span data-ttu-id="a7d5b-126">設定`Option Strict Off`暗黙的な縮小変換を許可するか、</span><span class="sxs-lookup"><span data-stu-id="a7d5b-126">Set `Option Strict Off` to allow implicit narrowing conversions; or</span></span>  
  
-   <span data-ttu-id="a7d5b-127">変換キーワードを使用して、データ型を明示的に変換します。</span><span class="sxs-lookup"><span data-stu-id="a7d5b-127">Use a conversion keyword to explicitly convert the data type.</span></span>  
  
### <a name="type-parameters"></a><span data-ttu-id="a7d5b-128">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="a7d5b-128">Type Parameters</span></span>  
 <span data-ttu-id="a7d5b-129">A*ジェネリック プロシージャ*も 1 つまたは複数定義します*パラメーター入力*だけでなく、通常のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="a7d5b-129">A *generic procedure* also defines one or more *type parameters* in addition to its normal parameters.</span></span> <span data-ttu-id="a7d5b-130">ジェネリック プロシージャでは、個々 の呼び出しの要件をデータ型を調整できるように、プロシージャを呼び出すたびに異なるデータ型を渡すコードの呼び出しを許可します。</span><span class="sxs-lookup"><span data-stu-id="a7d5b-130">A generic procedure allows the calling code to pass different data types each time it calls the procedure, so it can tailor the data types to the requirements of each individual call.</span></span> <span data-ttu-id="a7d5b-131">「 [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7d5b-131">See [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7d5b-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="a7d5b-132">See also</span></span>
- [<span data-ttu-id="a7d5b-133">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="a7d5b-133">Procedures</span></span>](./index.md)
- [<span data-ttu-id="a7d5b-134">Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="a7d5b-134">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="a7d5b-135">Function プロシージャ</span><span class="sxs-lookup"><span data-stu-id="a7d5b-135">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="a7d5b-136">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="a7d5b-136">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="a7d5b-137">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="a7d5b-137">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="a7d5b-138">方法: プロシージャのパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="a7d5b-138">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)
- [<span data-ttu-id="a7d5b-139">方法: プロシージャに引数を渡す</span><span class="sxs-lookup"><span data-stu-id="a7d5b-139">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="a7d5b-140">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="a7d5b-140">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="a7d5b-141">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="a7d5b-141">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="a7d5b-142">Visual Basic における型変換</span><span class="sxs-lookup"><span data-stu-id="a7d5b-142">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
