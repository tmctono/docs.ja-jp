---
title: '方法: 不特定数のパラメーター (Visual Basic) を受け取るプロシージャをオーバー ロードします。'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], indefinite number of parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
ms.openlocfilehash: 3cf75fc6221364704379eb23d308481c34e6c0d6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61955741"
---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a><span data-ttu-id="c429f-102">方法: 不特定数のパラメーター (Visual Basic) を受け取るプロシージャをオーバー ロードします。</span><span class="sxs-lookup"><span data-stu-id="c429f-102">How to: Overload a Procedure that Takes an Indefinite Number of Parameters (Visual Basic)</span></span>
<span data-ttu-id="c429f-103">プロシージャがある場合、 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)パラメーター、パラメーター配列の 1 次元配列を取得するオーバー ロードされたバージョンを定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="c429f-103">If a procedure has a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, you cannot define an overloaded version taking a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="c429f-104">詳細については、「暗黙的なオーバー ロードを ParamArray パラメーター」を参照してください[プロシージャのオーバー ロードに関する考慮事項](./considerations-in-overloading-procedures.md)します。</span><span class="sxs-lookup"><span data-stu-id="c429f-104">For more information, see "Implicit Overloads for a ParamArray Parameter" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a><span data-ttu-id="c429f-105">可変個のパラメーターを受け取るプロシージャをオーバー ロードするには</span><span class="sxs-lookup"><span data-stu-id="c429f-105">To overload a procedure that takes a variable number of parameters</span></span>  
  
1. <span data-ttu-id="c429f-106">プロシージャは、コード ロジックのメリットを呼び出すことがから複数のバージョンのオーバー ロードされたことを確認、`ParamArray`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="c429f-106">Ascertain that the procedure and calling code logic benefits from overloaded versions more than from a `ParamArray` parameter.</span></span> <span data-ttu-id="c429f-107">「オーバー ロードと Paramarray」を参照してください[プロシージャのオーバー ロードに関する考慮事項](./considerations-in-overloading-procedures.md)します。</span><span class="sxs-lookup"><span data-stu-id="c429f-107">See "Overloads and ParamArrays" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
2. <span data-ttu-id="c429f-108">パラメーター リストの可変部分で、プロシージャが受け取る指定された値の数を決定します。</span><span class="sxs-lookup"><span data-stu-id="c429f-108">Determine which numbers of supplied values the procedure should accept in the variable part of the parameter list.</span></span> <span data-ttu-id="c429f-109">これは、値はありませんの大文字と小文字が含まれます、1 つの 1 次元配列の大文字と小文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c429f-109">This might include the case of no value, and it might include the case of a single one-dimensional array.</span></span>  
  
3. <span data-ttu-id="c429f-110">指定された値の許容数はそれぞれ、書き込み、`Sub`または`Function`宣言ステートメントを対応するパラメーター リストを定義します。</span><span class="sxs-lookup"><span data-stu-id="c429f-110">For each acceptable number of supplied values, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="c429f-111">使用しないで、`Optional`または`ParamArray`このオーバー ロードされたバージョンのキーワード。</span><span class="sxs-lookup"><span data-stu-id="c429f-111">Do not use either the `Optional` or the `ParamArray` keyword in this overloaded version.</span></span>  
  
4. <span data-ttu-id="c429f-112">各宣言の前に、`Sub`または`Function`キーワード、[オーバー ロード](../../../../visual-basic/language-reference/modifiers/overloads.md)キーワード。</span><span class="sxs-lookup"><span data-stu-id="c429f-112">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
5. <span data-ttu-id="c429f-113">次の各宣言には、呼び出し元のコードは、宣言のパラメーター リストに対応する値を指定すると実行されるプロシージャ コードを記述します。</span><span class="sxs-lookup"><span data-stu-id="c429f-113">Following each declaration, write the procedure code that should execute when the calling code supplies values corresponding to that declaration's parameter list.</span></span>  
  
6. <span data-ttu-id="c429f-114">各プロシージャの終了、`End Sub`または`End Function`に応じてステートメント。</span><span class="sxs-lookup"><span data-stu-id="c429f-114">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c429f-115">例</span><span class="sxs-lookup"><span data-stu-id="c429f-115">Example</span></span>  
 <span data-ttu-id="c429f-116">次の例で定義されている手順を示しています、 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)パラメーターとし、同等の一連のオーバー ロードされたプロシージャ。</span><span class="sxs-lookup"><span data-stu-id="c429f-116">The following example shows a procedure defined with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, and then an equivalent set of overloaded procedures.</span></span>  
  
 [!code-vb[VbVbcnProcedures#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#69)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 <span data-ttu-id="c429f-117">パラメーター配列の 1 次元配列を受け取るパラメーター リストで、このようなプロシージャをオーバー ロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c429f-117">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="c429f-118">ただし、他の暗黙的なオーバー ロードのシグネチャを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="c429f-118">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="c429f-119">次の宣言では、これについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c429f-119">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
 <span data-ttu-id="c429f-120">オーバー ロードされたバージョンのコードは呼び出し元のコードの 1 つまたは複数の値を指定するかどうかをテストする必要はありません、`ParamArray`パラメーター、そうである場合、または数。</span><span class="sxs-lookup"><span data-stu-id="c429f-120">The code in the overloaded versions does not have to test whether the calling code supplied one or more values for the `ParamArray` parameter, or if so, how many.</span></span> <span data-ttu-id="c429f-121">Visual Basic では、呼び出し元の引数リストに一致するバージョンに制御を渡します。</span><span class="sxs-lookup"><span data-stu-id="c429f-121">Visual Basic passes control to the version matching the calling argument list.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c429f-122">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="c429f-122">Compiling the Code</span></span>  
 <span data-ttu-id="c429f-123">ため、使用するプロシージャを`ParamArray`パラメーターは、一連のオーバー ロードされたバージョンに、これらの暗黙的なオーバー ロードのいずれかに対応するパラメーター リストで、このようなプロシージャをオーバー ロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c429f-123">Because a procedure with a `ParamArray` parameter is equivalent to a set of overloaded versions, you cannot overload such a procedure with a parameter list corresponding to any of these implicit overloads.</span></span> <span data-ttu-id="c429f-124">詳細については、次を参照してください。[プロシージャのオーバー ロードに関する考慮事項](./considerations-in-overloading-procedures.md)します。</span><span class="sxs-lookup"><span data-stu-id="c429f-124">For more information, see [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="c429f-125">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="c429f-125">.NET Framework Security</span></span>  
 <span data-ttu-id="c429f-126">無限に増大することができる配列を処理するたびに、アプリケーションの内部の容量を超過してしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c429f-126">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="c429f-127">パラメーター配列を受け取る場合は、呼び出し元のコードは、渡された配列の長さをテストし、がアプリケーションには大きすぎる場合は、適切な手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c429f-127">If you accept a parameter array, you should test for the length of the array the calling code passed to it, and take appropriate steps if it is too large for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c429f-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="c429f-128">See also</span></span>

- [<span data-ttu-id="c429f-129">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="c429f-129">Procedures</span></span>](./index.md)
- [<span data-ttu-id="c429f-130">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="c429f-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="c429f-131">省略可能なパラメーター</span><span class="sxs-lookup"><span data-stu-id="c429f-131">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="c429f-132">パラメーター配列</span><span class="sxs-lookup"><span data-stu-id="c429f-132">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="c429f-133">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="c429f-133">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="c429f-134">プロシージャのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c429f-134">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="c429f-135">方法: 複数のバージョンのプロシージャを定義します。</span><span class="sxs-lookup"><span data-stu-id="c429f-135">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="c429f-136">方法: オーバー ロードされたプロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="c429f-136">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="c429f-137">方法: 省略可能なパラメーターを受け取るプロシージャをオーバー ロードします。</span><span class="sxs-lookup"><span data-stu-id="c429f-137">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="c429f-138">オーバーロードの解決</span><span class="sxs-lookup"><span data-stu-id="c429f-138">Overload Resolution</span></span>](./overload-resolution.md)
