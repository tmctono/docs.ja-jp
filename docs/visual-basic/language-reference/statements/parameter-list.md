---
title: パラメーター リスト
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic
- parameters [Visual Basic], lists
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- arguments [Visual Basic], Visual Basic
- procedures [Visual Basic], parameter lists
ms.assetid: 5d737319-0c34-4df9-a23d-188fc840becd
ms.openlocfilehash: ec4ce0f12b540478d889832fb18f1ef008613f1f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346480"
---
# <a name="parameter-list-visual-basic"></a><span data-ttu-id="614b6-102">パラメーターの一覧 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="614b6-102">Parameter List (Visual Basic)</span></span>

<span data-ttu-id="614b6-103">プロシージャが呼び出されるときに、プロシージャで期待するパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="614b6-103">Specifies the parameters a procedure expects when it is called.</span></span> <span data-ttu-id="614b6-104">複数のパラメーターはコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="614b6-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="614b6-105">次に 1 つのパラメーターの構文を示します。</span><span class="sxs-lookup"><span data-stu-id="614b6-105">The following is the syntax for one parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="614b6-106">構文</span><span class="sxs-lookup"><span data-stu-id="614b6-106">Syntax</span></span>

```vb
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]
parametername[( )] [ As parametertype ] [ = defaultvalue ]
```

## <a name="parts"></a><span data-ttu-id="614b6-107">指定項目</span><span class="sxs-lookup"><span data-stu-id="614b6-107">Parts</span></span>

`attributelist`  
<span data-ttu-id="614b6-108">任意。</span><span class="sxs-lookup"><span data-stu-id="614b6-108">Optional.</span></span> <span data-ttu-id="614b6-109">このパラメーターに適用される属性の一覧。</span><span class="sxs-lookup"><span data-stu-id="614b6-109">List of attributes that apply to this parameter.</span></span> <span data-ttu-id="614b6-110">[属性リスト](../../../visual-basic/language-reference/statements/attribute-list.md)は山かっこ ("`<`" および "`>`") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="614b6-110">You must enclose the [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>

`Optional`  
<span data-ttu-id="614b6-111">任意。</span><span class="sxs-lookup"><span data-stu-id="614b6-111">Optional.</span></span> <span data-ttu-id="614b6-112">プロシージャが呼び出されるときに、このパラメーターが必須でないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="614b6-112">Specifies that this parameter is not required when the procedure is called.</span></span>

`ByVal`  
<span data-ttu-id="614b6-113">任意。</span><span class="sxs-lookup"><span data-stu-id="614b6-113">Optional.</span></span> <span data-ttu-id="614b6-114">プロシージャで、呼び出し元のコード内の対応する引数の基になる変数要素を置換または再代入できないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="614b6-114">Specifies that the procedure cannot replace or reassign the variable element underlying the corresponding argument in the calling code.</span></span>

`ByRef`  
<span data-ttu-id="614b6-115">任意。</span><span class="sxs-lookup"><span data-stu-id="614b6-115">Optional.</span></span> <span data-ttu-id="614b6-116">プロシージャで、呼び出し元のコード自体で可能な同じ方法で、呼び出し元のコード内の基になる変数要素を変更できることを指定します。</span><span class="sxs-lookup"><span data-stu-id="614b6-116">Specifies that the procedure can modify the underlying variable element in the calling code the same way the calling code itself can.</span></span>

`ParamArray`  
<span data-ttu-id="614b6-117">任意。</span><span class="sxs-lookup"><span data-stu-id="614b6-117">Optional.</span></span> <span data-ttu-id="614b6-118">パラメーター リストの最後のパラメーターが、指定したデータ型の要素の省略可能な配列であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="614b6-118">Specifies that the last parameter in the parameter list is an optional array of elements of the specified data type.</span></span> <span data-ttu-id="614b6-119">これにより、呼び出し元のコードで、プロシージャに任意の数の引数を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="614b6-119">This lets the calling code pass an arbitrary number of arguments to the procedure.</span></span>

`parametername`  
<span data-ttu-id="614b6-120">必須です。</span><span class="sxs-lookup"><span data-stu-id="614b6-120">Required.</span></span> <span data-ttu-id="614b6-121">パラメーターを表すローカル変数の名前。</span><span class="sxs-lookup"><span data-stu-id="614b6-121">Name of the local variable representing the parameter.</span></span>

`parametertype`  
<span data-ttu-id="614b6-122">`Option Strict` が `On` の場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="614b6-122">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="614b6-123">パラメーターを表すローカル変数のデータ型。</span><span class="sxs-lookup"><span data-stu-id="614b6-123">Data type of the local variable representing the parameter.</span></span>

`defaultvalue`  
<span data-ttu-id="614b6-124">`Optional` パラメーターに必須です。</span><span class="sxs-lookup"><span data-stu-id="614b6-124">Required for `Optional` parameters.</span></span> <span data-ttu-id="614b6-125">パラメーターのデータ型に評価される定数または定数式。</span><span class="sxs-lookup"><span data-stu-id="614b6-125">Any constant or constant expression that evaluates to the data type of the parameter.</span></span> <span data-ttu-id="614b6-126">型が `Object`、クラス、インターフェイス、配列、または構造体の場合、既定値は `Nothing` のみ指定できます。</span><span class="sxs-lookup"><span data-stu-id="614b6-126">If the type is `Object`, or a class, interface, array, or structure, the default value can only be `Nothing`.</span></span>

## <a name="remarks"></a><span data-ttu-id="614b6-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="614b6-127">Remarks</span></span>

<span data-ttu-id="614b6-128">パラメーターは、かっこで囲み、コンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="614b6-128">Parameters are surrounded by parentheses and separated by commas.</span></span> <span data-ttu-id="614b6-129">パラメーターは任意のデータ型で宣言できます。</span><span class="sxs-lookup"><span data-stu-id="614b6-129">A parameter can be declared with any data type.</span></span> <span data-ttu-id="614b6-130">`parametertype` を指定しない場合、既定で `Object` が設定されます。</span><span class="sxs-lookup"><span data-stu-id="614b6-130">If you do not specify `parametertype`, it defaults to `Object`.</span></span>

<span data-ttu-id="614b6-131">呼び出し元のコードでプロシージャを呼び出すと、各必須パラメーターに*引数*が渡されます。</span><span class="sxs-lookup"><span data-stu-id="614b6-131">When the calling code calls the procedure, it passes an *argument* to each required parameter.</span></span> <span data-ttu-id="614b6-132">詳細については、「[パラメーターと引数の違い](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="614b6-132">For more information, see [Differences Between Parameters and Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).</span></span>

<span data-ttu-id="614b6-133">呼び出し元のコードから各パラメーターに渡される引数は、呼び出し元のコード内の基になる要素へのポインターです。</span><span class="sxs-lookup"><span data-stu-id="614b6-133">The argument the calling code passes to each parameter is a pointer to an underlying element in the calling code.</span></span> <span data-ttu-id="614b6-134">この要素が*変数でない* (定数、リテラル、列挙型、または式) 場合、どのコードでもそれを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="614b6-134">If this element is *nonvariable* (a constant, literal, enumeration, or expression), it is impossible for any code to change it.</span></span> <span data-ttu-id="614b6-135">それが*変数*要素 (宣言された変数、フィールド、プロパティ、配列要素、または構造体要素) の場合は、呼び出し元のコードでそれを変更できます。</span><span class="sxs-lookup"><span data-stu-id="614b6-135">If it is a *variable* element (a declared variable, field, property, array element, or structure element), the calling code can change it.</span></span> <span data-ttu-id="614b6-136">詳細については、「[変更できる引数と変更できない引数の違い](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="614b6-136">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).</span></span>

<span data-ttu-id="614b6-137">変数要素が `ByRef` で渡された場合は、プロシージャでそれを変更できます。</span><span class="sxs-lookup"><span data-stu-id="614b6-137">If a variable element is passed `ByRef`, the procedure can change it as well.</span></span> <span data-ttu-id="614b6-138">詳細については、「[引数の値渡しと参照渡しの違い](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="614b6-138">For more information, see [Differences Between Passing an Argument By Value and By Reference](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>

## <a name="rules"></a><span data-ttu-id="614b6-139">ルール</span><span class="sxs-lookup"><span data-stu-id="614b6-139">Rules</span></span>

- <span data-ttu-id="614b6-140">**かっこ。**</span><span class="sxs-lookup"><span data-stu-id="614b6-140">**Parentheses.**</span></span> <span data-ttu-id="614b6-141">パラメーター リストを指定する場合は、かっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="614b6-141">If you specify a parameter list, you must enclose it in parentheses.</span></span> <span data-ttu-id="614b6-142">パラメーターがない場合でも、空のリストを囲むかっこを使用できます。</span><span class="sxs-lookup"><span data-stu-id="614b6-142">If there are no parameters, you can still use parentheses enclosing an empty list.</span></span> <span data-ttu-id="614b6-143">これにより、要素がプロシージャであることを明確にすることで、コードの読みやすさが向上します。</span><span class="sxs-lookup"><span data-stu-id="614b6-143">This improves the readability of your code by clarifying that the element is a procedure.</span></span>

- <span data-ttu-id="614b6-144">**省略可能なパラメーター。**</span><span class="sxs-lookup"><span data-stu-id="614b6-144">**Optional Parameters.**</span></span> <span data-ttu-id="614b6-145">パラメーターで `Optional` 修飾子を使用する場合、リスト内の後続のすべてのパラメーターも省略可能で、`Optional` 修飾子を使用して宣言されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="614b6-145">If you use the `Optional` modifier on a parameter, all subsequent parameters in the list must also be optional and be declared by using the `Optional` modifier.</span></span>

     <span data-ttu-id="614b6-146">省略可能なすべてのパラメーター宣言で、`defaultvalue` 句を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="614b6-146">Every optional parameter declaration must supply the `defaultvalue` clause.</span></span>

     <span data-ttu-id="614b6-147">詳細については、「[省略可能なパラメーター](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="614b6-147">For more information, see [Optional Parameters](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).</span></span>

- <span data-ttu-id="614b6-148">**パラメーター配列。**</span><span class="sxs-lookup"><span data-stu-id="614b6-148">**Parameter Arrays.**</span></span> <span data-ttu-id="614b6-149">`ParamArray` パラメーターには `ByVal` を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="614b6-149">You must specify `ByVal` for a `ParamArray` parameter.</span></span>

     <span data-ttu-id="614b6-150">同じパラメーター リストで `Optional` と `ParamArray` の両方を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="614b6-150">You cannot use both `Optional` and `ParamArray` in the same parameter list.</span></span>

     <span data-ttu-id="614b6-151">詳細については、「[パラメーター配列](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="614b6-151">For more information, see [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>

- <span data-ttu-id="614b6-152">**引渡し方法。**</span><span class="sxs-lookup"><span data-stu-id="614b6-152">**Passing Mechanism.**</span></span> <span data-ttu-id="614b6-153">すべての引数の既定の方法は `ByVal` です。これは、プロシージャで基になる変数要素を変更できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="614b6-153">The default mechanism for every argument is `ByVal`, which means the procedure cannot change the underlying variable element.</span></span> <span data-ttu-id="614b6-154">ただし、要素が参照型の場合、プロシージャで、オブジェクト自体の置換や再代入ができなくても、基になるオブジェクトの内容やメンバーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="614b6-154">However, if the element is a reference type, the procedure can modify the contents or members of the underlying object, even though it cannot replace or reassign the object itself.</span></span>

- <span data-ttu-id="614b6-155">**パラメーター名。**</span><span class="sxs-lookup"><span data-stu-id="614b6-155">**Parameter Names.**</span></span> <span data-ttu-id="614b6-156">パラメーターのデータ型が配列である場合は、`parametername` の直後にかっこで指定します。</span><span class="sxs-lookup"><span data-stu-id="614b6-156">If the parameter's data type is an array, follow `parametername` immediately by parentheses.</span></span> <span data-ttu-id="614b6-157">パラメーター名の詳細については、「[宣言された要素の名前](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="614b6-157">For more information on parameter names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

## <a name="example"></a><span data-ttu-id="614b6-158">例</span><span class="sxs-lookup"><span data-stu-id="614b6-158">Example</span></span>

<span data-ttu-id="614b6-159">次の例では、2 つのパラメーターを定義する `Function` プロシージャを示しています。</span><span class="sxs-lookup"><span data-stu-id="614b6-159">The following example shows a `Function` procedure that defines two parameters.</span></span>

[!code-vb[VbVbalrStatements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#2)]

## <a name="see-also"></a><span data-ttu-id="614b6-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="614b6-160">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="614b6-161">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="614b6-161">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="614b6-162">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="614b6-162">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="614b6-163">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="614b6-163">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="614b6-164">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="614b6-164">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="614b6-165">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="614b6-165">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="614b6-166">属性の概要</span><span class="sxs-lookup"><span data-stu-id="614b6-166">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="614b6-167">方法: コード内でステートメントを分割および連結する</span><span class="sxs-lookup"><span data-stu-id="614b6-167">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
