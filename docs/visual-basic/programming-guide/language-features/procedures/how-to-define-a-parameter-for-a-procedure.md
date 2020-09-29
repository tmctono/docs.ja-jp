---
title: '方法: プロシージャにパラメーターを定義する'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure parameters [Visual Basic], defining data types for
- procedures [Visual Basic], parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters [Visual Basic], defining
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
ms.openlocfilehash: 73b53dcf7cd732af1a4f1d23cd0d3b9ef5b5529b
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91087441"
---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a><span data-ttu-id="54e90-102">方法: プロシージャにパラメーターを定義する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54e90-102">How to: Define a Parameter for a Procedure (Visual Basic)</span></span>

<span data-ttu-id="54e90-103">"*パラメーター*" では、その呼び出し時に呼び出し元コードでプロシージャに値を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="54e90-103">A *parameter* allows the calling code to pass a value to the procedure when it calls it.</span></span> <span data-ttu-id="54e90-104">プロシージャの各パラメーターは、変数を宣言する場合と同じ方法で、その名前とデータ型を指定して宣言します。</span><span class="sxs-lookup"><span data-stu-id="54e90-104">You declare each parameter for a procedure the same way you declare a variable, specifying its name and data type.</span></span> <span data-ttu-id="54e90-105">引渡し方法と、パラメーターが省略可能かどうかを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="54e90-105">You also specify the passing mechanism, and whether the parameter is optional.</span></span>  
  
 <span data-ttu-id="54e90-106">詳細については、「[プロシージャのパラメーターと引数](./procedure-parameters-and-arguments.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54e90-106">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-define-a-procedure-parameter"></a><span data-ttu-id="54e90-107">プロシージャのパラメーターを定義するには</span><span class="sxs-lookup"><span data-stu-id="54e90-107">To define a procedure parameter</span></span>  
  
1. <span data-ttu-id="54e90-108">プロシージャの宣言では、プロシージャのパラメーター リストにパラメーター名を追加し、他のパラメーターとコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="54e90-108">In the procedure declaration, add the parameter name to the procedure's parameter list, separating it from other parameters by commas.</span></span>  
  
2. <span data-ttu-id="54e90-109">パラメーターのデータ型を決定します。</span><span class="sxs-lookup"><span data-stu-id="54e90-109">Decide the data type of the parameter.</span></span>  
  
3. <span data-ttu-id="54e90-110">パラメーター名の後に `As` 句を付けて、データ型を指定します。</span><span class="sxs-lookup"><span data-stu-id="54e90-110">Follow the parameter name with an `As` clause to specify the data type.</span></span>  
  
4. <span data-ttu-id="54e90-111">パラメーターに必要な引渡し方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="54e90-111">Decide the passing mechanism you want for the parameter.</span></span> <span data-ttu-id="54e90-112">プロシージャで呼び出し元コードの値を変更できるようにする必要がある場合を除き、通常は値でパラメーターを渡します。</span><span class="sxs-lookup"><span data-stu-id="54e90-112">Normally you pass a parameter by value, unless you want the procedure to be able to change its value in the calling code.</span></span>  
  
5. <span data-ttu-id="54e90-113">パラメーター名の前に [ByVal](../../../language-reference/modifiers/byval.md) または [ByRef](../../../language-reference/modifiers/byref.md) を付けて、引渡し方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="54e90-113">Precede the parameter name with [ByVal](../../../language-reference/modifiers/byval.md) or [ByRef](../../../language-reference/modifiers/byref.md) to specify the passing mechanism.</span></span> <span data-ttu-id="54e90-114">詳細については、「[引数の値渡しと参照渡しの違い](./differences-between-passing-an-argument-by-value-and-by-reference.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54e90-114">For more information, see [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
6. <span data-ttu-id="54e90-115">パラメーターが省略可能な場合は、引渡し方法の前に [Optional](../../../language-reference/modifiers/optional.md) を付け、パラメーターのデータ型の後に等号 (`=`) と既定値を付けます。</span><span class="sxs-lookup"><span data-stu-id="54e90-115">If the parameter is optional, precede the passing mechanism with [Optional](../../../language-reference/modifiers/optional.md) and follow the parameter data type with an equal sign (`=`) and a default value.</span></span>  
  
     <span data-ttu-id="54e90-116">次の例では、3 つのパラメーターがある `Sub` プロシージャを定義します。</span><span class="sxs-lookup"><span data-stu-id="54e90-116">The following example defines the outline of a `Sub` procedure with three parameters.</span></span> <span data-ttu-id="54e90-117">最初の 2 つは必須で、3 つ目は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="54e90-117">The first two are required and the third is optional.</span></span> <span data-ttu-id="54e90-118">パラメーターの宣言は、パラメーター リスト内でコンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="54e90-118">The parameter declarations are separated in the parameter list by commas.</span></span>  
  
     [!code-vb[VbVbcnProcedures#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#33)]  
  
     <span data-ttu-id="54e90-119">最初のパラメーターでは `customer` オブジェクトを受け入れ、`updateCustomer` では `c` に渡された変数を直接更新することができます。これは、引数が [ByRef](../../../language-reference/modifiers/byref.md) で渡されるためです。</span><span class="sxs-lookup"><span data-stu-id="54e90-119">The first parameter accepts a `customer` object, and `updateCustomer` can directly update the variable passed to `c` because the argument is passed [ByRef](../../../language-reference/modifiers/byref.md).</span></span> <span data-ttu-id="54e90-120">このプロシージャでは、最後の 2 つの引数の値を変更することはできません。これは、それらが [ByVal](../../../language-reference/modifiers/byval.md) で渡されるためです。</span><span class="sxs-lookup"><span data-stu-id="54e90-120">The procedure cannot change the values of the last two arguments because they are passed [ByVal](../../../language-reference/modifiers/byval.md).</span></span>  
  
     <span data-ttu-id="54e90-121">呼び出し元コードで `level` パラメーターの値が指定されていない場合は、Visual Basic で既定値の 0 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="54e90-121">If the calling code does not supply a value for the `level` parameter, Visual Basic sets it to the default value of 0.</span></span>  
  
     <span data-ttu-id="54e90-122">型チェック スイッチ ([Option Strict ステートメント](../../../language-reference/statements/option-strict-statement.md)) が `Off` の場合は、パラメーターを定義するときに `As` 句を省略できます。</span><span class="sxs-lookup"><span data-stu-id="54e90-122">If the type checking switch ([Option Strict Statement](../../../language-reference/statements/option-strict-statement.md)) is `Off`, the `As` clause is optional when you define a parameter.</span></span> <span data-ttu-id="54e90-123">しかし、いずれかのパラメーターで `As` 句を使用する場合は、それらすべてで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54e90-123">However, if any one parameter uses an `As` clause, all of them must use it.</span></span> <span data-ttu-id="54e90-124">型チェック スイッチが `On` の場合は、すべてのパラメーター定義に対して `As` 句が必須となります。</span><span class="sxs-lookup"><span data-stu-id="54e90-124">If the type checking switch is `On`, the `As` clause is required for every parameter definition.</span></span>  
  
     <span data-ttu-id="54e90-125">すべてのプログラミング要素に対してデータ型を指定することを、"*厳密な型指定*" と呼びます。</span><span class="sxs-lookup"><span data-stu-id="54e90-125">Specifying data types for all your programming elements is known as *strong typing*.</span></span> <span data-ttu-id="54e90-126">`Option Strict On` を設定すると、Visual Basic で厳密な型指定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="54e90-126">When you set `Option Strict On`, Visual Basic enforces strong typing.</span></span> <span data-ttu-id="54e90-127">次の理由により、これを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="54e90-127">This is strongly recommended, for the following reasons:</span></span>  
  
    - <span data-ttu-id="54e90-128">これにより、変数とパラメーターの IntelliSense サポートが有効になります。</span><span class="sxs-lookup"><span data-stu-id="54e90-128">It enables IntelliSense support for your variables and parameters.</span></span> <span data-ttu-id="54e90-129">これにより、コードを入力しながら、プロパティとその他のメンバーを確認できます。</span><span class="sxs-lookup"><span data-stu-id="54e90-129">This allows you to see their properties and other members as you type in your code.</span></span>  
  
    - <span data-ttu-id="54e90-130">これにより、コンパイラで型チェックを実行できます。</span><span class="sxs-lookup"><span data-stu-id="54e90-130">It allows the compiler to perform type checking.</span></span> <span data-ttu-id="54e90-131">これは、オーバーフローなどのエラーによって、実行時に失敗する可能性があるステートメントをキャッチするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="54e90-131">This helps catch statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="54e90-132">また、メソッドをサポートしていないオブジェクトに対するそれらの呼び出しもキャッチされます。</span><span class="sxs-lookup"><span data-stu-id="54e90-132">It also catches calls to methods on objects that do not support them.</span></span>  
  
    - <span data-ttu-id="54e90-133">これにより、コードの実行時間が短縮されます。</span><span class="sxs-lookup"><span data-stu-id="54e90-133">It results in faster execution of your code.</span></span> <span data-ttu-id="54e90-134">この理由の 1 つは、プログラミング要素のデータ型を指定しない場合、Visual Basic コンパイラによって `Object` 型が割り当てられることです。</span><span class="sxs-lookup"><span data-stu-id="54e90-134">One reason for this is that if you do not specify a data type for a programming element, the Visual Basic compiler assigns it the `Object` type.</span></span> <span data-ttu-id="54e90-135">コンパイルされたコードでは、`Object` とその他のデータ型との間で変換を行う必要がある場合があり、これによりパフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="54e90-135">Your compiled code might have to convert back and forth between `Object` and other data types, which reduces performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54e90-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="54e90-136">See also</span></span>

- [<span data-ttu-id="54e90-137">手順</span><span class="sxs-lookup"><span data-stu-id="54e90-137">Procedures</span></span>](./index.md)
- [<span data-ttu-id="54e90-138">Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="54e90-138">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="54e90-139">Function プロシージャ</span><span class="sxs-lookup"><span data-stu-id="54e90-139">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="54e90-140">方法: プロシージャに引数を渡す</span><span class="sxs-lookup"><span data-stu-id="54e90-140">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="54e90-141">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="54e90-141">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="54e90-142">再帰プロシージャ</span><span class="sxs-lookup"><span data-stu-id="54e90-142">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="54e90-143">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="54e90-143">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="54e90-144">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="54e90-144">Objects and Classes</span></span>](../objects-and-classes/index.md)
- [<span data-ttu-id="54e90-145">オブジェクト指向プログラミング (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54e90-145">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
