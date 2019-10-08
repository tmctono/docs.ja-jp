---
title: トラブルシューティング手順 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting Visual Basic, procedures
- procedures [Visual Basic], troubleshooting
- Visual Basic code, procedures
- troubleshooting procedures
- procedures [Visual Basic], about procedures
ms.assetid: 525721e8-2e02-4f75-b5d8-6b893462cf2b
ms.openlocfilehash: c74947e21de8ba26ffde01f6f28aea67346c2071
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002077"
---
# <a name="troubleshooting-procedures-visual-basic"></a><span data-ttu-id="a6f19-102">トラブルシューティング手順 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6f19-102">Troubleshooting procedures (Visual Basic)</span></span>

<span data-ttu-id="a6f19-103">このページでは、プロシージャの使用時に発生する可能性がある一般的な問題をいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="a6f19-103">This page lists some common problems that can occur when working with procedures.</span></span>  
  
## <a name="returning-an-array-type-from-a-function-procedure"></a><span data-ttu-id="a6f19-104">関数プロシージャから配列型を返す</span><span class="sxs-lookup"><span data-stu-id="a6f19-104">Returning an array type from a function procedure</span></span>

<span data-ttu-id="a6f19-105">@No__t 0 のプロシージャが配列のデータ型を返す場合、`Function` の名前を使用して配列の要素に値を格納することはできません。</span><span class="sxs-lookup"><span data-stu-id="a6f19-105">If a `Function` procedure returns an array data type, you cannot use the `Function` name to store values in the elements of the array.</span></span> <span data-ttu-id="a6f19-106">これを実行しようとすると、コンパイラは `Function` の呼び出しとして解釈します。</span><span class="sxs-lookup"><span data-stu-id="a6f19-106">If you attempt to do this, the compiler interprets it as a call to the `Function`.</span></span> <span data-ttu-id="a6f19-107">次の例では、コンパイラエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="a6f19-107">The following example generates compiler errors:</span></span>
  
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

<span data-ttu-id="a6f19-108">ステートメント `AllOnes(i) = 1` は、間違ったデータ型 (`Integer` 配列ではなくスカラー `Integer`) の引数を指定して `AllOnes` を呼び出すと表示されるため、コンパイラエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="a6f19-108">The statement `AllOnes(i) = 1` generates a compiler error because it appears to call `AllOnes` with an argument of the wrong data type (a scalar `Integer` instead of an `Integer` array).</span></span> <span data-ttu-id="a6f19-109">ステートメント `Return AllOnes()` は、引数を指定せずに `AllOnes` を呼び出すように見えるため、コンパイラエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="a6f19-109">The statement `Return AllOnes()` generates a compiler error because it appears to call `AllOnes` with no argument.</span></span>  
  
 <span data-ttu-id="a6f19-110">**正しい方法:** 返される配列の要素を変更できるようにするには、内部配列をローカル変数として定義します。</span><span class="sxs-lookup"><span data-stu-id="a6f19-110">**Correct approach:** To be able to modify the elements of an array that is to be returned, define an internal array as a local variable.</span></span> <span data-ttu-id="a6f19-111">次の例では、エラーなしでコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="a6f19-111">The following example compiles without error:</span></span>

 [!code-vb[VbVbcnProcedures#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#66)]

## <a name="argument-not-modified-by-procedure-call"></a><span data-ttu-id="a6f19-112">引数がプロシージャ呼び出しによって変更されていません</span><span class="sxs-lookup"><span data-stu-id="a6f19-112">Argument not modified by procedure call</span></span>

<span data-ttu-id="a6f19-113">プロシージャが、呼び出し元のコードの引数の基になるプログラミング要素を変更できるようにする場合は、参照渡しで渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6f19-113">If you intend to allow a procedure to change a programming element underlying an argument in the calling code, you must pass it by reference.</span></span> <span data-ttu-id="a6f19-114">ただし、プロシージャは、値によって渡された場合でも、参照型引数の要素にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a6f19-114">But a procedure can access the elements of a reference type argument even if you pass it by value.</span></span>

- <span data-ttu-id="a6f19-115">**基になる変数**。</span><span class="sxs-lookup"><span data-stu-id="a6f19-115">**Underlying variable**.</span></span> <span data-ttu-id="a6f19-116">プロシージャが基になる変数の要素自体の値を置き換えることができるようにするには、プロシージャで[ByRef](../../../language-reference/modifiers/byref.md)パラメーターを宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6f19-116">To allow the procedure to replace the value of the underlying variable element itself, the procedure must declare the parameter [ByRef](../../../language-reference/modifiers/byref.md).</span></span> <span data-ttu-id="a6f19-117">また、呼び出し元のコードでは、引数をかっこで囲む必要はありません。これは @no__t 0 渡しの機構をオーバーライドするためです。</span><span class="sxs-lookup"><span data-stu-id="a6f19-117">Also, the calling code must not enclose the argument in parentheses, because that would override the `ByRef` passing mechanism.</span></span>

- <span data-ttu-id="a6f19-118">**参照型の要素**。</span><span class="sxs-lookup"><span data-stu-id="a6f19-118">**Reference type elements**.</span></span> <span data-ttu-id="a6f19-119">パラメーター [ByVal](../../../language-reference/modifiers/byval.md)を宣言する場合、プロシージャは、基になる変数要素自体を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="a6f19-119">If you declare a parameter [ByVal](../../../language-reference/modifiers/byval.md), the procedure cannot modify the underlying variable element itself.</span></span> <span data-ttu-id="a6f19-120">ただし、引数が参照型の場合、プロシージャは、変数の値を置き換えることができなくても、その参照先のオブジェクトのメンバーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="a6f19-120">However, if the argument is a reference type, the procedure can modify the members of the object to which it points, even though it cannot replace the variable's value.</span></span> <span data-ttu-id="a6f19-121">たとえば、引数が配列変数の場合、プロシージャは新しい配列を割り当てることはできませんが、1つ以上の要素を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="a6f19-121">For example, if the argument is an array variable, the procedure cannot assign a new array to it, but it can change one or more of its elements.</span></span> <span data-ttu-id="a6f19-122">変更された要素は、呼び出し元のコード内の基になる配列変数に反映されます。</span><span class="sxs-lookup"><span data-stu-id="a6f19-122">The changed elements are reflected in the underlying array variable in the calling code.</span></span>

<span data-ttu-id="a6f19-123">次の例では、値によって配列変数を受け取り、その要素を操作する2つのプロシージャを定義します。</span><span class="sxs-lookup"><span data-stu-id="a6f19-123">The following example defines two procedures that take an array variable by value and operate on its elements.</span></span> <span data-ttu-id="a6f19-124">プロシージャ `increase` は、各要素に1つずつ追加します。</span><span class="sxs-lookup"><span data-stu-id="a6f19-124">Procedure `increase` simply adds one to each element.</span></span> <span data-ttu-id="a6f19-125">手順 `replace` @no__t 新しい配列をパラメーターに割り当ててから、各要素に1を追加します。</span><span class="sxs-lookup"><span data-stu-id="a6f19-125">Procedure `replace` assigns a new array to the parameter `a()` and then adds one to each element.</span></span> <span data-ttu-id="a6f19-126">ただし、再割り当ては、`a()` が `ByVal` と宣言されているため、呼び出し元のコード内の基になる配列変数には影響しません。</span><span class="sxs-lookup"><span data-stu-id="a6f19-126">However, the reassignment does not affect the underlying array variable in the calling code because `a()` is declared `ByVal`.</span></span>

[!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]

[!code-vb[VbVbcnProcedures#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#38)]

<span data-ttu-id="a6f19-127">次の例では、`increase` および `replace` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a6f19-127">The following example makes calls to `increase` and `replace`:</span></span>

[!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]
  
<span data-ttu-id="a6f19-128">最初の `MsgBox` 呼び出しでは、"増加後 (n)" が表示されます。11、21、31、41 "。</span><span class="sxs-lookup"><span data-stu-id="a6f19-128">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="a6f19-129">@No__t-0 は参照型であるため、`increase` は `ByVal` で渡される場合でも、メンバーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="a6f19-129">Because `n` is a reference type, `increase` can change its members, even though it is passed `ByVal`.</span></span>

<span data-ttu-id="a6f19-130">2番目の `MsgBox` 呼び出しは、"置換後 (n):11、21、31、41 "。</span><span class="sxs-lookup"><span data-stu-id="a6f19-130">The second `MsgBox` call displays "After replace(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="a6f19-131">@No__t-0 が-1 @no__t 渡されるため、`replace` では、新しい配列を割り当てることによって変数 `n` を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="a6f19-131">Because `n` is passed `ByVal`, `replace` cannot modify the variable `n` by assigning a new array to it.</span></span> <span data-ttu-id="a6f19-132">@No__t-0 @no__t 新しい配列インスタンスを作成して、それをローカル変数 `a` に割り当てると、呼び出し元のコードによって渡された `n` への参照が失われます。</span><span class="sxs-lookup"><span data-stu-id="a6f19-132">When `replace` creates the new array instance `k` and assigns it to the local variable `a`, it loses the reference to `n` passed in by the calling code.</span></span> <span data-ttu-id="a6f19-133">@No__t-0 のメンバーをインクリメントすると、ローカル配列 `k` のみが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="a6f19-133">When it increments the members of `a`, only the local array `k` is affected.</span></span>

<span data-ttu-id="a6f19-134">**正しい方法:** 基になる変数要素自体を変更できるようにするには、参照渡しで渡します。</span><span class="sxs-lookup"><span data-stu-id="a6f19-134">**Correct approach:** To be able to modify an underlying variable element itself, pass it by reference.</span></span> <span data-ttu-id="a6f19-135">次の例では、呼び出し元のコードで配列を別の配列に置き換えることができるようにする `replace` の宣言の変更を示しています。</span><span class="sxs-lookup"><span data-stu-id="a6f19-135">The following example shows the change in the declaration of `replace` that allows it to replace one array with another in the calling code:</span></span>

[!code-vb[VbVbcnProcedures#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#64)]

## <a name="unable-to-define-an-overload"></a><span data-ttu-id="a6f19-136">オーバーロードを定義できません</span><span class="sxs-lookup"><span data-stu-id="a6f19-136">Unable to define an overload</span></span>

<span data-ttu-id="a6f19-137">オーバーロードされたバージョンのプロシージャを定義する場合は、同じ名前で、別のシグネチャを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6f19-137">If you want to define an overloaded version of a procedure, you must use the same name but a different signature.</span></span> <span data-ttu-id="a6f19-138">コンパイラが同じシグネチャを持つオーバーロードから宣言を区別できない場合は、エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="a6f19-138">If the compiler cannot differentiate your declaration from an overload with the same signature, it generates an error.</span></span>

<span data-ttu-id="a6f19-139">プロシージャの*シグネチャ*は、プロシージャ名とパラメーターリストによって決まります。</span><span class="sxs-lookup"><span data-stu-id="a6f19-139">The *signature* of a procedure is determined by the procedure name and the parameter list.</span></span> <span data-ttu-id="a6f19-140">各オーバーロードは、他のすべてのオーバーロードと同じ名前を持つ必要がありますが、シグネチャの他のコンポーネントの少なくとも1つでは、それらのすべてが異なる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6f19-140">Each overload must have the same name as all the other overloads but must differ from all of them in at least one of the other components of the signature.</span></span> <span data-ttu-id="a6f19-141">詳細については、「 [Procedure Overloading](./procedure-overloading.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6f19-141">For more information, see [Procedure Overloading](./procedure-overloading.md).</span></span>

<span data-ttu-id="a6f19-142">次の項目は、パラメーターリストに関連する場合でも、プロシージャのシグネチャのコンポーネントではありません。</span><span class="sxs-lookup"><span data-stu-id="a6f19-142">The following items, even though they pertain to the parameter list, are not components of a procedure's signature:</span></span>

- <span data-ttu-id="a6f19-143">プロシージャ修飾子キーワード (`Public`、`Shared`、`Static` など)。</span><span class="sxs-lookup"><span data-stu-id="a6f19-143">Procedure modifier keywords, such as `Public`, `Shared`, and `Static`.</span></span>
- <span data-ttu-id="a6f19-144">パラメーター名。</span><span class="sxs-lookup"><span data-stu-id="a6f19-144">Parameter names.</span></span>
- <span data-ttu-id="a6f19-145">パラメーター修飾子キーワード (`ByRef` や `Optional` など)。</span><span class="sxs-lookup"><span data-stu-id="a6f19-145">Parameter modifier keywords, such as `ByRef` and `Optional`.</span></span>
- <span data-ttu-id="a6f19-146">戻り値のデータ型 (変換演算子を除く)。</span><span class="sxs-lookup"><span data-stu-id="a6f19-146">The data type of the return value (except for a conversion operator).</span></span>

<span data-ttu-id="a6f19-147">前の項目のうち1つ以上を変更してプロシージャをオーバーロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a6f19-147">You cannot overload a procedure by varying only one or more of the preceding items.</span></span>

<span data-ttu-id="a6f19-148">**正しい方法:** プロシージャオーバーロードを定義できるようにするには、シグネチャを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6f19-148">**Correct approach:** To be able to define a procedure overload, you must vary the signature.</span></span> <span data-ttu-id="a6f19-149">同じ名前を使用する必要があるため、パラメーターの数、順序、またはデータ型を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6f19-149">Because you must use the same name, you must vary the number, order, or data types of the parameters.</span></span> <span data-ttu-id="a6f19-150">ジェネリックプロシージャでは、型パラメーターの数を変更できます。</span><span class="sxs-lookup"><span data-stu-id="a6f19-150">In a generic procedure, you can vary the number of type parameters.</span></span> <span data-ttu-id="a6f19-151">変換演算子 ([CType 関数](../../../language-reference/functions/ctype-function.md)) では、戻り値の型を変更できます。</span><span class="sxs-lookup"><span data-stu-id="a6f19-151">In a conversion operator ([CType Function](../../../language-reference/functions/ctype-function.md)), you can vary the return type.</span></span>

### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a><span data-ttu-id="a6f19-152">省略可能な引数と ParamArray 引数を使用したオーバーロードの解決</span><span class="sxs-lookup"><span data-stu-id="a6f19-152">Overload resolution with Optional and ParamArray arguments</span></span>

<span data-ttu-id="a6f19-153">1つ以上の[省略可能](../../../language-reference/modifiers/optional.md)なパラメーターまたは[ParamArray](../../../language-reference/modifiers/paramarray.md)パラメーターを使用してプロシージャをオーバーロードする場合は、*暗黙的なオーバーロード*の複製を避ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6f19-153">If you are overloading a procedure with one or more [Optional](../../../language-reference/modifiers/optional.md) parameters or a [ParamArray](../../../language-reference/modifiers/paramarray.md) parameter, you must avoid duplicating any of the *implicit overloads*.</span></span> <span data-ttu-id="a6f19-154">詳細については、「[プロシージャのオーバーロードに関する考慮事項](./considerations-in-overloading-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6f19-154">For information, see [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>

## <a name="calling-the-wrong-version-of-an-overloaded-procedure"></a><span data-ttu-id="a6f19-155">オーバーロードされたプロシージャの間違ったバージョンの呼び出し</span><span class="sxs-lookup"><span data-stu-id="a6f19-155">Calling the wrong version of an overloaded procedure</span></span>

<span data-ttu-id="a6f19-156">プロシージャに複数のオーバーロードされたバージョンがある場合は、すべてのパラメーターリストを理解し、Visual Basic がオーバーロード間の呼び出しを解決する方法を理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6f19-156">If a procedure has several overloaded versions, you should be familiar with all their parameter lists and understand how Visual Basic resolves calls among the overloads.</span></span> <span data-ttu-id="a6f19-157">それ以外の場合は、意図したもの以外のオーバーロードを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="a6f19-157">Otherwise you could call an overload other than the intended one.</span></span>

<span data-ttu-id="a6f19-158">呼び出すオーバーロードを決定したら、次の規則に注意してください。</span><span class="sxs-lookup"><span data-stu-id="a6f19-158">When you have determined which overload you want to call, be careful to observe the following rules:</span></span>

- <span data-ttu-id="a6f19-159">正しい数の引数を正しい順序で指定してください。</span><span class="sxs-lookup"><span data-stu-id="a6f19-159">Supply the correct number of arguments, and in the correct order.</span></span>  
- <span data-ttu-id="a6f19-160">理想的には、引数は、対応するパラメーターとまったく同じデータ型を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6f19-160">Ideally, your arguments should have the exact same data types as the corresponding parameters.</span></span> <span data-ttu-id="a6f19-161">いずれの場合も、各引数のデータ型は、対応するパラメーターのデータ型に拡大変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6f19-161">In any case, the data type of each argument must widen to that of its corresponding parameter.</span></span> <span data-ttu-id="a6f19-162">これは、 [Option Strict ステートメント](../../../language-reference/statements/option-strict-statement.md)が `Off` に設定されている場合でも同様です。</span><span class="sxs-lookup"><span data-stu-id="a6f19-162">This is true even with the [Option Strict Statement](../../../language-reference/statements/option-strict-statement.md) set to `Off`.</span></span> <span data-ttu-id="a6f19-163">オーバーロードに引数リストからの縮小変換が必要な場合、そのオーバーロードは呼び出される対象ではありません。</span><span class="sxs-lookup"><span data-stu-id="a6f19-163">If an overload requires any narrowing conversion from your argument list, that overload is not eligible to be called.</span></span>
- <span data-ttu-id="a6f19-164">拡張を必要とする引数を指定する場合は、対応するパラメーターのデータ型にできるだけ近いデータ型を指定してください。</span><span class="sxs-lookup"><span data-stu-id="a6f19-164">If you supply arguments that require widening, make their data types as close as possible to the corresponding parameter data types.</span></span> <span data-ttu-id="a6f19-165">引数のデータ型を受け入れるオーバーロードが2つ以上ある場合、コンパイラは、より少ない拡大率でを呼び出すオーバーロードの呼び出しを解決します。</span><span class="sxs-lookup"><span data-stu-id="a6f19-165">If two or more overloads accept your argument data types, the compiler resolves your call to the overload that calls for the least amount of widening.</span></span>

<span data-ttu-id="a6f19-166">引数を準備するときに[CType 関数](../../../language-reference/functions/ctype-function.md)変換キーワードを使用すると、データ型の不一致の可能性を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="a6f19-166">You can reduce the chance of data type mismatches by using the [CType Function](../../../language-reference/functions/ctype-function.md) conversion keyword when preparing your arguments.</span></span>

### <a name="overload-resolution-failure"></a><span data-ttu-id="a6f19-167">オーバーロードの解決エラー</span><span class="sxs-lookup"><span data-stu-id="a6f19-167">Overload resolution failure</span></span>

<span data-ttu-id="a6f19-168">オーバーロードされたプロシージャを呼び出すと、コンパイラはオーバーロードの1つを除くすべてを削除しようとします。</span><span class="sxs-lookup"><span data-stu-id="a6f19-168">When you call an overloaded procedure, the compiler attempts to eliminate all but one of the overloads.</span></span> <span data-ttu-id="a6f19-169">成功した場合は、そのオーバーロードの呼び出しを解決します。</span><span class="sxs-lookup"><span data-stu-id="a6f19-169">If it succeeds, it resolves the call to that overload.</span></span> <span data-ttu-id="a6f19-170">すべてのオーバーロードを除外する場合、または対象となるオーバーロードを1つの候補に減らすことができない場合は、エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="a6f19-170">If it eliminates all the overloads, or if it cannot reduce the eligible overloads to a single candidate, it generates an error.</span></span>

<span data-ttu-id="a6f19-171">次の例は、オーバーロードの解決プロセスを示しています。</span><span class="sxs-lookup"><span data-stu-id="a6f19-171">The following example illustrates the overload resolution process:</span></span>

[!code-vb[VbVbcnProcedures#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#62)]

[!code-vb[VbVbcnProcedures#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#63)]
  
<span data-ttu-id="a6f19-172">最初の呼び出しでは、最初の引数の型 (`Short`) が対応するパラメーター (`Byte`) の型に限定されるため、コンパイラは最初のオーバーロードを削除します。</span><span class="sxs-lookup"><span data-stu-id="a6f19-172">In the first call, the compiler eliminates the first overload because the type of the first argument (`Short`) narrows to the type of the corresponding parameter (`Byte`).</span></span> <span data-ttu-id="a6f19-173">次に3番目のオーバーロードを削除します。これは、2番目のオーバーロード (`Short` および `Single`) の各引数の型が、3番目のオーバーロード (`Integer` および `Single`) の対応する型に拡大変換されるためです。</span><span class="sxs-lookup"><span data-stu-id="a6f19-173">It then eliminates the third overload because each argument type in the second overload (`Short` and `Single`) widens to the corresponding type in the third overload (`Integer` and `Single`).</span></span> <span data-ttu-id="a6f19-174">2番目のオーバーロードでは、より少ない拡大が必要になるため、コンパイラはこれを呼び出しに使用します。</span><span class="sxs-lookup"><span data-stu-id="a6f19-174">The second overload requires less widening, so the compiler uses it for the call.</span></span>

<span data-ttu-id="a6f19-175">2番目の呼び出しでは、コンパイラは、縮小に基づいてオーバーロードのいずれかを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="a6f19-175">In the second call, the compiler cannot eliminate any of the overloads on the basis of narrowing.</span></span> <span data-ttu-id="a6f19-176">最初の呼び出しの場合と同じ理由で3番目のオーバーロードを削除します。これは、引数の型をより拡大して、2番目のオーバーロードを呼び出すことができるためです。</span><span class="sxs-lookup"><span data-stu-id="a6f19-176">It eliminates the third overload for the same reason as in the first call, because it can call the second overload with less widening of the argument types.</span></span> <span data-ttu-id="a6f19-177">ただし、コンパイラは1番目と2番目のオーバーロード間で解決できません。</span><span class="sxs-lookup"><span data-stu-id="a6f19-177">However, the compiler cannot resolve between the first and second overloads.</span></span> <span data-ttu-id="a6f19-178">各には、もう一方の型に拡大変換する定義済みのパラメーター型が1つあります (`Byte` ~ `Short`、`Single` から `Double`)。</span><span class="sxs-lookup"><span data-stu-id="a6f19-178">Each has one defined parameter type that widens to the corresponding type in the other (`Byte` to `Short`, but `Single` to `Double`).</span></span> <span data-ttu-id="a6f19-179">そのため、コンパイラはオーバーロードの解決エラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="a6f19-179">The compiler therefore generates an overload resolution error.</span></span>

<span data-ttu-id="a6f19-180">**正しい方法:** オーバーロードされたプロシージャをあいまいで呼び出すことができるようにするには、 [CType 関数](../../../language-reference/functions/ctype-function.md)を使用して、引数のデータ型をパラメーターの型と照合します。</span><span class="sxs-lookup"><span data-stu-id="a6f19-180">**Correct approach:** To be able to call an overloaded procedure without ambiguity, use [CType Function](../../../language-reference/functions/ctype-function.md) to match the argument data types to the parameter types.</span></span> <span data-ttu-id="a6f19-181">次の例は、2番目のオーバーロードを強制的に解決する `z` の呼び出しを示しています。</span><span class="sxs-lookup"><span data-stu-id="a6f19-181">The following example shows a call to `z` that forces resolution to the second overload.</span></span>

[!code-vb[VbVbcnProcedures#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#65)]

### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a><span data-ttu-id="a6f19-182">省略可能な引数と ParamArray 引数を使用したオーバーロードの解決</span><span class="sxs-lookup"><span data-stu-id="a6f19-182">Overload resolution with Optional and ParamArray arguments</span></span>

<span data-ttu-id="a6f19-183">1つのプロシージャの2つのオーバーロードが同じシグネチャを持つ場合、最後のパラメーターは[省略可能](../../../language-reference/modifiers/optional.md)として宣言され、もう一方では[ParamArray](../../../language-reference/modifiers/paramarray.md)が適用されます。ただし、コンパイラは、最も近い一致に従って、そのプロシージャの呼び出しを解決します。</span><span class="sxs-lookup"><span data-stu-id="a6f19-183">If two overloads of a procedure have identical signatures except that the last parameter is declared [Optional](../../../language-reference/modifiers/optional.md) in one and [ParamArray](../../../language-reference/modifiers/paramarray.md) in the other, the compiler resolves a call to that procedure according to the closest match.</span></span> <span data-ttu-id="a6f19-184">詳細については、「 [Overload Resolution](./overload-resolution.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6f19-184">For more information, see [Overload Resolution](./overload-resolution.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a6f19-185">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6f19-185">See also</span></span>

- [<span data-ttu-id="a6f19-186">手順</span><span class="sxs-lookup"><span data-stu-id="a6f19-186">Procedures</span></span>](index.md)
- [<span data-ttu-id="a6f19-187">Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="a6f19-187">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="a6f19-188">Function プロシージャ</span><span class="sxs-lookup"><span data-stu-id="a6f19-188">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="a6f19-189">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="a6f19-189">Property Procedures</span></span>](property-procedures.md)
- [<span data-ttu-id="a6f19-190">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="a6f19-190">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="a6f19-191">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="a6f19-191">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="a6f19-192">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="a6f19-192">Procedure Overloading</span></span>](procedure-overloading.md)
- [<span data-ttu-id="a6f19-193">プロシージャのオーバーロードに関する注意事項</span><span class="sxs-lookup"><span data-stu-id="a6f19-193">Considerations in Overloading Procedures</span></span>](considerations-in-overloading-procedures.md)
- [<span data-ttu-id="a6f19-194">オーバーロードの解決</span><span class="sxs-lookup"><span data-stu-id="a6f19-194">Overload Resolution</span></span>](overload-resolution.md)
