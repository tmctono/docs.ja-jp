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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346480"
---
# <a name="parameter-list-visual-basic"></a><span data-ttu-id="acfb8-102">パラメーター リスト (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="acfb8-102">Parameter List (Visual Basic)</span></span>

<span data-ttu-id="acfb8-103">プロシージャが呼び出されるときに予期されるパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="acfb8-103">Specifies the parameters a procedure expects when it is called.</span></span> <span data-ttu-id="acfb8-104">複数のパラメーターはコンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="acfb8-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="acfb8-105">1つのパラメーターの構文を次に示します。</span><span class="sxs-lookup"><span data-stu-id="acfb8-105">The following is the syntax for one parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="acfb8-106">構文</span><span class="sxs-lookup"><span data-stu-id="acfb8-106">Syntax</span></span>

```vb
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]
parametername[( )] [ As parametertype ] [ = defaultvalue ]
```

## <a name="parts"></a><span data-ttu-id="acfb8-107">指定項目</span><span class="sxs-lookup"><span data-stu-id="acfb8-107">Parts</span></span>

`attributelist`  
<span data-ttu-id="acfb8-108">省略可。</span><span class="sxs-lookup"><span data-stu-id="acfb8-108">Optional.</span></span> <span data-ttu-id="acfb8-109">このパラメーターに適用される属性の一覧。</span><span class="sxs-lookup"><span data-stu-id="acfb8-109">List of attributes that apply to this parameter.</span></span> <span data-ttu-id="acfb8-110">[属性リスト](../../../visual-basic/language-reference/statements/attribute-list.md)は山かっこ ("`<`" と "`>`") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="acfb8-110">You must enclose the [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>

`Optional`  
<span data-ttu-id="acfb8-111">省略可。</span><span class="sxs-lookup"><span data-stu-id="acfb8-111">Optional.</span></span> <span data-ttu-id="acfb8-112">プロシージャを呼び出すときに、このパラメーターが必要ないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="acfb8-112">Specifies that this parameter is not required when the procedure is called.</span></span>

`ByVal`  
<span data-ttu-id="acfb8-113">省略可。</span><span class="sxs-lookup"><span data-stu-id="acfb8-113">Optional.</span></span> <span data-ttu-id="acfb8-114">プロシージャが、呼び出し元のコードの対応する引数の基になる変数要素を置換または再割り当てできないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="acfb8-114">Specifies that the procedure cannot replace or reassign the variable element underlying the corresponding argument in the calling code.</span></span>

`ByRef`  
<span data-ttu-id="acfb8-115">省略可。</span><span class="sxs-lookup"><span data-stu-id="acfb8-115">Optional.</span></span> <span data-ttu-id="acfb8-116">プロシージャが、呼び出し元のコード自体と同じように、呼び出し元のコード内の基になる変数要素を変更できることを指定します。</span><span class="sxs-lookup"><span data-stu-id="acfb8-116">Specifies that the procedure can modify the underlying variable element in the calling code the same way the calling code itself can.</span></span>

`ParamArray`  
<span data-ttu-id="acfb8-117">省略可。</span><span class="sxs-lookup"><span data-stu-id="acfb8-117">Optional.</span></span> <span data-ttu-id="acfb8-118">パラメーターリストの最後のパラメーターが、指定されたデータ型の要素のオプションの配列であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="acfb8-118">Specifies that the last parameter in the parameter list is an optional array of elements of the specified data type.</span></span> <span data-ttu-id="acfb8-119">これにより、呼び出し元のコードは、プロシージャに任意の数の引数を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="acfb8-119">This lets the calling code pass an arbitrary number of arguments to the procedure.</span></span>

`parametername`  
<span data-ttu-id="acfb8-120">必須。</span><span class="sxs-lookup"><span data-stu-id="acfb8-120">Required.</span></span> <span data-ttu-id="acfb8-121">パラメーターを表すローカル変数の名前。</span><span class="sxs-lookup"><span data-stu-id="acfb8-121">Name of the local variable representing the parameter.</span></span>

`parametertype`  
<span data-ttu-id="acfb8-122">`Option Strict` が `On`の場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="acfb8-122">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="acfb8-123">パラメーターを表すローカル変数のデータ型。</span><span class="sxs-lookup"><span data-stu-id="acfb8-123">Data type of the local variable representing the parameter.</span></span>

`defaultvalue`  
<span data-ttu-id="acfb8-124">`Optional` パラメーターに必要です。</span><span class="sxs-lookup"><span data-stu-id="acfb8-124">Required for `Optional` parameters.</span></span> <span data-ttu-id="acfb8-125">パラメーターのデータ型に評価される定数または定数式。</span><span class="sxs-lookup"><span data-stu-id="acfb8-125">Any constant or constant expression that evaluates to the data type of the parameter.</span></span> <span data-ttu-id="acfb8-126">型が `Object`、クラス、インターフェイス、配列、または構造体の場合、既定値は `Nothing`のみ可能です。</span><span class="sxs-lookup"><span data-stu-id="acfb8-126">If the type is `Object`, or a class, interface, array, or structure, the default value can only be `Nothing`.</span></span>

## <a name="remarks"></a><span data-ttu-id="acfb8-127">コメント</span><span class="sxs-lookup"><span data-stu-id="acfb8-127">Remarks</span></span>

<span data-ttu-id="acfb8-128">パラメーターは、かっこで囲まれ、コンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="acfb8-128">Parameters are surrounded by parentheses and separated by commas.</span></span> <span data-ttu-id="acfb8-129">パラメーターは任意のデータ型で宣言できます。</span><span class="sxs-lookup"><span data-stu-id="acfb8-129">A parameter can be declared with any data type.</span></span> <span data-ttu-id="acfb8-130">`parametertype`を指定しない場合、既定で `Object`が使用されます。</span><span class="sxs-lookup"><span data-stu-id="acfb8-130">If you do not specify `parametertype`, it defaults to `Object`.</span></span>

<span data-ttu-id="acfb8-131">呼び出し元のコードがプロシージャを呼び出すと、必要な各パラメーターに*引数*が渡されます。</span><span class="sxs-lookup"><span data-stu-id="acfb8-131">When the calling code calls the procedure, it passes an *argument* to each required parameter.</span></span> <span data-ttu-id="acfb8-132">詳細については、「[パラメーターと引数の違い](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acfb8-132">For more information, see [Differences Between Parameters and Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).</span></span>

<span data-ttu-id="acfb8-133">呼び出し元のコードが各パラメーターに渡す引数は、呼び出し元のコード内の基になる要素へのポインターです。</span><span class="sxs-lookup"><span data-stu-id="acfb8-133">The argument the calling code passes to each parameter is a pointer to an underlying element in the calling code.</span></span> <span data-ttu-id="acfb8-134">この要素が*不変* (定数、リテラル、列挙型、または式) の場合、どのコードでも変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="acfb8-134">If this element is *nonvariable* (a constant, literal, enumeration, or expression), it is impossible for any code to change it.</span></span> <span data-ttu-id="acfb8-135">*変数*要素 (宣言された変数、フィールド、プロパティ、配列要素、または構造体要素) の場合は、呼び出し元のコードで変更できます。</span><span class="sxs-lookup"><span data-stu-id="acfb8-135">If it is a *variable* element (a declared variable, field, property, array element, or structure element), the calling code can change it.</span></span> <span data-ttu-id="acfb8-136">詳細については、「[変更できる引数と変更できない引数の違い](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acfb8-136">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).</span></span>

<span data-ttu-id="acfb8-137">変数要素が `ByRef`渡された場合は、プロシージャでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="acfb8-137">If a variable element is passed `ByRef`, the procedure can change it as well.</span></span> <span data-ttu-id="acfb8-138">詳細については、「[引数を値で渡す方法と参照渡しの違い](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acfb8-138">For more information, see [Differences Between Passing an Argument By Value and By Reference](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>

## <a name="rules"></a><span data-ttu-id="acfb8-139">ルール</span><span class="sxs-lookup"><span data-stu-id="acfb8-139">Rules</span></span>

- <span data-ttu-id="acfb8-140">\*\*かっこ。</span><span class="sxs-lookup"><span data-stu-id="acfb8-140">**Parentheses.**</span></span> <span data-ttu-id="acfb8-141">\*\* パラメーターリストを指定する場合は、かっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="acfb8-141">If you specify a parameter list, you must enclose it in parentheses.</span></span> <span data-ttu-id="acfb8-142">パラメーターがない場合でも、空のリストを囲むかっこを使用できます。</span><span class="sxs-lookup"><span data-stu-id="acfb8-142">If there are no parameters, you can still use parentheses enclosing an empty list.</span></span> <span data-ttu-id="acfb8-143">これにより、要素がプロシージャであることを明確にすることで、コードの読みやすさが向上します。</span><span class="sxs-lookup"><span data-stu-id="acfb8-143">This improves the readability of your code by clarifying that the element is a procedure.</span></span>

- <span data-ttu-id="acfb8-144">**省略可能なパラメーター。**</span><span class="sxs-lookup"><span data-stu-id="acfb8-144">**Optional Parameters.**</span></span> <span data-ttu-id="acfb8-145">パラメーターで `Optional` 修飾子を使用する場合は、リスト内の後続のすべてのパラメーターも省略可能であり、`Optional` 修飾子を使用して宣言されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="acfb8-145">If you use the `Optional` modifier on a parameter, all subsequent parameters in the list must also be optional and be declared by using the `Optional` modifier.</span></span>

     <span data-ttu-id="acfb8-146">省略可能なすべてのパラメーター宣言では、`defaultvalue` 句を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="acfb8-146">Every optional parameter declaration must supply the `defaultvalue` clause.</span></span>

     <span data-ttu-id="acfb8-147">詳細については、「[省略可能なパラメーター](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acfb8-147">For more information, see [Optional Parameters](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).</span></span>

- <span data-ttu-id="acfb8-148">**パラメーター配列。**</span><span class="sxs-lookup"><span data-stu-id="acfb8-148">**Parameter Arrays.**</span></span> <span data-ttu-id="acfb8-149">`ParamArray` パラメーターには `ByVal` を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="acfb8-149">You must specify `ByVal` for a `ParamArray` parameter.</span></span>

     <span data-ttu-id="acfb8-150">同じパラメーターリストで `Optional` と `ParamArray` の両方を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="acfb8-150">You cannot use both `Optional` and `ParamArray` in the same parameter list.</span></span>

     <span data-ttu-id="acfb8-151">詳細については、「[パラメーター配列](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acfb8-151">For more information, see [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>

- <span data-ttu-id="acfb8-152">**渡すメカニズム。**</span><span class="sxs-lookup"><span data-stu-id="acfb8-152">**Passing Mechanism.**</span></span> <span data-ttu-id="acfb8-153">すべての引数の既定の機構は `ByVal`です。これは、プロシージャが基になる変数要素を変更できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="acfb8-153">The default mechanism for every argument is `ByVal`, which means the procedure cannot change the underlying variable element.</span></span> <span data-ttu-id="acfb8-154">ただし、要素が参照型の場合、このプロシージャでは、オブジェクト自体を置き換えることも再割り当てできない場合でも、基になるオブジェクトの内容やメンバーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="acfb8-154">However, if the element is a reference type, the procedure can modify the contents or members of the underlying object, even though it cannot replace or reassign the object itself.</span></span>

- <span data-ttu-id="acfb8-155">**パラメーター名。**</span><span class="sxs-lookup"><span data-stu-id="acfb8-155">**Parameter Names.**</span></span> <span data-ttu-id="acfb8-156">パラメーターのデータ型が配列である場合は、`parametername` の直後にかっこを入力します。</span><span class="sxs-lookup"><span data-stu-id="acfb8-156">If the parameter's data type is an array, follow `parametername` immediately by parentheses.</span></span> <span data-ttu-id="acfb8-157">パラメーター名の詳細については、「[宣言された要素の名前](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acfb8-157">For more information on parameter names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

## <a name="example"></a><span data-ttu-id="acfb8-158">例</span><span class="sxs-lookup"><span data-stu-id="acfb8-158">Example</span></span>

<span data-ttu-id="acfb8-159">次の例は、2つのパラメーターを定義する `Function` プロシージャを示しています。</span><span class="sxs-lookup"><span data-stu-id="acfb8-159">The following example shows a `Function` procedure that defines two parameters.</span></span>

[!code-vb[VbVbalrStatements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#2)]

## <a name="see-also"></a><span data-ttu-id="acfb8-160">参照</span><span class="sxs-lookup"><span data-stu-id="acfb8-160">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="acfb8-161">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="acfb8-161">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="acfb8-162">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="acfb8-162">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="acfb8-163">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="acfb8-163">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="acfb8-164">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="acfb8-164">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="acfb8-165">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="acfb8-165">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="acfb8-166">属性の概要</span><span class="sxs-lookup"><span data-stu-id="acfb8-166">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="acfb8-167">方法 : コード内でステートメントを分割および連結する</span><span class="sxs-lookup"><span data-stu-id="acfb8-167">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
