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
ms.openlocfilehash: 6197fa4041a22944542b2657e35bc293a6e5c244
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075058"
---
# <a name="considerations-in-overloading-procedures-visual-basic"></a><span data-ttu-id="02334-102">プロシージャのオーバーロードに関する注意事項 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="02334-102">Considerations in Overloading Procedures (Visual Basic)</span></span>

<span data-ttu-id="02334-103">プロシージャをオーバーロードするときは、オーバーロードされたバージョンごとに異なる "*シグネチャ*" を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02334-103">When you overload a procedure, you must use a different *signature* for each overloaded version.</span></span> <span data-ttu-id="02334-104">通常、これはバージョンごとに異なるパラメーター リストを指定する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="02334-104">This usually means each version must specify a different parameter list.</span></span> <span data-ttu-id="02334-105">詳細については、「[プロシージャのオーバーロード](./procedure-overloading.md)」の「異なるシグネチャ」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="02334-105">For more information, see "Different Signature" in [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
 <span data-ttu-id="02334-106">シグネチャが異なるという前提で、`Function` プロシージャを `Sub` プロシージャでオーバーロードすることができ、その逆も可能です。</span><span class="sxs-lookup"><span data-stu-id="02334-106">You can overload a `Function` procedure with a `Sub` procedure, and vice versa, provided they have different signatures.</span></span> <span data-ttu-id="02334-107">一方に戻り値があり、もう一方にはないという点だけでは、2 つのオーバーロードが異なると見なすことはできません。</span><span class="sxs-lookup"><span data-stu-id="02334-107">Two overloads cannot differ only in that one has a return value and the other does not.</span></span>  
  
 <span data-ttu-id="02334-108">プロパティは、プロシージャをオーバーロードする場合と同じ方法で、同じ制限を適用してオーバーロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="02334-108">You can overload a property the same way you overload a procedure, and with the same restrictions.</span></span> <span data-ttu-id="02334-109">ただし、プロパティでプロシージャをオーバーロードすることはできません。その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="02334-109">However, you cannot overload a procedure with a property, or vice versa.</span></span>  
  
## <a name="alternatives-to-overloaded-versions"></a><span data-ttu-id="02334-110">オーバーロードされたバージョンの代替</span><span class="sxs-lookup"><span data-stu-id="02334-110">Alternatives to Overloaded Versions</span></span>  

 <span data-ttu-id="02334-111">特に、引数が省略可能である場合やその数が可変である場合は、オーバーロードされたバージョンに代わるものを使用することがあります。</span><span class="sxs-lookup"><span data-stu-id="02334-111">You sometimes have alternatives to overloaded versions, particularly when the presence of arguments is optional or their number is variable.</span></span>  
  
 <span data-ttu-id="02334-112">省略可能な引数はすべての言語で必ずしもサポートされているわけではなく、パラメーター配列は Visual Basic に限定されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="02334-112">Keep in mind that optional arguments are not necessarily supported by all languages, and parameter arrays are limited to Visual Basic.</span></span> <span data-ttu-id="02334-113">さまざまな言語のいずれかで記述されたコードから呼び出される可能性が高いプロシージャを作成する場合は、オーバーロードされたバージョンが最も優れた柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="02334-113">If you are writing a procedure that is likely to be called from code written in any of several different languages, overloaded versions offer the greatest flexibility.</span></span>  
  
### <a name="overloads-and-optional-arguments"></a><span data-ttu-id="02334-114">オーバーロードと省略可能な引数</span><span class="sxs-lookup"><span data-stu-id="02334-114">Overloads and Optional Arguments</span></span>  

 <span data-ttu-id="02334-115">呼び出し元のコードが、1 つ以上の引数を必要に応じて指定または省略できる場合は、複数のオーバーロードされたバージョンを定義することも、省略可能なパラメーターを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="02334-115">When the calling code can optionally supply or omit one or more arguments, you can define multiple overloaded versions or use optional parameters.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="02334-116">オーバーロードされたバージョンを使用する場合</span><span class="sxs-lookup"><span data-stu-id="02334-116">When to Use Overloaded Versions</span></span>  

 <span data-ttu-id="02334-117">次の場合は、一連のオーバーロードされたバージョンを定義することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="02334-117">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
- <span data-ttu-id="02334-118">呼び出し元のコードが省略可能な引数を指定するかどうかによって、プロシージャ コードのロジックが大きく異なる場合。</span><span class="sxs-lookup"><span data-stu-id="02334-118">The logic in the procedure code is significantly different depending on whether the calling code supplies an optional argument or not.</span></span>  
  
- <span data-ttu-id="02334-119">プロシージャ コードで、呼び出し元のコードが省略可能な引数を指定しているかどうかを確実にテストすることができない場合。</span><span class="sxs-lookup"><span data-stu-id="02334-119">The procedure code cannot reliably test whether the calling code has supplied an optional argument.</span></span> <span data-ttu-id="02334-120">たとえば、呼び出し元のコードが指定することを期待できない既定値の候補が存在しない場合は、これに該当します。</span><span class="sxs-lookup"><span data-stu-id="02334-120">This is the case, for example, if there is no possible candidate for a default value that the calling code could not be expected to supply.</span></span>  
  
#### <a name="when-to-use-optional-parameters"></a><span data-ttu-id="02334-121">省略可能なパラメーターを使用する場合</span><span class="sxs-lookup"><span data-stu-id="02334-121">When to Use Optional Parameters</span></span>  

 <span data-ttu-id="02334-122">次の場合には、1 つ以上の省略可能なパラメーターを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="02334-122">You might prefer one or more optional parameters in the following cases:</span></span>  
  
- <span data-ttu-id="02334-123">呼び出し元のコードが省略可能な引数を指定しない場合に必要な唯一のアクションが、パラメーターを既定値に設定することである場合。</span><span class="sxs-lookup"><span data-stu-id="02334-123">The only required action when the calling code does not supply an optional argument is to set the parameter to a default value.</span></span> <span data-ttu-id="02334-124">このような場合、1 つ以上の `Optional` パラメーターを持つ単一のバージョンを定義すると、プロシージャー コードの複雑さを軽減できます。</span><span class="sxs-lookup"><span data-stu-id="02334-124">In such a case, the procedure code can be less complicated if you define a single version with one or more `Optional` parameters.</span></span>  
  
 <span data-ttu-id="02334-125">詳細については、「[省略可能なパラメーター](./optional-parameters.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="02334-125">For more information, see [Optional Parameters](./optional-parameters.md).</span></span>  
  
### <a name="overloads-and-paramarrays"></a><span data-ttu-id="02334-126">オーバーロードと ParamArray</span><span class="sxs-lookup"><span data-stu-id="02334-126">Overloads and ParamArrays</span></span>  

 <span data-ttu-id="02334-127">呼び出し元のコードが可変数の引数を渡すことができる場合は、複数のオーバーロードされたバージョンを定義することも、パラメーター配列を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="02334-127">When the calling code can pass a variable number of arguments, you can define multiple overloaded versions or use a parameter array.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="02334-128">オーバーロードされたバージョンを使用する場合</span><span class="sxs-lookup"><span data-stu-id="02334-128">When to Use Overloaded Versions</span></span>  

 <span data-ttu-id="02334-129">次の場合は、一連のオーバーロードされたバージョンを定義することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="02334-129">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
- <span data-ttu-id="02334-130">呼び出し元のコードがパラメーター配列に渡す値が常に少数であることがわかっている場合。</span><span class="sxs-lookup"><span data-stu-id="02334-130">You know that the calling code never passes more than a small number of values to the parameter array.</span></span>  
  
- <span data-ttu-id="02334-131">呼び出し元のコードが渡す値の数によって、プロシージャ コードのロジックが大きく異なる場合。</span><span class="sxs-lookup"><span data-stu-id="02334-131">The logic in the procedure code is significantly different depending on how many values the calling code passes.</span></span>  
  
- <span data-ttu-id="02334-132">呼び出し元のコードがさまざまなデータ型の値を渡すことができる場合。</span><span class="sxs-lookup"><span data-stu-id="02334-132">The calling code can pass values of different data types.</span></span>  
  
#### <a name="when-to-use-a-parameter-array"></a><span data-ttu-id="02334-133">パラメーター配列を使用する場合</span><span class="sxs-lookup"><span data-stu-id="02334-133">When to Use a Parameter Array</span></span>  

 <span data-ttu-id="02334-134">次の場合は、`ParamArray` パラメーターの方が適しています。</span><span class="sxs-lookup"><span data-stu-id="02334-134">You are better served by a `ParamArray` parameter in the following cases:</span></span>  
  
- <span data-ttu-id="02334-135">呼び出し元のコードがパラメーター配列に渡すことができる値の数を予測できず、数が多くなる可能性がある場合。</span><span class="sxs-lookup"><span data-stu-id="02334-135">You are not able to predict how many values the calling code can pass to the parameter array, and it could be a large number.</span></span>  
  
- <span data-ttu-id="02334-136">プロシージャのロジックが、すべての値に対して基本的に同じ操作を実行するものであり、呼び出し元のコードから渡されるすべての値を反復処理するのに適している場合。</span><span class="sxs-lookup"><span data-stu-id="02334-136">The procedure logic lends itself to iterating through all the values the calling code passes, performing essentially the same operations on every value.</span></span>  
  
 <span data-ttu-id="02334-137">詳細については、「[パラメーター配列](./parameter-arrays.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="02334-137">For more information, see [Parameter Arrays](./parameter-arrays.md).</span></span>  
  
## <a name="implicit-overloads-for-optional-parameters"></a><span data-ttu-id="02334-138">Optional パラメーターの暗黙的なオーバーロード</span><span class="sxs-lookup"><span data-stu-id="02334-138">Implicit Overloads for Optional Parameters</span></span>  

 <span data-ttu-id="02334-139">[Optional](../../../language-reference/modifiers/optional.md) パラメーターを持つプロシージャは、省略可能なパラメーターを持つものと持たないものの 2 つのオーバーロードされたプロシージャと同等です。</span><span class="sxs-lookup"><span data-stu-id="02334-139">A procedure with an [Optional](../../../language-reference/modifiers/optional.md) parameter is equivalent to two overloaded procedures, one with the optional parameter and one without it.</span></span> <span data-ttu-id="02334-140">これらのいずれかに対応するパラメーター リストでこのようなプロシージャをオーバーロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="02334-140">You cannot overload such a procedure with a parameter list corresponding to either of these.</span></span> <span data-ttu-id="02334-141">次の宣言はこれを示しています。</span><span class="sxs-lookup"><span data-stu-id="02334-141">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#58)]  
  
 [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
 [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
 <span data-ttu-id="02334-142">複数の省略可能なパラメーターを持つプロシージャでは、前の例と同様のロジックで到達する一連の暗黙的なオーバーロードがあります。</span><span class="sxs-lookup"><span data-stu-id="02334-142">For a procedure with more than one optional parameter, there is a set of implicit overloads, arrived at by logic similar to that in the preceding example.</span></span>  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a><span data-ttu-id="02334-143">ParamArray パラメーターの暗黙的なオーバーロード</span><span class="sxs-lookup"><span data-stu-id="02334-143">Implicit Overloads for a ParamArray Parameter</span></span>  

 <span data-ttu-id="02334-144">コンパイラは、[ParamArray](../../../language-reference/modifiers/paramarray.md) パラメーターを持つプロシージャを、次のように、呼び出し元のコードがパラメーター配列に渡す内容が相互に異なる無数のオーバーロードを持つものと見なします。</span><span class="sxs-lookup"><span data-stu-id="02334-144">The compiler considers a procedure with a [ParamArray](../../../language-reference/modifiers/paramarray.md) parameter to have an infinite number of overloads, differing from each other in what the calling code passes to the parameter array, as follows:</span></span>  
  
- <span data-ttu-id="02334-145">呼び出し元のコードが `ParamArray` に引数を指定しない場合に対応する 1 つのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="02334-145">One overload for when the calling code does not supply an argument to the `ParamArray`</span></span>  
  
- <span data-ttu-id="02334-146">呼び出し元のコードが `ParamArray` 要素型の 1 次元配列を指定した場合に対応する 1 つのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="02334-146">One overload for when the calling code supplies a one-dimensional array of the `ParamArray` element type</span></span>  
  
- <span data-ttu-id="02334-147">すべての正の整数について、呼び出し元のコードがその数の引数を各 `ParamArray` 要素型に指定した場合に対応する 1 つのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="02334-147">For every positive integer, one overload for when the calling code supplies that number of arguments, each of the `ParamArray` element type</span></span>  
  
 <span data-ttu-id="02334-148">次の宣言は、これらの暗黙的なオーバーロードを示しています。</span><span class="sxs-lookup"><span data-stu-id="02334-148">The following declarations illustrate these implicit overloads.</span></span>  
  
 [!code-vb[VbVbcnProcedures#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#68)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 <span data-ttu-id="02334-149">パラメーター配列に対して 1 次元配列を受け取るパラメーター リストでそのようなプロシージャをオーバーロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="02334-149">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="02334-150">ただし、他の暗黙的なオーバーロードのシグネチャを使用できます。</span><span class="sxs-lookup"><span data-stu-id="02334-150">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="02334-151">次の宣言はこれを示しています。</span><span class="sxs-lookup"><span data-stu-id="02334-151">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a><span data-ttu-id="02334-152">オーバーロードの代替手段としての型宣言を省略したプログラミング</span><span class="sxs-lookup"><span data-stu-id="02334-152">Typeless Programming as an Alternative to Overloading</span></span>  

 <span data-ttu-id="02334-153">呼び出し元のコードがパラメーターにさまざまなデータ型を渡すことができるようにする場合、別の方法として、型宣言を省略したプログラミングがあります。</span><span class="sxs-lookup"><span data-stu-id="02334-153">If you want to allow the calling code to pass different data types to a parameter, an alternative approach is typeless programming.</span></span> <span data-ttu-id="02334-154">[Option Strict ステートメント](../../../language-reference/statements/option-strict-statement.md)または [-optionstrict](../../../reference/command-line-compiler/optionstrict.md) コンパイラ オプションで、型チェック スイッチを `Off` に設定できます。</span><span class="sxs-lookup"><span data-stu-id="02334-154">You can set the type checking switch to `Off` with either the [Option Strict Statement](../../../language-reference/statements/option-strict-statement.md) or the [-optionstrict](../../../reference/command-line-compiler/optionstrict.md) compiler option.</span></span> <span data-ttu-id="02334-155">その後、パラメーターのデータ型を宣言する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="02334-155">Then you do not have to declare the parameter's data type.</span></span> <span data-ttu-id="02334-156">ただし、オーバーロードと比較して、この方法には次の欠点があります。</span><span class="sxs-lookup"><span data-stu-id="02334-156">However, this approach has the following disadvantages compared to overloading:</span></span>  
  
- <span data-ttu-id="02334-157">型宣言を省略したプログラミングでは、効率的ではない実行コードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="02334-157">Typeless programming produces less efficient execution code.</span></span>  
  
- <span data-ttu-id="02334-158">プロシージャは、渡されることが予想されるすべてのデータ型をテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="02334-158">The procedure must test for every data type it anticipates being passed.</span></span>  
  
- <span data-ttu-id="02334-159">呼び出し元のコードが、プロシージャでサポートされていないデータ型を渡した場合、コンパイラはエラーを通知できません。</span><span class="sxs-lookup"><span data-stu-id="02334-159">The compiler cannot signal an error if the calling code passes a data type that the procedure does not support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02334-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="02334-160">See also</span></span>

- [<span data-ttu-id="02334-161">手順</span><span class="sxs-lookup"><span data-stu-id="02334-161">Procedures</span></span>](./index.md)
- [<span data-ttu-id="02334-162">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="02334-162">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="02334-163">プロシージャのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="02334-163">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="02334-164">方法: プロシージャの複数のバージョンを定義する</span><span class="sxs-lookup"><span data-stu-id="02334-164">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="02334-165">方法: オーバーロードされたプロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="02334-165">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="02334-166">方法: 省略可能なパラメーターを受け取るプロシージャをオーバーロードする</span><span class="sxs-lookup"><span data-stu-id="02334-166">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="02334-167">方法: 不特定数のパラメーターを受け取るプロシージャをオーバーロードする</span><span class="sxs-lookup"><span data-stu-id="02334-167">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="02334-168">オーバーロードの解決</span><span class="sxs-lookup"><span data-stu-id="02334-168">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="02334-169">Overloads</span><span class="sxs-lookup"><span data-stu-id="02334-169">Overloads</span></span>](../../../language-reference/modifiers/overloads.md)
