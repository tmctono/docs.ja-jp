---
title: プロシージャのトラブルシューティング
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting Visual Basic, procedures
- procedures [Visual Basic], troubleshooting
- Visual Basic code, procedures
- troubleshooting procedures
- procedures [Visual Basic], about procedures
ms.assetid: 525721e8-2e02-4f75-b5d8-6b893462cf2b
ms.openlocfilehash: 8d4c4929e299efb12d283492a101c18ae794110b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352515"
---
# <a name="troubleshooting-procedures-visual-basic"></a><span data-ttu-id="04a41-102">プロシージャのトラブルシューティング (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04a41-102">Troubleshooting procedures (Visual Basic)</span></span>

<span data-ttu-id="04a41-103">このページでは、プロシージャを使用しているときに発生する可能性のある一般的な問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="04a41-103">This page lists some common problems that can occur when working with procedures.</span></span>  
  
## <a name="returning-an-array-type-from-a-function-procedure"></a><span data-ttu-id="04a41-104">関数プロシージャから配列の型を返す</span><span class="sxs-lookup"><span data-stu-id="04a41-104">Returning an array type from a function procedure</span></span>

<span data-ttu-id="04a41-105">`Function` プロシージャが配列のデータ型を返す場合、`Function` 名を使用して配列の要素に値を格納することはできません。</span><span class="sxs-lookup"><span data-stu-id="04a41-105">If a `Function` procedure returns an array data type, you cannot use the `Function` name to store values in the elements of the array.</span></span> <span data-ttu-id="04a41-106">これを行おうとすると、コンパイラは `Function` の呼び出しと解釈します。</span><span class="sxs-lookup"><span data-stu-id="04a41-106">If you attempt to do this, the compiler interprets it as a call to the `Function`.</span></span> <span data-ttu-id="04a41-107">次の例ではコンパイラ エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="04a41-107">The following example generates compiler errors:</span></span>
  
```vb
Function AllOnes(n As Integer) As Integer()
   For i As Integer = 1 To n - 1  
      ' The following statement generates a COMPILER ERROR.  
      AllOnes(i) = 1  
   Next  

   ' The following statement generates a COMPILER ERROR.  
   Return AllOnes()  
End Function
```

<span data-ttu-id="04a41-108">`AllOnes(i) = 1` ステートメントは、間違ったデータ型の引数 (`Integer` 配列ではなく、スカラー `Integer`) で `AllOnes` を呼び出しているように見えるため、コンパイラ エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="04a41-108">The statement `AllOnes(i) = 1` generates a compiler error because it appears to call `AllOnes` with an argument of the wrong data type (a scalar `Integer` instead of an `Integer` array).</span></span> <span data-ttu-id="04a41-109">`Return AllOnes()` ステートメントは、引数なしで `AllOnes` を呼び出しているように見えるため、コンパイラ エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="04a41-109">The statement `Return AllOnes()` generates a compiler error because it appears to call `AllOnes` with no argument.</span></span>  
  
 <span data-ttu-id="04a41-110">**正しい方法:** 返される配列の要素を変更できるようにするには、内部配列をローカル変数として定義します。</span><span class="sxs-lookup"><span data-stu-id="04a41-110">**Correct approach:** To be able to modify the elements of an array that is to be returned, define an internal array as a local variable.</span></span> <span data-ttu-id="04a41-111">次の例はエラーなしでコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="04a41-111">The following example compiles without error:</span></span>

 [!code-vb[VbVbcnProcedures#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#66)]

## <a name="argument-not-modified-by-procedure-call"></a><span data-ttu-id="04a41-112">プロシージャ呼び出しによって引数が変更されない</span><span class="sxs-lookup"><span data-stu-id="04a41-112">Argument not modified by procedure call</span></span>

<span data-ttu-id="04a41-113">プロシージャが、引数の基になる呼び出し元のコードのプログラミング要素を変更できるようにする場合は、参照渡しにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="04a41-113">If you intend to allow a procedure to change a programming element underlying an argument in the calling code, you must pass it by reference.</span></span> <span data-ttu-id="04a41-114">ただし、値渡しにした場合でも、プロシージャは参照型引数の要素にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="04a41-114">But a procedure can access the elements of a reference type argument even if you pass it by value.</span></span>

- <span data-ttu-id="04a41-115">**基になる変数**:</span><span class="sxs-lookup"><span data-stu-id="04a41-115">**Underlying variable**.</span></span> <span data-ttu-id="04a41-116">プロシージャが、基になる変数要素自体の値を置き換えることができるようにするには、プロシージャでパラメーターを [ByRef](../../../language-reference/modifiers/byref.md) として宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04a41-116">To allow the procedure to replace the value of the underlying variable element itself, the procedure must declare the parameter [ByRef](../../../language-reference/modifiers/byref.md).</span></span> <span data-ttu-id="04a41-117">また、呼び出し元のコードでは、引数をかっこで囲むことはできません。これを行うと、引渡し方法 `ByRef` がオーバーライドされるためです。</span><span class="sxs-lookup"><span data-stu-id="04a41-117">Also, the calling code must not enclose the argument in parentheses, because that would override the `ByRef` passing mechanism.</span></span>

- <span data-ttu-id="04a41-118">**参照型の要素**:</span><span class="sxs-lookup"><span data-stu-id="04a41-118">**Reference type elements**.</span></span> <span data-ttu-id="04a41-119">パラメーターを [ByVal](../../../language-reference/modifiers/byval.md) として宣言した場合、プロシージャは基になる変数要素自体を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="04a41-119">If you declare a parameter [ByVal](../../../language-reference/modifiers/byval.md), the procedure cannot modify the underlying variable element itself.</span></span> <span data-ttu-id="04a41-120">ただし、引数が参照型の場合、プロシージャは変数の値を置き換えることはできなくても、参照先のオブジェクトのメンバーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="04a41-120">However, if the argument is a reference type, the procedure can modify the members of the object to which it points, even though it cannot replace the variable's value.</span></span> <span data-ttu-id="04a41-121">たとえば、引数が配列変数の場合、プロシージャは新しい配列を割り当てることはできませんが、1 つ以上の要素を変更できます。</span><span class="sxs-lookup"><span data-stu-id="04a41-121">For example, if the argument is an array variable, the procedure cannot assign a new array to it, but it can change one or more of its elements.</span></span> <span data-ttu-id="04a41-122">変更された要素は、呼び出し元のコードの基になる配列変数に反映されます。</span><span class="sxs-lookup"><span data-stu-id="04a41-122">The changed elements are reflected in the underlying array variable in the calling code.</span></span>

<span data-ttu-id="04a41-123">次の例では、配列変数を値で受け取り、その要素を操作する 2 つのプロシージャを定義します。</span><span class="sxs-lookup"><span data-stu-id="04a41-123">The following example defines two procedures that take an array variable by value and operate on its elements.</span></span> <span data-ttu-id="04a41-124">`increase` プロシージャは、各要素に 1 を加算するだけです。</span><span class="sxs-lookup"><span data-stu-id="04a41-124">Procedure `increase` simply adds one to each element.</span></span> <span data-ttu-id="04a41-125">`replace` プロシージャは、`a()` パラメーターに新しい配列を割り当ててから、各要素に 1 を加算します。</span><span class="sxs-lookup"><span data-stu-id="04a41-125">Procedure `replace` assigns a new array to the parameter `a()` and then adds one to each element.</span></span> <span data-ttu-id="04a41-126">ただし、`a()` は `ByVal` として宣言されているため、再割り当ては呼び出し元のコードの基になる配列変数には影響しません。</span><span class="sxs-lookup"><span data-stu-id="04a41-126">However, the reassignment does not affect the underlying array variable in the calling code because `a()` is declared `ByVal`.</span></span>

[!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]

[!code-vb[VbVbcnProcedures#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#38)]

<span data-ttu-id="04a41-127">次の例では、`increase` と `replace` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="04a41-127">The following example makes calls to `increase` and `replace`:</span></span>

[!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]
  
<span data-ttu-id="04a41-128">最初の `MsgBox` 呼び出しでは、"After increase(n): 11, 21, 31, 41" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="04a41-128">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="04a41-129">`n` は参照型であるため、`ByVal` で渡されても、`increase` はそのメンバーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="04a41-129">Because `n` is a reference type, `increase` can change its members, even though it is passed `ByVal`.</span></span>

<span data-ttu-id="04a41-130">2 番目の `MsgBox` 呼び出しでは、"After replace(n): 11, 21, 31, 41" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="04a41-130">The second `MsgBox` call displays "After replace(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="04a41-131">`n` は `ByVal` で渡されるため、`replace` は変数 `n` に新しい配列を割り当てて変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="04a41-131">Because `n` is passed `ByVal`, `replace` cannot modify the variable `n` by assigning a new array to it.</span></span> <span data-ttu-id="04a41-132">`replace` が新しい配列インスタンス `k` を作成し、ローカル変数 `a` に割り当てると、呼び出し元のコードによって渡された `n` への参照は失われます。</span><span class="sxs-lookup"><span data-stu-id="04a41-132">When `replace` creates the new array instance `k` and assigns it to the local variable `a`, it loses the reference to `n` passed in by the calling code.</span></span> <span data-ttu-id="04a41-133">`a` のメンバーをインクリメントすると、ローカル配列 `k` だけが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="04a41-133">When it increments the members of `a`, only the local array `k` is affected.</span></span>

<span data-ttu-id="04a41-134">**正しい方法:** 基になる変数要素自体を変更できるようにするには、参照渡しにします。</span><span class="sxs-lookup"><span data-stu-id="04a41-134">**Correct approach:** To be able to modify an underlying variable element itself, pass it by reference.</span></span> <span data-ttu-id="04a41-135">次の例は、呼び出し元のコードの配列を別の配列に置き換えることができるようにするための、`replace` の宣言の変更を示しています。</span><span class="sxs-lookup"><span data-stu-id="04a41-135">The following example shows the change in the declaration of `replace` that allows it to replace one array with another in the calling code:</span></span>

[!code-vb[VbVbcnProcedures#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#64)]

## <a name="unable-to-define-an-overload"></a><span data-ttu-id="04a41-136">オーバーロードを定義できない</span><span class="sxs-lookup"><span data-stu-id="04a41-136">Unable to define an overload</span></span>

<span data-ttu-id="04a41-137">プロシージャのオーバーロードされたバージョンを定義する場合は、同じ名前を使用し、異なるシグネチャを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04a41-137">If you want to define an overloaded version of a procedure, you must use the same name but a different signature.</span></span> <span data-ttu-id="04a41-138">コンパイラが、同じシグネチャを持つオーバーロードと宣言を区別できない場合、エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="04a41-138">If the compiler cannot differentiate your declaration from an overload with the same signature, it generates an error.</span></span>

<span data-ttu-id="04a41-139">プロシージャの "*シグネチャ*" は、プロシージャ名とパラメーター リストによって決まります。</span><span class="sxs-lookup"><span data-stu-id="04a41-139">The *signature* of a procedure is determined by the procedure name and the parameter list.</span></span> <span data-ttu-id="04a41-140">各オーバーロードの名前は、他のすべてのオーバーロードと同じである必要がありますが、シグネチャの他の構成要素の少なくとも 1 つですべてのオーバーロードを区別できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="04a41-140">Each overload must have the same name as all the other overloads but must differ from all of them in at least one of the other components of the signature.</span></span> <span data-ttu-id="04a41-141">詳細については、「 [Procedure Overloading](./procedure-overloading.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04a41-141">For more information, see [Procedure Overloading](./procedure-overloading.md).</span></span>

<span data-ttu-id="04a41-142">次の項目はパラメーター リストに関連するものですが、プロシージャのシグネチャの構成要素ではありません。</span><span class="sxs-lookup"><span data-stu-id="04a41-142">The following items, even though they pertain to the parameter list, are not components of a procedure's signature:</span></span>

- <span data-ttu-id="04a41-143">プロシージャ修飾子キーワード (`Public`、`Shared`、`Static` など)</span><span class="sxs-lookup"><span data-stu-id="04a41-143">Procedure modifier keywords, such as `Public`, `Shared`, and `Static`.</span></span>
- <span data-ttu-id="04a41-144">パラメーター名</span><span class="sxs-lookup"><span data-stu-id="04a41-144">Parameter names.</span></span>
- <span data-ttu-id="04a41-145">パラメーター修飾子キーワード (`ByRef` や `Optional` など)</span><span class="sxs-lookup"><span data-stu-id="04a41-145">Parameter modifier keywords, such as `ByRef` and `Optional`.</span></span>
- <span data-ttu-id="04a41-146">戻り値のデータ型 (変換演算子を除く)</span><span class="sxs-lookup"><span data-stu-id="04a41-146">The data type of the return value (except for a conversion operator).</span></span>

<span data-ttu-id="04a41-147">上記の 1 つ以上の項目を変えるだけでは、プロシージャをオーバーロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="04a41-147">You cannot overload a procedure by varying only one or more of the preceding items.</span></span>

<span data-ttu-id="04a41-148">**正しい方法:** プロシージャのオーバーロードを定義できるようにするには、シグネチャを変える必要があります。</span><span class="sxs-lookup"><span data-stu-id="04a41-148">**Correct approach:** To be able to define a procedure overload, you must vary the signature.</span></span> <span data-ttu-id="04a41-149">同じ名前を使用する必要があるため、パラメーターの数、順序、またはデータ型を変える必要があります。</span><span class="sxs-lookup"><span data-stu-id="04a41-149">Because you must use the same name, you must vary the number, order, or data types of the parameters.</span></span> <span data-ttu-id="04a41-150">ジェネリック プロシージャでは、型パラメーターの数を変えることができます。</span><span class="sxs-lookup"><span data-stu-id="04a41-150">In a generic procedure, you can vary the number of type parameters.</span></span> <span data-ttu-id="04a41-151">変換演算子 ([CType 関数](../../../language-reference/functions/ctype-function.md)) では、戻り値の型を変えることができます。</span><span class="sxs-lookup"><span data-stu-id="04a41-151">In a conversion operator ([CType Function](../../../language-reference/functions/ctype-function.md)), you can vary the return type.</span></span>

### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a><span data-ttu-id="04a41-152">Optional および ParamArray 引数によるオーバーロードの解決</span><span class="sxs-lookup"><span data-stu-id="04a41-152">Overload resolution with Optional and ParamArray arguments</span></span>

<span data-ttu-id="04a41-153">1 つ以上の [Optional](../../../language-reference/modifiers/optional.md) パラメーターまたは [ParamArray](../../../language-reference/modifiers/paramarray.md) パラメーターでプロシージャをオーバーロードする場合は、"*暗黙的なオーバーロード*" のいずれかと重複しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="04a41-153">If you are overloading a procedure with one or more [Optional](../../../language-reference/modifiers/optional.md) parameters or a [ParamArray](../../../language-reference/modifiers/paramarray.md) parameter, you must avoid duplicating any of the *implicit overloads*.</span></span> <span data-ttu-id="04a41-154">詳細については、「[プロシージャのオーバーロードに関する注意事項](./considerations-in-overloading-procedures.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="04a41-154">For information, see [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>

## <a name="calling-the-wrong-version-of-an-overloaded-procedure"></a><span data-ttu-id="04a41-155">オーバーロードされたプロシージャの間違ったバージョンの呼び出し</span><span class="sxs-lookup"><span data-stu-id="04a41-155">Calling the wrong version of an overloaded procedure</span></span>

<span data-ttu-id="04a41-156">プロシージャに複数のオーバーロードされたバージョンがある場合は、すべてのパラメーター リストを把握し、Visual Basic がオーバーロード間で呼び出しを解決する方法を理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="04a41-156">If a procedure has several overloaded versions, you should be familiar with all their parameter lists and understand how Visual Basic resolves calls among the overloads.</span></span> <span data-ttu-id="04a41-157">そうしないと、目的のもの以外のオーバーロードを呼び出す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="04a41-157">Otherwise you could call an overload other than the intended one.</span></span>

<span data-ttu-id="04a41-158">呼び出すオーバーロードを決定したら、次の規則に従うよう注意してください。</span><span class="sxs-lookup"><span data-stu-id="04a41-158">When you have determined which overload you want to call, be careful to observe the following rules:</span></span>

- <span data-ttu-id="04a41-159">正しい数の引数を正しい順序で指定します。</span><span class="sxs-lookup"><span data-stu-id="04a41-159">Supply the correct number of arguments, and in the correct order.</span></span>  
- <span data-ttu-id="04a41-160">引数は、対応するパラメーターとまったく同じデータ型であるのが理想的です。</span><span class="sxs-lookup"><span data-stu-id="04a41-160">Ideally, your arguments should have the exact same data types as the corresponding parameters.</span></span> <span data-ttu-id="04a41-161">いずれにしても、各引数のデータ型は、対応するパラメーターのデータ型に拡大変換する必要があります</span><span class="sxs-lookup"><span data-stu-id="04a41-161">In any case, the data type of each argument must widen to that of its corresponding parameter.</span></span> <span data-ttu-id="04a41-162">これは、[Option Strict ステートメント](../../../language-reference/statements/option-strict-statement.md)が `Off` に設定されている場合でも同様です。</span><span class="sxs-lookup"><span data-stu-id="04a41-162">This is true even with the [Option Strict Statement](../../../language-reference/statements/option-strict-statement.md) set to `Off`.</span></span> <span data-ttu-id="04a41-163">オーバーロードが引数リストからの縮小変換を必要とする場合、そのオーバーロードは呼び出し対象にはなりません。</span><span class="sxs-lookup"><span data-stu-id="04a41-163">If an overload requires any narrowing conversion from your argument list, that overload is not eligible to be called.</span></span>
- <span data-ttu-id="04a41-164">拡大変換を必要とする引数を指定する場合は、それらのデータ型を、対応するパラメーターのデータ型にできるだけ近いものにします。</span><span class="sxs-lookup"><span data-stu-id="04a41-164">If you supply arguments that require widening, make their data types as close as possible to the corresponding parameter data types.</span></span> <span data-ttu-id="04a41-165">2 つ以上のオーバーロードが引数のデータ型を受け入れる場合、コンパイラは、必要な拡大変換が最も少ないオーバーロードに呼び出しを解決します。</span><span class="sxs-lookup"><span data-stu-id="04a41-165">If two or more overloads accept your argument data types, the compiler resolves your call to the overload that calls for the least amount of widening.</span></span>

<span data-ttu-id="04a41-166">引数を準備するときに、[CType 関数](../../../language-reference/functions/ctype-function.md)変換キーワードを使用すると、データ型の不一致の可能性を低減できます。</span><span class="sxs-lookup"><span data-stu-id="04a41-166">You can reduce the chance of data type mismatches by using the [CType Function](../../../language-reference/functions/ctype-function.md) conversion keyword when preparing your arguments.</span></span>

### <a name="overload-resolution-failure"></a><span data-ttu-id="04a41-167">オーバーロードの解決の失敗</span><span class="sxs-lookup"><span data-stu-id="04a41-167">Overload resolution failure</span></span>

<span data-ttu-id="04a41-168">オーバーロードされたプロシージャを呼び出すと、コンパイラはオーバーロードの 1 つを除くすべてを排除することを試みます。</span><span class="sxs-lookup"><span data-stu-id="04a41-168">When you call an overloaded procedure, the compiler attempts to eliminate all but one of the overloads.</span></span> <span data-ttu-id="04a41-169">これが成功すると、呼び出しがそのオーバーロードに解決されます。</span><span class="sxs-lookup"><span data-stu-id="04a41-169">If it succeeds, it resolves the call to that overload.</span></span> <span data-ttu-id="04a41-170">すべてのオーバーロードが排除された場合や、対象となるオーバーロードを 1 つの候補に絞り込むことができない場合は、エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="04a41-170">If it eliminates all the overloads, or if it cannot reduce the eligible overloads to a single candidate, it generates an error.</span></span>

<span data-ttu-id="04a41-171">次の例は、オーバーロード解決プロセスを示しています。</span><span class="sxs-lookup"><span data-stu-id="04a41-171">The following example illustrates the overload resolution process:</span></span>

[!code-vb[VbVbcnProcedures#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#62)]

[!code-vb[VbVbcnProcedures#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#63)]
  
<span data-ttu-id="04a41-172">最初の呼び出しでは、最初の引数の型 (`Short`) が対応するパラメーターの型 (`Byte`) に縮小変換されるため、コンパイラは最初のオーバーロードを排除します。</span><span class="sxs-lookup"><span data-stu-id="04a41-172">In the first call, the compiler eliminates the first overload because the type of the first argument (`Short`) narrows to the type of the corresponding parameter (`Byte`).</span></span> <span data-ttu-id="04a41-173">次に、2 番目のオーバーロードの各引数の型 (`Short` と `Single`) は、3 番目のオーバーロードの対応する型 (`Integer` と `Single`) に拡大変換されるため、3 番目のオーバーロードが排除されます。</span><span class="sxs-lookup"><span data-stu-id="04a41-173">It then eliminates the third overload because each argument type in the second overload (`Short` and `Single`) widens to the corresponding type in the third overload (`Integer` and `Single`).</span></span> <span data-ttu-id="04a41-174">2 番目のオーバーロードは必要な拡大変換が少ないため、コンパイラはこれを呼び出しに使用します。</span><span class="sxs-lookup"><span data-stu-id="04a41-174">The second overload requires less widening, so the compiler uses it for the call.</span></span>

<span data-ttu-id="04a41-175">2 番目の呼び出しでは、コンパイラは縮小変換に基づいてオーバーロードのいずれかを排除することができません。</span><span class="sxs-lookup"><span data-stu-id="04a41-175">In the second call, the compiler cannot eliminate any of the overloads on the basis of narrowing.</span></span> <span data-ttu-id="04a41-176">最初の呼び出しと同じ理由で、3 番目のオーバーロードが排除されます。引数の型の拡大変換が少ない 2 番目のオーバーロードを呼び出すことができるためです。</span><span class="sxs-lookup"><span data-stu-id="04a41-176">It eliminates the third overload for the same reason as in the first call, because it can call the second overload with less widening of the argument types.</span></span> <span data-ttu-id="04a41-177">ただし、コンパイラは最初と 2 番目のオーバーロード間で解決することはできません。</span><span class="sxs-lookup"><span data-stu-id="04a41-177">However, the compiler cannot resolve between the first and second overloads.</span></span> <span data-ttu-id="04a41-178">それぞれ、もう一方の対応する型に拡大変換されるパラメーターの型が定義されています (`Byte` から `Short`、`Single` から `Double`)。</span><span class="sxs-lookup"><span data-stu-id="04a41-178">Each has one defined parameter type that widens to the corresponding type in the other (`Byte` to `Short`, but `Single` to `Double`).</span></span> <span data-ttu-id="04a41-179">そのため、コンパイラはオーバーロード解決エラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="04a41-179">The compiler therefore generates an overload resolution error.</span></span>

<span data-ttu-id="04a41-180">**正しい方法:** あいまいさを伴わずに、オーバーロードされたプロシージャを呼び出すことができるようにするには、[CType 関数](../../../language-reference/functions/ctype-function.md)を使用して、引数のデータ型をパラメーターの型と一致させます。</span><span class="sxs-lookup"><span data-stu-id="04a41-180">**Correct approach:** To be able to call an overloaded procedure without ambiguity, use [CType Function](../../../language-reference/functions/ctype-function.md) to match the argument data types to the parameter types.</span></span> <span data-ttu-id="04a41-181">次の例は、2 番目のオーバーロードへの解決を強制する `z` の呼び出しを示しています。</span><span class="sxs-lookup"><span data-stu-id="04a41-181">The following example shows a call to `z` that forces resolution to the second overload.</span></span>

[!code-vb[VbVbcnProcedures#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#65)]

### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a><span data-ttu-id="04a41-182">Optional および ParamArray 引数によるオーバーロードの解決</span><span class="sxs-lookup"><span data-stu-id="04a41-182">Overload resolution with Optional and ParamArray arguments</span></span>

<span data-ttu-id="04a41-183">最後のパラメーターが一方では [Optional](../../../language-reference/modifiers/optional.md)、もう一方では [ParamArray](../../../language-reference/modifiers/paramarray.md) として宣言されている点を除き、プロシージャの 2 つのオーバーロードが同じシグネチャを持つ場合、コンパイラは最も一致するものに従って、そのプロシージャの呼び出しを解決します。</span><span class="sxs-lookup"><span data-stu-id="04a41-183">If two overloads of a procedure have identical signatures except that the last parameter is declared [Optional](../../../language-reference/modifiers/optional.md) in one and [ParamArray](../../../language-reference/modifiers/paramarray.md) in the other, the compiler resolves a call to that procedure according to the closest match.</span></span> <span data-ttu-id="04a41-184">詳細については、「 [Overload Resolution](./overload-resolution.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04a41-184">For more information, see [Overload Resolution](./overload-resolution.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="04a41-185">関連項目</span><span class="sxs-lookup"><span data-stu-id="04a41-185">See also</span></span>

- [<span data-ttu-id="04a41-186">手順</span><span class="sxs-lookup"><span data-stu-id="04a41-186">Procedures</span></span>](index.md)
- [<span data-ttu-id="04a41-187">Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="04a41-187">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="04a41-188">Function プロシージャ</span><span class="sxs-lookup"><span data-stu-id="04a41-188">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="04a41-189">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="04a41-189">Property Procedures</span></span>](property-procedures.md)
- [<span data-ttu-id="04a41-190">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="04a41-190">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="04a41-191">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="04a41-191">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="04a41-192">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="04a41-192">Procedure Overloading</span></span>](procedure-overloading.md)
- [<span data-ttu-id="04a41-193">プロシージャのオーバーロードに関する注意事項</span><span class="sxs-lookup"><span data-stu-id="04a41-193">Considerations in Overloading Procedures</span></span>](considerations-in-overloading-procedures.md)
- [<span data-ttu-id="04a41-194">オーバーロードの解決</span><span class="sxs-lookup"><span data-stu-id="04a41-194">Overload Resolution</span></span>](overload-resolution.md)
