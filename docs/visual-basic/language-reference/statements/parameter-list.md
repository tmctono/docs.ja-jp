---
title: パラメーター リスト (Visual Basic)
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
ms.openlocfilehash: e58d80896d11b4154c7197d4cdaf73a536fdd5e7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64583550"
---
# <a name="parameter-list-visual-basic"></a><span data-ttu-id="30ccf-102">パラメーター リスト (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="30ccf-102">Parameter List (Visual Basic)</span></span>
<span data-ttu-id="30ccf-103">プロシージャは呼び出された場合、パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="30ccf-103">Specifies the parameters a procedure expects when it is called.</span></span> <span data-ttu-id="30ccf-104">複数のパラメーターは、コンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="30ccf-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="30ccf-105">1 つのパラメーターの構文を次に示します。</span><span class="sxs-lookup"><span data-stu-id="30ccf-105">The following is the syntax for one parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30ccf-106">構文</span><span class="sxs-lookup"><span data-stu-id="30ccf-106">Syntax</span></span>  
  
```  
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]   
parametername[( )] [ As parametertype ] [ = defaultvalue ]  
```  
  
## <a name="parts"></a><span data-ttu-id="30ccf-107">指定項目</span><span class="sxs-lookup"><span data-stu-id="30ccf-107">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="30ccf-108">任意。</span><span class="sxs-lookup"><span data-stu-id="30ccf-108">Optional.</span></span> <span data-ttu-id="30ccf-109">このパラメーターに適用される属性の一覧です。</span><span class="sxs-lookup"><span data-stu-id="30ccf-109">List of attributes that apply to this parameter.</span></span> <span data-ttu-id="30ccf-110">囲む必要があります、[属性リスト](../../../visual-basic/language-reference/statements/attribute-list.md)山かっこ ("`<`「と」`>`")。</span><span class="sxs-lookup"><span data-stu-id="30ccf-110">You must enclose the [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>  
  
 `Optional`  
 <span data-ttu-id="30ccf-111">任意。</span><span class="sxs-lookup"><span data-stu-id="30ccf-111">Optional.</span></span> <span data-ttu-id="30ccf-112">プロシージャが呼び出されたときに、このパラメーターが必要ないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="30ccf-112">Specifies that this parameter is not required when the procedure is called.</span></span>  
  
 `ByVal`  
 <span data-ttu-id="30ccf-113">任意。</span><span class="sxs-lookup"><span data-stu-id="30ccf-113">Optional.</span></span> <span data-ttu-id="30ccf-114">プロシージャが置換または呼び出し元のコードに対応する引数の基になる変数の要素を再割り当てできませんを指定します。</span><span class="sxs-lookup"><span data-stu-id="30ccf-114">Specifies that the procedure cannot replace or reassign the variable element underlying the corresponding argument in the calling code.</span></span>  
  
 `ByRef`  
 <span data-ttu-id="30ccf-115">任意。</span><span class="sxs-lookup"><span data-stu-id="30ccf-115">Optional.</span></span> <span data-ttu-id="30ccf-116">あるプロシージャ要素を変更できます、基になる変数呼び出し元のコードで呼び出し元コード自体と同じようを指定します。</span><span class="sxs-lookup"><span data-stu-id="30ccf-116">Specifies that the procedure can modify the underlying variable element in the calling code the same way the calling code itself can.</span></span>  
  
 `ParamArray`  
 <span data-ttu-id="30ccf-117">任意。</span><span class="sxs-lookup"><span data-stu-id="30ccf-117">Optional.</span></span> <span data-ttu-id="30ccf-118">パラメーター リストの最後のパラメーターが指定されたデータ型の要素の省略可能な配列であることを示します。</span><span class="sxs-lookup"><span data-stu-id="30ccf-118">Specifies that the last parameter in the parameter list is an optional array of elements of the specified data type.</span></span> <span data-ttu-id="30ccf-119">これには、呼び出し元のコード、プロシージャに任意の数の引数を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="30ccf-119">This lets the calling code pass an arbitrary number of arguments to the procedure.</span></span>  
  
 `parametername`  
 <span data-ttu-id="30ccf-120">必須。</span><span class="sxs-lookup"><span data-stu-id="30ccf-120">Required.</span></span> <span data-ttu-id="30ccf-121">パラメーターを表すローカル変数の名前です。</span><span class="sxs-lookup"><span data-stu-id="30ccf-121">Name of the local variable representing the parameter.</span></span>  
  
 `parametertype`  
 <span data-ttu-id="30ccf-122">場合に、必ず`Option Strict`は`On`します。</span><span class="sxs-lookup"><span data-stu-id="30ccf-122">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="30ccf-123">パラメーターを表すローカル変数のデータ型。</span><span class="sxs-lookup"><span data-stu-id="30ccf-123">Data type of the local variable representing the parameter.</span></span>  
  
 `defaultvalue`  
 <span data-ttu-id="30ccf-124">必要な`Optional`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="30ccf-124">Required for `Optional` parameters.</span></span> <span data-ttu-id="30ccf-125">パラメーターのデータ型に評価される定数または定数式です。</span><span class="sxs-lookup"><span data-stu-id="30ccf-125">Any constant or constant expression that evaluates to the data type of the parameter.</span></span> <span data-ttu-id="30ccf-126">型の場合`Object`、クラス、インターフェイス、配列、または構造体では、既定値を指定できますのみまたは`Nothing`します。</span><span class="sxs-lookup"><span data-stu-id="30ccf-126">If the type is `Object`, or a class, interface, array, or structure, the default value can only be `Nothing`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30ccf-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="30ccf-127">Remarks</span></span>  
 <span data-ttu-id="30ccf-128">パラメーターはかっこで囲むし、コンマで区切られました。</span><span class="sxs-lookup"><span data-stu-id="30ccf-128">Parameters are surrounded by parentheses and separated by commas.</span></span> <span data-ttu-id="30ccf-129">任意のデータ型では、パラメーターを宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="30ccf-129">A parameter can be declared with any data type.</span></span> <span data-ttu-id="30ccf-130">指定しない場合`parametertype`、既定値は`Object`します。</span><span class="sxs-lookup"><span data-stu-id="30ccf-130">If you do not specify `parametertype`, it defaults to `Object`.</span></span>  
  
 <span data-ttu-id="30ccf-131">呼び出し元のコードはプロシージャを呼び出す際に渡して、*引数*必要な各パラメーターにします。</span><span class="sxs-lookup"><span data-stu-id="30ccf-131">When the calling code calls the procedure, it passes an *argument* to each required parameter.</span></span> <span data-ttu-id="30ccf-132">詳細については、次を参照してください。[の相違点の間でパラメーターと引数](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md)します。</span><span class="sxs-lookup"><span data-stu-id="30ccf-132">For more information, see [Differences Between Parameters and Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).</span></span>  
  
 <span data-ttu-id="30ccf-133">呼び出し元のコードは、各パラメーターに渡す引数は、呼び出し元のコード内の基になる要素へのポインターです。</span><span class="sxs-lookup"><span data-stu-id="30ccf-133">The argument the calling code passes to each parameter is a pointer to an underlying element in the calling code.</span></span> <span data-ttu-id="30ccf-134">この要素が場合*不変*(定数、リテラル、列挙型、または式)、すべてのコードを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="30ccf-134">If this element is *nonvariable* (a constant, literal, enumeration, or expression), it is impossible for any code to change it.</span></span> <span data-ttu-id="30ccf-135">ある場合、*変数*要素 (宣言された変数、フィールド、プロパティ、配列の要素、または構造体の要素)、呼び出し元のコードを変更できます。</span><span class="sxs-lookup"><span data-stu-id="30ccf-135">If it is a *variable* element (a declared variable, field, property, array element, or structure element), the calling code can change it.</span></span> <span data-ttu-id="30ccf-136">詳細については、次を参照してください。[変更の間の相違点と変更できない引数](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md)します。</span><span class="sxs-lookup"><span data-stu-id="30ccf-136">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).</span></span>  
  
 <span data-ttu-id="30ccf-137">Variable 要素が渡された場合`ByRef`プロシージャがも変更できます。</span><span class="sxs-lookup"><span data-stu-id="30ccf-137">If a variable element is passed `ByRef`, the procedure can change it as well.</span></span> <span data-ttu-id="30ccf-138">詳細については、次を参照してください。[の相違点の間の値と参照渡しによって引数を渡す](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md)します。</span><span class="sxs-lookup"><span data-stu-id="30ccf-138">For more information, see [Differences Between Passing an Argument By Value and By Reference](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="30ccf-139">ルール</span><span class="sxs-lookup"><span data-stu-id="30ccf-139">Rules</span></span>  
  
- <span data-ttu-id="30ccf-140">**かっこです。**</span><span class="sxs-lookup"><span data-stu-id="30ccf-140">**Parentheses.**</span></span> <span data-ttu-id="30ccf-141">パラメーター リストを指定する場合は、かっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="30ccf-141">If you specify a parameter list, you must enclose it in parentheses.</span></span> <span data-ttu-id="30ccf-142">パラメーターがない場合は、空のリストを囲むかっこを引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="30ccf-142">If there are no parameters, you can still use parentheses enclosing an empty list.</span></span> <span data-ttu-id="30ccf-143">これにより、プロシージャに要素が明確にすることによって、コードの読みやすさが向上します。</span><span class="sxs-lookup"><span data-stu-id="30ccf-143">This improves the readability of your code by clarifying that the element is a procedure.</span></span>  
  
- <span data-ttu-id="30ccf-144">**省略可能なパラメーター。**</span><span class="sxs-lookup"><span data-stu-id="30ccf-144">**Optional Parameters.**</span></span> <span data-ttu-id="30ccf-145">使用する場合、`Optional`パラメーター修飾子の一覧ですべての後続のパラメーターはオプションもありを使用して宣言する、`Optional`修飾子。</span><span class="sxs-lookup"><span data-stu-id="30ccf-145">If you use the `Optional` modifier on a parameter, all subsequent parameters in the list must also be optional and be declared by using the `Optional` modifier.</span></span>  
  
     <span data-ttu-id="30ccf-146">すべての省略可能なパラメーター宣言を指定する必要があります、`defaultvalue`句。</span><span class="sxs-lookup"><span data-stu-id="30ccf-146">Every optional parameter declaration must supply the `defaultvalue` clause.</span></span>  
  
     <span data-ttu-id="30ccf-147">詳細については、次を参照してください。[省略可能なパラメーター](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)します。</span><span class="sxs-lookup"><span data-stu-id="30ccf-147">For more information, see [Optional Parameters](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).</span></span>  
  
- <span data-ttu-id="30ccf-148">**パラメーターの配列。**</span><span class="sxs-lookup"><span data-stu-id="30ccf-148">**Parameter Arrays.**</span></span> <span data-ttu-id="30ccf-149">指定する必要があります`ByVal`の`ParamArray`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="30ccf-149">You must specify `ByVal` for a `ParamArray` parameter.</span></span>  
  
     <span data-ttu-id="30ccf-150">両方を使用することはできません`Optional`と`ParamArray`パラメーター リストを同じにします。</span><span class="sxs-lookup"><span data-stu-id="30ccf-150">You cannot use both `Optional` and `ParamArray` in the same parameter list.</span></span>  
  
     <span data-ttu-id="30ccf-151">詳細については、次を参照してください。[パラメーター配列](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)します。</span><span class="sxs-lookup"><span data-stu-id="30ccf-151">For more information, see [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
- <span data-ttu-id="30ccf-152">**値渡し。**</span><span class="sxs-lookup"><span data-stu-id="30ccf-152">**Passing Mechanism.**</span></span> <span data-ttu-id="30ccf-153">すべての引数について既定のメカニズムは`ByVal`手順、つまり基になる可変要素を変更できません。</span><span class="sxs-lookup"><span data-stu-id="30ccf-153">The default mechanism for every argument is `ByVal`, which means the procedure cannot change the underlying variable element.</span></span> <span data-ttu-id="30ccf-154">ただし、要素が参照型の場合は、プロシージャが変更できます内容や、基になるオブジェクトのメンバーでも交換や、オブジェクト自体を再割り当てはできません。</span><span class="sxs-lookup"><span data-stu-id="30ccf-154">However, if the element is a reference type, the procedure can modify the contents or members of the underlying object, even though it cannot replace or reassign the object itself.</span></span>  
  
- <span data-ttu-id="30ccf-155">**パラメーター名。**</span><span class="sxs-lookup"><span data-stu-id="30ccf-155">**Parameter Names.**</span></span> <span data-ttu-id="30ccf-156">次のパラメーターのデータ型が配列の場合は、`parametername`かっこの直後にします。</span><span class="sxs-lookup"><span data-stu-id="30ccf-156">If the parameter's data type is an array, follow `parametername` immediately by parentheses.</span></span> <span data-ttu-id="30ccf-157">パラメーター名の詳細については、次を参照してください。 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)します。</span><span class="sxs-lookup"><span data-stu-id="30ccf-157">For more information on parameter names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="30ccf-158">例</span><span class="sxs-lookup"><span data-stu-id="30ccf-158">Example</span></span>  
 <span data-ttu-id="30ccf-159">次の例は、`Function`プロシージャを 2 つのパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="30ccf-159">The following example shows a `Function` procedure that defines two parameters.</span></span>  
  
 [!code-vb[VbVbalrStatements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="30ccf-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="30ccf-160">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="30ccf-161">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="30ccf-161">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="30ccf-162">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="30ccf-162">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="30ccf-163">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="30ccf-163">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="30ccf-164">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="30ccf-164">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="30ccf-165">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="30ccf-165">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="30ccf-166">属性の概要</span><span class="sxs-lookup"><span data-stu-id="30ccf-166">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="30ccf-167">方法: コード内でステートメントを分割および連結する</span><span class="sxs-lookup"><span data-stu-id="30ccf-167">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
