---
title: Const ステートメント (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Const
helpviewer_keywords:
- Const statement [Visual Basic]
ms.assetid: 495b318d-b7c5-4198-94f8-0790a541b07a
ms.openlocfilehash: 522ac71767707ae90a3f1d11d45ef8b29471ae6c
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005116"
---
# <a name="const-statement-visual-basic"></a><span data-ttu-id="11c15-102">Const ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="11c15-102">Const Statement (Visual Basic)</span></span>
<span data-ttu-id="11c15-103">1つ以上の定数を宣言して定義します。</span><span class="sxs-lookup"><span data-stu-id="11c15-103">Declares and defines one or more constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11c15-104">構文</span><span class="sxs-lookup"><span data-stu-id="11c15-104">Syntax</span></span>  
  
```vb  
[ <attributelist> ] [ accessmodifier ] [ Shadows ]   
Const constantlist  
```  
  
## <a name="parts"></a><span data-ttu-id="11c15-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="11c15-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="11c15-106">任意。</span><span class="sxs-lookup"><span data-stu-id="11c15-106">Optional.</span></span> <span data-ttu-id="11c15-107">このステートメントで宣言されているすべての定数に適用される属性のリスト。</span><span class="sxs-lookup"><span data-stu-id="11c15-107">List of attributes that apply to all the constants declared in this statement.</span></span> <span data-ttu-id="11c15-108">山かっこ ("`<`" と "@no__t") の[属性リスト](../../../visual-basic/language-reference/statements/attribute-list.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11c15-108">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="11c15-109">任意。</span><span class="sxs-lookup"><span data-stu-id="11c15-109">Optional.</span></span> <span data-ttu-id="11c15-110">これらの定数にアクセスできるコードを指定するには、これを使用します。</span><span class="sxs-lookup"><span data-stu-id="11c15-110">Use this to specify what code can access these constants.</span></span> <span data-ttu-id="11c15-111">[Public](../../../visual-basic/language-reference/modifiers/public.md)、 [protected](../../../visual-basic/language-reference/modifiers/protected.md)、 [friend](../../../visual-basic/language-reference/modifiers/friend.md)、 [Protected Friend](../modifiers/protected-friend.md)、 [private](../../../visual-basic/language-reference/modifiers/private.md)、または[private](../../language-reference/modifiers/private-protected.md)を指定できます。</span><span class="sxs-lookup"><span data-stu-id="11c15-111">Can be [Public](../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), [Protected Friend](../modifiers/protected-friend.md), [Private](../../../visual-basic/language-reference/modifiers/private.md), or [Private Protected](../../language-reference/modifiers/private-protected.md).</span></span>
  
 `Shadows`  
 <span data-ttu-id="11c15-112">任意。</span><span class="sxs-lookup"><span data-stu-id="11c15-112">Optional.</span></span> <span data-ttu-id="11c15-113">基底クラスのプログラミング要素を再宣言および非表示にするには、これを使用します。</span><span class="sxs-lookup"><span data-stu-id="11c15-113">Use this to redeclare and hide a programming element in a base class.</span></span> <span data-ttu-id="11c15-114">「[シャドウ](../../../visual-basic/language-reference/modifiers/shadows.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11c15-114">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
 `constantlist`  
 <span data-ttu-id="11c15-115">必須。</span><span class="sxs-lookup"><span data-stu-id="11c15-115">Required.</span></span> <span data-ttu-id="11c15-116">このステートメントで宣言されている定数の一覧。</span><span class="sxs-lookup"><span data-stu-id="11c15-116">List of constants being declared in this statement.</span></span>  
  
 <span data-ttu-id="11c15-117">`constant` `[ ,` `constant` `... ]`</span><span class="sxs-lookup"><span data-stu-id="11c15-117">`constant` `[ ,` `constant` `... ]`</span></span>  
  
 <span data-ttu-id="11c15-118">`constant` の構文と指定項目は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="11c15-118">Each `constant` has the following syntax and parts:</span></span>  
  
 <span data-ttu-id="11c15-119">`constantname` `[ As` `datatype` `] =` `initializer`</span><span class="sxs-lookup"><span data-stu-id="11c15-119">`constantname` `[ As` `datatype` `] =` `initializer`</span></span>  
  
|<span data-ttu-id="11c15-120">要素</span><span class="sxs-lookup"><span data-stu-id="11c15-120">Part</span></span>|<span data-ttu-id="11c15-121">説明</span><span class="sxs-lookup"><span data-stu-id="11c15-121">Description</span></span>|  
|----------|-----------------|  
|`constantname`|<span data-ttu-id="11c15-122">必須。</span><span class="sxs-lookup"><span data-stu-id="11c15-122">Required.</span></span> <span data-ttu-id="11c15-123">定数の名前。</span><span class="sxs-lookup"><span data-stu-id="11c15-123">Name of the constant.</span></span> <span data-ttu-id="11c15-124">「 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11c15-124">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`datatype`|<span data-ttu-id="11c15-125">@No__t-0 が `On` の場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="11c15-125">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="11c15-126">定数のデータ型。</span><span class="sxs-lookup"><span data-stu-id="11c15-126">Data type of the constant.</span></span>|  
|`initializer`|<span data-ttu-id="11c15-127">必須。</span><span class="sxs-lookup"><span data-stu-id="11c15-127">Required.</span></span> <span data-ttu-id="11c15-128">コンパイル時に評価され、定数に割り当てられる式。</span><span class="sxs-lookup"><span data-stu-id="11c15-128">Expression that is evaluated at compile time and assigned to the constant.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11c15-129">コメント</span><span class="sxs-lookup"><span data-stu-id="11c15-129">Remarks</span></span>  
 <span data-ttu-id="11c15-130">アプリケーションで変更されない値がある場合は、名前付き定数を定義し、リテラル値の代わりに使用することができます。</span><span class="sxs-lookup"><span data-stu-id="11c15-130">If you have a value that never changes in your application, you can define a named constant and use it in place of a literal value.</span></span> <span data-ttu-id="11c15-131">名前は、値よりも覚えやすくなります。</span><span class="sxs-lookup"><span data-stu-id="11c15-131">A name is easier to remember than a value.</span></span> <span data-ttu-id="11c15-132">定数は一度だけ定義し、コード内の多くの場所で使用できます。</span><span class="sxs-lookup"><span data-stu-id="11c15-132">You can define the constant just once and use it in many places in your code.</span></span> <span data-ttu-id="11c15-133">後のバージョンで値を再定義する必要がある場合は、`Const` ステートメントだけを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11c15-133">If in a later version you need to redefine the value, the `Const` statement is the only place you need to make a change.</span></span>  
  
 <span data-ttu-id="11c15-134">@No__t-0 は、モジュールレベルまたはプロシージャレベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="11c15-134">You can use `Const` only at module or procedure level.</span></span> <span data-ttu-id="11c15-135">つまり、変数の*宣言コンテキスト*はクラス、構造体、モジュール、プロシージャ、またはブロックである必要があり、ソースファイル、名前空間、またはインターフェイスにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="11c15-135">This means the *declaration context* for a variable must be a class, structure, module, procedure, or block, and cannot be a source file, namespace, or interface.</span></span> <span data-ttu-id="11c15-136">詳細については、「[宣言コンテキストと既定のアクセス レベル](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11c15-136">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="11c15-137">ローカル定数 (プロシージャ内) は、既定でパブリックアクセスに設定され、アクセス修飾子を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="11c15-137">Local constants (inside a procedure) default to public access, and you cannot use any access modifiers on them.</span></span> <span data-ttu-id="11c15-138">クラスとモジュールのメンバー定数 (プロシージャ以外) では、既定でプライベートアクセスが使用され、構造体メンバー定数は既定でパブリックアクセスになります。</span><span class="sxs-lookup"><span data-stu-id="11c15-138">Class and module member constants (outside any procedure) default to private access, and structure member constants default to public access.</span></span> <span data-ttu-id="11c15-139">アクセス修飾子を使用してこれらのアクセス レベルを調整できます。</span><span class="sxs-lookup"><span data-stu-id="11c15-139">You can adjust their access levels with the access modifiers.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="11c15-140">ルール</span><span class="sxs-lookup"><span data-stu-id="11c15-140">Rules</span></span>  
  
- <span data-ttu-id="11c15-141">**宣言コンテキスト。**</span><span class="sxs-lookup"><span data-stu-id="11c15-141">**Declaration Context.**</span></span> <span data-ttu-id="11c15-142">モジュールレベルで、プロシージャの外部で宣言された定数は、*メンバー定数*です。これは、それを宣言するクラス、構造体、またはモジュールのメンバーです。</span><span class="sxs-lookup"><span data-stu-id="11c15-142">A constant declared at module level, outside any procedure, is a *member constant*; it is a member of the class, structure, or module that declares it.</span></span>  
  
     <span data-ttu-id="11c15-143">プロシージャレベルで宣言された定数は*ローカル定数*です。これは、それを宣言するプロシージャまたはブロックに対してローカルです。</span><span class="sxs-lookup"><span data-stu-id="11c15-143">A constant declared at procedure level is a *local constant*; it is local to the procedure or block that declares it.</span></span>  
  
- <span data-ttu-id="11c15-144">**アトリビュート.**</span><span class="sxs-lookup"><span data-stu-id="11c15-144">**Attributes.**</span></span> <span data-ttu-id="11c15-145">属性は、ローカル定数ではなく、メンバー定数にのみ適用できます。</span><span class="sxs-lookup"><span data-stu-id="11c15-145">You can apply attributes only to member constants, not to local constants.</span></span> <span data-ttu-id="11c15-146">属性は、アセンブリのメタデータに情報を提供します。これは、ローカル定数などの一時的なストレージには意味がありません。</span><span class="sxs-lookup"><span data-stu-id="11c15-146">An attribute contributes information to the assembly's metadata, which is not meaningful for temporary storage such as local constants.</span></span>  
  
- <span data-ttu-id="11c15-147">**ド.**</span><span class="sxs-lookup"><span data-stu-id="11c15-147">**Modifiers.**</span></span> <span data-ttu-id="11c15-148">既定では、すべての定数は `Shared`、`Static`、`ReadOnly` です。</span><span class="sxs-lookup"><span data-stu-id="11c15-148">By default, all constants are `Shared`, `Static`, and `ReadOnly`.</span></span> <span data-ttu-id="11c15-149">定数を宣言するときに、これらのキーワードを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="11c15-149">You cannot use any of these keywords when declaring a constant.</span></span>  
  
     <span data-ttu-id="11c15-150">プロシージャレベルでは、`Shadows` または任意のアクセス修飾子を使用してローカル定数を宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="11c15-150">At procedure level, you cannot use `Shadows` or any access modifiers to declare local constants.</span></span>  
  
- <span data-ttu-id="11c15-151">**複数の定数。**</span><span class="sxs-lookup"><span data-stu-id="11c15-151">**Multiple Constants.**</span></span> <span data-ttu-id="11c15-152">同じ宣言ステートメントで複数の定数を宣言し、それぞれに対して @no__t 0 の部分を指定できます。</span><span class="sxs-lookup"><span data-stu-id="11c15-152">You can declare several constants in the same declaration statement, specifying the `constantname` part for each one.</span></span> <span data-ttu-id="11c15-153">複数の定数は、コンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="11c15-153">Multiple constants are separated by commas.</span></span>  
  
## <a name="data-type-rules"></a><span data-ttu-id="11c15-154">データ型ルール</span><span class="sxs-lookup"><span data-stu-id="11c15-154">Data Type Rules</span></span>  
  
- <span data-ttu-id="11c15-155">**データ型。**</span><span class="sxs-lookup"><span data-stu-id="11c15-155">**Data Types.**</span></span> <span data-ttu-id="11c15-156">@No__t-0 ステートメントでは、変数のデータ型を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="11c15-156">The `Const` statement can declare the data type of a variable.</span></span> <span data-ttu-id="11c15-157">任意のデータ型または列挙型の名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="11c15-157">You can specify any data type or the name of an enumeration.</span></span>  
  
- <span data-ttu-id="11c15-158">**既定の型。**</span><span class="sxs-lookup"><span data-stu-id="11c15-158">**Default Type.**</span></span> <span data-ttu-id="11c15-159">@No__t-0 に指定しない場合、定数は `initializer` のデータ型になります。</span><span class="sxs-lookup"><span data-stu-id="11c15-159">If you do not specify `datatype`, the constant takes the data type of `initializer`.</span></span> <span data-ttu-id="11c15-160">@No__t-0 と `initializer` の両方を指定した場合、`initializer` のデータ型は `datatype` に変換可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="11c15-160">If you specify both `datatype` and `initializer`, the data type of `initializer` must be convertible to `datatype`.</span></span> <span data-ttu-id="11c15-161">@No__t-0 も `initializer` も存在しない場合、データ型は既定で `Object` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="11c15-161">If neither `datatype` nor `initializer` is present, the data type defaults to `Object`.</span></span>  
  
- <span data-ttu-id="11c15-162">**異なる型。**</span><span class="sxs-lookup"><span data-stu-id="11c15-162">**Different Types.**</span></span> <span data-ttu-id="11c15-163">宣言する変数ごとに個別の `As` 句を使用して、異なる定数に異なるデータ型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="11c15-163">You can specify different data types for different constants by using a separate `As` clause for each variable you declare.</span></span> <span data-ttu-id="11c15-164">ただし、共通の `As` 句を使用して、同じ型の複数の定数を宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="11c15-164">However, you cannot declare several constants to be of the same type by using a common `As` clause.</span></span>  
  
- <span data-ttu-id="11c15-165">**イニシャライズ.**</span><span class="sxs-lookup"><span data-stu-id="11c15-165">**Initialization.**</span></span> <span data-ttu-id="11c15-166">@No__t-0 のすべての定数の値を初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11c15-166">You must initialize the value of every constant in `constantlist`.</span></span> <span data-ttu-id="11c15-167">定数に割り当てられる式を指定するには、`initializer` を使用します。</span><span class="sxs-lookup"><span data-stu-id="11c15-167">You use `initializer` to supply an expression to be assigned to the constant.</span></span> <span data-ttu-id="11c15-168">式には、リテラルの任意の組み合わせ、既に定義されている他の定数、および既に定義されている列挙メンバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="11c15-168">The expression can be any combination of literals, other constants that are already defined, and enumeration members that are already defined.</span></span> <span data-ttu-id="11c15-169">算術演算子と論理演算子を使用すると、このような要素を組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="11c15-169">You can use arithmetic and logical operators to combine such elements.</span></span>  
  
     <span data-ttu-id="11c15-170">@No__t-0 の変数または関数は使用できません。</span><span class="sxs-lookup"><span data-stu-id="11c15-170">You cannot use variables or functions in `initializer`.</span></span> <span data-ttu-id="11c15-171">ただし、`CByte` や `CShort` などの変換キーワードを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="11c15-171">However, you can use conversion keywords such as `CByte` and `CShort`.</span></span> <span data-ttu-id="11c15-172">@No__t-0 は、定数 `String` または `Char` 引数を使用して呼び出す場合にも使用できます。これはコンパイル時に評価されるためです。</span><span class="sxs-lookup"><span data-stu-id="11c15-172">You can also use `AscW` if you call it with a constant `String` or `Char` argument, since that can be evaluated at compile time.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="11c15-173">動作</span><span class="sxs-lookup"><span data-stu-id="11c15-173">Behavior</span></span>  
  
- <span data-ttu-id="11c15-174">**検索.**</span><span class="sxs-lookup"><span data-stu-id="11c15-174">**Scope.**</span></span> <span data-ttu-id="11c15-175">ローカル定数は、プロシージャまたはブロック内からのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="11c15-175">Local constants are accessible only from within their procedure or block.</span></span> <span data-ttu-id="11c15-176">メンバー定数は、クラス、構造体、またはモジュール内のどこからでもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="11c15-176">Member constants are accessible from anywhere within their class, structure, or module.</span></span>  
  
- <span data-ttu-id="11c15-177">**修飾。**</span><span class="sxs-lookup"><span data-stu-id="11c15-177">**Qualification.**</span></span> <span data-ttu-id="11c15-178">クラス、構造体、またはモジュールの外部のコードでは、メンバー定数の名前を、そのクラス、構造体、またはモジュールの名前で修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11c15-178">Code outside a class, structure, or module must qualify a member constant's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="11c15-179">プロシージャまたはブロックの外側のコードは、そのプロシージャまたはブロック内のローカル定数を参照できません。</span><span class="sxs-lookup"><span data-stu-id="11c15-179">Code outside a procedure or block cannot refer to any local constants within that procedure or block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11c15-180">例</span><span class="sxs-lookup"><span data-stu-id="11c15-180">Example</span></span>  
 <span data-ttu-id="11c15-181">次の例では、`Const` ステートメントを使用して、リテラル値の代わりに使用する定数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="11c15-181">The following example uses the `Const` statement to declare constants for use in place of literal values.</span></span>  
  
 [!code-vb[VbVbalrStatements#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#13)]  
  
## <a name="example"></a><span data-ttu-id="11c15-182">例</span><span class="sxs-lookup"><span data-stu-id="11c15-182">Example</span></span>  
 <span data-ttu-id="11c15-183">データ型が `Object` の定数を定義すると、Visual Basic コンパイラによって、`Object` ではなく `initializer` の型が指定されます。</span><span class="sxs-lookup"><span data-stu-id="11c15-183">If you define a constant with data type `Object`, the Visual Basic compiler gives it the type of `initializer`, instead of `Object`.</span></span> <span data-ttu-id="11c15-184">次の例では、定数 `naturalLogBase` は実行時の型 `Decimal` です。</span><span class="sxs-lookup"><span data-stu-id="11c15-184">In the following example, the constant `naturalLogBase` has the run-time type `Decimal`.</span></span>  
  
 [!code-vb[VbVbalrStatements#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#87)]  
  
 <span data-ttu-id="11c15-185">前の例では、 [GetType 演算子](../../../visual-basic/language-reference/operators/gettype-operator.md)によって返される <xref:System.Type> オブジェクトに対して <xref:System.Type.ToString%2A> メソッドを使用しています。 <xref:System.Type> は、`CStr` を使用して `String` に変換することはできません。</span><span class="sxs-lookup"><span data-stu-id="11c15-185">The preceding example uses the <xref:System.Type.ToString%2A> method on the <xref:System.Type> object returned by the [GetType Operator](../../../visual-basic/language-reference/operators/gettype-operator.md), because <xref:System.Type> cannot be converted to `String` using `CStr`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11c15-186">関連項目</span><span class="sxs-lookup"><span data-stu-id="11c15-186">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [<span data-ttu-id="11c15-187">Enum ステートメント</span><span class="sxs-lookup"><span data-stu-id="11c15-187">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="11c15-188">#Const ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="11c15-188">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)
- [<span data-ttu-id="11c15-189">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="11c15-189">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="11c15-190">ReDim ステートメント</span><span class="sxs-lookup"><span data-stu-id="11c15-190">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="11c15-191">暗黙の型変換と明示的な型変換</span><span class="sxs-lookup"><span data-stu-id="11c15-191">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="11c15-192">定数と列挙体</span><span class="sxs-lookup"><span data-stu-id="11c15-192">Constants and Enumerations</span></span>](../../../visual-basic/programming-guide/language-features/constants-enums/index.md)
- [<span data-ttu-id="11c15-193">定数と列挙体</span><span class="sxs-lookup"><span data-stu-id="11c15-193">Constants and Enumerations</span></span>](../../../visual-basic/language-reference/constants-and-enumerations.md)
- [<span data-ttu-id="11c15-194">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="11c15-194">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
