---
title: '方法: プロシージャ (Visual Basic) のパラメーターを定義します。'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure parameters [Visual Basic], defining data types for
- procedures [Visual Basic], parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters [Visual Basic], defining
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
ms.openlocfilehash: 55925b0f007b1be2f5d46ffc0854601f483b2e2d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61863702"
---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a><span data-ttu-id="c2297-102">方法: プロシージャ (Visual Basic) のパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="c2297-102">How to: Define a Parameter for a Procedure (Visual Basic)</span></span>
<span data-ttu-id="c2297-103">A*パラメーター*それを呼び出すときに、プロシージャに値を渡すコードの呼び出しを許可します。</span><span class="sxs-lookup"><span data-stu-id="c2297-103">A *parameter* allows the calling code to pass a value to the procedure when it calls it.</span></span> <span data-ttu-id="c2297-104">プロシージャの各パラメーターは、変数を宣言すると、その名前とデータ型を指定することと同じ方法で宣言します。</span><span class="sxs-lookup"><span data-stu-id="c2297-104">You declare each parameter for a procedure the same way you declare a variable, specifying its name and data type.</span></span> <span data-ttu-id="c2297-105">渡す方法を指定するかどうか、パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c2297-105">You also specify the passing mechanism, and whether the parameter is optional.</span></span>  
  
 <span data-ttu-id="c2297-106">詳細については、次を参照してください。[プロシージャのパラメーターと引数](./procedure-parameters-and-arguments.md)します。</span><span class="sxs-lookup"><span data-stu-id="c2297-106">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-define-a-procedure-parameter"></a><span data-ttu-id="c2297-107">プロシージャのパラメーターを定義するには</span><span class="sxs-lookup"><span data-stu-id="c2297-107">To define a procedure parameter</span></span>  
  
1. <span data-ttu-id="c2297-108">プロシージャの宣言では、その他のパラメーターをコンマで区切って、プロシージャのパラメーター リストに、パラメーター名を追加します。</span><span class="sxs-lookup"><span data-stu-id="c2297-108">In the procedure declaration, add the parameter name to the procedure's parameter list, separating it from other parameters by commas.</span></span>  
  
2. <span data-ttu-id="c2297-109">パラメーターのデータ型を決定します。</span><span class="sxs-lookup"><span data-stu-id="c2297-109">Decide the data type of the parameter.</span></span>  
  
3. <span data-ttu-id="c2297-110">パラメーター名に続けて、`As`データ型を指定する句。</span><span class="sxs-lookup"><span data-stu-id="c2297-110">Follow the parameter name with an `As` clause to specify the data type.</span></span>  
  
4. <span data-ttu-id="c2297-111">パラメーターの引き渡し方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="c2297-111">Decide the passing mechanism you want for the parameter.</span></span> <span data-ttu-id="c2297-112">通常、プロシージャ呼び出し元のコードでは、その値を変更できるようにする場合を除きに、値でパラメーターを渡します。</span><span class="sxs-lookup"><span data-stu-id="c2297-112">Normally you pass a parameter by value, unless you want the procedure to be able to change its value in the calling code.</span></span>  
  
5. <span data-ttu-id="c2297-113">パラメーター名の前に[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)または[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)引き渡し方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="c2297-113">Precede the parameter name with [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) to specify the passing mechanism.</span></span> <span data-ttu-id="c2297-114">詳細については、次を参照してください。[の相違点の間の値と参照渡しによって引数を渡す](./differences-between-passing-an-argument-by-value-and-by-reference.md)します。</span><span class="sxs-lookup"><span data-stu-id="c2297-114">For more information, see [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
6. <span data-ttu-id="c2297-115">渡しのパラメーターが省略可能な場合は、前に[(省略可能)](../../../../visual-basic/language-reference/modifiers/optional.md)は等号でパラメーターのデータ型に従います (`=`) と、既定値。</span><span class="sxs-lookup"><span data-stu-id="c2297-115">If the parameter is optional, precede the passing mechanism with [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) and follow the parameter data type with an equal sign (`=`) and a default value.</span></span>  
  
     <span data-ttu-id="c2297-116">次の例のアウトラインを定義する、 `Sub` 3 つのパラメーターを持つプロシージャ。</span><span class="sxs-lookup"><span data-stu-id="c2297-116">The following example defines the outline of a `Sub` procedure with three parameters.</span></span> <span data-ttu-id="c2297-117">最初の 2 つが必要ですし、3 つ目は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c2297-117">The first two are required and the third is optional.</span></span> <span data-ttu-id="c2297-118">パラメーターの宣言は、パラメーター リストにコンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="c2297-118">The parameter declarations are separated in the parameter list by commas.</span></span>  
  
     [!code-vb[VbVbcnProcedures#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#33)]  
  
     <span data-ttu-id="c2297-119">最初のパラメーターを受け入れる、`customer`オブジェクト、および`updateCustomer`に渡される変数を直接更新できます`c`引数が渡されるため[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)します。</span><span class="sxs-lookup"><span data-stu-id="c2297-119">The first parameter accepts a `customer` object, and `updateCustomer` can directly update the variable passed to `c` because the argument is passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span></span> <span data-ttu-id="c2297-120">渡されるために、プロシージャが最後の 2 つの引数の値を変更できません[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)します。</span><span class="sxs-lookup"><span data-stu-id="c2297-120">The procedure cannot change the values of the last two arguments because they are passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span>  
  
     <span data-ttu-id="c2297-121">呼び出し元のコードがの値を指定しないかどうか、`level`パラメーターでは、Visual Basic 設定を既定値の 0。</span><span class="sxs-lookup"><span data-stu-id="c2297-121">If the calling code does not supply a value for the `level` parameter, Visual Basic sets it to the default value of 0.</span></span>  
  
     <span data-ttu-id="c2297-122">型チェック スイッチの場合 ([Option Strict ステートメント](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) は`Off`、`As`パラメーターを定義するときに、句は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c2297-122">If the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `Off`, the `As` clause is optional when you define a parameter.</span></span> <span data-ttu-id="c2297-123">ただし、任意の 1 つのパラメーターを使用している場合、`As`句では、いずれも使用する必要あります。</span><span class="sxs-lookup"><span data-stu-id="c2297-123">However, if any one parameter uses an `As` clause, all of them must use it.</span></span> <span data-ttu-id="c2297-124">型チェック スイッチがある場合`On`、`As`句がすべてのパラメーター定義が必要です。</span><span class="sxs-lookup"><span data-stu-id="c2297-124">If the type checking switch is `On`, the `As` clause is required for every parameter definition.</span></span>  
  
     <span data-ttu-id="c2297-125">すべてのプログラミング要素のデータ型の指定と呼びます*厳密な型指定*します。</span><span class="sxs-lookup"><span data-stu-id="c2297-125">Specifying data types for all your programming elements is known as *strong typing*.</span></span> <span data-ttu-id="c2297-126">設定すると`Option Strict On`、Visual Basic は、厳密な型指定を適用します。</span><span class="sxs-lookup"><span data-stu-id="c2297-126">When you set `Option Strict On`, Visual Basic enforces strong typing.</span></span> <span data-ttu-id="c2297-127">これは強くお勧めします、次の理由。</span><span class="sxs-lookup"><span data-stu-id="c2297-127">This is strongly recommended, for the following reasons:</span></span>  
  
    -   <span data-ttu-id="c2297-128">変数とパラメーターの IntelliSense のサポートが有効にするとします。</span><span class="sxs-lookup"><span data-stu-id="c2297-128">It enables IntelliSense support for your variables and parameters.</span></span> <span data-ttu-id="c2297-129">これにより、コードに入力すると、プロパティやその他のメンバーを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="c2297-129">This allows you to see their properties and other members as you type in your code.</span></span>  
  
    -   <span data-ttu-id="c2297-130">これにより、コンパイラが型チェックを実行できます。</span><span class="sxs-lookup"><span data-stu-id="c2297-130">It allows the compiler to perform type checking.</span></span> <span data-ttu-id="c2297-131">これは、オーバーフローなどのエラーにより実行時に失敗するステートメントを検出するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c2297-131">This helps catch statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="c2297-132">サポートしていないオブジェクトに対するメソッドの呼び出しをキャッチします。</span><span class="sxs-lookup"><span data-stu-id="c2297-132">It also catches calls to methods on objects that do not support them.</span></span>  
  
    -   <span data-ttu-id="c2297-133">コードの実行速度が速くなります。</span><span class="sxs-lookup"><span data-stu-id="c2297-133">It results in faster execution of your code.</span></span> <span data-ttu-id="c2297-134">この理由の 1 つは、プログラミング要素のデータ型を指定しない場合、Visual Basic コンパイラが割り当てる、`Object`型。</span><span class="sxs-lookup"><span data-stu-id="c2297-134">One reason for this is that if you do not specify a data type for a programming element, the Visual Basic compiler assigns it the `Object` type.</span></span> <span data-ttu-id="c2297-135">コンパイル済みのコードは、間を気軽に変換する必要があります`Object`とその他のデータ型は、パフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="c2297-135">Your compiled code might have to convert back and forth between `Object` and other data types, which reduces performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2297-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2297-136">See also</span></span>

- [<span data-ttu-id="c2297-137">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="c2297-137">Procedures</span></span>](./index.md)
- [<span data-ttu-id="c2297-138">Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="c2297-138">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="c2297-139">Function プロシージャ</span><span class="sxs-lookup"><span data-stu-id="c2297-139">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="c2297-140">方法: プロシージャに引数を渡す</span><span class="sxs-lookup"><span data-stu-id="c2297-140">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="c2297-141">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="c2297-141">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="c2297-142">再帰プロシージャ</span><span class="sxs-lookup"><span data-stu-id="c2297-142">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="c2297-143">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="c2297-143">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="c2297-144">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="c2297-144">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="c2297-145">オブジェクト指向プログラミング (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c2297-145">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
