---
title: '方法 : プロシージャにパラメーターを定義する'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure parameters [Visual Basic], defining data types for
- procedures [Visual Basic], parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters [Visual Basic], defining
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
ms.openlocfilehash: 411959a7be92ea49a59558b508e992bfba8eff95
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344882"
---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a><span data-ttu-id="f92e3-102">方法: プロシージャに対してパラメーターを定義する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f92e3-102">How to: Define a Parameter for a Procedure (Visual Basic)</span></span>
<span data-ttu-id="f92e3-103">*パラメーター*を使用すると、呼び出し元のコードは、呼び出し時にプロシージャに値を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="f92e3-103">A *parameter* allows the calling code to pass a value to the procedure when it calls it.</span></span> <span data-ttu-id="f92e3-104">プロシージャの各パラメーターは、変数を宣言する場合と同じ方法で宣言し、名前とデータ型を指定します。</span><span class="sxs-lookup"><span data-stu-id="f92e3-104">You declare each parameter for a procedure the same way you declare a variable, specifying its name and data type.</span></span> <span data-ttu-id="f92e3-105">また、渡す機構と、パラメーターが省略可能かどうかも指定します。</span><span class="sxs-lookup"><span data-stu-id="f92e3-105">You also specify the passing mechanism, and whether the parameter is optional.</span></span>  
  
 <span data-ttu-id="f92e3-106">詳細については、「[プロシージャのパラメーターと引数](./procedure-parameters-and-arguments.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f92e3-106">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-define-a-procedure-parameter"></a><span data-ttu-id="f92e3-107">プロシージャパラメーターを定義するには</span><span class="sxs-lookup"><span data-stu-id="f92e3-107">To define a procedure parameter</span></span>  
  
1. <span data-ttu-id="f92e3-108">プロシージャの宣言で、プロシージャのパラメーターリストにパラメーター名を追加し、他のパラメーターとコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="f92e3-108">In the procedure declaration, add the parameter name to the procedure's parameter list, separating it from other parameters by commas.</span></span>  
  
2. <span data-ttu-id="f92e3-109">パラメーターのデータ型を決定します。</span><span class="sxs-lookup"><span data-stu-id="f92e3-109">Decide the data type of the parameter.</span></span>  
  
3. <span data-ttu-id="f92e3-110">パラメーター名の後に `As` 句を入力して、データ型を指定します。</span><span class="sxs-lookup"><span data-stu-id="f92e3-110">Follow the parameter name with an `As` clause to specify the data type.</span></span>  
  
4. <span data-ttu-id="f92e3-111">パラメーターに渡すメカニズムを決定します。</span><span class="sxs-lookup"><span data-stu-id="f92e3-111">Decide the passing mechanism you want for the parameter.</span></span> <span data-ttu-id="f92e3-112">通常、プロシージャが呼び出し元のコードで値を変更できないようにする場合は、パラメーターを値で渡します。</span><span class="sxs-lookup"><span data-stu-id="f92e3-112">Normally you pass a parameter by value, unless you want the procedure to be able to change its value in the calling code.</span></span>  
  
5. <span data-ttu-id="f92e3-113">パラメーター名の前に、 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)または[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)を渡して、渡すメカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="f92e3-113">Precede the parameter name with [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) to specify the passing mechanism.</span></span> <span data-ttu-id="f92e3-114">詳細については、「[引数を値で渡す方法と参照渡しの違い](./differences-between-passing-an-argument-by-value-and-by-reference.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f92e3-114">For more information, see [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
6. <span data-ttu-id="f92e3-115">パラメーターが省略可能な場合は、渡される機構の前に[オプション](../../../../visual-basic/language-reference/modifiers/optional.md)を指定し、等号 (`=`) と既定値を指定してパラメーターのデータ型に従います。</span><span class="sxs-lookup"><span data-stu-id="f92e3-115">If the parameter is optional, precede the passing mechanism with [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) and follow the parameter data type with an equal sign (`=`) and a default value.</span></span>  
  
     <span data-ttu-id="f92e3-116">次の例では、3つのパラメーターを持つ `Sub` プロシージャのアウトラインを定義します。</span><span class="sxs-lookup"><span data-stu-id="f92e3-116">The following example defines the outline of a `Sub` procedure with three parameters.</span></span> <span data-ttu-id="f92e3-117">最初の2つは必須で、3番目のオプションは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="f92e3-117">The first two are required and the third is optional.</span></span> <span data-ttu-id="f92e3-118">パラメーターの宣言は、パラメーターリスト内でコンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="f92e3-118">The parameter declarations are separated in the parameter list by commas.</span></span>  
  
     [!code-vb[VbVbcnProcedures#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#33)]  
  
     <span data-ttu-id="f92e3-119">最初のパラメーターは `customer` オブジェクトを受け入れます。引数は[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)で渡されるため、`updateCustomer` は `c` に渡された変数を直接更新できます。</span><span class="sxs-lookup"><span data-stu-id="f92e3-119">The first parameter accepts a `customer` object, and `updateCustomer` can directly update the variable passed to `c` because the argument is passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span></span> <span data-ttu-id="f92e3-120">プロシージャは[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)で渡されるため、最後の2つの引数の値を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="f92e3-120">The procedure cannot change the values of the last two arguments because they are passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span>  
  
     <span data-ttu-id="f92e3-121">呼び出し元のコードが `level` パラメーターの値を指定していない場合は、Visual Basic 既定値の0に設定されます。</span><span class="sxs-lookup"><span data-stu-id="f92e3-121">If the calling code does not supply a value for the `level` parameter, Visual Basic sets it to the default value of 0.</span></span>  
  
     <span data-ttu-id="f92e3-122">型チェックスイッチ ([Option Strict ステートメント](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) が `Off`場合、パラメーターを定義するときに、`As` 句は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="f92e3-122">If the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `Off`, the `As` clause is optional when you define a parameter.</span></span> <span data-ttu-id="f92e3-123">ただし、1つのパラメーターで `As` 句を使用する場合は、すべてのパラメーターでそれを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f92e3-123">However, if any one parameter uses an `As` clause, all of them must use it.</span></span> <span data-ttu-id="f92e3-124">型チェックスイッチが `On`場合は、すべてのパラメーター定義に対して `As` 句が必要です。</span><span class="sxs-lookup"><span data-stu-id="f92e3-124">If the type checking switch is `On`, the `As` clause is required for every parameter definition.</span></span>  
  
     <span data-ttu-id="f92e3-125">すべてのプログラミング要素のデータ型の指定は、*厳密な*型指定と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="f92e3-125">Specifying data types for all your programming elements is known as *strong typing*.</span></span> <span data-ttu-id="f92e3-126">`Option Strict On`を設定すると、Visual Basic は厳密な型指定を適用します。</span><span class="sxs-lookup"><span data-stu-id="f92e3-126">When you set `Option Strict On`, Visual Basic enforces strong typing.</span></span> <span data-ttu-id="f92e3-127">これは、次の理由から強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f92e3-127">This is strongly recommended, for the following reasons:</span></span>  
  
    - <span data-ttu-id="f92e3-128">これにより、変数とパラメーターの IntelliSense サポートが有効になります。</span><span class="sxs-lookup"><span data-stu-id="f92e3-128">It enables IntelliSense support for your variables and parameters.</span></span> <span data-ttu-id="f92e3-129">これにより、コードを入力するときに、プロパティとその他のメンバーを表示できます。</span><span class="sxs-lookup"><span data-stu-id="f92e3-129">This allows you to see their properties and other members as you type in your code.</span></span>  
  
    - <span data-ttu-id="f92e3-130">これにより、コンパイラは型チェックを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f92e3-130">It allows the compiler to perform type checking.</span></span> <span data-ttu-id="f92e3-131">これは、オーバーフローなどのエラーによって実行時に失敗する可能性があるステートメントをキャッチするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f92e3-131">This helps catch statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="f92e3-132">また、サポートされていないオブジェクトのメソッドの呼び出しもキャッチします。</span><span class="sxs-lookup"><span data-stu-id="f92e3-132">It also catches calls to methods on objects that do not support them.</span></span>  
  
    - <span data-ttu-id="f92e3-133">これにより、コードの実行時間が短縮されます。</span><span class="sxs-lookup"><span data-stu-id="f92e3-133">It results in faster execution of your code.</span></span> <span data-ttu-id="f92e3-134">その理由の1つは、プログラミング要素のデータ型を指定しない場合、Visual Basic コンパイラによって `Object` 型に割り当てられることです。</span><span class="sxs-lookup"><span data-stu-id="f92e3-134">One reason for this is that if you do not specify a data type for a programming element, the Visual Basic compiler assigns it the `Object` type.</span></span> <span data-ttu-id="f92e3-135">コンパイルされたコードは、`Object` とその他のデータ型との間で変換を行う必要があります。これにより、パフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="f92e3-135">Your compiled code might have to convert back and forth between `Object` and other data types, which reduces performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f92e3-136">参照</span><span class="sxs-lookup"><span data-stu-id="f92e3-136">See also</span></span>

- [<span data-ttu-id="f92e3-137">Visual Basic におけるプロシージャ</span><span class="sxs-lookup"><span data-stu-id="f92e3-137">Procedures</span></span>](./index.md)
- [<span data-ttu-id="f92e3-138">Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="f92e3-138">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="f92e3-139">Function プロシージャ</span><span class="sxs-lookup"><span data-stu-id="f92e3-139">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="f92e3-140">方法: プロシージャに引数を渡す</span><span class="sxs-lookup"><span data-stu-id="f92e3-140">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="f92e3-141">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="f92e3-141">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="f92e3-142">再帰プロシージャ</span><span class="sxs-lookup"><span data-stu-id="f92e3-142">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="f92e3-143">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="f92e3-143">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="f92e3-144">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="f92e3-144">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="f92e3-145">オブジェクト指向プログラミング (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f92e3-145">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
