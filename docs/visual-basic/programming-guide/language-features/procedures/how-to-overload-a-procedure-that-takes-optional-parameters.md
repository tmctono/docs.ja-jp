---
title: '方法: 省略可能なパラメーター (Visual Basic) を受け取るプロシージャをオーバー ロードします。'
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
ms.openlocfilehash: 4374a229392d51b67c99210da91ae05dd3342e96
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "66424055"
---
# <a name="how-to-overload-a-procedure-that-takes-optional-parameters-visual-basic"></a><span data-ttu-id="14818-102">方法: 省略可能なパラメーター (Visual Basic) を受け取るプロシージャをオーバー ロードします。</span><span class="sxs-lookup"><span data-stu-id="14818-102">How to: Overload a Procedure that Takes Optional Parameters (Visual Basic)</span></span>
<span data-ttu-id="14818-103">プロシージャが 1 つまたは複数場合[(省略可能)](../../../../visual-basic/language-reference/modifiers/optional.md)パラメーターの暗黙のオーバー ロードのいずれかに一致するオーバー ロードされたバージョンを定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="14818-103">If a procedure has one or more [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) parameters, you cannot define an overloaded version matching any of its implicit overloads.</span></span> <span data-ttu-id="14818-104">詳細については、"暗黙的なオーバー ロードの省略可能なパラメーター"を参照してください[プロシージャのオーバー ロードに関する考慮事項](./considerations-in-overloading-procedures.md)します。</span><span class="sxs-lookup"><span data-stu-id="14818-104">For more information, see "Implicit Overloads for Optional Parameters" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="one-optional-parameter"></a><span data-ttu-id="14818-105">1 つの省略可能なパラメーター</span><span class="sxs-lookup"><span data-stu-id="14818-105">One Optional Parameter</span></span>  
  
#### <a name="to-overload-a-procedure-that-takes-one-optional-parameter"></a><span data-ttu-id="14818-106">1 つの省略可能なパラメーターを受け取るプロシージャをオーバー ロードするには</span><span class="sxs-lookup"><span data-stu-id="14818-106">To overload a procedure that takes one optional parameter</span></span>  
  
1. <span data-ttu-id="14818-107">書き込みを`Sub`または`Function`宣言ステートメントをパラメーター リストで省略可能なパラメーターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="14818-107">Write a `Sub` or `Function` declaration statement that includes the optional parameter in the parameter list.</span></span> <span data-ttu-id="14818-108">使用しないでください、`Optional`このオーバー ロードされたバージョンのキーワード。</span><span class="sxs-lookup"><span data-stu-id="14818-108">Do not use the `Optional` keyword in this overloaded version.</span></span>  
  
2. <span data-ttu-id="14818-109">前に、`Sub`または`Function`キーワード、[オーバー ロード](../../../../visual-basic/language-reference/modifiers/overloads.md)キーワード。</span><span class="sxs-lookup"><span data-stu-id="14818-109">Precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
3. <span data-ttu-id="14818-110">呼び出し元のコードは省略可能な引数を指定すると実行されるプロシージャ コードを記述します。</span><span class="sxs-lookup"><span data-stu-id="14818-110">Write the procedure code that should execute when the calling code supplies the optional argument.</span></span>  
  
4. <span data-ttu-id="14818-111">プロシージャの終了、`End Sub`または`End Function`に応じてステートメント。</span><span class="sxs-lookup"><span data-stu-id="14818-111">Terminate the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
5. <span data-ttu-id="14818-112">パラメーター リストで省略可能なパラメーターは含まれませんが、最初の宣言と同じである 2 番目の宣言ステートメントを記述します。</span><span class="sxs-lookup"><span data-stu-id="14818-112">Write a second declaration statement that is identical to the first declaration except that it does not include the optional parameter in the parameter list.</span></span>  
  
6. <span data-ttu-id="14818-113">呼び出し元のコードは省略可能な引数を指定しない場合に実行するプロシージャのコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="14818-113">Write the procedure code that should execute when the calling code does not supply the optional argument.</span></span> <span data-ttu-id="14818-114">プロシージャの終了、`End Sub`または`End Function`に応じてステートメント。</span><span class="sxs-lookup"><span data-stu-id="14818-114">Terminate the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
     <span data-ttu-id="14818-115">次の例では、2 つのオーバー ロードされたプロシージャと、最後に有効と無効なオーバー ロードされたバージョンの例の等価セット オプションのパラメーターで定義されている手順を示します。</span><span class="sxs-lookup"><span data-stu-id="14818-115">The following example shows a procedure defined with an optional parameter,  an equivalent set of two overloaded procedures, and finally examples of both invalid and valid overloaded versions.</span></span>  
  
     [!code-vb[VbVbcnProcedures#59](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#59)]  
  
     [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
     [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
## <a name="multiple-optional-parameters"></a><span data-ttu-id="14818-116">複数の省略可能なパラメーター</span><span class="sxs-lookup"><span data-stu-id="14818-116">Multiple Optional Parameters</span></span>  
 <span data-ttu-id="14818-117">省略可能なパラメーターを 1 つ以上のプロシージャでは、通常 2 つ以上のオーバー ロードされたバージョンを必要します。</span><span class="sxs-lookup"><span data-stu-id="14818-117">For a procedure with more than one optional parameter, you normally need more than two overloaded versions.</span></span> <span data-ttu-id="14818-118">たとえば、2 つの省略可能なパラメーターがあるで呼び出し元のコードを指定したり、他とは無関係にそれぞれを省略した場合は、指定された引数の組み合わせごとに 1 つずつ、4 つのオーバー ロードされたバージョン必要があります。</span><span class="sxs-lookup"><span data-stu-id="14818-118">For example, if there are two optional parameters, and the calling code can supply or omit each one independently of the other, you need four overloaded versions, one for each possible combination of supplied arguments.</span></span>  
  
 <span data-ttu-id="14818-119">省略可能なパラメーターの数が多いほど、オーバー ロードの複雑さが増加します。</span><span class="sxs-lookup"><span data-stu-id="14818-119">As the number of optional parameters increases, the complexity of the overloading increases.</span></span> <span data-ttu-id="14818-120">指定された引数のいくつかの組み合わせが許容されない場合を除き、N の省略可能なパラメーターの必要がある 2 ^ N のオーバー ロードされたバージョン。</span><span class="sxs-lookup"><span data-stu-id="14818-120">Unless some combinations of supplied arguments are not acceptable, for N optional parameters you need 2 ^ N overloaded versions.</span></span> <span data-ttu-id="14818-121">、プロシージャの性質によっては、ロジックをわかりやすくするために、すべてのオーバー ロードされたバージョンを定義するという余分な作業によって正当化されることがあります。</span><span class="sxs-lookup"><span data-stu-id="14818-121">Depending on the nature of the procedure, you might find that the clarity of logic justifies the extra effort of defining all the overloaded versions.</span></span>  
  
#### <a name="to-overload-a-procedure-that-takes-more-than-one-optional-parameter"></a><span data-ttu-id="14818-122">1 つ以上の省略可能なパラメーターを受け取るプロシージャをオーバー ロードするには</span><span class="sxs-lookup"><span data-stu-id="14818-122">To overload a procedure that takes more than one optional parameter</span></span>  
  
1. <span data-ttu-id="14818-123">プロシージャのロジックを指定できる省略可能な引数の組み合わせを決定します。</span><span class="sxs-lookup"><span data-stu-id="14818-123">Determine which combinations of supplied optional arguments are acceptable to the logic of the procedure.</span></span> <span data-ttu-id="14818-124">受け入れられない組み合わせは、別の 1 つの省略可能なパラメーターが依存している場合に発生する可能性です。</span><span class="sxs-lookup"><span data-stu-id="14818-124">An unacceptable combination might arise if one optional parameter depends on another.</span></span> <span data-ttu-id="14818-125">たとえば、1 つのパラメーターが人の名前を受け入れ、人物の年齢を受け取る場合は、年齢が名前を省略すると、引数の組み合わせは許されません。</span><span class="sxs-lookup"><span data-stu-id="14818-125">For example, if one parameter accepts a person's name and another accepts the person's age, a combination of arguments supplying the age but omitting the name is unacceptable.</span></span>  
  
2. <span data-ttu-id="14818-126">省略可能な引数の許容可能な組み合わせごとに、書き込み、`Sub`または`Function`宣言ステートメントを対応するパラメーター リストを定義します。</span><span class="sxs-lookup"><span data-stu-id="14818-126">For each acceptable combination of supplied optional arguments, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="14818-127">使用しないでください、`Optional`キーワード。</span><span class="sxs-lookup"><span data-stu-id="14818-127">Do not use the `Optional` keyword.</span></span>  
  
3. <span data-ttu-id="14818-128">各宣言の前に、`Sub`または`Function`キーワード、[オーバー ロード](../../../../visual-basic/language-reference/modifiers/overloads.md)キーワード。</span><span class="sxs-lookup"><span data-stu-id="14818-128">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
4. <span data-ttu-id="14818-129">次の各宣言には、呼び出し元のコードは、宣言のパラメーター リストに対応する引数リストを提供する場合に実行するプロシージャ コードを記述します。</span><span class="sxs-lookup"><span data-stu-id="14818-129">Following each declaration, write the procedure code that should execute when the calling code supplies an argument list corresponding to that declaration's parameter list.</span></span>  
  
5. <span data-ttu-id="14818-130">各プロシージャの終了、`End Sub`または`End Function`に応じてステートメント。</span><span class="sxs-lookup"><span data-stu-id="14818-130">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14818-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="14818-131">See also</span></span>

- [<span data-ttu-id="14818-132">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="14818-132">Procedures</span></span>](./index.md)
- [<span data-ttu-id="14818-133">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="14818-133">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="14818-134">省略可能なパラメーター</span><span class="sxs-lookup"><span data-stu-id="14818-134">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="14818-135">パラメーター配列</span><span class="sxs-lookup"><span data-stu-id="14818-135">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="14818-136">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="14818-136">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="14818-137">プロシージャのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="14818-137">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="14818-138">方法: 複数のバージョンのプロシージャを定義します。</span><span class="sxs-lookup"><span data-stu-id="14818-138">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="14818-139">方法: オーバー ロードされたプロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="14818-139">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="14818-140">方法: 不特定数のパラメーターを受け取るプロシージャをオーバー ロードします。</span><span class="sxs-lookup"><span data-stu-id="14818-140">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="14818-141">オーバーロードの解決</span><span class="sxs-lookup"><span data-stu-id="14818-141">Overload Resolution</span></span>](./overload-resolution.md)
