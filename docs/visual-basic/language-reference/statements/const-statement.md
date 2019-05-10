---
title: Const ステートメント (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Const
helpviewer_keywords:
- Const statement [Visual Basic]
ms.assetid: 495b318d-b7c5-4198-94f8-0790a541b07a
ms.openlocfilehash: 9d2e0c7b2b81a79f95fa852b3975f4512d87f8e0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623990"
---
# <a name="const-statement-visual-basic"></a><span data-ttu-id="a33a3-102">Const ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a33a3-102">Const Statement (Visual Basic)</span></span>
<span data-ttu-id="a33a3-103">宣言し、1 つまたは複数の定数を定義します。</span><span class="sxs-lookup"><span data-stu-id="a33a3-103">Declares and defines one or more constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a33a3-104">構文</span><span class="sxs-lookup"><span data-stu-id="a33a3-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ]   
Const constantlist  
```  
  
## <a name="parts"></a><span data-ttu-id="a33a3-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="a33a3-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="a33a3-106">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a33a3-106">Optional.</span></span> <span data-ttu-id="a33a3-107">すべての定数に適用される属性の一覧は、このステートメントで宣言します。</span><span class="sxs-lookup"><span data-stu-id="a33a3-107">List of attributes that apply to all the constants declared in this statement.</span></span> <span data-ttu-id="a33a3-108">参照してください[属性リスト](../../../visual-basic/language-reference/statements/attribute-list.md)山かっこ ("`<`「と」`>`")。</span><span class="sxs-lookup"><span data-stu-id="a33a3-108">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="a33a3-109">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a33a3-109">Optional.</span></span> <span data-ttu-id="a33a3-110">これを使用して、どのようなコードがアクセスできるは、これらの定数を指定します。</span><span class="sxs-lookup"><span data-stu-id="a33a3-110">Use this to specify what code can access these constants.</span></span> <span data-ttu-id="a33a3-111">[パブリック](../../../visual-basic/language-reference/modifiers/public.md)、 [Protected](../../../visual-basic/language-reference/modifiers/protected.md)、[フレンド](../../../visual-basic/language-reference/modifiers/friend.md)、 [Protected Friend](../modifiers/protected-friend.md)、[プライベート](../../../visual-basic/language-reference/modifiers/private.md)、または[Private Protected](../../language-reference/modifiers/private-protected.md)します。</span><span class="sxs-lookup"><span data-stu-id="a33a3-111">Can be [Public](../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), [Protected Friend](../modifiers/protected-friend.md), [Private](../../../visual-basic/language-reference/modifiers/private.md), or [Private Protected](../../language-reference/modifiers/private-protected.md).</span></span>
  
 `Shadows`  
 <span data-ttu-id="a33a3-112">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a33a3-112">Optional.</span></span> <span data-ttu-id="a33a3-113">再宣言して、基底クラスでのプログラミング要素を非表示にするには、これを使用します。</span><span class="sxs-lookup"><span data-stu-id="a33a3-113">Use this to redeclare and hide a programming element in a base class.</span></span> <span data-ttu-id="a33a3-114">参照してください[Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)します。</span><span class="sxs-lookup"><span data-stu-id="a33a3-114">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
 `constantlist`  
 <span data-ttu-id="a33a3-115">必須。</span><span class="sxs-lookup"><span data-stu-id="a33a3-115">Required.</span></span> <span data-ttu-id="a33a3-116">このステートメントで宣言されている定数の一覧です。</span><span class="sxs-lookup"><span data-stu-id="a33a3-116">List of constants being declared in this statement.</span></span>  
  
 <span data-ttu-id="a33a3-117">`constant` `[ ,` `constant` `... ]`</span><span class="sxs-lookup"><span data-stu-id="a33a3-117">`constant` `[ ,` `constant` `... ]`</span></span>  
  
 <span data-ttu-id="a33a3-118">`constant` の構文と指定項目は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a33a3-118">Each `constant` has the following syntax and parts:</span></span>  
  
 <span data-ttu-id="a33a3-119">`constantname` `[ As` `datatype` `] =` `initializer`</span><span class="sxs-lookup"><span data-stu-id="a33a3-119">`constantname` `[ As` `datatype` `] =` `initializer`</span></span>  
  
|<span data-ttu-id="a33a3-120">パーツ</span><span class="sxs-lookup"><span data-stu-id="a33a3-120">Part</span></span>|<span data-ttu-id="a33a3-121">説明</span><span class="sxs-lookup"><span data-stu-id="a33a3-121">Description</span></span>|  
|----------|-----------------|  
|`constantname`|<span data-ttu-id="a33a3-122">必須。</span><span class="sxs-lookup"><span data-stu-id="a33a3-122">Required.</span></span> <span data-ttu-id="a33a3-123">定数の名前。</span><span class="sxs-lookup"><span data-stu-id="a33a3-123">Name of the constant.</span></span> <span data-ttu-id="a33a3-124">「 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a33a3-124">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`datatype`|<span data-ttu-id="a33a3-125">場合に、必ず`Option Strict`は`On`します。</span><span class="sxs-lookup"><span data-stu-id="a33a3-125">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="a33a3-126">定数のデータ型。</span><span class="sxs-lookup"><span data-stu-id="a33a3-126">Data type of the constant.</span></span>|  
|`initializer`|<span data-ttu-id="a33a3-127">必須。</span><span class="sxs-lookup"><span data-stu-id="a33a3-127">Required.</span></span> <span data-ttu-id="a33a3-128">式がコンパイル時に評価され、定数に割り当てられているです。</span><span class="sxs-lookup"><span data-stu-id="a33a3-128">Expression that is evaluated at compile time and assigned to the constant.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a33a3-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="a33a3-129">Remarks</span></span>  
 <span data-ttu-id="a33a3-130">を、アプリケーションで変更されない値がある場合は、名前付き定数を定義し、リテラル値の代わりに使用します。</span><span class="sxs-lookup"><span data-stu-id="a33a3-130">If you have a value that never changes in your application, you can define a named constant and use it in place of a literal value.</span></span> <span data-ttu-id="a33a3-131">名前は、値よりも覚えやすい。</span><span class="sxs-lookup"><span data-stu-id="a33a3-131">A name is easier to remember than a value.</span></span> <span data-ttu-id="a33a3-132">定数を 1 回だけ定義でき、コード内のさまざまな場所で使用できます。</span><span class="sxs-lookup"><span data-stu-id="a33a3-132">You can define the constant just once and use it in many places in your code.</span></span> <span data-ttu-id="a33a3-133">以降のバージョンでは、値を再定義する必要がある場合、`Const`ステートメントは唯一の場所を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a33a3-133">If in a later version you need to redefine the value, the `Const` statement is the only place you need to make a change.</span></span>  
  
 <span data-ttu-id="a33a3-134">使用することができます`Const`モジュールまたはプロシージャ レベルでのみです。</span><span class="sxs-lookup"><span data-stu-id="a33a3-134">You can use `Const` only at module or procedure level.</span></span> <span data-ttu-id="a33a3-135">つまり、*宣言コンテキスト*変数は、クラス、構造体、モジュール、プロシージャ、またはブロックする必要があり、ソース ファイル、名前空間、またはインターフェイスにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a33a3-135">This means the *declaration context* for a variable must be a class, structure, module, procedure, or block, and cannot be a source file, namespace, or interface.</span></span> <span data-ttu-id="a33a3-136">詳細については、「[宣言コンテキストと既定のアクセス レベル](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a33a3-136">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="a33a3-137">ローカル定数 (プロシージャ) 内にある既定で、パブリック アクセスに、アクセス修飾子を使用できません。</span><span class="sxs-lookup"><span data-stu-id="a33a3-137">Local constants (inside a procedure) default to public access, and you cannot use any access modifiers on them.</span></span> <span data-ttu-id="a33a3-138">プライベート アクセスは、クラスとモジュールのメンバー (プロシージャ) の外部定数既定、構造体メンバー定数既定でパブリック アクセスします。</span><span class="sxs-lookup"><span data-stu-id="a33a3-138">Class and module member constants (outside any procedure) default to private access, and structure member constants default to public access.</span></span> <span data-ttu-id="a33a3-139">アクセス修飾子を使用してこれらのアクセス レベルを調整できます。</span><span class="sxs-lookup"><span data-stu-id="a33a3-139">You can adjust their access levels with the access modifiers.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="a33a3-140">ルール</span><span class="sxs-lookup"><span data-stu-id="a33a3-140">Rules</span></span>  
  
- <span data-ttu-id="a33a3-141">**宣言コンテキスト。**</span><span class="sxs-lookup"><span data-stu-id="a33a3-141">**Declaration Context.**</span></span> <span data-ttu-id="a33a3-142">定数宣言、プロシージャの外側のモジュール レベルでは、*メンバー定数*; クラス、構造体のメンバーであるか、宣言するモジュール。</span><span class="sxs-lookup"><span data-stu-id="a33a3-142">A constant declared at module level, outside any procedure, is a *member constant*; it is a member of the class, structure, or module that declares it.</span></span>  
  
     <span data-ttu-id="a33a3-143">プロシージャ レベルで宣言された定数は、*ローカル定数*; プロシージャまたは宣言ブロックに対してローカルです。</span><span class="sxs-lookup"><span data-stu-id="a33a3-143">A constant declared at procedure level is a *local constant*; it is local to the procedure or block that declares it.</span></span>  
  
- <span data-ttu-id="a33a3-144">**属性。**</span><span class="sxs-lookup"><span data-stu-id="a33a3-144">**Attributes.**</span></span> <span data-ttu-id="a33a3-145">ローカル定数ではなく、メンバーの定数にのみ、属性を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="a33a3-145">You can apply attributes only to member constants, not to local constants.</span></span> <span data-ttu-id="a33a3-146">属性は、ローカル定数などの一時的なストレージの意味はないアセンブリのメタデータに情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="a33a3-146">An attribute contributes information to the assembly's metadata, which is not meaningful for temporary storage such as local constants.</span></span>  
  
- <span data-ttu-id="a33a3-147">**修飾子。**</span><span class="sxs-lookup"><span data-stu-id="a33a3-147">**Modifiers.**</span></span> <span data-ttu-id="a33a3-148">すべての定数は、既定では、 `Shared`、 `Static`、および`ReadOnly`します。</span><span class="sxs-lookup"><span data-stu-id="a33a3-148">By default, all constants are `Shared`, `Static`, and `ReadOnly`.</span></span> <span data-ttu-id="a33a3-149">定数を宣言するときに、これらのキーワードのいずれかを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="a33a3-149">You cannot use any of these keywords when declaring a constant.</span></span>  
  
     <span data-ttu-id="a33a3-150">プロシージャ レベルで使用することはできません`Shadows`またはのいずれかのアクセス修飾子をローカル定数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="a33a3-150">At procedure level, you cannot use `Shadows` or any access modifiers to declare local constants.</span></span>  
  
- <span data-ttu-id="a33a3-151">**複数の定数。**</span><span class="sxs-lookup"><span data-stu-id="a33a3-151">**Multiple Constants.**</span></span> <span data-ttu-id="a33a3-152">同じ宣言ステートメントで複数の定数を宣言することを指定する、`constantname`それぞれの一部です。</span><span class="sxs-lookup"><span data-stu-id="a33a3-152">You can declare several constants in the same declaration statement, specifying the `constantname` part for each one.</span></span> <span data-ttu-id="a33a3-153">複数の定数は、コンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="a33a3-153">Multiple constants are separated by commas.</span></span>  
  
## <a name="data-type-rules"></a><span data-ttu-id="a33a3-154">データ型のルール</span><span class="sxs-lookup"><span data-stu-id="a33a3-154">Data Type Rules</span></span>  
  
- <span data-ttu-id="a33a3-155">**データ型。**</span><span class="sxs-lookup"><span data-stu-id="a33a3-155">**Data Types.**</span></span> <span data-ttu-id="a33a3-156">`Const`ステートメントは、変数のデータ型を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="a33a3-156">The `Const` statement can declare the data type of a variable.</span></span> <span data-ttu-id="a33a3-157">任意のデータ型または列挙型の名前を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="a33a3-157">You can specify any data type or the name of an enumeration.</span></span>  
  
- <span data-ttu-id="a33a3-158">**既定の型。**</span><span class="sxs-lookup"><span data-stu-id="a33a3-158">**Default Type.**</span></span> <span data-ttu-id="a33a3-159">指定しない場合`datatype`、定数のデータ型は、`initializer`します。</span><span class="sxs-lookup"><span data-stu-id="a33a3-159">If you do not specify `datatype`, the constant takes the data type of `initializer`.</span></span> <span data-ttu-id="a33a3-160">両方を指定する場合`datatype`と`initializer`のデータ型`initializer`に変換できる必要があります`datatype`します。</span><span class="sxs-lookup"><span data-stu-id="a33a3-160">If you specify both `datatype` and `initializer`, the data type of `initializer` must be convertible to `datatype`.</span></span> <span data-ttu-id="a33a3-161">どちらの場合`datatype`も`initializer`が存在するデータ型の既定値は`Object`します。</span><span class="sxs-lookup"><span data-stu-id="a33a3-161">If neither `datatype` nor `initializer` is present, the data type defaults to `Object`.</span></span>  
  
- <span data-ttu-id="a33a3-162">**さまざまな種類。**</span><span class="sxs-lookup"><span data-stu-id="a33a3-162">**Different Types.**</span></span> <span data-ttu-id="a33a3-163">異なる定数に異なるデータ型を指定するには、個別を使用して`As`を宣言する変数ごとの句。</span><span class="sxs-lookup"><span data-stu-id="a33a3-163">You can specify different data types for different constants by using a separate `As` clause for each variable you declare.</span></span> <span data-ttu-id="a33a3-164">ただし、一般的なを使用して、同じ型にするいくつかの定数を宣言することはできません`As`句。</span><span class="sxs-lookup"><span data-stu-id="a33a3-164">However, you cannot declare several constants to be of the same type by using a common `As` clause.</span></span>  
  
- <span data-ttu-id="a33a3-165">**初期化します。**</span><span class="sxs-lookup"><span data-stu-id="a33a3-165">**Initialization.**</span></span> <span data-ttu-id="a33a3-166">内のすべての定数の値を初期化する必要があります`constantlist`します。</span><span class="sxs-lookup"><span data-stu-id="a33a3-166">You must initialize the value of every constant in `constantlist`.</span></span> <span data-ttu-id="a33a3-167">使用する`initializer`定数に割り当てられる式を指定します。</span><span class="sxs-lookup"><span data-stu-id="a33a3-167">You use `initializer` to supply an expression to be assigned to the constant.</span></span> <span data-ttu-id="a33a3-168">式には、リテラル、既に定義されている他の定数と既に定義されている列挙型メンバーの任意の組み合わせを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a33a3-168">The expression can be any combination of literals, other constants that are already defined, and enumeration members that are already defined.</span></span> <span data-ttu-id="a33a3-169">算術演算および論理演算子を使用すると、このような要素を結合します。</span><span class="sxs-lookup"><span data-stu-id="a33a3-169">You can use arithmetic and logical operators to combine such elements.</span></span>  
  
     <span data-ttu-id="a33a3-170">変数または関数で使用することはできません`initializer`します。</span><span class="sxs-lookup"><span data-stu-id="a33a3-170">You cannot use variables or functions in `initializer`.</span></span> <span data-ttu-id="a33a3-171">変換キーワードなどを使用するただし、`CByte`と`CShort`します。</span><span class="sxs-lookup"><span data-stu-id="a33a3-171">However, you can use conversion keywords such as `CByte` and `CShort`.</span></span> <span data-ttu-id="a33a3-172">使用することも`AscW`定数で呼び出す場合`String`または`Char`引数、コンパイル時に評価できるためです。</span><span class="sxs-lookup"><span data-stu-id="a33a3-172">You can also use `AscW` if you call it with a constant `String` or `Char` argument, since that can be evaluated at compile time.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="a33a3-173">動作</span><span class="sxs-lookup"><span data-stu-id="a33a3-173">Behavior</span></span>  
  
- <span data-ttu-id="a33a3-174">**スコープ。**</span><span class="sxs-lookup"><span data-stu-id="a33a3-174">**Scope.**</span></span> <span data-ttu-id="a33a3-175">ローカル定数は、そのプロシージャまたはブロック内からのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a33a3-175">Local constants are accessible only from within their procedure or block.</span></span> <span data-ttu-id="a33a3-176">メンバー定数には、クラス、構造体、またはモジュール内で任意の場所からアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a33a3-176">Member constants are accessible from anywhere within their class, structure, or module.</span></span>  
  
- <span data-ttu-id="a33a3-177">**パス名です。**</span><span class="sxs-lookup"><span data-stu-id="a33a3-177">**Qualification.**</span></span> <span data-ttu-id="a33a3-178">コード、クラスの外部で構造体、またはモジュール修飾する必要があります、クラス、構造体、モジュールの名前を持つメンバー定数の名前。</span><span class="sxs-lookup"><span data-stu-id="a33a3-178">Code outside a class, structure, or module must qualify a member constant's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="a33a3-179">コードの外部プロシージャまたはブロックは、そのプロシージャまたはブロック内の任意のローカル定数を参照できません。</span><span class="sxs-lookup"><span data-stu-id="a33a3-179">Code outside a procedure or block cannot refer to any local constants within that procedure or block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a33a3-180">例</span><span class="sxs-lookup"><span data-stu-id="a33a3-180">Example</span></span>  
 <span data-ttu-id="a33a3-181">次の例では、`Const`リテラル値の代わりに使用するための定数を宣言するステートメント。</span><span class="sxs-lookup"><span data-stu-id="a33a3-181">The following example uses the `Const` statement to declare constants for use in place of literal values.</span></span>  
  
 [!code-vb[VbVbalrStatements#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#13)]  
  
## <a name="example"></a><span data-ttu-id="a33a3-182">例</span><span class="sxs-lookup"><span data-stu-id="a33a3-182">Example</span></span>  
 <span data-ttu-id="a33a3-183">データ型の定数を定義した場合`Object`、Visual Basic コンパイラは、の型を提供、`initializer`の代わりに`Object`します。</span><span class="sxs-lookup"><span data-stu-id="a33a3-183">If you define a constant with data type `Object`, the Visual Basic compiler gives it the type of `initializer`, instead of `Object`.</span></span> <span data-ttu-id="a33a3-184">次の例では、定数`naturalLogBase`実行時の型を持つ`Decimal`します。</span><span class="sxs-lookup"><span data-stu-id="a33a3-184">In the following example, the constant `naturalLogBase` has the run-time type `Decimal`.</span></span>  
  
 [!code-vb[VbVbalrStatements#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#87)]  
  
 <span data-ttu-id="a33a3-185">上記の例では、<xref:System.Type.ToString%2A>メソッドを<xref:System.Type>によって返されるオブジェクト、 [GetType 演算子](../../../visual-basic/language-reference/operators/gettype-operator.md)ため、<xref:System.Type>に変換できない`String`を使用して`CStr`します。</span><span class="sxs-lookup"><span data-stu-id="a33a3-185">The preceding example uses the <xref:System.Type.ToString%2A> method on the <xref:System.Type> object returned by the [GetType Operator](../../../visual-basic/language-reference/operators/gettype-operator.md), because <xref:System.Type> cannot be converted to `String` using `CStr`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a33a3-186">関連項目</span><span class="sxs-lookup"><span data-stu-id="a33a3-186">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [<span data-ttu-id="a33a3-187">Enum ステートメント</span><span class="sxs-lookup"><span data-stu-id="a33a3-187">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="a33a3-188">#Const ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="a33a3-188">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)
- [<span data-ttu-id="a33a3-189">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="a33a3-189">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="a33a3-190">ReDim ステートメント</span><span class="sxs-lookup"><span data-stu-id="a33a3-190">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="a33a3-191">暗黙の型変換と明示的な型変換</span><span class="sxs-lookup"><span data-stu-id="a33a3-191">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="a33a3-192">定数と列挙体</span><span class="sxs-lookup"><span data-stu-id="a33a3-192">Constants and Enumerations</span></span>](../../../visual-basic/programming-guide/language-features/constants-enums/index.md)
- [<span data-ttu-id="a33a3-193">定数と列挙体</span><span class="sxs-lookup"><span data-stu-id="a33a3-193">Constants and Enumerations</span></span>](../../../visual-basic/language-reference/constants-and-enumerations.md)
- [<span data-ttu-id="a33a3-194">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="a33a3-194">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
