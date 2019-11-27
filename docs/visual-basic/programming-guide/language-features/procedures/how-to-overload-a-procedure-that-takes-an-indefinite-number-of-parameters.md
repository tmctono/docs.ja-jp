---
title: '方法 : 不特定数のパラメーターを受け取るプロシージャをオーバーロードする'
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
ms.openlocfilehash: 047d566c13f03803d2e5c3bc6cce0db56df4a3f0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345851"
---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a><span data-ttu-id="bcf2c-102">方法: 不特定数のパラメーターを受け取るプロシージャをオーバーロードする (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bcf2c-102">How to: Overload a Procedure that Takes an Indefinite Number of Parameters (Visual Basic)</span></span>
<span data-ttu-id="bcf2c-103">プロシージャに[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)パラメーターがある場合、パラメーター配列に1次元配列を受け取るオーバーロードされたバージョンを定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="bcf2c-103">If a procedure has a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, you cannot define an overloaded version taking a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="bcf2c-104">詳細については、「[プロシージャのオーバーロードに関する考慮事項](./considerations-in-overloading-procedures.md)」の「ParamArray パラメーターの暗黙のオーバーロード」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcf2c-104">For more information, see "Implicit Overloads for a ParamArray Parameter" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a><span data-ttu-id="bcf2c-105">可変個のパラメーターを受け取るプロシージャをオーバーロードするには</span><span class="sxs-lookup"><span data-stu-id="bcf2c-105">To overload a procedure that takes a variable number of parameters</span></span>  
  
1. <span data-ttu-id="bcf2c-106">プロシージャと呼び出しコードロジックが、`ParamArray` パラメーターよりも多くのオーバーロードされたバージョンの恩恵を得られることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bcf2c-106">Ascertain that the procedure and calling code logic benefits from overloaded versions more than from a `ParamArray` parameter.</span></span> <span data-ttu-id="bcf2c-107">「オーバーロードと ParamArrays」の「[オーバーロードと](./considerations-in-overloading-procedures.md)paramarrays」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcf2c-107">See "Overloads and ParamArrays" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
2. <span data-ttu-id="bcf2c-108">パラメーターリストの変数部分で、プロシージャが受け入れる指定された値の数を決定します。</span><span class="sxs-lookup"><span data-stu-id="bcf2c-108">Determine which numbers of supplied values the procedure should accept in the variable part of the parameter list.</span></span> <span data-ttu-id="bcf2c-109">これには、値のないケース、1つの1次元配列のケースなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bcf2c-109">This might include the case of no value, and it might include the case of a single one-dimensional array.</span></span>  
  
3. <span data-ttu-id="bcf2c-110">指定された許容される値の数ごとに、対応するパラメーターリストを定義する `Sub` または `Function` 宣言ステートメントを記述します。</span><span class="sxs-lookup"><span data-stu-id="bcf2c-110">For each acceptable number of supplied values, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="bcf2c-111">このオーバーロードされたバージョンでは、`Optional` または `ParamArray` キーワードは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="bcf2c-111">Do not use either the `Optional` or the `ParamArray` keyword in this overloaded version.</span></span>  
  
4. <span data-ttu-id="bcf2c-112">各宣言で、`Sub` または `Function` キーワードの前に[Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="bcf2c-112">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
5. <span data-ttu-id="bcf2c-113">各宣言の後に、呼び出し元のコードがその宣言のパラメーターリストに対応する値を指定したときに実行する必要があるプロシージャコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="bcf2c-113">Following each declaration, write the procedure code that should execute when the calling code supplies values corresponding to that declaration's parameter list.</span></span>  
  
6. <span data-ttu-id="bcf2c-114">必要に応じて、`End Sub` または `End Function` ステートメントを使用して各プロシージャを終了します。</span><span class="sxs-lookup"><span data-stu-id="bcf2c-114">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bcf2c-115">例</span><span class="sxs-lookup"><span data-stu-id="bcf2c-115">Example</span></span>  
 <span data-ttu-id="bcf2c-116">次の例では、 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)パラメーターを使用して定義されたプロシージャと、それと同等のオーバーロードされたプロシージャのセットを示します。</span><span class="sxs-lookup"><span data-stu-id="bcf2c-116">The following example shows a procedure defined with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, and then an equivalent set of overloaded procedures.</span></span>  
  
 [!code-vb[VbVbcnProcedures#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#69)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 <span data-ttu-id="bcf2c-117">パラメーター配列の1次元配列を受け取るパラメーターリストを使用して、このようなプロシージャをオーバーロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="bcf2c-117">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="bcf2c-118">ただし、他の暗黙的なオーバーロードのシグネチャを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="bcf2c-118">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="bcf2c-119">次の宣言はこれを示しています。</span><span class="sxs-lookup"><span data-stu-id="bcf2c-119">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
 <span data-ttu-id="bcf2c-120">オーバーロードされたバージョンのコードでは、呼び出し元のコードが `ParamArray` パラメーターに対して1つ以上の値を提供したかどうかをテストする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bcf2c-120">The code in the overloaded versions does not have to test whether the calling code supplied one or more values for the `ParamArray` parameter, or if so, how many.</span></span> <span data-ttu-id="bcf2c-121">Visual Basic は、呼び出し元の引数リストと一致するバージョンに制御を渡します。</span><span class="sxs-lookup"><span data-stu-id="bcf2c-121">Visual Basic passes control to the version matching the calling argument list.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bcf2c-122">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="bcf2c-122">Compiling the Code</span></span>  
 <span data-ttu-id="bcf2c-123">`ParamArray` パラメーターを持つプロシージャは、オーバーロードされたバージョンのセットと等価であるため、このようなプロシージャは、これらの暗黙的なオーバーロードのいずれかに対応するパラメーターリストを使用してオーバーロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="bcf2c-123">Because a procedure with a `ParamArray` parameter is equivalent to a set of overloaded versions, you cannot overload such a procedure with a parameter list corresponding to any of these implicit overloads.</span></span> <span data-ttu-id="bcf2c-124">詳細については、「[プロシージャのオーバーロードに関する考慮事項](./considerations-in-overloading-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcf2c-124">For more information, see [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="bcf2c-125">.NET Framework のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="bcf2c-125">.NET Framework Security</span></span>  
 <span data-ttu-id="bcf2c-126">無限に大きくなる可能性がある配列を処理する場合、アプリケーションの内部容量がオーバーランするリスクがあります。</span><span class="sxs-lookup"><span data-stu-id="bcf2c-126">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="bcf2c-127">パラメーター配列を受け入れる場合は、渡された呼び出し元のコードが配列の長さであるかどうかをテストし、アプリケーションに対して大きすぎる場合は適切な手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcf2c-127">If you accept a parameter array, you should test for the length of the array the calling code passed to it, and take appropriate steps if it is too large for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcf2c-128">参照</span><span class="sxs-lookup"><span data-stu-id="bcf2c-128">See also</span></span>

- [<span data-ttu-id="bcf2c-129">手順</span><span class="sxs-lookup"><span data-stu-id="bcf2c-129">Procedures</span></span>](./index.md)
- [<span data-ttu-id="bcf2c-130">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="bcf2c-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="bcf2c-131">省略可能なパラメーター</span><span class="sxs-lookup"><span data-stu-id="bcf2c-131">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="bcf2c-132">パラメーター配列</span><span class="sxs-lookup"><span data-stu-id="bcf2c-132">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="bcf2c-133">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="bcf2c-133">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="bcf2c-134">プロシージャのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="bcf2c-134">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="bcf2c-135">方法 : プロシージャの複数のバージョンを定義する</span><span class="sxs-lookup"><span data-stu-id="bcf2c-135">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="bcf2c-136">方法 : オーバーロードされたプロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="bcf2c-136">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="bcf2c-137">方法 : 省略可能なパラメーターを受け取るプロシージャをオーバーロードする</span><span class="sxs-lookup"><span data-stu-id="bcf2c-137">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="bcf2c-138">オーバーロードの解決</span><span class="sxs-lookup"><span data-stu-id="bcf2c-138">Overload Resolution</span></span>](./overload-resolution.md)
