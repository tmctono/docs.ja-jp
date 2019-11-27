---
title: Operator ステートメント
ms.date: 07/20/2015
f1_keywords:
- vb.operator
helpviewer_keywords:
- operators [Visual Basic]
- procedures [Visual Basic], operator
- Narrowing keyword [Visual Basic], conversion operators
- Visual Basic code, operators
- Widening keyword [Visual Basic], conversion operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
- Operator statement [Visual Basic]
- CType function [Visual Basic], Operator statement
ms.assetid: b12ec4af-1ad7-4a17-865b-c5ee96320ae5
ms.openlocfilehash: aa6ae3977977ded05e47d12dabe72f09251f262d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353806"
---
# <a name="operator-statement"></a><span data-ttu-id="2e672-102">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="2e672-102">Operator Statement</span></span>

<span data-ttu-id="2e672-103">クラスまたは構造体に演算子プロシージャを定義する演算子記号、オペランド、およびコードを宣言します。</span><span class="sxs-lookup"><span data-stu-id="2e672-103">Declares the operator symbol, operands, and code that define an operator procedure on a class or structure.</span></span>

## <a name="syntax"></a><span data-ttu-id="2e672-104">構文</span><span class="sxs-lookup"><span data-stu-id="2e672-104">Syntax</span></span>

```vb
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]
    [ statements ]
    [ statements ]
    Return returnvalue
    [ statements ]
End Operator
```

## <a name="parts"></a><span data-ttu-id="2e672-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="2e672-105">Parts</span></span>

`attrlist`  
<span data-ttu-id="2e672-106">省略可。</span><span class="sxs-lookup"><span data-stu-id="2e672-106">Optional.</span></span> <span data-ttu-id="2e672-107">「[属性リスト](../../../visual-basic/language-reference/statements/attribute-list.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e672-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>

`Public`  
<span data-ttu-id="2e672-108">必須。</span><span class="sxs-lookup"><span data-stu-id="2e672-108">Required.</span></span> <span data-ttu-id="2e672-109">この演算子プロシージャに[パブリック](../../../visual-basic/language-reference/modifiers/public.md)アクセスがあることを示します。</span><span class="sxs-lookup"><span data-stu-id="2e672-109">Indicates that this operator procedure has [Public](../../../visual-basic/language-reference/modifiers/public.md) access.</span></span>

`Overloads`  
<span data-ttu-id="2e672-110">省略可。</span><span class="sxs-lookup"><span data-stu-id="2e672-110">Optional.</span></span> <span data-ttu-id="2e672-111">「[オーバーロード](../../../visual-basic/language-reference/modifiers/overloads.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e672-111">See [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md).</span></span>

`Shared`  
<span data-ttu-id="2e672-112">必須。</span><span class="sxs-lookup"><span data-stu-id="2e672-112">Required.</span></span> <span data-ttu-id="2e672-113">この演算子プロシージャが[共有](../../../visual-basic/language-reference/modifiers/shared.md)プロシージャであることを示します。</span><span class="sxs-lookup"><span data-stu-id="2e672-113">Indicates that this operator procedure is a [Shared](../../../visual-basic/language-reference/modifiers/shared.md) procedure.</span></span>

`Shadows`  
<span data-ttu-id="2e672-114">省略可。</span><span class="sxs-lookup"><span data-stu-id="2e672-114">Optional.</span></span> <span data-ttu-id="2e672-115">「[シャドウ](../../../visual-basic/language-reference/modifiers/shadows.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e672-115">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>

`Widening`  
<span data-ttu-id="2e672-116">`Narrowing`を指定しない限り、変換演算子に対しては必須です。</span><span class="sxs-lookup"><span data-stu-id="2e672-116">Required for a conversion operator unless you specify `Narrowing`.</span></span> <span data-ttu-id="2e672-117">この演算子プロシージャが[拡大](../../../visual-basic/language-reference/modifiers/widening.md)変換を定義することを示します。</span><span class="sxs-lookup"><span data-stu-id="2e672-117">Indicates that this operator procedure defines a [Widening](../../../visual-basic/language-reference/modifiers/widening.md) conversion.</span></span> <span data-ttu-id="2e672-118">このヘルプページの「拡大変換と縮小変換」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e672-118">See "Widening and Narrowing Conversions" on this Help page.</span></span>

`Narrowing`  
<span data-ttu-id="2e672-119">`Widening`を指定しない限り、変換演算子に対しては必須です。</span><span class="sxs-lookup"><span data-stu-id="2e672-119">Required for a conversion operator unless you specify `Widening`.</span></span> <span data-ttu-id="2e672-120">この演算子プロシージャが[縮小](../../../visual-basic/language-reference/modifiers/narrowing.md)変換を定義することを示します。</span><span class="sxs-lookup"><span data-stu-id="2e672-120">Indicates that this operator procedure defines a [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) conversion.</span></span> <span data-ttu-id="2e672-121">このヘルプページの「拡大変換と縮小変換」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e672-121">See "Widening and Narrowing Conversions" on this Help page.</span></span>

`operatorsymbol`  
<span data-ttu-id="2e672-122">必須。</span><span class="sxs-lookup"><span data-stu-id="2e672-122">Required.</span></span> <span data-ttu-id="2e672-123">この演算子プロシージャが定義する演算子のシンボルまたは識別子。</span><span class="sxs-lookup"><span data-stu-id="2e672-123">The symbol or identifier of the operator that this operator procedure defines.</span></span>

`operand1`  
<span data-ttu-id="2e672-124">必須。</span><span class="sxs-lookup"><span data-stu-id="2e672-124">Required.</span></span> <span data-ttu-id="2e672-125">単項演算子 (変換演算子を含む) または二項演算子の左オペランドの1つのオペランドの名前と型。</span><span class="sxs-lookup"><span data-stu-id="2e672-125">The name and type of the single operand of a unary operator (including a conversion operator) or the left operand of a binary operator.</span></span>

`operand2`  
<span data-ttu-id="2e672-126">二項演算子の場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="2e672-126">Required for binary operators.</span></span> <span data-ttu-id="2e672-127">二項演算子の右オペランドの名前と型。</span><span class="sxs-lookup"><span data-stu-id="2e672-127">The name and type of the right operand of a binary operator.</span></span>

<span data-ttu-id="2e672-128">`operand1` と `operand2` には、次の構文と部分があります。</span><span class="sxs-lookup"><span data-stu-id="2e672-128">`operand1` and `operand2` have the following syntax and parts:</span></span>

`[ ByVal ] operandname [ As operandtype ]`

|<span data-ttu-id="2e672-129">要素</span><span class="sxs-lookup"><span data-stu-id="2e672-129">Part</span></span>|<span data-ttu-id="2e672-130">説明</span><span class="sxs-lookup"><span data-stu-id="2e672-130">Description</span></span>|
|----------|-----------------|
|`ByVal`|<span data-ttu-id="2e672-131">省略可能ですが、渡すメカニズムは[ByVal](../../../visual-basic/language-reference/modifiers/byval.md)である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e672-131">Optional, but the passing mechanism must be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>|
|`operandname`|<span data-ttu-id="2e672-132">必須。</span><span class="sxs-lookup"><span data-stu-id="2e672-132">Required.</span></span> <span data-ttu-id="2e672-133">このオペランドを表す変数の名前。</span><span class="sxs-lookup"><span data-stu-id="2e672-133">Name of the variable representing this operand.</span></span> <span data-ttu-id="2e672-134">「 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e672-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|
|`operandtype`|<span data-ttu-id="2e672-135">`Option Strict` が `On`場合を除き、省略可能です。</span><span class="sxs-lookup"><span data-stu-id="2e672-135">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="2e672-136">このオペランドのデータ型。</span><span class="sxs-lookup"><span data-stu-id="2e672-136">Data type of this operand.</span></span>|

`type`  
<span data-ttu-id="2e672-137">`Option Strict` が `On`場合を除き、省略可能です。</span><span class="sxs-lookup"><span data-stu-id="2e672-137">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="2e672-138">演算子プロシージャが返す値のデータ型。</span><span class="sxs-lookup"><span data-stu-id="2e672-138">Data type of the value the operator procedure returns.</span></span>

`statements`  
<span data-ttu-id="2e672-139">省略可。</span><span class="sxs-lookup"><span data-stu-id="2e672-139">Optional.</span></span> <span data-ttu-id="2e672-140">演算子プロシージャによって実行されるステートメントのブロック。</span><span class="sxs-lookup"><span data-stu-id="2e672-140">Block of statements that the operator procedure runs.</span></span>

`returnvalue`  
<span data-ttu-id="2e672-141">必須。</span><span class="sxs-lookup"><span data-stu-id="2e672-141">Required.</span></span> <span data-ttu-id="2e672-142">演算子プロシージャが呼び出し元のコードに返す値。</span><span class="sxs-lookup"><span data-stu-id="2e672-142">The value that the operator procedure returns to the calling code.</span></span>

<span data-ttu-id="2e672-143">`End` `Operator`</span><span class="sxs-lookup"><span data-stu-id="2e672-143">`End` `Operator`</span></span>  
<span data-ttu-id="2e672-144">必須。</span><span class="sxs-lookup"><span data-stu-id="2e672-144">Required.</span></span> <span data-ttu-id="2e672-145">この演算子プロシージャの定義を終了します。</span><span class="sxs-lookup"><span data-stu-id="2e672-145">Terminates the definition of this operator procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="2e672-146">コメント</span><span class="sxs-lookup"><span data-stu-id="2e672-146">Remarks</span></span>

<span data-ttu-id="2e672-147">`Operator` は、クラスまたは構造体でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2e672-147">You can use `Operator` only in a class or structure.</span></span> <span data-ttu-id="2e672-148">つまり、演算子の*宣言コンテキスト*をソースファイル、名前空間、モジュール、インターフェイス、プロシージャ、またはブロックにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="2e672-148">This means the *declaration context* for an operator cannot be a source file, namespace, module, interface, procedure, or block.</span></span> <span data-ttu-id="2e672-149">詳細については、「[宣言コンテキストと既定のアクセス レベル](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e672-149">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="2e672-150">すべての演算子は `Public Shared`である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e672-150">All operators must be `Public Shared`.</span></span> <span data-ttu-id="2e672-151">どちらのオペランドに対しても `ByRef`、`Optional`、または `ParamArray` を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="2e672-151">You cannot specify `ByRef`, `Optional`, or `ParamArray` for either operand.</span></span>

<span data-ttu-id="2e672-152">戻り値を保持するために、演算子記号や識別子を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="2e672-152">You cannot use the operator symbol or identifier to hold a return value.</span></span> <span data-ttu-id="2e672-153">`Return` ステートメントを使用する必要があります。また、値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e672-153">You must use the `Return` statement, and it must specify a value.</span></span> <span data-ttu-id="2e672-154">任意の数の `Return` ステートメントをプロシージャ内の任意の場所に記述できます。</span><span class="sxs-lookup"><span data-stu-id="2e672-154">Any number of `Return` statements can appear anywhere in the procedure.</span></span>

<span data-ttu-id="2e672-155">このように演算子を定義することは、`Overloads` キーワードを使用するかどうかにかかわらず、*演算子のオーバーロード*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="2e672-155">Defining an operator in this way is called *operator overloading*, whether or not you use the `Overloads` keyword.</span></span> <span data-ttu-id="2e672-156">定義可能な演算子を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="2e672-156">The following table lists the operators you can define.</span></span>

|<span data-ttu-id="2e672-157">種類</span><span class="sxs-lookup"><span data-stu-id="2e672-157">Type</span></span>|<span data-ttu-id="2e672-158">演算子</span><span class="sxs-lookup"><span data-stu-id="2e672-158">Operators</span></span>|
|----------|---------------|
|<span data-ttu-id="2e672-159">単項</span><span class="sxs-lookup"><span data-stu-id="2e672-159">Unary</span></span>|<span data-ttu-id="2e672-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="2e672-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|
|<span data-ttu-id="2e672-161">Binary</span><span class="sxs-lookup"><span data-stu-id="2e672-161">Binary</span></span>|<span data-ttu-id="2e672-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="2e672-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|
|<span data-ttu-id="2e672-163">変換 (単項)</span><span class="sxs-lookup"><span data-stu-id="2e672-163">Conversion (unary)</span></span>|`CType`|

<span data-ttu-id="2e672-164">バイナリリストの `=` 演算子は、代入演算子ではなく、比較演算子であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2e672-164">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>

<span data-ttu-id="2e672-165">`CType`を定義する場合は、`Widening` または `Narrowing`のいずれかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e672-165">When you define `CType`, you must specify either `Widening` or `Narrowing`.</span></span>

## <a name="matched-pairs"></a><span data-ttu-id="2e672-166">一致したペア</span><span class="sxs-lookup"><span data-stu-id="2e672-166">Matched Pairs</span></span>

<span data-ttu-id="2e672-167">特定の演算子を一致するペアとして定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e672-167">You must define certain operators as matched pairs.</span></span> <span data-ttu-id="2e672-168">このようなペアのいずれかの演算子を定義する場合は、他の演算子も定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e672-168">If you define either operator of such a pair, you must define the other as well.</span></span> <span data-ttu-id="2e672-169">一致するペアは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2e672-169">The matched pairs are the following:</span></span>

- <span data-ttu-id="2e672-170">`=` および `<>`</span><span class="sxs-lookup"><span data-stu-id="2e672-170">`=` and `<>`</span></span>

- <span data-ttu-id="2e672-171">`>` および `<`</span><span class="sxs-lookup"><span data-stu-id="2e672-171">`>` and `<`</span></span>

- <span data-ttu-id="2e672-172">`>=` および `<=`</span><span class="sxs-lookup"><span data-stu-id="2e672-172">`>=` and `<=`</span></span>

- <span data-ttu-id="2e672-173">`IsTrue` および `IsFalse`</span><span class="sxs-lookup"><span data-stu-id="2e672-173">`IsTrue` and `IsFalse`</span></span>

## <a name="data-type-restrictions"></a><span data-ttu-id="2e672-174">データ型の制限</span><span class="sxs-lookup"><span data-stu-id="2e672-174">Data Type Restrictions</span></span>

<span data-ttu-id="2e672-175">定義するすべての演算子には、定義するクラスまたは構造体が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e672-175">Every operator you define must involve the class or structure on which you define it.</span></span> <span data-ttu-id="2e672-176">これは、クラスまたは構造体が、次のデータ型として表示される必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="2e672-176">This means that the class or structure must appear as the data type of the following:</span></span>

- <span data-ttu-id="2e672-177">単項演算子のオペランド。</span><span class="sxs-lookup"><span data-stu-id="2e672-177">The operand of a unary operator.</span></span>

- <span data-ttu-id="2e672-178">二項演算子のオペランドのうち、少なくとも1つ。</span><span class="sxs-lookup"><span data-stu-id="2e672-178">At least one of the operands of a binary operator.</span></span>

- <span data-ttu-id="2e672-179">変換演算子のオペランドまたは戻り値の型。</span><span class="sxs-lookup"><span data-stu-id="2e672-179">Either the operand or the return type of a conversion operator.</span></span>

 <span data-ttu-id="2e672-180">特定の演算子には、次のような追加のデータ型制限があります。</span><span class="sxs-lookup"><span data-stu-id="2e672-180">Certain operators have additional data type restrictions, as follows:</span></span>

- <span data-ttu-id="2e672-181">`IsTrue` 演算子と `IsFalse` 演算子を定義する場合は、両方とも `Boolean` 型を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e672-181">If you define the `IsTrue` and `IsFalse` operators, they must both return the `Boolean` type.</span></span>

- <span data-ttu-id="2e672-182">`<<` 演算子と `>>` 演算子を定義する場合は、`operand2`の `operandtype` の `Integer` の種類を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e672-182">If you define the `<<` and `>>` operators, they must both specify the `Integer` type for the `operandtype` of `operand2`.</span></span>

<span data-ttu-id="2e672-183">戻り値の型は、どちらのオペランドの型にも対応している必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2e672-183">The return type does not have to correspond to the type of either operand.</span></span> <span data-ttu-id="2e672-184">たとえば、`=` や `<>` などの比較演算子は、どちらのオペランドも `Boolean`ない場合でも `Boolean` を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="2e672-184">For example, a comparison operator such as `=` or `<>` can return `Boolean` even if neither operand is `Boolean`.</span></span>

## <a name="logical-and-bitwise-operators"></a><span data-ttu-id="2e672-185">論理演算子とビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="2e672-185">Logical and Bitwise Operators</span></span>

<span data-ttu-id="2e672-186">`And`、`Or`、`Not`、および `Xor` の各演算子では、Visual Basic で論理操作またはビットごとの演算を実行できます。</span><span class="sxs-lookup"><span data-stu-id="2e672-186">The `And`, `Or`, `Not`, and `Xor` operators can perform either logical or bitwise operations in Visual Basic.</span></span> <span data-ttu-id="2e672-187">ただし、クラスまたは構造体でこれらの演算子のいずれかを定義する場合は、そのビットごとの演算だけを定義できます。</span><span class="sxs-lookup"><span data-stu-id="2e672-187">However, if you define one of these operators on a class or structure, you can define only its bitwise operation.</span></span>

<span data-ttu-id="2e672-188">`Operator` ステートメントを使用して、`AndAlso` 演算子を直接定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="2e672-188">You cannot define the `AndAlso` operator directly with an `Operator` statement.</span></span> <span data-ttu-id="2e672-189">ただし、次の条件を満たしている場合は、`AndAlso` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2e672-189">However, you can use `AndAlso` if you have fulfilled the following conditions:</span></span>

- <span data-ttu-id="2e672-190">`AndAlso`に使用するのと同じオペランド型に `And` が定義されています。</span><span class="sxs-lookup"><span data-stu-id="2e672-190">You have defined `And` on the same operand types you want to use for `AndAlso`.</span></span>

- <span data-ttu-id="2e672-191">`And` の定義により、定義済みのクラスまたは構造体と同じ型が返されます。</span><span class="sxs-lookup"><span data-stu-id="2e672-191">Your definition of `And` returns the same type as the class or structure on which you have defined it.</span></span>

- <span data-ttu-id="2e672-192">`And`を定義したクラスまたは構造体に `IsFalse` 演算子を定義しました。</span><span class="sxs-lookup"><span data-stu-id="2e672-192">You have defined the `IsFalse` operator on the class or structure on which you have defined `And`.</span></span>

<span data-ttu-id="2e672-193">同様に、クラスまたは構造体の戻り値の型を使用して同じオペランドで `Or` を定義し、クラスまたは構造体に `IsTrue` を定義している場合は、`OrElse` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2e672-193">Similarly, you can use `OrElse` if you have defined `Or` on the same operands, with the return type of the class or structure, and you have defined `IsTrue` on the class or structure.</span></span>

## <a name="widening-and-narrowing-conversions"></a><span data-ttu-id="2e672-194">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="2e672-194">Widening and Narrowing Conversions</span></span>

<span data-ttu-id="2e672-195">*拡大変換*は実行時に常に成功しますが、*縮小変換*は実行時に失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2e672-195">A *widening conversion* always succeeds at run time, while a *narrowing conversion* can fail at run time.</span></span> <span data-ttu-id="2e672-196">詳細については、「 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e672-196">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>

<span data-ttu-id="2e672-197">`Widening`する変換プロシージャを宣言する場合、プロシージャコードでエラーが発生しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e672-197">If you declare a conversion procedure to be `Widening`, your procedure code must not generate any failures.</span></span> <span data-ttu-id="2e672-198">これは、次のことを意味します。</span><span class="sxs-lookup"><span data-stu-id="2e672-198">This means the following:</span></span>

- <span data-ttu-id="2e672-199">常に `type`型の有効な値を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e672-199">It must always return a valid value of type `type`.</span></span>

- <span data-ttu-id="2e672-200">これは、考えられるすべての例外とその他のエラー条件を処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e672-200">It must handle all possible exceptions and other error conditions.</span></span>

- <span data-ttu-id="2e672-201">このメソッドは、呼び出したすべてのプロシージャからのエラーを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e672-201">It must handle any error returns from any procedures it calls.</span></span>

<span data-ttu-id="2e672-202">変換プロシージャが失敗する可能性がある場合、またはハンドルされない例外が発生する可能性がある場合は、`Narrowing`するように宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e672-202">If there is any possibility that a conversion procedure might not succeed, or that it might cause an unhandled exception, you must declare it to be `Narrowing`.</span></span>

## <a name="example"></a><span data-ttu-id="2e672-203">例</span><span class="sxs-lookup"><span data-stu-id="2e672-203">Example</span></span>

<span data-ttu-id="2e672-204">次のコード例では、`Operator` ステートメントを使用して、`And`、`Or`、`IsFalse`、および `IsTrue` の各演算子の演算子プロシージャを含む構造体のアウトラインを定義します。</span><span class="sxs-lookup"><span data-stu-id="2e672-204">The following code example uses the `Operator` statement to define the outline of a structure that includes operator procedures for the `And`, `Or`, `IsFalse`, and `IsTrue` operators.</span></span> <span data-ttu-id="2e672-205">`And` と `Or` は、`abc` 型のオペランドを2つ受け取り、戻り値の型 `abc`です。</span><span class="sxs-lookup"><span data-stu-id="2e672-205">`And` and `Or` each take two operands of type `abc` and return type `abc`.</span></span> <span data-ttu-id="2e672-206">`IsFalse` と `IsTrue` はそれぞれ `abc` 型の1つのオペランドを受け取り、`Boolean`を返します。</span><span class="sxs-lookup"><span data-stu-id="2e672-206">`IsFalse` and `IsTrue` each take a single operand of type `abc` and return `Boolean`.</span></span> <span data-ttu-id="2e672-207">これらの定義により、呼び出し元のコードでは、`And`、`AndAlso`、`Or`、および型 `abc`のオペランドを使用して `OrElse` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2e672-207">These definitions allow the calling code to use `And`, `AndAlso`, `Or`, and `OrElse` with operands of type `abc`.</span></span>

[!code-vb[VbVbalrStatements#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#44)]

## <a name="see-also"></a><span data-ttu-id="2e672-208">参照</span><span class="sxs-lookup"><span data-stu-id="2e672-208">See also</span></span>

- [<span data-ttu-id="2e672-209">IsFalse 演算子</span><span class="sxs-lookup"><span data-stu-id="2e672-209">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="2e672-210">IsTrue 演算子</span><span class="sxs-lookup"><span data-stu-id="2e672-210">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="2e672-211">Widening</span><span class="sxs-lookup"><span data-stu-id="2e672-211">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="2e672-212">Narrowing</span><span class="sxs-lookup"><span data-stu-id="2e672-212">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="2e672-213">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="2e672-213">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="2e672-214">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="2e672-214">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="2e672-215">方法 : 演算子を定義する</span><span class="sxs-lookup"><span data-stu-id="2e672-215">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="2e672-216">方法 : 変換演算子を定義する</span><span class="sxs-lookup"><span data-stu-id="2e672-216">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="2e672-217">方法 : 演算子プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="2e672-217">How to: Call an Operator Procedure</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="2e672-218">方法: 演算子を定義するクラスを使用する</span><span class="sxs-lookup"><span data-stu-id="2e672-218">How to: Use a Class that Defines Operators</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
