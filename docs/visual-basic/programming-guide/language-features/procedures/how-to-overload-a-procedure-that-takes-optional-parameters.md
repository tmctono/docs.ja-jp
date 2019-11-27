---
title: '方法 : 省略可能なパラメーターを受け取るプロシージャをオーバーロードする'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], optional parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: 825f9d56-4cde-43fd-993a-b9171717e2eb
ms.openlocfilehash: 4d31980e4b968cff274091ba4f307dffddab1100
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350864"
---
# <a name="how-to-overload-a-procedure-that-takes-optional-parameters-visual-basic"></a><span data-ttu-id="40fc8-102">方法: 省略可能なパラメーターを受け取るプロシージャをオーバーロードする (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="40fc8-102">How to: Overload a Procedure that Takes Optional Parameters (Visual Basic)</span></span>
<span data-ttu-id="40fc8-103">プロシージャに[省略可能](../../../../visual-basic/language-reference/modifiers/optional.md)なパラメーターが1つ以上ある場合、その暗黙的なオーバーロードのいずれかに一致するオーバーロードされたバージョンを定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="40fc8-103">If a procedure has one or more [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) parameters, you cannot define an overloaded version matching any of its implicit overloads.</span></span> <span data-ttu-id="40fc8-104">詳細については、「[プロシージャのオーバーロードに関する考慮事項](./considerations-in-overloading-procedures.md)」の「省略可能なパラメーターの暗黙のオーバーロード」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40fc8-104">For more information, see "Implicit Overloads for Optional Parameters" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="one-optional-parameter"></a><span data-ttu-id="40fc8-105">1つの省略可能なパラメーター</span><span class="sxs-lookup"><span data-stu-id="40fc8-105">One Optional Parameter</span></span>  
  
#### <a name="to-overload-a-procedure-that-takes-one-optional-parameter"></a><span data-ttu-id="40fc8-106">省略可能なパラメーターを1つ受け取るプロシージャをオーバーロードするには</span><span class="sxs-lookup"><span data-stu-id="40fc8-106">To overload a procedure that takes one optional parameter</span></span>  
  
1. <span data-ttu-id="40fc8-107">パラメーターリストに省略可能なパラメーターを含む `Sub` または `Function` 宣言ステートメントを記述します。</span><span class="sxs-lookup"><span data-stu-id="40fc8-107">Write a `Sub` or `Function` declaration statement that includes the optional parameter in the parameter list.</span></span> <span data-ttu-id="40fc8-108">このオーバーロードされたバージョンでは、`Optional` キーワードを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="40fc8-108">Do not use the `Optional` keyword in this overloaded version.</span></span>  
  
2. <span data-ttu-id="40fc8-109">`Sub` または `Function` キーワードの前に[Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)キーワードを付けます。</span><span class="sxs-lookup"><span data-stu-id="40fc8-109">Precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
3. <span data-ttu-id="40fc8-110">呼び出し元のコードがオプションの引数を提供するときに実行する必要があるプロシージャコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="40fc8-110">Write the procedure code that should execute when the calling code supplies the optional argument.</span></span>  
  
4. <span data-ttu-id="40fc8-111">必要に応じて、`End Sub` または `End Function` ステートメントを使用してプロシージャを終了します。</span><span class="sxs-lookup"><span data-stu-id="40fc8-111">Terminate the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
5. <span data-ttu-id="40fc8-112">パラメーターリストに省略可能なパラメーターが含まれない点を除いて、最初の宣言と同じである2番目の宣言ステートメントを記述します。</span><span class="sxs-lookup"><span data-stu-id="40fc8-112">Write a second declaration statement that is identical to the first declaration except that it does not include the optional parameter in the parameter list.</span></span>  
  
6. <span data-ttu-id="40fc8-113">呼び出し元のコードで省略可能な引数が指定されていない場合に実行するプロシージャコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="40fc8-113">Write the procedure code that should execute when the calling code does not supply the optional argument.</span></span> <span data-ttu-id="40fc8-114">必要に応じて、`End Sub` または `End Function` ステートメントを使用してプロシージャを終了します。</span><span class="sxs-lookup"><span data-stu-id="40fc8-114">Terminate the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
     <span data-ttu-id="40fc8-115">次の例では、省略可能なパラメーターを使用して定義されたプロシージャ、2つのオーバーロードされたプロシージャのセット、および無効なオーバーロードバージョンと有効なオーバーロードされたバージョンの両方の最後の例を示します。</span><span class="sxs-lookup"><span data-stu-id="40fc8-115">The following example shows a procedure defined with an optional parameter,  an equivalent set of two overloaded procedures, and finally examples of both invalid and valid overloaded versions.</span></span>  
  
     [!code-vb[VbVbcnProcedures#59](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#59)]  
  
     [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
     [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
## <a name="multiple-optional-parameters"></a><span data-ttu-id="40fc8-116">複数の省略可能なパラメーター</span><span class="sxs-lookup"><span data-stu-id="40fc8-116">Multiple Optional Parameters</span></span>  
 <span data-ttu-id="40fc8-117">省略可能なパラメーターを複数持つプロシージャの場合は、通常、3つ以上のオーバーロードされたバージョンが必要です。</span><span class="sxs-lookup"><span data-stu-id="40fc8-117">For a procedure with more than one optional parameter, you normally need more than two overloaded versions.</span></span> <span data-ttu-id="40fc8-118">たとえば、2つの省略可能なパラメーターがあり、呼び出し元のコードが互いに独立してそれぞれを指定または省略できる場合は、指定された引数の組み合わせごとに1つずつ、4つのオーバーロードされたバージョンが必要です。</span><span class="sxs-lookup"><span data-stu-id="40fc8-118">For example, if there are two optional parameters, and the calling code can supply or omit each one independently of the other, you need four overloaded versions, one for each possible combination of supplied arguments.</span></span>  
  
 <span data-ttu-id="40fc8-119">省略可能なパラメーターの数が増えるにつれて、オーバーロードの複雑さが増します。</span><span class="sxs-lookup"><span data-stu-id="40fc8-119">As the number of optional parameters increases, the complexity of the overloading increases.</span></span> <span data-ttu-id="40fc8-120">指定された引数の組み合わせが受け入れられない場合は、N 個の省略可能なパラメーターについては、2 ^ N のオーバーロードされたバージョンが必要です。</span><span class="sxs-lookup"><span data-stu-id="40fc8-120">Unless some combinations of supplied arguments are not acceptable, for N optional parameters you need 2 ^ N overloaded versions.</span></span> <span data-ttu-id="40fc8-121">プロシージャの性質によっては、オーバーロードされたすべてのバージョンを定義する余分な作業をロジックが明確にすることがわかります。</span><span class="sxs-lookup"><span data-stu-id="40fc8-121">Depending on the nature of the procedure, you might find that the clarity of logic justifies the extra effort of defining all the overloaded versions.</span></span>  
  
#### <a name="to-overload-a-procedure-that-takes-more-than-one-optional-parameter"></a><span data-ttu-id="40fc8-122">複数の省略可能なパラメーターを受け取るプロシージャをオーバーロードするには</span><span class="sxs-lookup"><span data-stu-id="40fc8-122">To overload a procedure that takes more than one optional parameter</span></span>  
  
1. <span data-ttu-id="40fc8-123">指定された省略可能な引数の組み合わせを、プロシージャのロジックに対して使用できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="40fc8-123">Determine which combinations of supplied optional arguments are acceptable to the logic of the procedure.</span></span> <span data-ttu-id="40fc8-124">1つの省略可能なパラメーターが別のパラメーターに依存している場合、許容されない組み合わせが発生する可能性が</span><span class="sxs-lookup"><span data-stu-id="40fc8-124">An unacceptable combination might arise if one optional parameter depends on another.</span></span> <span data-ttu-id="40fc8-125">たとえば、1つのパラメーターが人名を受け取り、別のパラメーターがその年齢を受け入れる場合、age を指定し、名前を省略する引数の組み合わせは使用できません。</span><span class="sxs-lookup"><span data-stu-id="40fc8-125">For example, if one parameter accepts a person's name and another accepts the person's age, a combination of arguments supplying the age but omitting the name is unacceptable.</span></span>  
  
2. <span data-ttu-id="40fc8-126">指定された省略可能な引数の組み合わせを使用できる場合は、対応するパラメーターリストを定義する `Sub` または `Function` 宣言ステートメントを記述します。</span><span class="sxs-lookup"><span data-stu-id="40fc8-126">For each acceptable combination of supplied optional arguments, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="40fc8-127">`Optional` キーワードは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="40fc8-127">Do not use the `Optional` keyword.</span></span>  
  
3. <span data-ttu-id="40fc8-128">各宣言で、`Sub` または `Function` キーワードの前に[Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="40fc8-128">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
4. <span data-ttu-id="40fc8-129">各宣言の後に、呼び出し元のコードがその宣言のパラメーターリストに対応する引数リストを提供するときに実行する必要があるプロシージャコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="40fc8-129">Following each declaration, write the procedure code that should execute when the calling code supplies an argument list corresponding to that declaration's parameter list.</span></span>  
  
5. <span data-ttu-id="40fc8-130">必要に応じて、`End Sub` または `End Function` ステートメントを使用して各プロシージャを終了します。</span><span class="sxs-lookup"><span data-stu-id="40fc8-130">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40fc8-131">参照</span><span class="sxs-lookup"><span data-stu-id="40fc8-131">See also</span></span>

- [<span data-ttu-id="40fc8-132">手順</span><span class="sxs-lookup"><span data-stu-id="40fc8-132">Procedures</span></span>](./index.md)
- [<span data-ttu-id="40fc8-133">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="40fc8-133">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="40fc8-134">省略可能なパラメーター</span><span class="sxs-lookup"><span data-stu-id="40fc8-134">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="40fc8-135">パラメーター配列</span><span class="sxs-lookup"><span data-stu-id="40fc8-135">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="40fc8-136">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="40fc8-136">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="40fc8-137">プロシージャのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="40fc8-137">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="40fc8-138">方法 : プロシージャの複数のバージョンを定義する</span><span class="sxs-lookup"><span data-stu-id="40fc8-138">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="40fc8-139">方法 : オーバーロードされたプロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="40fc8-139">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="40fc8-140">方法 : 不特定数のパラメーターを受け取るプロシージャをオーバーロードする</span><span class="sxs-lookup"><span data-stu-id="40fc8-140">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="40fc8-141">オーバーロードの解決</span><span class="sxs-lookup"><span data-stu-id="40fc8-141">Overload Resolution</span></span>](./overload-resolution.md)
