---
title: let バインド
description: 識別子を値またはF#関数に関連付ける ' let ' バインドの使用方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: 654631c7d1c48d8737e6098c98efee54cfdd91be
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630641"
---
# <a name="let-bindings"></a><span data-ttu-id="3ac91-103">let バインド</span><span class="sxs-lookup"><span data-stu-id="3ac91-103">let Bindings</span></span>

<span data-ttu-id="3ac91-104">*バインド*は、識別子を値または関数に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="3ac91-104">A *binding* associates an identifier with a value or function.</span></span> <span data-ttu-id="3ac91-105">キーワードを使用`let`して、名前を値または関数にバインドします。</span><span class="sxs-lookup"><span data-stu-id="3ac91-105">You use the `let` keyword to bind a name to a value or function.</span></span>

## <a name="syntax"></a><span data-ttu-id="3ac91-106">構文</span><span class="sxs-lookup"><span data-stu-id="3ac91-106">Syntax</span></span>

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a><span data-ttu-id="3ac91-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="3ac91-107">Remarks</span></span>

<span data-ttu-id="3ac91-108">キーワード`let`は、1つまたは複数の名前の値または関数の値を定義するために、バインド式で使用されます。</span><span class="sxs-lookup"><span data-stu-id="3ac91-108">The `let` keyword is used in binding expressions to define values or function values for one or more names.</span></span> <span data-ttu-id="3ac91-109">`let`式の最も単純な形式は、次のように単純な値に名前をバインドします。</span><span class="sxs-lookup"><span data-stu-id="3ac91-109">The simplest form of the `let` expression binds a name to a simple value, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

<span data-ttu-id="3ac91-110">新しい行を使用して識別子から式を分離する場合は、次のコードのように、式の各行をインデントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ac91-110">If you separate the expression from the identifier by using a new line, you must indent each line of the expression, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

<span data-ttu-id="3ac91-111">次のコードに示すように、名前だけでなく、名前を含むパターンを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="3ac91-111">Instead of just a name, a pattern that contains names can be specified, for example, a tuple, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

<span data-ttu-id="3ac91-112">*本体式*は、名前が使用される式です。</span><span class="sxs-lookup"><span data-stu-id="3ac91-112">The *body-expression* is the expression in which the names are used.</span></span> <span data-ttu-id="3ac91-113">本文の式は、 `let`キーワード内の最初の文字と正確に一致する行にインデントされています。</span><span class="sxs-lookup"><span data-stu-id="3ac91-113">The body expression appears on its own line, indented to line up exactly with the first character in the `let` keyword:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

<span data-ttu-id="3ac91-114">バインディング`let`は、モジュールレベル、クラス型の定義、またはローカルスコープ (関数定義など) で表示できます。</span><span class="sxs-lookup"><span data-stu-id="3ac91-114">A `let` binding can appear at the module level, in the definition of a class type, or in local scopes, such as in a function definition.</span></span> <span data-ttu-id="3ac91-115">モジュール内の最上位レベルまたはクラス型のバインディングは、本体式を持つ必要はありませんが、その他のスコープレベルでは、本体式が必要です。`let`</span><span class="sxs-lookup"><span data-stu-id="3ac91-115">A `let` binding at the top level in a module or in a class type does not need to have a body expression, but at other scope levels, the body expression is required.</span></span> <span data-ttu-id="3ac91-116">バインドされた名前は、次のコードに示すように、定義の時点`let`より後で使用できますが、バインドが表示される前の時点では使用できません。</span><span class="sxs-lookup"><span data-stu-id="3ac91-116">The bound names are usable after the point of definition, but not at any point before the `let` binding appears, as is illustrated in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]

## <a name="function-bindings"></a><span data-ttu-id="3ac91-117">関数のバインド</span><span class="sxs-lookup"><span data-stu-id="3ac91-117">Function Bindings</span></span>

<span data-ttu-id="3ac91-118">関数のバインドは、次のコードに示すように、関数のバインドに関数名とパラメーターが含まれている点を除いて、値のバインドの規則に従います。</span><span class="sxs-lookup"><span data-stu-id="3ac91-118">Function bindings follow the rules for value bindings, except that function bindings include the function name and the parameters, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

<span data-ttu-id="3ac91-119">一般に、パラメーターはタプルパターンなどのパターンです。</span><span class="sxs-lookup"><span data-stu-id="3ac91-119">In general, parameters are patterns, such as a tuple pattern:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

<span data-ttu-id="3ac91-120">バインド`let`式は、最後の式の値に評価されます。</span><span class="sxs-lookup"><span data-stu-id="3ac91-120">A `let` binding expression evaluates to the value of the last expression.</span></span> <span data-ttu-id="3ac91-121">したがって、次のコード例では、の`result`値はに`100 * function3 (1, 2)` `300`評価されるから計算されます。</span><span class="sxs-lookup"><span data-stu-id="3ac91-121">Therefore, in the following code example, the value of `result` is computed from `100 * function3 (1, 2)`, which evaluates to `300`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

<span data-ttu-id="3ac91-122">詳細については、「[関数](index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ac91-122">For more information, see [Functions](index.md).</span></span>

## <a name="type-annotations"></a><span data-ttu-id="3ac91-123">型の注釈</span><span class="sxs-lookup"><span data-stu-id="3ac91-123">Type Annotations</span></span>

<span data-ttu-id="3ac91-124">パラメーターの型は、コロン (:) を含めることによって指定できます。の後に型名が続き、すべてがかっこで囲まれています。</span><span class="sxs-lookup"><span data-stu-id="3ac91-124">You can specify types for parameters by including a colon (:) followed by a type name, all enclosed in parentheses.</span></span> <span data-ttu-id="3ac91-125">戻り値の型を指定するには、最後のパラメーターの後にコロンと型を追加します。</span><span class="sxs-lookup"><span data-stu-id="3ac91-125">You can also specify the type of the return value by appending the colon and type after the last parameter.</span></span> <span data-ttu-id="3ac91-126">パラメーターの型とし`function1`て整数を持つの完全な型の注釈は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3ac91-126">The full type annotations for `function1`, with integers as the parameter types, would be as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

<span data-ttu-id="3ac91-127">明示的な型パラメーターがない場合は、型の推定を使用して、関数のパラメーターの型を決定します。</span><span class="sxs-lookup"><span data-stu-id="3ac91-127">When there are no explicit type parameters, type inference is used to determine the types of parameters of functions.</span></span> <span data-ttu-id="3ac91-128">これには、ジェネリックにするパラメーターの型を自動的に一般化することが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3ac91-128">This can include automatically generalizing the type of a parameter to be generic.</span></span>

<span data-ttu-id="3ac91-129">詳細については、「[自動汎](../generics/automatic-generalization.md)化と[型推論](../type-inference.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ac91-129">For more information, see [Automatic Generalization](../generics/automatic-generalization.md) and [Type Inference](../type-inference.md).</span></span>

## <a name="let-bindings-in-classes"></a><span data-ttu-id="3ac91-130">クラス内の let 束縛</span><span class="sxs-lookup"><span data-stu-id="3ac91-130">let Bindings in Classes</span></span>

<span data-ttu-id="3ac91-131">バインド`let`はクラス型では表示できますが、構造体またはレコード型では使用できません。</span><span class="sxs-lookup"><span data-stu-id="3ac91-131">A `let` binding can appear in a class type but not in a structure or record type.</span></span> <span data-ttu-id="3ac91-132">クラス型で let バインドを使用するには、クラスにプライマリコンストラクターが必要です。</span><span class="sxs-lookup"><span data-stu-id="3ac91-132">To use a let binding in a class type, the class must have a primary constructor.</span></span> <span data-ttu-id="3ac91-133">コンストラクターのパラメーターは、クラス定義の型名の後に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ac91-133">Constructor parameters must appear after the type name in the class definition.</span></span> <span data-ttu-id="3ac91-134">クラス`let`型のバインディングは、そのクラス型のプライベートフィールドとメンバーを定義し、型`do`のバインディングと共に、型のプライマリコンストラクターのコードを形成します。</span><span class="sxs-lookup"><span data-stu-id="3ac91-134">A `let` binding in a class type defines private fields and members for that class type and, together with `do` bindings in the type, forms the code for the primary constructor for the type.</span></span> <span data-ttu-id="3ac91-135">次のコード例は、プライベート`MyClass`フィールド`field1`と`field2`を持つクラスを示しています。</span><span class="sxs-lookup"><span data-stu-id="3ac91-135">The following code examples show a class `MyClass` with private fields `field1` and `field2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

<span data-ttu-id="3ac91-136">`field1` と`field2`のスコープは、宣言されている型に制限されます。</span><span class="sxs-lookup"><span data-stu-id="3ac91-136">The scopes of `field1` and `field2` are limited to the type in which they are declared.</span></span> <span data-ttu-id="3ac91-137">詳細については、「クラスおよび[クラス](../classes.md) [ `let`のバインド](../members/let-bindings-in-classes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ac91-137">For more information, see [`let` Bindings in Classes](../members/let-bindings-in-classes.md) and [Classes](../classes.md).</span></span>

## <a name="type-parameters-in-let-bindings"></a><span data-ttu-id="3ac91-138">Let バインドの型パラメーター</span><span class="sxs-lookup"><span data-stu-id="3ac91-138">Type Parameters in let Bindings</span></span>

<span data-ttu-id="3ac91-139">モジュールレベル、型、またはコンピュテーション式内のバインディングは、明示的な型パラメーターを持つことができます。`let`</span><span class="sxs-lookup"><span data-stu-id="3ac91-139">A `let` binding at the module level, in a type, or in a computation expression can have explicit type parameters.</span></span> <span data-ttu-id="3ac91-140">関数定義内などの式で let バインドを使用する場合、型パラメーターを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="3ac91-140">A let binding in an expression, such as within a function definition, cannot have type parameters.</span></span> <span data-ttu-id="3ac91-141">詳細については、「[ジェネリック](../generics/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ac91-141">For more information, see [Generics](../generics/index.md).</span></span>

## <a name="attributes-on-let-bindings"></a><span data-ttu-id="3ac91-142">Let バインドの属性</span><span class="sxs-lookup"><span data-stu-id="3ac91-142">Attributes on let Bindings</span></span>

<span data-ttu-id="3ac91-143">属性は、次のコードに示す`let`ように、モジュールの最上位のバインドに適用できます。</span><span class="sxs-lookup"><span data-stu-id="3ac91-143">Attributes can be applied to top-level `let` bindings in a module, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]

## <a name="scope-and-accessibility-of-let-bindings"></a><span data-ttu-id="3ac91-144">Let バインドのスコープとアクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="3ac91-144">Scope and Accessibility of Let Bindings</span></span>

<span data-ttu-id="3ac91-145">Let バインドを使用して宣言されたエンティティのスコープは、バインドが表示された後に、コンテナースコープ (関数、モジュール、ファイル、クラスなど) の部分に限定されます。</span><span class="sxs-lookup"><span data-stu-id="3ac91-145">The scope of an entity declared with a let binding is limited to the portion of the containing scope (such as a function, module, file or class) after the binding appears.</span></span> <span data-ttu-id="3ac91-146">そのため、let バインドによって名前がスコープに導入されることがあります。</span><span class="sxs-lookup"><span data-stu-id="3ac91-146">Therefore, it can be said that a let binding introduces a name into a scope.</span></span> <span data-ttu-id="3ac91-147">モジュールでは、モジュール内の let バインドがモジュールのパブリック関数にコンパイルされるので、モジュールがアクセス可能であればモジュールのクライアントが使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3ac91-147">In a module, a let-bound value or function is accessible to clients of a module as long as the module is accessible, since the let bindings in a module are compiled into public functions of the module.</span></span> <span data-ttu-id="3ac91-148">これに対して、クラス内のバインディングはクラスに対してプライベートです。</span><span class="sxs-lookup"><span data-stu-id="3ac91-148">By contrast, let bindings in a class are private to the class.</span></span>

<span data-ttu-id="3ac91-149">通常、モジュール内の関数は、クライアントコードで使用するときに、モジュールの名前で修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ac91-149">Normally, functions in modules must be qualified by the name of the module when used by client code.</span></span> <span data-ttu-id="3ac91-150">たとえば、モジュール`Module1`に関数`function1`がある場合、ユーザーは関数を`Module1.function1`参照するように指定します。</span><span class="sxs-lookup"><span data-stu-id="3ac91-150">For example, if a module `Module1` has a function `function1`, users would specify `Module1.function1` to refer to the function.</span></span>

<span data-ttu-id="3ac91-151">モジュールのユーザーは、インポート宣言を使用して、モジュール名で修飾されていなくても、そのモジュール内の関数を使用できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="3ac91-151">Users of a module may use an import declaration to make the functions within that module available for use without being qualified by the module name.</span></span> <span data-ttu-id="3ac91-152">前述の例では、モジュールのユーザーはインポート宣言`Module1`を使用してモジュールを開くことができ、その後は直接を`function1`参照します。</span><span class="sxs-lookup"><span data-stu-id="3ac91-152">In the example just mentioned, users of the module can in that case open the module by using the import declaration open `Module1` and thereafter refer to `function1` directly.</span></span>

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

<span data-ttu-id="3ac91-153">一部のモジュールには[RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15)属性があります。つまり、公開する関数がモジュールの名前で修飾されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ac91-153">Some modules have the attribute [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), which means that the functions that they expose must be qualified with the name of the module.</span></span> <span data-ttu-id="3ac91-154">たとえば、F# List モジュールには、この属性があります。</span><span class="sxs-lookup"><span data-stu-id="3ac91-154">For example, the F# List module has this attribute.</span></span>

<span data-ttu-id="3ac91-155">モジュールとアクセス制御の詳細については、「[モジュール](../modules.md)と[Access Control](../access-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ac91-155">For more information on modules and access control, see [Modules](../modules.md) and [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3ac91-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ac91-156">See also</span></span>

- [<span data-ttu-id="3ac91-157">関数</span><span class="sxs-lookup"><span data-stu-id="3ac91-157">Functions</span></span>](index.md)
- [<span data-ttu-id="3ac91-158">クラス内の `let` バインド</span><span class="sxs-lookup"><span data-stu-id="3ac91-158">`let` Bindings in Classes</span></span>](../members/let-bindings-in-classes.md)
