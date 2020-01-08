---
title: 型リスト
ms.date: 07/20/2015
f1_keywords:
- StructureConstraint
- vb.StructureConstraint
- ClassConstraint
- vb.ClassConstraint
helpviewer_keywords:
- class constraint
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- generics [Visual Basic], type list
- structure constraint
- constraints, in type parameters
- generics [Visual Basic], generic types
- parameters [Visual Basic], type
- constraints, Structure keyword
- type parameters [Visual Basic], constraints
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], type parameters
- type parameters
- constraints, Class keyword
ms.assetid: 56db947a-2ae8-40f2-a70a-960764e9d0db
ms.openlocfilehash: 3f2aaa65293ed2bcc6c8eeb4bd77e49907d93425
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352774"
---
# <a name="type-list-visual-basic"></a><span data-ttu-id="cef3c-102">型リスト (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cef3c-102">Type List (Visual Basic)</span></span>

<span data-ttu-id="cef3c-103">*ジェネリック*プログラミング要素の*型パラメーター*を指定します。</span><span class="sxs-lookup"><span data-stu-id="cef3c-103">Specifies the *type parameters* for a *generic* programming element.</span></span> <span data-ttu-id="cef3c-104">複数のパラメーターはコンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="cef3c-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="cef3c-105">1つの型パラメーターの構文を次に示します。</span><span class="sxs-lookup"><span data-stu-id="cef3c-105">Following is the syntax for one type parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="cef3c-106">構文</span><span class="sxs-lookup"><span data-stu-id="cef3c-106">Syntax</span></span>

```vb
[genericmodifier] typename [ As constraintlist ]
```

## <a name="parts"></a><span data-ttu-id="cef3c-107">指定項目</span><span class="sxs-lookup"><span data-stu-id="cef3c-107">Parts</span></span>

|<span data-ttu-id="cef3c-108">用語</span><span class="sxs-lookup"><span data-stu-id="cef3c-108">Term</span></span>|<span data-ttu-id="cef3c-109">Definition</span><span class="sxs-lookup"><span data-stu-id="cef3c-109">Definition</span></span>|
|---|---|
|`genericmodifier`|<span data-ttu-id="cef3c-110">省略可。</span><span class="sxs-lookup"><span data-stu-id="cef3c-110">Optional.</span></span> <span data-ttu-id="cef3c-111">は、ジェネリックインターフェイスおよびデリゲートでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="cef3c-111">Can be used only in generic interfaces and delegates.</span></span> <span data-ttu-id="cef3c-112">[In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)キーワードを使用し[て、型](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)を共変として宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="cef3c-112">You can declare a type covariant by using the [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) keyword or contravariant by using the [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) keyword.</span></span> <span data-ttu-id="cef3c-113">[共変性と反変性](../../programming-guide/concepts/covariance-contravariance/index.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cef3c-113">See [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>|
|`typename`|<span data-ttu-id="cef3c-114">必須。</span><span class="sxs-lookup"><span data-stu-id="cef3c-114">Required.</span></span> <span data-ttu-id="cef3c-115">型パラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="cef3c-115">Name of the type parameter.</span></span> <span data-ttu-id="cef3c-116">これは、対応する型引数によって提供される定義済みの型に置き換えられるプレースホルダーです。</span><span class="sxs-lookup"><span data-stu-id="cef3c-116">This is a placeholder, to be replaced by a defined type supplied by the corresponding type argument.</span></span>|
|`constraintlist`|<span data-ttu-id="cef3c-117">省略可。</span><span class="sxs-lookup"><span data-stu-id="cef3c-117">Optional.</span></span> <span data-ttu-id="cef3c-118">`typename`に指定できるデータ型を制限する要件の一覧。</span><span class="sxs-lookup"><span data-stu-id="cef3c-118">List of requirements that constrain the data type that can be supplied for `typename`.</span></span> <span data-ttu-id="cef3c-119">複数の制約がある場合は、それらを中かっこ (`{ }`) で囲み、コンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="cef3c-119">If you have multiple constraints, enclose them in curly braces (`{ }`) and separate them with commas.</span></span> <span data-ttu-id="cef3c-120">制約リストは [As](../../../visual-basic/language-reference/statements/as-clause.md) キーワードを使用して導入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cef3c-120">You must introduce the constraint list with the [As](../../../visual-basic/language-reference/statements/as-clause.md) keyword.</span></span> <span data-ttu-id="cef3c-121">`As` は、リストの先頭で1回だけ使用します。</span><span class="sxs-lookup"><span data-stu-id="cef3c-121">You use `As` only once, at the beginning of the list.</span></span>|

## <a name="remarks"></a><span data-ttu-id="cef3c-122">コメント</span><span class="sxs-lookup"><span data-stu-id="cef3c-122">Remarks</span></span>

<span data-ttu-id="cef3c-123">すべてのジェネリックプログラミング要素は、少なくとも1つの型パラメーターを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="cef3c-123">Every generic programming element must take at least one type parameter.</span></span> <span data-ttu-id="cef3c-124">型パラメーターは、ジェネリック型のインスタンスを作成するときにクライアントコードによって指定される特定の型 (構築された*要素*) のプレースホルダーです。</span><span class="sxs-lookup"><span data-stu-id="cef3c-124">A type parameter is a placeholder for a specific type (a *constructed element*) that client code specifies when it creates an instance of the generic type.</span></span> <span data-ttu-id="cef3c-125">ジェネリッククラス、構造体、インターフェイス、プロシージャ、またはデリゲートを定義できます。</span><span class="sxs-lookup"><span data-stu-id="cef3c-125">You can define a generic class, structure, interface, procedure, or delegate.</span></span>

<span data-ttu-id="cef3c-126">ジェネリック型を定義する場合の詳細については、「[Visual Basic におけるジェネリック型](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cef3c-126">For more information on when to define a generic type, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span> <span data-ttu-id="cef3c-127">型パラメーター名の詳細については、「[宣言された要素の名前](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cef3c-127">For more information on type parameter names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

## <a name="rules"></a><span data-ttu-id="cef3c-128">ルール</span><span class="sxs-lookup"><span data-stu-id="cef3c-128">Rules</span></span>

- <span data-ttu-id="cef3c-129">**Parentheses.**</span><span class="sxs-lookup"><span data-stu-id="cef3c-129">**Parentheses.**</span></span> <span data-ttu-id="cef3c-130">型パラメータのリストを指定する場合は、リストをかっこで囲み、[Of](../../../visual-basic/language-reference/statements/of-clause.md) キーワードを使って特定する必要があります。 `Of` はリストの先頭に一度だけ記述します。</span><span class="sxs-lookup"><span data-stu-id="cef3c-130">If you supply a type parameter list, you must enclose it in parentheses, and you must introduce the list with the [Of](../../../visual-basic/language-reference/statements/of-clause.md) keyword.</span></span> <span data-ttu-id="cef3c-131">`Of` は、リストの先頭に一度だけ記述します。</span><span class="sxs-lookup"><span data-stu-id="cef3c-131">You use `Of` only once, at the beginning of the list.</span></span>

- <span data-ttu-id="cef3c-132">**制約。**</span><span class="sxs-lookup"><span data-stu-id="cef3c-132">**Constraints.**</span></span> <span data-ttu-id="cef3c-133">\*\* 型パラメータに対する制約のリストには、次の項目を任意の組み合わせで定義できます。</span><span class="sxs-lookup"><span data-stu-id="cef3c-133">A list of *constraints* on a type parameter can include the following items in any combination:</span></span>

  - <span data-ttu-id="cef3c-134">任意の数のインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="cef3c-134">Any number of interfaces.</span></span> <span data-ttu-id="cef3c-135">指定された型は、このリスト内のすべてのインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cef3c-135">The supplied type must implement every interface in this list.</span></span>

  - <span data-ttu-id="cef3c-136">クラスは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="cef3c-136">At most one class.</span></span> <span data-ttu-id="cef3c-137">指定された型は、そのクラスから継承する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cef3c-137">The supplied type must inherit from that class.</span></span>

  - <span data-ttu-id="cef3c-138">`New` キーワード。</span><span class="sxs-lookup"><span data-stu-id="cef3c-138">The `New` keyword.</span></span> <span data-ttu-id="cef3c-139">指定された型は、ジェネリック型がアクセスできるパラメーターなしのコンストラクターを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cef3c-139">The supplied type must expose a parameterless constructor that your generic type can access.</span></span> <span data-ttu-id="cef3c-140">これは、1つまたは複数のインターフェイスによって型パラメーターを制約する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="cef3c-140">This is useful if you constrain a type parameter by one or more interfaces.</span></span> <span data-ttu-id="cef3c-141">インターフェイスを実装する型は、必ずしもコンストラクターを公開するわけではありません。また、コンストラクターのアクセスレベルによっては、ジェネリック型内のコードがアクセスできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="cef3c-141">A type that implements interfaces does not necessarily expose a constructor, and depending on the access level of a constructor, the code within the generic type might not be able to access it.</span></span>

  - <span data-ttu-id="cef3c-142">`Class` キーワードまたは `Structure` キーワード。</span><span class="sxs-lookup"><span data-stu-id="cef3c-142">Either the `Class` keyword or the `Structure` keyword.</span></span> <span data-ttu-id="cef3c-143">`Class` キーワードは、ジェネリック型パラメーターを制約して、その型引数が参照型であることを要求します (文字列、配列、デリゲート、クラスから作成されたオブジェクトなど)。</span><span class="sxs-lookup"><span data-stu-id="cef3c-143">The `Class` keyword constrains a generic type parameter to require that any type argument passed to it be a reference type, for example a string, array, or delegate, or an object created from a class.</span></span> <span data-ttu-id="cef3c-144">`Structure` キーワードは、構造体、列挙型、基本データ型など、型引数が値型であることを要求するジェネリック型パラメーターを制約します。</span><span class="sxs-lookup"><span data-stu-id="cef3c-144">The `Structure` keyword constrains a generic type parameter to require that any type argument passed to it be a value type, for example a structure, enumeration, or elementary data type.</span></span> <span data-ttu-id="cef3c-145">`Class` と `Structure` を同じ `constraintlist`に含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="cef3c-145">You cannot include both `Class` and `Structure` in the same `constraintlist`.</span></span>

  <span data-ttu-id="cef3c-146">指定された型は、`constraintlist`に含まれるすべての要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cef3c-146">The supplied type must satisfy every requirement you include in `constraintlist`.</span></span>

  <span data-ttu-id="cef3c-147">型パラメーターごとの制約は、他の型パラメーターに対する制約とは無関係です。</span><span class="sxs-lookup"><span data-stu-id="cef3c-147">Constraints on each type parameter are independent of constraints on other type parameters.</span></span>

## <a name="behavior"></a><span data-ttu-id="cef3c-148">動作</span><span class="sxs-lookup"><span data-stu-id="cef3c-148">Behavior</span></span>

- <span data-ttu-id="cef3c-149">**コンパイル時の代入。**</span><span class="sxs-lookup"><span data-stu-id="cef3c-149">**Compile-Time Substitution.**</span></span> <span data-ttu-id="cef3c-150">ジェネリックプログラミング要素から構築された型を作成する場合は、型パラメーターごとに定義済みの型を指定します。</span><span class="sxs-lookup"><span data-stu-id="cef3c-150">When you create a constructed type from a generic programming element, you supply a defined type for each type parameter.</span></span> <span data-ttu-id="cef3c-151">Visual Basic コンパイラは、ジェネリック要素内で `typename` が発生するたびに、指定された型を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="cef3c-151">The Visual Basic compiler substitutes that supplied type for every occurrence of `typename` within the generic element.</span></span>

- <span data-ttu-id="cef3c-152">**制約の省略。**</span><span class="sxs-lookup"><span data-stu-id="cef3c-152">**Absence of Constraints.**</span></span> <span data-ttu-id="cef3c-153">型パラメーターに対して制約を指定しない場合、コードは、その型パラメーターの [Object データ型](../../../visual-basic/language-reference/data-types/object-data-type.md)でサポートされている操作とメンバーに制限されます。</span><span class="sxs-lookup"><span data-stu-id="cef3c-153">If you do not specify any constraints on a type parameter, your code is limited to the operations and members supported by the [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md) for that type parameter.</span></span>

## <a name="example"></a><span data-ttu-id="cef3c-154">例</span><span class="sxs-lookup"><span data-stu-id="cef3c-154">Example</span></span>

<span data-ttu-id="cef3c-155">次の例は、ジェネリックディクショナリクラスのスケルトン定義を示しています。これには、新しいエントリをディクショナリに追加するスケルトン関数も含まれます。</span><span class="sxs-lookup"><span data-stu-id="cef3c-155">The following example shows a skeleton definition of a generic dictionary class, including a skeleton function to add a new entry to the dictionary.</span></span>

[!code-vb[VbVbalrStatements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#3)]

## <a name="example"></a><span data-ttu-id="cef3c-156">例</span><span class="sxs-lookup"><span data-stu-id="cef3c-156">Example</span></span>

<span data-ttu-id="cef3c-157">`dictionary` はジェネリックであるため、このメソッドを使用するコードは、それぞれが同じ機能を持ち、別のデータ型に対して動作する、さまざまなオブジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="cef3c-157">Because `dictionary` is generic, the code that uses it can create a variety of objects from it, each having the same functionality but acting on a different data type.</span></span> <span data-ttu-id="cef3c-158">次の例は、`String` エントリと `Integer` キーを持つ `dictionary` オブジェクトを作成するコード行を示しています。</span><span class="sxs-lookup"><span data-stu-id="cef3c-158">The following example shows a line of code that creates a `dictionary` object with `String` entries and `Integer` keys.</span></span>

[!code-vb[VbVbalrStatements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#4)]

## <a name="example"></a><span data-ttu-id="cef3c-159">例</span><span class="sxs-lookup"><span data-stu-id="cef3c-159">Example</span></span>

<span data-ttu-id="cef3c-160">次の例は、前の例で生成された同等のスケルトン定義を示しています。</span><span class="sxs-lookup"><span data-stu-id="cef3c-160">The following example shows the equivalent skeleton definition generated by the preceding example.</span></span>

[!code-vb[VbVbalrStatements#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="cef3c-161">参照</span><span class="sxs-lookup"><span data-stu-id="cef3c-161">See also</span></span>

- [<span data-ttu-id="cef3c-162">Of</span><span class="sxs-lookup"><span data-stu-id="cef3c-162">Of</span></span>](../../../visual-basic/language-reference/statements/of-clause.md)
- [<span data-ttu-id="cef3c-163">New 演算子</span><span class="sxs-lookup"><span data-stu-id="cef3c-163">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="cef3c-164">Visual Basic でのアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="cef3c-164">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="cef3c-165">Object データ型</span><span class="sxs-lookup"><span data-stu-id="cef3c-165">Object Data Type</span></span>](../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="cef3c-166">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="cef3c-166">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="cef3c-167">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="cef3c-167">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="cef3c-168">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="cef3c-168">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="cef3c-169">方法 : ジェネリック クラスを使用する</span><span class="sxs-lookup"><span data-stu-id="cef3c-169">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="cef3c-170">共変性と反変性</span><span class="sxs-lookup"><span data-stu-id="cef3c-170">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)
- [<span data-ttu-id="cef3c-171">In</span><span class="sxs-lookup"><span data-stu-id="cef3c-171">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [<span data-ttu-id="cef3c-172">Out</span><span class="sxs-lookup"><span data-stu-id="cef3c-172">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
