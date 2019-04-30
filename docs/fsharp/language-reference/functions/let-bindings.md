---
title: let バインド
description: 使用する方法について説明します、 F# 'let' バインドの値または関数の識別子を関連付けます。
ms.date: 05/16/2016
ms.openlocfilehash: 45de82acf6f4423698cd8037266968e023f40dcb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941005"
---
# <a name="let-bindings"></a><span data-ttu-id="4ecf6-103">let バインド</span><span class="sxs-lookup"><span data-stu-id="4ecf6-103">let Bindings</span></span>

<span data-ttu-id="4ecf6-104">A*バインド*を値または関数と識別子を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-104">A *binding* associates an identifier with a value or function.</span></span> <span data-ttu-id="4ecf6-105">使用する、`let`値または関数に名前をバインドするキーワード。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-105">You use the `let` keyword to bind a name to a value or function.</span></span>

## <a name="syntax"></a><span data-ttu-id="4ecf6-106">構文</span><span class="sxs-lookup"><span data-stu-id="4ecf6-106">Syntax</span></span>

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a><span data-ttu-id="4ecf6-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="4ecf6-107">Remarks</span></span>

<span data-ttu-id="4ecf6-108">`let`キーワード値または関数名の値を 1 つまたは複数定義する式のバインドで使用されます。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-108">The `let` keyword is used in binding expressions to define values or function values for one or more names.</span></span> <span data-ttu-id="4ecf6-109">最も単純な形式、`let`式の名前からの単純な値の次のようにバインドします。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-109">The simplest form of the `let` expression binds a name to a simple value, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

<span data-ttu-id="4ecf6-110">新しい行を使用して、識別子から式を分離する場合は、次のコードのように、式の各行をインデントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-110">If you separate the expression from the identifier by using a new line, you must indent each line of the expression, as in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

<span data-ttu-id="4ecf6-111">名前だけではなく、名前を含むパターンを指定できますが、たとえば、タプル次のコードに示すようにします。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-111">Instead of just a name, a pattern that contains names can be specified, for example, a tuple, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

<span data-ttu-id="4ecf6-112">*式の本体*名前が使用される式です。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-112">The *body-expression* is the expression in which the names are used.</span></span> <span data-ttu-id="4ecf6-113">式の本体が最初の文字と完全にする行にインデント、独自の行に表示されます、`let`キーワード。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-113">The body expression appears on its own line, indented to line up exactly with the first character in the `let` keyword:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

<span data-ttu-id="4ecf6-114">A`let`バインドに記述できるクラス型の定義で、またはローカルのスコープで、モジュール レベル関数の定義のようにします。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-114">A `let` binding can appear at the module level, in the definition of a class type, or in local scopes, such as in a function definition.</span></span> <span data-ttu-id="4ecf6-115">A`let`最上位レベルのモジュールまたはクラス型のバインドは、本文の式を指定する必要はありませんが、他のスコープ レベルでは、式の本体が必要です。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-115">A `let` binding at the top level in a module or in a class type does not need to have a body expression, but at other scope levels, the body expression is required.</span></span> <span data-ttu-id="4ecf6-116">前に、任意の時点ではなくが、定義の時点より後バインド名は使用可能な`let`は次のコードに示すように、バインドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-116">The bound names are usable after the point of definition, but not at any point before the `let` binding appears, as is illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]

## <a name="function-bindings"></a><span data-ttu-id="4ecf6-117">関数のバインディング</span><span class="sxs-lookup"><span data-stu-id="4ecf6-117">Function Bindings</span></span>

<span data-ttu-id="4ecf6-118">関数バインドは関数バインドでは関数名をパラメーターでは、次のコードに示すように準じた値のバインディングの規則に従います。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-118">Function bindings follow the rules for value bindings, except that function bindings include the function name and the parameters, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

<span data-ttu-id="4ecf6-119">一般に、パラメーターは、タプル パターンなどのパターンです。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-119">In general, parameters are patterns, such as a tuple pattern:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

<span data-ttu-id="4ecf6-120">A`let`最後の式の値に評価される式をバインドします。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-120">A `let` binding expression evaluates to the value of the last expression.</span></span> <span data-ttu-id="4ecf6-121">そのため、次のコード例の値で`result`から計算`100 * function3 (1, 2)`に評価されます`300`します。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-121">Therefore, in the following code example, the value of `result` is computed from `100 * function3 (1, 2)`, which evaluates to `300`.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

<span data-ttu-id="4ecf6-122">詳細については、「[関数](index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-122">For more information, see [Functions](index.md).</span></span>

## <a name="type-annotations"></a><span data-ttu-id="4ecf6-123">型の注釈</span><span class="sxs-lookup"><span data-stu-id="4ecf6-123">Type Annotations</span></span>

<span data-ttu-id="4ecf6-124">後にかっこで囲まれているすべての型名、コロン (:) を含めることによって、型パラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-124">You can specify types for parameters by including a colon (:) followed by a type name, all enclosed in parentheses.</span></span> <span data-ttu-id="4ecf6-125">最後のパラメーターの後にコロンと型を追加して、戻り値の型を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-125">You can also specify the type of the return value by appending the colon and type after the last parameter.</span></span> <span data-ttu-id="4ecf6-126">完全な型注釈には、`function1`パラメーターの型として整数であるようにします。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-126">The full type annotations for `function1`, with integers as the parameter types, would be as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

<span data-ttu-id="4ecf6-127">明示的な型のパラメーターがない場合は、関数のパラメーターの種類を決定する型の推定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-127">When there are no explicit type parameters, type inference is used to determine the types of parameters of functions.</span></span> <span data-ttu-id="4ecf6-128">これをジェネリック パラメーターの型を自動的に一般化を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-128">This can include automatically generalizing the type of a parameter to be generic.</span></span>

<span data-ttu-id="4ecf6-129">詳細については、次を参照してください。[自動ジェネリック化](../generics/automatic-generalization.md)と[型の推定](../type-inference.md)します。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-129">For more information, see [Automatic Generalization](../generics/automatic-generalization.md) and [Type Inference](../type-inference.md).</span></span>

## <a name="let-bindings-in-classes"></a><span data-ttu-id="4ecf6-130">クラス内の let 束縛</span><span class="sxs-lookup"><span data-stu-id="4ecf6-130">let Bindings in Classes</span></span>

<span data-ttu-id="4ecf6-131">A`let`構造体またはレコードの種類ではなく、クラス型にバインドを表示できます。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-131">A `let` binding can appear in a class type but not in a structure or record type.</span></span> <span data-ttu-id="4ecf6-132">Let クラス型でバインディングを使用するには、クラスは、プライマリ コンス トラクターをいる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-132">To use a let binding in a class type, the class must have a primary constructor.</span></span> <span data-ttu-id="4ecf6-133">コンス トラクターのパラメーターは、クラス定義内の型名の後に表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-133">Constructor parameters must appear after the type name in the class definition.</span></span> <span data-ttu-id="4ecf6-134">A`let`クラス型のバインディングは、プライベート フィールドとそのクラス型と、と共にメンバーを定義します。`do`バインドの種類では、型のプライマリ コンス トラクターのコードをフォーム。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-134">A `let` binding in a class type defines private fields and members for that class type and, together with `do` bindings in the type, forms the code for the primary constructor for the type.</span></span> <span data-ttu-id="4ecf6-135">次のコード例は、クラスを表示する`MyClass`プライベート フィールドを持つ`field1`と`field2`します。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-135">The following code examples show a class `MyClass` with private fields `field1` and `field2`.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

<span data-ttu-id="4ecf6-136">スコープ`field1`と`field2`は宣言されている型に制限されます。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-136">The scopes of `field1` and `field2` are limited to the type in which they are declared.</span></span> <span data-ttu-id="4ecf6-137">詳細については、次を参照してください。 [ `let`クラス内のバインディング](../members/let-bindings-in-classes.md)と[クラス](../classes.md)します。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-137">For more information, see [`let` Bindings in Classes](../members/let-bindings-in-classes.md) and [Classes](../classes.md).</span></span>

## <a name="type-parameters-in-let-bindings"></a><span data-ttu-id="4ecf6-138">型パラメーターの let 束縛</span><span class="sxs-lookup"><span data-stu-id="4ecf6-138">Type Parameters in let Bindings</span></span>

<span data-ttu-id="4ecf6-139">A`let`型、またはコンピュテーション式で、モジュール レベルでバインドが明示的な型のパラメーターを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-139">A `let` binding at the module level, in a type, or in a computation expression can have explicit type parameters.</span></span> <span data-ttu-id="4ecf6-140">Let 関数の定義内など、式の中でバインディングには、型パラメーターを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-140">A let binding in an expression, such as within a function definition, cannot have type parameters.</span></span> <span data-ttu-id="4ecf6-141">詳細については、「[ジェネリック](../generics/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-141">For more information, see [Generics](../generics/index.md).</span></span>

## <a name="attributes-on-let-bindings"></a><span data-ttu-id="4ecf6-142">属性の let 束縛</span><span class="sxs-lookup"><span data-stu-id="4ecf6-142">Attributes on let Bindings</span></span>

<span data-ttu-id="4ecf6-143">属性は、最上位レベルに適用できる`let`モジュールに、次のコードに示すようにバインドします。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-143">Attributes can be applied to top-level `let` bindings in a module, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]

## <a name="scope-and-accessibility-of-let-bindings"></a><span data-ttu-id="4ecf6-144">スコープとユーザー補助の Let バインド</span><span class="sxs-lookup"><span data-stu-id="4ecf6-144">Scope and Accessibility of Let Bindings</span></span>

<span data-ttu-id="4ecf6-145">Let によるバインドで宣言されたエンティティのスコープを含むの部分に制限されていますが、バインドが表示された後のスコープを (関数、モジュール、ファイル クラスなど)。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-145">The scope of an entity declared with a let binding is limited to the portion of the containing scope (such as a function, module, file or class) after the binding appears.</span></span> <span data-ttu-id="4ecf6-146">そのため、そのことが言えます let によるバインドがスコープに名前を導入します。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-146">Therefore, it can be said that a let binding introduces a name into a scope.</span></span> <span data-ttu-id="4ecf6-147">モジュールに let バインドされた値または関数モジュールのクライアントにアクセスできる限りは、モジュール内の let バインドは、モジュールのパブリック関数にコンパイルされるため、モジュールがアクセス可能で。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-147">In a module, a let-bound value or function is accessible to clients of a module as long as the module is accessible, since the let bindings in a module are compiled into public functions of the module.</span></span> <span data-ttu-id="4ecf6-148">これに対し、let バインド クラスでは、クラスにプライベートです。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-148">By contrast, let bindings in a class are private to the class.</span></span>

<span data-ttu-id="4ecf6-149">通常、モジュール内の関数は、クライアント コードで使用すると、モジュールの名前で修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-149">Normally, functions in modules must be qualified by the name of the module when used by client code.</span></span> <span data-ttu-id="4ecf6-150">たとえば、モジュール`Module1`関数があります`function1`、ユーザーは指定`Module1.function1`関数を参照します。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-150">For example, if a module `Module1` has a function `function1`, users would specify `Module1.function1` to refer to the function.</span></span>

<span data-ttu-id="4ecf6-151">モジュールのユーザーは、インポート宣言を使用して、モジュール名によって修飾されることがなくそのモジュール内の関数を使用できるようにすることがあります。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-151">Users of a module may use an import declaration to make the functions within that module available for use without being qualified by the module name.</span></span> <span data-ttu-id="4ecf6-152">先ほど説明した例では、モジュールのユーザー開くことができる場合、モジュールのインポート宣言のオープンを使用して`Module1`し、その後を参照してください`function1`直接します。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-152">In the example just mentioned, users of the module can in that case open the module by using the import declaration open `Module1` and thereafter refer to `function1` directly.</span></span>

```fsharp
module Module1 =
    let function1 x = x + 1.0

module Module2 =
    let function2 x =
        Module1.function1 x

open Module1

let function3 x =
    function1 x
```

<span data-ttu-id="4ecf6-153">一部のモジュールは、属性を持つ[RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15)、つまり、モジュールの名前で公開されている関数を修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-153">Some modules have the attribute [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), which means that the functions that they expose must be qualified with the name of the module.</span></span> <span data-ttu-id="4ecf6-154">たとえば、F# List モジュールには、この属性があります。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-154">For example, the F# List module has this attribute.</span></span>

<span data-ttu-id="4ecf6-155">モジュールとアクセス制御の詳細については、次を参照してください。[モジュール](../modules.md)と[アクセス制御](../access-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="4ecf6-155">For more information on modules and access control, see [Modules](../modules.md) and [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4ecf6-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ecf6-156">See also</span></span>

- [<span data-ttu-id="4ecf6-157">関数</span><span class="sxs-lookup"><span data-stu-id="4ecf6-157">Functions</span></span>](index.md)
- [<span data-ttu-id="4ecf6-158">クラス内の `let` バインド</span><span class="sxs-lookup"><span data-stu-id="4ecf6-158">`let` Bindings in Classes</span></span>](../members/let-bindings-in-classes.md)