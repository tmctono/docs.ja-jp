---
title: let 束縛
description: "識別子を値または関数に関連付ける F # ' let ' バインドの使用方法について説明します。"
ms.date: 05/16/2016
ms.openlocfilehash: 6f2396f480c5e6c631d0022f4732419ee5b07db6
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812225"
---
# <a name="let-bindings"></a><span data-ttu-id="16023-103">let 束縛</span><span class="sxs-lookup"><span data-stu-id="16023-103">let Bindings</span></span>

<span data-ttu-id="16023-104">*バインド*は、識別子を値または関数に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="16023-104">A *binding* associates an identifier with a value or function.</span></span> <span data-ttu-id="16023-105">キーワードを使用して、 `let` 名前を値または関数にバインドします。</span><span class="sxs-lookup"><span data-stu-id="16023-105">You use the `let` keyword to bind a name to a value or function.</span></span>

## <a name="syntax"></a><span data-ttu-id="16023-106">構文</span><span class="sxs-lookup"><span data-stu-id="16023-106">Syntax</span></span>

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a><span data-ttu-id="16023-107">解説</span><span class="sxs-lookup"><span data-stu-id="16023-107">Remarks</span></span>

<span data-ttu-id="16023-108">キーワードは、 `let` 1 つまたは複数の名前の値または関数の値を定義するために、バインド式で使用されます。</span><span class="sxs-lookup"><span data-stu-id="16023-108">The `let` keyword is used in binding expressions to define values or function values for one or more names.</span></span> <span data-ttu-id="16023-109">式の最も単純な形式は、次のよう `let` に単純な値に名前をバインドします。</span><span class="sxs-lookup"><span data-stu-id="16023-109">The simplest form of the `let` expression binds a name to a simple value, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

<span data-ttu-id="16023-110">新しい行を使用して識別子から式を分離する場合は、次のコードのように、式の各行をインデントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="16023-110">If you separate the expression from the identifier by using a new line, you must indent each line of the expression, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

<span data-ttu-id="16023-111">次のコードに示すように、名前だけでなく、名前を含むパターンを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="16023-111">Instead of just a name, a pattern that contains names can be specified, for example, a tuple, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

<span data-ttu-id="16023-112">*本体式*は、名前が使用される式です。</span><span class="sxs-lookup"><span data-stu-id="16023-112">The *body-expression* is the expression in which the names are used.</span></span> <span data-ttu-id="16023-113">本文の式は、キーワード内の最初の文字と正確に一致する行にインデントされてい `let` ます。</span><span class="sxs-lookup"><span data-stu-id="16023-113">The body expression appears on its own line, indented to line up exactly with the first character in the `let` keyword:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

<span data-ttu-id="16023-114">バインディングは、 `let` モジュールレベル、クラス型の定義、またはローカルスコープ (関数定義など) で表示できます。</span><span class="sxs-lookup"><span data-stu-id="16023-114">A `let` binding can appear at the module level, in the definition of a class type, or in local scopes, such as in a function definition.</span></span> <span data-ttu-id="16023-115">`let`モジュール内の最上位レベルまたはクラス型のバインディングは、本体式を持つ必要はありませんが、その他のスコープレベルでは、本体式が必要です。</span><span class="sxs-lookup"><span data-stu-id="16023-115">A `let` binding at the top level in a module or in a class type does not need to have a body expression, but at other scope levels, the body expression is required.</span></span> <span data-ttu-id="16023-116">バインドされた名前は、次のコードに示すように、定義の時点より後で使用できますが、バインドが表示される前の時点では使用できません `let` 。</span><span class="sxs-lookup"><span data-stu-id="16023-116">The bound names are usable after the point of definition, but not at any point before the `let` binding appears, as is illustrated in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]

## <a name="function-bindings"></a><span data-ttu-id="16023-117">関数のバインド</span><span class="sxs-lookup"><span data-stu-id="16023-117">Function Bindings</span></span>

<span data-ttu-id="16023-118">関数のバインドは、次のコードに示すように、関数のバインドに関数名とパラメーターが含まれている点を除いて、値のバインドの規則に従います。</span><span class="sxs-lookup"><span data-stu-id="16023-118">Function bindings follow the rules for value bindings, except that function bindings include the function name and the parameters, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

<span data-ttu-id="16023-119">一般に、パラメーターはタプルパターンなどのパターンです。</span><span class="sxs-lookup"><span data-stu-id="16023-119">In general, parameters are patterns, such as a tuple pattern:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

<span data-ttu-id="16023-120">`let`バインド式は、最後の式の値に評価されます。</span><span class="sxs-lookup"><span data-stu-id="16023-120">A `let` binding expression evaluates to the value of the last expression.</span></span> <span data-ttu-id="16023-121">したがって、次のコード例では、の値 `result` はに評価されるから計算され `100 * function3 (1, 2)` `300` ます。</span><span class="sxs-lookup"><span data-stu-id="16023-121">Therefore, in the following code example, the value of `result` is computed from `100 * function3 (1, 2)`, which evaluates to `300`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

<span data-ttu-id="16023-122">詳細については、「[関数](index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16023-122">For more information, see [Functions](index.md).</span></span>

## <a name="type-annotations"></a><span data-ttu-id="16023-123">型の注釈</span><span class="sxs-lookup"><span data-stu-id="16023-123">Type Annotations</span></span>

<span data-ttu-id="16023-124">パラメーターの型は、コロン (:) を含めることによって指定できます。の後に型名が続き、すべてがかっこで囲まれています。</span><span class="sxs-lookup"><span data-stu-id="16023-124">You can specify types for parameters by including a colon (:) followed by a type name, all enclosed in parentheses.</span></span> <span data-ttu-id="16023-125">戻り値の型を指定するには、最後のパラメーターの後にコロンと型を追加します。</span><span class="sxs-lookup"><span data-stu-id="16023-125">You can also specify the type of the return value by appending the colon and type after the last parameter.</span></span> <span data-ttu-id="16023-126">`function1`パラメーターの型として整数を持つの完全な型の注釈は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="16023-126">The full type annotations for `function1`, with integers as the parameter types, would be as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

<span data-ttu-id="16023-127">明示的な型パラメーターがない場合は、型の推定を使用して、関数のパラメーターの型を決定します。</span><span class="sxs-lookup"><span data-stu-id="16023-127">When there are no explicit type parameters, type inference is used to determine the types of parameters of functions.</span></span> <span data-ttu-id="16023-128">これには、ジェネリックにするパラメーターの型を自動的に一般化することが含まれます。</span><span class="sxs-lookup"><span data-stu-id="16023-128">This can include automatically generalizing the type of a parameter to be generic.</span></span>

<span data-ttu-id="16023-129">詳細については、「 [自動汎](../generics/automatic-generalization.md) 化と [型推論](../type-inference.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16023-129">For more information, see [Automatic Generalization](../generics/automatic-generalization.md) and [Type Inference](../type-inference.md).</span></span>

## <a name="let-bindings-in-classes"></a><span data-ttu-id="16023-130">クラス内の let 束縛</span><span class="sxs-lookup"><span data-stu-id="16023-130">let Bindings in Classes</span></span>

<span data-ttu-id="16023-131">`let`バインドはクラス型では表示できますが、構造体またはレコード型では使用できません。</span><span class="sxs-lookup"><span data-stu-id="16023-131">A `let` binding can appear in a class type but not in a structure or record type.</span></span> <span data-ttu-id="16023-132">クラス型で let バインドを使用するには、クラスにプライマリコンストラクターが必要です。</span><span class="sxs-lookup"><span data-stu-id="16023-132">To use a let binding in a class type, the class must have a primary constructor.</span></span> <span data-ttu-id="16023-133">コンストラクターのパラメーターは、クラス定義の型名の後に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16023-133">Constructor parameters must appear after the type name in the class definition.</span></span> <span data-ttu-id="16023-134">`let`クラス型のバインディングは、そのクラス型のプライベートフィールドとメンバーを定義し、型のバインディングと共に、 `do` 型のプライマリコンストラクターのコードを形成します。</span><span class="sxs-lookup"><span data-stu-id="16023-134">A `let` binding in a class type defines private fields and members for that class type and, together with `do` bindings in the type, forms the code for the primary constructor for the type.</span></span> <span data-ttu-id="16023-135">次のコード例は、プライベートフィールドとを持つクラスを示して `MyClass` `field1` `field2` います。</span><span class="sxs-lookup"><span data-stu-id="16023-135">The following code examples show a class `MyClass` with private fields `field1` and `field2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

<span data-ttu-id="16023-136">とのスコープ `field1` は、宣言されている `field2` 型に制限されます。</span><span class="sxs-lookup"><span data-stu-id="16023-136">The scopes of `field1` and `field2` are limited to the type in which they are declared.</span></span> <span data-ttu-id="16023-137">詳細については、「クラスおよび[クラス](../classes.md) [ `let` のバインド](../members/let-bindings-in-classes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16023-137">For more information, see [`let` Bindings in Classes](../members/let-bindings-in-classes.md) and [Classes](../classes.md).</span></span>

## <a name="type-parameters-in-let-bindings"></a><span data-ttu-id="16023-138">Let バインドの型パラメーター</span><span class="sxs-lookup"><span data-stu-id="16023-138">Type Parameters in let Bindings</span></span>

<span data-ttu-id="16023-139">`let`モジュールレベル、型、またはコンピュテーション式内のバインディングは、明示的な型パラメーターを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="16023-139">A `let` binding at the module level, in a type, or in a computation expression can have explicit type parameters.</span></span> <span data-ttu-id="16023-140">関数定義内などの式で let バインドを使用する場合、型パラメーターを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="16023-140">A let binding in an expression, such as within a function definition, cannot have type parameters.</span></span> <span data-ttu-id="16023-141">詳細については、「[ジェネリック](../generics/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16023-141">For more information, see [Generics](../generics/index.md).</span></span>

## <a name="attributes-on-let-bindings"></a><span data-ttu-id="16023-142">Let バインドの属性</span><span class="sxs-lookup"><span data-stu-id="16023-142">Attributes on let Bindings</span></span>

<span data-ttu-id="16023-143">属性は、 `let` 次のコードに示すように、モジュールの最上位のバインドに適用できます。</span><span class="sxs-lookup"><span data-stu-id="16023-143">Attributes can be applied to top-level `let` bindings in a module, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]

## <a name="scope-and-accessibility-of-let-bindings"></a><span data-ttu-id="16023-144">Let バインドのスコープとアクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="16023-144">Scope and Accessibility of Let Bindings</span></span>

<span data-ttu-id="16023-145">Let バインドを使用して宣言されたエンティティのスコープは、バインドが表示された後に、コンテナースコープ (関数、モジュール、ファイル、クラスなど) の部分に限定されます。</span><span class="sxs-lookup"><span data-stu-id="16023-145">The scope of an entity declared with a let binding is limited to the portion of the containing scope (such as a function, module, file or class) after the binding appears.</span></span> <span data-ttu-id="16023-146">そのため、let バインドによって名前がスコープに導入されることがあります。</span><span class="sxs-lookup"><span data-stu-id="16023-146">Therefore, it can be said that a let binding introduces a name into a scope.</span></span> <span data-ttu-id="16023-147">モジュールでは、モジュール内の let バインドがモジュールのパブリック関数にコンパイルされるので、モジュールがアクセス可能であればモジュールのクライアントが使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="16023-147">In a module, a let-bound value or function is accessible to clients of a module as long as the module is accessible, since the let bindings in a module are compiled into public functions of the module.</span></span> <span data-ttu-id="16023-148">これに対して、クラス内のバインディングはクラスに対してプライベートです。</span><span class="sxs-lookup"><span data-stu-id="16023-148">By contrast, let bindings in a class are private to the class.</span></span>

<span data-ttu-id="16023-149">通常、モジュール内の関数は、クライアントコードで使用するときに、モジュールの名前で修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16023-149">Normally, functions in modules must be qualified by the name of the module when used by client code.</span></span> <span data-ttu-id="16023-150">たとえば、モジュールに `Module1` 関数がある場合、 `function1` ユーザーは `Module1.function1` 関数を参照するように指定します。</span><span class="sxs-lookup"><span data-stu-id="16023-150">For example, if a module `Module1` has a function `function1`, users would specify `Module1.function1` to refer to the function.</span></span>

<span data-ttu-id="16023-151">モジュールのユーザーは、インポート宣言を使用して、モジュール名で修飾されていなくても、そのモジュール内の関数を使用できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="16023-151">Users of a module may use an import declaration to make the functions within that module available for use without being qualified by the module name.</span></span> <span data-ttu-id="16023-152">前述の例では、モジュールのユーザーはインポート宣言を使用してモジュールを開くことができ、その `Module1` 後は直接を参照し `function1` ます。</span><span class="sxs-lookup"><span data-stu-id="16023-152">In the example just mentioned, users of the module can in that case open the module by using the import declaration open `Module1` and thereafter refer to `function1` directly.</span></span>

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

<span data-ttu-id="16023-153">一部のモジュールには [RequireQualifiedAccess](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html)属性があります。つまり、公開する関数がモジュールの名前で修飾されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="16023-153">Some modules have the attribute [RequireQualifiedAccess](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html), which means that the functions that they expose must be qualified with the name of the module.</span></span> <span data-ttu-id="16023-154">たとえば、F # リストモジュールにはこの属性があります。</span><span class="sxs-lookup"><span data-stu-id="16023-154">For example, the F# List module has this attribute.</span></span>

<span data-ttu-id="16023-155">モジュールとアクセス制御の詳細については、「 [モジュール](../modules.md) と [Access Control](../access-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16023-155">For more information on modules and access control, see [Modules](../modules.md) and [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="16023-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="16023-156">See also</span></span>

- [<span data-ttu-id="16023-157">関数</span><span class="sxs-lookup"><span data-stu-id="16023-157">Functions</span></span>](index.md)
- [<span data-ttu-id="16023-158">`let` クラス内のバインディング</span><span class="sxs-lookup"><span data-stu-id="16023-158">`let` Bindings in Classes</span></span>](../members/let-bindings-in-classes.md)
