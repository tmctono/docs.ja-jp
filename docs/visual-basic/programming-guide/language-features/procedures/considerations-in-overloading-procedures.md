---
title: プロシージャのオーバーロードに関する注意事項
ms.date: 07/20/2015
helpviewer_keywords:
- signatures [Visual Basic], ParamArray arguments
- ParamArray keyword [Visual Basic], parameter arrays
- ParamArray keyword [Visual Basic], arguments and signatures
- function overloading [Visual Basic], implicit overloads for ParamArray
- ParamArray keyword [Visual Basic], signatures
- Visual Basic code, procedures
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], overloading
- parameters [Visual Basic], lists
- function overloading [Visual Basic], typeless programming
- typeless programming
- function overloading [Visual Basic], restrictions
- arguments [Visual Basic], optional
- optional arguments [Visual Basic], overloading
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- parameter arrays [Visual Basic], overloading arguments
- Visual Basic code, parameter lists
- procedure overloading [Visual Basic], considerations
- Option Explicit statement [Visual Basic]
- restrictions [Visual Basic], overloading procedures
- procedures [Visual Basic], parameter lists
ms.assetid: a2001248-10d0-42c5-b0ce-eeedc987319f
ms.openlocfilehash: 4a0cfe176a59b3f90f5850ae8b4e34784c400c6b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351010"
---
# <a name="considerations-in-overloading-procedures-visual-basic"></a><span data-ttu-id="923b1-102">プロシージャのオーバーロードに関する注意事項 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="923b1-102">Considerations in Overloading Procedures (Visual Basic)</span></span>
<span data-ttu-id="923b1-103">プロシージャをオーバーロードする場合は、オーバーロードされたバージョンごとに異なる*シグネチャ*を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="923b1-103">When you overload a procedure, you must use a different *signature* for each overloaded version.</span></span> <span data-ttu-id="923b1-104">これは通常、各バージョンで別のパラメーターリストを指定する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="923b1-104">This usually means each version must specify a different parameter list.</span></span> <span data-ttu-id="923b1-105">詳細については、「[プロシージャのオーバーロード](./procedure-overloading.md)」の「別の署名」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="923b1-105">For more information, see "Different Signature" in [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
 <span data-ttu-id="923b1-106">`Sub` プロシージャを使用して `Function` プロシージャをオーバーロードすることができます。また、シグネチャが異なる場合は、その逆も可能です。</span><span class="sxs-lookup"><span data-stu-id="923b1-106">You can overload a `Function` procedure with a `Sub` procedure, and vice versa, provided they have different signatures.</span></span> <span data-ttu-id="923b1-107">2つのオーバーロードは、一方が戻り値を持ち、もう一方が戻り値を持たない場合にのみ、異なることはできません。</span><span class="sxs-lookup"><span data-stu-id="923b1-107">Two overloads cannot differ only in that one has a return value and the other does not.</span></span>  
  
 <span data-ttu-id="923b1-108">同じ制限を使用して、プロシージャをオーバーロードするのと同じ方法でプロパティをオーバーロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="923b1-108">You can overload a property the same way you overload a procedure, and with the same restrictions.</span></span> <span data-ttu-id="923b1-109">ただし、プロパティを使用してプロシージャをオーバーロードすることはできません。また、その逆もできません。</span><span class="sxs-lookup"><span data-stu-id="923b1-109">However, you cannot overload a procedure with a property, or vice versa.</span></span>  
  
## <a name="alternatives-to-overloaded-versions"></a><span data-ttu-id="923b1-110">オーバーロードされたバージョンの代替手段</span><span class="sxs-lookup"><span data-stu-id="923b1-110">Alternatives to Overloaded Versions</span></span>  
 <span data-ttu-id="923b1-111">オーバーロードされたバージョンに代わる選択肢がある場合があります。特に、引数の存在が省略可能な場合や、その数値が可変である場合です。</span><span class="sxs-lookup"><span data-stu-id="923b1-111">You sometimes have alternatives to overloaded versions, particularly when the presence of arguments is optional or their number is variable.</span></span>  
  
 <span data-ttu-id="923b1-112">省略可能な引数は、必ずしもすべての言語でサポートされているとは限らず、パラメーター配列は Visual Basic に制限されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="923b1-112">Keep in mind that optional arguments are not necessarily supported by all languages, and parameter arrays are limited to Visual Basic.</span></span> <span data-ttu-id="923b1-113">複数の異なる言語で記述されたコードから呼び出される可能性のあるプロシージャを作成する場合は、オーバーロードされたバージョンによって最大限の柔軟性が得られます。</span><span class="sxs-lookup"><span data-stu-id="923b1-113">If you are writing a procedure that is likely to be called from code written in any of several different languages, overloaded versions offer the greatest flexibility.</span></span>  
  
### <a name="overloads-and-optional-arguments"></a><span data-ttu-id="923b1-114">オーバーロードと省略可能な引数</span><span class="sxs-lookup"><span data-stu-id="923b1-114">Overloads and Optional Arguments</span></span>  
 <span data-ttu-id="923b1-115">呼び出し元のコードが必要に応じて1つ以上の引数を指定または省略できる場合は、オーバーロードされた複数のバージョンを定義したり、省略可能なパラメーターを使用したりできます。</span><span class="sxs-lookup"><span data-stu-id="923b1-115">When the calling code can optionally supply or omit one or more arguments, you can define multiple overloaded versions or use optional parameters.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="923b1-116">オーバーロードされたバージョンを使用する場合</span><span class="sxs-lookup"><span data-stu-id="923b1-116">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="923b1-117">次の場合は、一連のオーバーロードされたバージョンを定義することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="923b1-117">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
- <span data-ttu-id="923b1-118">プロシージャコードのロジックは、呼び出し元のコードがオプションの引数を提供するかどうかによって大きく異なります。</span><span class="sxs-lookup"><span data-stu-id="923b1-118">The logic in the procedure code is significantly different depending on whether the calling code supplies an optional argument or not.</span></span>  
  
- <span data-ttu-id="923b1-119">プロシージャコードは、呼び出し元のコードが省略可能な引数を指定しているかどうかを確実にテストすることはできません。</span><span class="sxs-lookup"><span data-stu-id="923b1-119">The procedure code cannot reliably test whether the calling code has supplied an optional argument.</span></span> <span data-ttu-id="923b1-120">これは、たとえば、呼び出し元のコードが提供する必要のない既定値の候補がない場合などです。</span><span class="sxs-lookup"><span data-stu-id="923b1-120">This is the case, for example, if there is no possible candidate for a default value that the calling code could not be expected to supply.</span></span>  
  
#### <a name="when-to-use-optional-parameters"></a><span data-ttu-id="923b1-121">省略可能なパラメーターを使用する場合</span><span class="sxs-lookup"><span data-stu-id="923b1-121">When to Use Optional Parameters</span></span>  
 <span data-ttu-id="923b1-122">次の場合には、省略可能なパラメーターを1つ以上使用することができます。</span><span class="sxs-lookup"><span data-stu-id="923b1-122">You might prefer one or more optional parameters in the following cases:</span></span>  
  
- <span data-ttu-id="923b1-123">呼び出し元のコードがオプションの引数を指定しない場合に必要な操作は、パラメーターを既定値に設定することだけです。</span><span class="sxs-lookup"><span data-stu-id="923b1-123">The only required action when the calling code does not supply an optional argument is to set the parameter to a default value.</span></span> <span data-ttu-id="923b1-124">このような場合、1つ以上の `Optional` パラメーターを使用して1つのバージョンを定義すると、プロシージャコードが複雑になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="923b1-124">In such a case, the procedure code can be less complicated if you define a single version with one or more `Optional` parameters.</span></span>  
  
 <span data-ttu-id="923b1-125">詳細については、「[省略可能なパラメーター](./optional-parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="923b1-125">For more information, see [Optional Parameters](./optional-parameters.md).</span></span>  
  
### <a name="overloads-and-paramarrays"></a><span data-ttu-id="923b1-126">オーバーロードと ParamArrays</span><span class="sxs-lookup"><span data-stu-id="923b1-126">Overloads and ParamArrays</span></span>  
 <span data-ttu-id="923b1-127">呼び出し元のコードが可変個の引数を渡すことができる場合は、オーバーロードされた複数のバージョンを定義することも、パラメーター配列を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="923b1-127">When the calling code can pass a variable number of arguments, you can define multiple overloaded versions or use a parameter array.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="923b1-128">オーバーロードされたバージョンを使用する場合</span><span class="sxs-lookup"><span data-stu-id="923b1-128">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="923b1-129">次の場合は、一連のオーバーロードされたバージョンを定義することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="923b1-129">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
- <span data-ttu-id="923b1-130">呼び出し元のコードは、少数の値をパラメーター配列に渡すことはないことがわかっています。</span><span class="sxs-lookup"><span data-stu-id="923b1-130">You know that the calling code never passes more than a small number of values to the parameter array.</span></span>  
  
- <span data-ttu-id="923b1-131">プロシージャコードのロジックは、呼び出し元のコードが渡す値の数によって大きく異なります。</span><span class="sxs-lookup"><span data-stu-id="923b1-131">The logic in the procedure code is significantly different depending on how many values the calling code passes.</span></span>  
  
- <span data-ttu-id="923b1-132">呼び出し元のコードは、さまざまなデータ型の値を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="923b1-132">The calling code can pass values of different data types.</span></span>  
  
#### <a name="when-to-use-a-parameter-array"></a><span data-ttu-id="923b1-133">パラメーター配列を使用する場合</span><span class="sxs-lookup"><span data-stu-id="923b1-133">When to Use a Parameter Array</span></span>  
 <span data-ttu-id="923b1-134">次の場合には、`ParamArray` パラメーターによって適切に処理されます。</span><span class="sxs-lookup"><span data-stu-id="923b1-134">You are better served by a `ParamArray` parameter in the following cases:</span></span>  
  
- <span data-ttu-id="923b1-135">呼び出し元のコードがパラメーター配列に渡すことができる値の数を予測することはできません。また、数値が大きい可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="923b1-135">You are not able to predict how many values the calling code can pass to the parameter array, and it could be a large number.</span></span>  
  
- <span data-ttu-id="923b1-136">プロシージャロジックは、呼び出し元のコードが渡すすべての値を反復処理するために使用され、実質的にすべての値に対して同じ操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="923b1-136">The procedure logic lends itself to iterating through all the values the calling code passes, performing essentially the same operations on every value.</span></span>  
  
 <span data-ttu-id="923b1-137">詳細については、「[パラメーター配列](./parameter-arrays.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="923b1-137">For more information, see [Parameter Arrays](./parameter-arrays.md).</span></span>  
  
## <a name="implicit-overloads-for-optional-parameters"></a><span data-ttu-id="923b1-138">省略可能なパラメーターの暗黙のオーバーロード</span><span class="sxs-lookup"><span data-stu-id="923b1-138">Implicit Overloads for Optional Parameters</span></span>  
 <span data-ttu-id="923b1-139">[省略可能](../../../../visual-basic/language-reference/modifiers/optional.md)なパラメーターを持つプロシージャは、2つのオーバーロードされたプロシージャに相当します。1つは省略可能なパラメーターで、もう1つは使用しません。</span><span class="sxs-lookup"><span data-stu-id="923b1-139">A procedure with an [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) parameter is equivalent to two overloaded procedures, one with the optional parameter and one without it.</span></span> <span data-ttu-id="923b1-140">このようなプロシージャは、これらのいずれかに対応するパラメーターリストを使用してオーバーロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="923b1-140">You cannot overload such a procedure with a parameter list corresponding to either of these.</span></span> <span data-ttu-id="923b1-141">次の宣言はこれを示しています。</span><span class="sxs-lookup"><span data-stu-id="923b1-141">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#58)]  
  
 [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
 [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
 <span data-ttu-id="923b1-142">省略可能なパラメーターを複数持つプロシージャの場合は、前の例のようにロジックによって受信された一連の暗黙的なオーバーロードがあります。</span><span class="sxs-lookup"><span data-stu-id="923b1-142">For a procedure with more than one optional parameter, there is a set of implicit overloads, arrived at by logic similar to that in the preceding example.</span></span>  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a><span data-ttu-id="923b1-143">ParamArray パラメーターの暗黙のオーバーロード</span><span class="sxs-lookup"><span data-stu-id="923b1-143">Implicit Overloads for a ParamArray Parameter</span></span>  
 <span data-ttu-id="923b1-144">コンパイラは、 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)パラメーターを持つプロシージャが、次のように、呼び出し元のコードがパラメーター配列に渡すものとは異なる無限のオーバーロードを持つと見なします。</span><span class="sxs-lookup"><span data-stu-id="923b1-144">The compiler considers a procedure with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter to have an infinite number of overloads, differing from each other in what the calling code passes to the parameter array, as follows:</span></span>  
  
- <span data-ttu-id="923b1-145">呼び出し元のコードが `ParamArray` に引数を指定しない場合の1つのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="923b1-145">One overload for when the calling code does not supply an argument to the `ParamArray`</span></span>  
  
- <span data-ttu-id="923b1-146">呼び出し元のコードが `ParamArray` 要素型の1次元配列を提供する場合の1つのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="923b1-146">One overload for when the calling code supplies a one-dimensional array of the `ParamArray` element type</span></span>  
  
- <span data-ttu-id="923b1-147">すべての正の整数に対して、呼び出し元のコードが引数の数を指定する場合の1つのオーバーロード (`ParamArray` 要素型)</span><span class="sxs-lookup"><span data-stu-id="923b1-147">For every positive integer, one overload for when the calling code supplies that number of arguments, each of the `ParamArray` element type</span></span>  
  
 <span data-ttu-id="923b1-148">次の宣言は、これらの暗黙的なオーバーロードを示しています。</span><span class="sxs-lookup"><span data-stu-id="923b1-148">The following declarations illustrate these implicit overloads.</span></span>  
  
 [!code-vb[VbVbcnProcedures#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#68)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 <span data-ttu-id="923b1-149">パラメーター配列の1次元配列を受け取るパラメーターリストを使用して、このようなプロシージャをオーバーロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="923b1-149">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="923b1-150">ただし、他の暗黙的なオーバーロードのシグネチャを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="923b1-150">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="923b1-151">次の宣言はこれを示しています。</span><span class="sxs-lookup"><span data-stu-id="923b1-151">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a><span data-ttu-id="923b1-152">オーバーロードの代替手段としてのタイプレスプログラミング</span><span class="sxs-lookup"><span data-stu-id="923b1-152">Typeless Programming as an Alternative to Overloading</span></span>  
 <span data-ttu-id="923b1-153">呼び出し元のコードが異なるデータ型をパラメーターに渡すことを許可する場合は、別の方法として、型指定のないプログラミングがあります。</span><span class="sxs-lookup"><span data-stu-id="923b1-153">If you want to allow the calling code to pass different data types to a parameter, an alternative approach is typeless programming.</span></span> <span data-ttu-id="923b1-154">[Option Strict ステートメント](../../../../visual-basic/language-reference/statements/option-strict-statement.md)または[-optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md)コンパイラオプションのいずれかを使用して、型チェックスイッチを `Off` に設定できます。</span><span class="sxs-lookup"><span data-stu-id="923b1-154">You can set the type checking switch to `Off` with either the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) or the [-optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) compiler option.</span></span> <span data-ttu-id="923b1-155">その後、パラメーターのデータ型を宣言する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="923b1-155">Then you do not have to declare the parameter's data type.</span></span> <span data-ttu-id="923b1-156">ただし、この方法には、オーバーロードと比較して次の欠点があります。</span><span class="sxs-lookup"><span data-stu-id="923b1-156">However, this approach has the following disadvantages compared to overloading:</span></span>  
  
- <span data-ttu-id="923b1-157">タイプレスプログラミングでは、実行コードの効率が低下します。</span><span class="sxs-lookup"><span data-stu-id="923b1-157">Typeless programming produces less efficient execution code.</span></span>  
  
- <span data-ttu-id="923b1-158">このプロシージャでは、渡されると予想されるすべてのデータ型をテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="923b1-158">The procedure must test for every data type it anticipates being passed.</span></span>  
  
- <span data-ttu-id="923b1-159">呼び出し元のコードが、プロシージャがサポートしていないデータ型を渡した場合、コンパイラはエラーを通知できません。</span><span class="sxs-lookup"><span data-stu-id="923b1-159">The compiler cannot signal an error if the calling code passes a data type that the procedure does not support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="923b1-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="923b1-160">See also</span></span>

- [<span data-ttu-id="923b1-161">Visual Basic におけるプロシージャ</span><span class="sxs-lookup"><span data-stu-id="923b1-161">Procedures</span></span>](./index.md)
- [<span data-ttu-id="923b1-162">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="923b1-162">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="923b1-163">プロシージャのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="923b1-163">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="923b1-164">方法 : プロシージャの複数のバージョンを定義する</span><span class="sxs-lookup"><span data-stu-id="923b1-164">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="923b1-165">方法 : オーバーロードされたプロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="923b1-165">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="923b1-166">方法 : 省略可能なパラメーターを受け取るプロシージャをオーバーロードする</span><span class="sxs-lookup"><span data-stu-id="923b1-166">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="923b1-167">方法 : 不特定数のパラメーターを受け取るプロシージャをオーバーロードする</span><span class="sxs-lookup"><span data-stu-id="923b1-167">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="923b1-168">オーバーロードの解決</span><span class="sxs-lookup"><span data-stu-id="923b1-168">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="923b1-169">Overloads</span><span class="sxs-lookup"><span data-stu-id="923b1-169">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
