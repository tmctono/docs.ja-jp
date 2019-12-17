---
title: Dim ステートメント
ms.date: 05/12/2018
f1_keywords:
- vb.Dim
- Dim
helpviewer_keywords:
- Public keyword [Visual Basic], in Dim statement
- Dim statement [Visual Basic]
- fixed-length strings [Visual Basic], declaring
- variables [Visual Basic], declaring
- WithEvents keyword [Visual Basic], Dim statement
- dynamic arrays [Visual Basic], Dim statement
- variables [Visual Basic], initializing
- '{} braces'
- fields [Visual Basic], as member variables
- declarations [Visual Basic], dynamic arrays
- member variables [Visual Basic]
- default values [Visual Basic]
- data types [Visual Basic], assigning
- braces {}
- As keyword [Visual Basic], in Dim statement
- arrays [Visual Basic], declaring
- New keyword [Visual Basic], Dim statement
- To keyword [Visual Basic], in Dim statement
- storage [Visual Basic], allocating
- local variables [Visual Basic]
- declaration statements [Visual Basic]
- Dim statement [Visual Basic], syntax
- variables [Visual Basic], member and local
ms.assetid: fae3eca1-f0b2-4400-994b-7aa58a848448
ms.openlocfilehash: ac66ffdba622673ef42017d147c05b2a2733dede
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343763"
---
# <a name="dim-statement-visual-basic"></a><span data-ttu-id="fb806-102">Dim ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb806-102">Dim Statement (Visual Basic)</span></span>

<span data-ttu-id="fb806-103">1つ以上の変数に対して記憶領域を宣言して割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fb806-103">Declares and allocates storage space for one or more variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="fb806-104">構文</span><span class="sxs-lookup"><span data-stu-id="fb806-104">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ] [[ Shared ] [ Shadows ] | [ Static ]] [ ReadOnly ]
Dim [ WithEvents ] variablelist
```

## <a name="parts"></a><span data-ttu-id="fb806-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="fb806-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="fb806-106">任意。</span><span class="sxs-lookup"><span data-stu-id="fb806-106">Optional.</span></span> <span data-ttu-id="fb806-107">「[属性リスト](../../../visual-basic/language-reference/statements/attribute-list.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb806-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>

- `accessmodifier`

  <span data-ttu-id="fb806-108">任意。</span><span class="sxs-lookup"><span data-stu-id="fb806-108">Optional.</span></span> <span data-ttu-id="fb806-109">次のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="fb806-109">Can be one of the following:</span></span>

  - [<span data-ttu-id="fb806-110">Public</span><span class="sxs-lookup"><span data-stu-id="fb806-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)

  - [<span data-ttu-id="fb806-111">Protected</span><span class="sxs-lookup"><span data-stu-id="fb806-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)

  - [<span data-ttu-id="fb806-112">Friend</span><span class="sxs-lookup"><span data-stu-id="fb806-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)

  - [<span data-ttu-id="fb806-113">Private</span><span class="sxs-lookup"><span data-stu-id="fb806-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)

  - [<span data-ttu-id="fb806-114">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="fb806-114">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

  - [<span data-ttu-id="fb806-115">Private Protected</span><span class="sxs-lookup"><span data-stu-id="fb806-115">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

  <span data-ttu-id="fb806-116">「[Visual Basic でのアクセス レベル](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb806-116">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `Shared`

  <span data-ttu-id="fb806-117">任意。</span><span class="sxs-lookup"><span data-stu-id="fb806-117">Optional.</span></span> <span data-ttu-id="fb806-118">「[Shared](../../../visual-basic/language-reference/modifiers/shared.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb806-118">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="fb806-119">任意。</span><span class="sxs-lookup"><span data-stu-id="fb806-119">Optional.</span></span> <span data-ttu-id="fb806-120">「[Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb806-120">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>

- `Static`

  <span data-ttu-id="fb806-121">任意。</span><span class="sxs-lookup"><span data-stu-id="fb806-121">Optional.</span></span> <span data-ttu-id="fb806-122">「[Static](../../../visual-basic/language-reference/modifiers/static.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb806-122">See [Static](../../../visual-basic/language-reference/modifiers/static.md).</span></span>

- `ReadOnly`

  <span data-ttu-id="fb806-123">任意。</span><span class="sxs-lookup"><span data-stu-id="fb806-123">Optional.</span></span> <span data-ttu-id="fb806-124">「[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb806-124">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>

- `WithEvents`

<span data-ttu-id="fb806-125">任意。</span><span class="sxs-lookup"><span data-stu-id="fb806-125">Optional.</span></span> <span data-ttu-id="fb806-126">イベントを発生させるクラスのインスタンスを参照するオブジェクト変数であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="fb806-126">Specifies that these are object variables that refer to instances of a class that can raise events.</span></span> <span data-ttu-id="fb806-127">「 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb806-127">See [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).</span></span>

- `variablelist`

  <span data-ttu-id="fb806-128">必須。</span><span class="sxs-lookup"><span data-stu-id="fb806-128">Required.</span></span> <span data-ttu-id="fb806-129">このステートメントで宣言されている変数のリスト。</span><span class="sxs-lookup"><span data-stu-id="fb806-129">List of variables being declared in this statement.</span></span>

  `variable [ , variable ... ]`

  <span data-ttu-id="fb806-130">`variable` の構文と指定項目は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fb806-130">Each `variable` has the following syntax and parts:</span></span>

  <span data-ttu-id="fb806-131">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="fb806-131">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span></span>

  |<span data-ttu-id="fb806-132">要素</span><span class="sxs-lookup"><span data-stu-id="fb806-132">Part</span></span>|<span data-ttu-id="fb806-133">説明</span><span class="sxs-lookup"><span data-stu-id="fb806-133">Description</span></span>|
  |---|---|
  |`variablename`|<span data-ttu-id="fb806-134">必須。</span><span class="sxs-lookup"><span data-stu-id="fb806-134">Required.</span></span> <span data-ttu-id="fb806-135">変数の名前。</span><span class="sxs-lookup"><span data-stu-id="fb806-135">Name of the variable.</span></span> <span data-ttu-id="fb806-136">「[宣言された要素の名前](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb806-136">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|
  |`boundslist`|<span data-ttu-id="fb806-137">任意。</span><span class="sxs-lookup"><span data-stu-id="fb806-137">Optional.</span></span> <span data-ttu-id="fb806-138">配列変数の各次元の境界の一覧。</span><span class="sxs-lookup"><span data-stu-id="fb806-138">List of bounds of each dimension of an array variable.</span></span>|
  |`New`|<span data-ttu-id="fb806-139">任意。</span><span class="sxs-lookup"><span data-stu-id="fb806-139">Optional.</span></span> <span data-ttu-id="fb806-140">`Dim` ステートメントの実行時に、クラスの新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="fb806-140">Creates a new instance of the class when the `Dim` statement runs.</span></span>|
  |`datatype`|<span data-ttu-id="fb806-141">任意。</span><span class="sxs-lookup"><span data-stu-id="fb806-141">Optional.</span></span> <span data-ttu-id="fb806-142">変数のデータ型。</span><span class="sxs-lookup"><span data-stu-id="fb806-142">Data type of the variable.</span></span>|
  |`With`|<span data-ttu-id="fb806-143">任意。</span><span class="sxs-lookup"><span data-stu-id="fb806-143">Optional.</span></span> <span data-ttu-id="fb806-144">オブジェクト初期化子リストについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fb806-144">Introduces the object initializer list.</span></span>|
  |`propertyname`|<span data-ttu-id="fb806-145">任意。</span><span class="sxs-lookup"><span data-stu-id="fb806-145">Optional.</span></span> <span data-ttu-id="fb806-146">インスタンスを作成しているクラスのプロパティの名前。</span><span class="sxs-lookup"><span data-stu-id="fb806-146">The name of a property in the class you are making an instance of.</span></span>|
  |`propinitializer`|<span data-ttu-id="fb806-147">`propertyname` = の後に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb806-147">Required after `propertyname` =.</span></span> <span data-ttu-id="fb806-148">評価され、プロパティ名に割り当てられる式。</span><span class="sxs-lookup"><span data-stu-id="fb806-148">The expression that is evaluated and assigned to the property name.</span></span>|
  |`initializer`|<span data-ttu-id="fb806-149">`New` が指定されていない場合は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="fb806-149">Optional if `New` is not specified.</span></span> <span data-ttu-id="fb806-150">評価され、作成時に変数に割り当てられる式。</span><span class="sxs-lookup"><span data-stu-id="fb806-150">Expression that is evaluated and assigned to the variable when it is created.</span></span>|

## <a name="remarks"></a><span data-ttu-id="fb806-151">コメント</span><span class="sxs-lookup"><span data-stu-id="fb806-151">Remarks</span></span>

<span data-ttu-id="fb806-152">Visual Basic コンパイラは、`Dim` ステートメントを使用して、変数のデータ型やその他の情報 (変数にアクセスできるコードなど) を決定します。</span><span class="sxs-lookup"><span data-stu-id="fb806-152">The Visual Basic compiler uses the `Dim` statement to determine the variable's data type and other information, such as what code can access the variable.</span></span> <span data-ttu-id="fb806-153">次の例では、`Integer` 値を保持する変数を宣言しています。</span><span class="sxs-lookup"><span data-stu-id="fb806-153">The following example declares a variable to hold an `Integer` value.</span></span>

```vb
Dim numberOfStudents As Integer
```

<span data-ttu-id="fb806-154">任意のデータ型を指定することも、列挙型、構造体、クラス、またはインターフェイスの名前を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="fb806-154">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>

```vb
Dim finished As Boolean
Dim monitorBox As System.Windows.Forms.Form
```

<span data-ttu-id="fb806-155">参照型の場合は、`New` キーワードを使用して、データ型によって指定されたクラスまたは構造体の新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="fb806-155">For a reference type, you use the `New` keyword to create a new instance of the class or structure that is specified by the data type.</span></span> <span data-ttu-id="fb806-156">`New`を使用する場合、初期化子式は使用しません。</span><span class="sxs-lookup"><span data-stu-id="fb806-156">If you use `New`, you do not use an initializer expression.</span></span> <span data-ttu-id="fb806-157">代わりに、変数を作成するクラスのコンストラクターに、必要に応じて引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="fb806-157">Instead, you supply arguments, if they are required, to the constructor of the class from which you are creating the variable.</span></span>

```vb
Dim bottomLabel As New System.Windows.Forms.Label
```

<span data-ttu-id="fb806-158">プロシージャ、ブロック、クラス、構造体、またはモジュールで変数を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="fb806-158">You can declare a variable in a procedure, block, class, structure, or module.</span></span> <span data-ttu-id="fb806-159">ソースファイル、名前空間、またはインターフェイスで変数を宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="fb806-159">You cannot declare a variable in a source file, namespace, or interface.</span></span> <span data-ttu-id="fb806-160">詳細については、「[宣言コンテキストと既定のアクセス レベル](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb806-160">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="fb806-161">モジュールレベルで、プロシージャの外部で宣言されている変数は、*メンバー変数*または*フィールド*です。</span><span class="sxs-lookup"><span data-stu-id="fb806-161">A variable that is declared at module level, outside any procedure, is a *member variable* or *field*.</span></span> <span data-ttu-id="fb806-162">メンバー変数は、クラス、構造体、またはモジュール全体でスコープ内にあります。</span><span class="sxs-lookup"><span data-stu-id="fb806-162">Member variables are in scope throughout their class, structure, or module.</span></span> <span data-ttu-id="fb806-163">プロシージャレベルで宣言された変数は、*ローカル変数*です。</span><span class="sxs-lookup"><span data-stu-id="fb806-163">A variable that is declared at procedure level is a *local variable*.</span></span> <span data-ttu-id="fb806-164">ローカル変数は、プロシージャまたはブロック内でのみスコープ内にあります。</span><span class="sxs-lookup"><span data-stu-id="fb806-164">Local variables are in scope only within their procedure or block.</span></span>

<span data-ttu-id="fb806-165">次のアクセス修飾子は、プロシージャの外部で変数を宣言するために使用されます: `Public`、`Protected`、`Friend`、`Protected Friend`、および `Private`。</span><span class="sxs-lookup"><span data-stu-id="fb806-165">The following access modifiers are used to declare variables outside a procedure: `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private`.</span></span> <span data-ttu-id="fb806-166">詳細については、「[Visual Basic でのアクセス レベル](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb806-166">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="fb806-167">`Dim` キーワードは省略可能で、通常、`Public`、`Protected`、`Friend`、`Protected Friend`、`Private`、`Shared`、`Shadows`、`Static`、`ReadOnly`、`WithEvents`のいずれかの修飾子を指定すると省略されます。</span><span class="sxs-lookup"><span data-stu-id="fb806-167">The `Dim` keyword is optional and usually omitted if you specify any of the following modifiers: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, or `WithEvents`.</span></span>

```vb
Public maximumAllowed As Double
Protected Friend currentUserName As String
Private salary As Decimal
Static runningTotal As Integer
```

<span data-ttu-id="fb806-168">`Option Explicit` が on (既定値) の場合、コンパイラは使用するすべての変数の宣言を必要とします。</span><span class="sxs-lookup"><span data-stu-id="fb806-168">If `Option Explicit` is on (the default), the compiler requires a declaration for every variable you use.</span></span> <span data-ttu-id="fb806-169">詳細については、「 [Option Explicit ステートメント](../../../visual-basic/language-reference/statements/option-explicit-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb806-169">For more information, see [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md).</span></span>

## <a name="specifying-an-initial-value"></a><span data-ttu-id="fb806-170">初期値の指定</span><span class="sxs-lookup"><span data-stu-id="fb806-170">Specifying an Initial Value</span></span>

<span data-ttu-id="fb806-171">変数を作成するときに、変数に値を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="fb806-171">You can assign a value to a variable when it is created.</span></span> <span data-ttu-id="fb806-172">値型の場合は、*初期化子*を使用して、変数に代入する式を指定します。</span><span class="sxs-lookup"><span data-stu-id="fb806-172">For a value type, you use an *initializer* to supply an expression to be assigned to the variable.</span></span> <span data-ttu-id="fb806-173">式は、コンパイル時に計算できる定数に評価される必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb806-173">The expression must evaluate to a constant that can be calculated at compile time.</span></span>

```vb
Dim quantity As Integer = 10
Dim message As String = "Just started"
```

<span data-ttu-id="fb806-174">初期化子が指定されていて、`As` 句でデータ型が指定されていない場合、*型の推定*は、初期化子からデータ型を推論するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="fb806-174">If an initializer is specified and a data type is not specified in an `As` clause, *type inference* is used to infer the data type from the initializer.</span></span> <span data-ttu-id="fb806-175">次の例では、`num1` と `num2` の両方が整数として厳密に型指定されています。</span><span class="sxs-lookup"><span data-stu-id="fb806-175">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span> <span data-ttu-id="fb806-176">2番目の宣言では、型の推定によって値3から型が推論されます。</span><span class="sxs-lookup"><span data-stu-id="fb806-176">In the second declaration, type inference infers the type from the value 3.</span></span>

```vb
' Use explicit typing.
Dim num1 As Integer = 3

' Use local type inference.
Dim num2 = 3
```

<span data-ttu-id="fb806-177">型の推定はプロシージャレベルで適用されます。</span><span class="sxs-lookup"><span data-stu-id="fb806-177">Type inference applies at the procedure level.</span></span> <span data-ttu-id="fb806-178">クラス、構造体、モジュール、またはインターフェイスのプロシージャの外側には適用されません。</span><span class="sxs-lookup"><span data-stu-id="fb806-178">It does not apply outside a procedure in a class, structure, module, or interface.</span></span> <span data-ttu-id="fb806-179">型の推定の詳細については、「[オプション推論ステートメント](../../../visual-basic/language-reference/statements/option-infer-statement.md)と[ローカル型の推論](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb806-179">For more information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>

<span data-ttu-id="fb806-180">データ型または初期化子が指定されていない場合の動作については、このトピックで後述する「[既定のデータ型と値](../../../visual-basic/language-reference/statements/dim-statement.md#default)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb806-180">For information about what happens when a data type or initializer is not specified, see [Default Data Types and Values](../../../visual-basic/language-reference/statements/dim-statement.md#default) later in this topic.</span></span>

<span data-ttu-id="fb806-181">*オブジェクト初期化子*を使用して、名前付きの型と匿名型のインスタンスを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="fb806-181">You can use an *object initializer* to declare instances of named and anonymous types.</span></span> <span data-ttu-id="fb806-182">次のコードでは、`Student` クラスのインスタンスを作成し、オブジェクト初期化子を使用してプロパティを初期化します。</span><span class="sxs-lookup"><span data-stu-id="fb806-182">The following code creates an instance of a `Student` class and uses an object initializer to initialize properties.</span></span>

```vb
Dim student1 As New Student With {.First = "Michael",
                                  .Last = "Tucker"}
```

<span data-ttu-id="fb806-183">オブジェクト初期化子の詳細については、「[方法: オブジェクト初期化子を使用してオブジェクトを宣言](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)する」、「[オブジェクト初期化子: 名前付きおよび匿名型](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)」、および「[匿名型](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb806-183">For more information about object initializers, see [How to: Declare an Object by Using an Object Initializer](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), and [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>

## <a name="declaring-multiple-variables"></a><span data-ttu-id="fb806-184">複数の変数の宣言</span><span class="sxs-lookup"><span data-stu-id="fb806-184">Declaring Multiple Variables</span></span>

<span data-ttu-id="fb806-185">1つの宣言ステートメントで複数の変数を宣言し、それぞれに変数名を指定し、各配列名をかっこで囲んで指定することができます。</span><span class="sxs-lookup"><span data-stu-id="fb806-185">You can declare several variables in one declaration statement, specifying the variable name for each one, and following each array name with parentheses.</span></span> <span data-ttu-id="fb806-186">複数の変数を指定するときは、コンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="fb806-186">Multiple variables are separated by commas.</span></span>

```vb
Dim lastTime, nextTime, allTimes() As Date
```

<span data-ttu-id="fb806-187">1つの `As` 句で複数の変数を宣言する場合、その変数グループの初期化子を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="fb806-187">If you declare more than one variable with one `As` clause, you cannot supply an initializer for that group of variables.</span></span>

<span data-ttu-id="fb806-188">宣言する変数ごとに個別の `As` 句を使用して、異なる変数に異なるデータ型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="fb806-188">You can specify different data types for different variables by using a separate `As` clause for each variable you declare.</span></span> <span data-ttu-id="fb806-189">各変数は、`variablename` 部分の後に出現する最初の `As` 句に指定されたデータ型を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="fb806-189">Each variable takes the data type specified in the first `As` clause encountered after its `variablename` part.</span></span>

```vb
Dim a, b, c As Single, x, y As Double, i As Integer
' a, b, and c are all Single; x and y are both Double
```

## <a name="arrays"></a><span data-ttu-id="fb806-190">配列</span><span class="sxs-lookup"><span data-stu-id="fb806-190">Arrays</span></span>

<span data-ttu-id="fb806-191">複数の値を保持できる*配列*を保持する変数を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="fb806-191">You can declare a variable to hold an *array*, which can hold multiple values.</span></span> <span data-ttu-id="fb806-192">変数が配列を保持するように指定するには、その `variablename` の直後にかっこを付けます。</span><span class="sxs-lookup"><span data-stu-id="fb806-192">To specify that a variable holds an array, follow its `variablename` immediately with parentheses.</span></span> <span data-ttu-id="fb806-193">配列の詳細については、「[配列](../../../visual-basic/programming-guide/language-features/arrays/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb806-193">For more information about arrays, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>

<span data-ttu-id="fb806-194">配列の各次元の下限と上限を指定できます。</span><span class="sxs-lookup"><span data-stu-id="fb806-194">You can specify the lower and upper bound of each dimension of an array.</span></span> <span data-ttu-id="fb806-195">これを行うには、かっこ内に `boundslist` を含めます。</span><span class="sxs-lookup"><span data-stu-id="fb806-195">To do this, include a `boundslist` inside the parentheses.</span></span> <span data-ttu-id="fb806-196">ディメンションごとに、`boundslist` は上限を指定し、必要に応じて下限を指定します。</span><span class="sxs-lookup"><span data-stu-id="fb806-196">For each dimension, the `boundslist` specifies the upper bound and optionally the lower bound.</span></span> <span data-ttu-id="fb806-197">下限は、指定したかどうかにかかわらず、常に0になります。</span><span class="sxs-lookup"><span data-stu-id="fb806-197">The lower bound is always zero, whether you specify it or not.</span></span> <span data-ttu-id="fb806-198">各インデックスは、0から上限値までの範囲内で異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fb806-198">Each index can vary from zero through its upper bound value.</span></span>

<span data-ttu-id="fb806-199">次の2つのステートメントは等価です。</span><span class="sxs-lookup"><span data-stu-id="fb806-199">The following two statements are equivalent.</span></span> <span data-ttu-id="fb806-200">各ステートメントは、21個の `Integer` 要素の配列を宣言します。</span><span class="sxs-lookup"><span data-stu-id="fb806-200">Each statement declares an array of 21 `Integer` elements.</span></span> <span data-ttu-id="fb806-201">配列にアクセスする場合、インデックスは 0 ~ 20 で異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fb806-201">When you access the array, the index can vary from 0 through 20.</span></span>

```vb
Dim totals(20) As Integer
Dim totals(0 To 20) As Integer
```

<span data-ttu-id="fb806-202">次のステートメントは、`Double`型の2次元配列を宣言しています。</span><span class="sxs-lookup"><span data-stu-id="fb806-202">The following statement declares a two-dimensional array of type `Double`.</span></span> <span data-ttu-id="fb806-203">配列には、6つの列 (5 + 1) の4行 (3 + 1) があります。</span><span class="sxs-lookup"><span data-stu-id="fb806-203">The array has 4 rows (3 + 1) of 6 columns (5 + 1) each.</span></span> <span data-ttu-id="fb806-204">上限は、ディメンションの長さではなく、インデックスの最大有効値を表します。</span><span class="sxs-lookup"><span data-stu-id="fb806-204">Note that an upper bound represents the highest possible value for the index, not the length of the dimension.</span></span> <span data-ttu-id="fb806-205">ディメンションの長さは、上限に1を加えた値です。</span><span class="sxs-lookup"><span data-stu-id="fb806-205">The length of the dimension is the upper bound plus one.</span></span>

```vb
Dim matrix2(3, 5) As Double
```

<span data-ttu-id="fb806-206">配列は、1 ~ 32 の次元を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="fb806-206">An array can have from 1 to 32 dimensions.</span></span>

<span data-ttu-id="fb806-207">配列宣言では、すべての境界を空白のままにすることができます。</span><span class="sxs-lookup"><span data-stu-id="fb806-207">You can leave all the bounds blank in an array declaration.</span></span> <span data-ttu-id="fb806-208">これを行うと、指定した次元の数が配列に含まれていますが、初期化されていません。</span><span class="sxs-lookup"><span data-stu-id="fb806-208">If you do this, the array has the number of dimensions you specify, but it is uninitialized.</span></span> <span data-ttu-id="fb806-209">この値は、少なくともその要素の一部を初期化するまで `Nothing` の値を持ちます。</span><span class="sxs-lookup"><span data-stu-id="fb806-209">It has a value of `Nothing` until you initialize at least some of its elements.</span></span> <span data-ttu-id="fb806-210">`Dim` ステートメントでは、すべてのディメンションに対して、またはディメンションなしの境界を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb806-210">The `Dim` statement must specify bounds either for all dimensions or for no dimensions.</span></span>

```vb
' Declare an array with blank array bounds.
Dim messages() As String
' Initialize the array.
ReDim messages(4)
```

<span data-ttu-id="fb806-211">配列に複数の次元がある場合は、ディメンションの数を示すために、かっこの間にコンマを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb806-211">If the array has more than one dimension, you must include commas between the parentheses to indicate the number of dimensions.</span></span>

```vb
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte
```

<span data-ttu-id="fb806-212">配列の次元の1つを-1 に宣言することによって、*長さ0の配列*を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="fb806-212">You can declare a *zero-length array* by declaring one of the array's dimensions to be -1.</span></span> <span data-ttu-id="fb806-213">長さ0の配列を保持する変数には `Nothing`値がありません。</span><span class="sxs-lookup"><span data-stu-id="fb806-213">A variable that holds a zero-length array does not have the value `Nothing`.</span></span> <span data-ttu-id="fb806-214">特定の共通言語ランタイム関数では、長さが0の配列が必要です。</span><span class="sxs-lookup"><span data-stu-id="fb806-214">Zero-length arrays are required by certain common language runtime functions.</span></span> <span data-ttu-id="fb806-215">このような配列にアクセスしようとすると、ランタイム例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="fb806-215">If you try to access such an array, a runtime exception occurs.</span></span> <span data-ttu-id="fb806-216">詳細については、「[配列](../../../visual-basic/programming-guide/language-features/arrays/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb806-216">For more information, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>

<span data-ttu-id="fb806-217">配列リテラルを使用して、配列の値を初期化できます。</span><span class="sxs-lookup"><span data-stu-id="fb806-217">You can initialize the values of an array by using an array literal.</span></span> <span data-ttu-id="fb806-218">これを行うには、初期化値を中かっこ (`{}`) で囲みます。</span><span class="sxs-lookup"><span data-stu-id="fb806-218">To do this, surround the initialization values with braces (`{}`).</span></span>

```vb
Dim longArray() As Long = {0, 1, 2, 3}
```

<span data-ttu-id="fb806-219">多次元配列の場合、各次元の初期化は外側の次元で中かっこで囲まれます。</span><span class="sxs-lookup"><span data-stu-id="fb806-219">For multidimensional arrays, the initialization for each separate dimension is enclosed in braces in the outer dimension.</span></span> <span data-ttu-id="fb806-220">これらの要素は、行優先順で指定されます。</span><span class="sxs-lookup"><span data-stu-id="fb806-220">The elements are specified in row-major order.</span></span>

```vb
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}
```

<span data-ttu-id="fb806-221">配列リテラルの詳細については、「[配列](../../../visual-basic/programming-guide/language-features/arrays/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb806-221">For more information about array literals, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>

## <a name="default"></a><span data-ttu-id="fb806-222">既定のデータ型と値</span><span class="sxs-lookup"><span data-stu-id="fb806-222">Default Data Types and Values</span></span>

<span data-ttu-id="fb806-223">次の表では、`Dim` ステートメントのデータ型と初期化子を指定するさまざまな組み合わせの結果を示します。</span><span class="sxs-lookup"><span data-stu-id="fb806-223">The following table describes the results of various combinations of specifying the data type and initializer in a `Dim` statement.</span></span>

|<span data-ttu-id="fb806-224">データ型が指定されているか</span><span class="sxs-lookup"><span data-stu-id="fb806-224">Data type specified?</span></span>|<span data-ttu-id="fb806-225">初期化子が指定されているか</span><span class="sxs-lookup"><span data-stu-id="fb806-225">Initializer specified?</span></span>|<span data-ttu-id="fb806-226">例</span><span class="sxs-lookup"><span data-stu-id="fb806-226">Example</span></span>|<span data-ttu-id="fb806-227">結果</span><span class="sxs-lookup"><span data-stu-id="fb806-227">Result</span></span>|
|---|---|---|---|
|<span data-ttu-id="fb806-228">いいえ</span><span class="sxs-lookup"><span data-stu-id="fb806-228">No</span></span>|<span data-ttu-id="fb806-229">いいえ</span><span class="sxs-lookup"><span data-stu-id="fb806-229">No</span></span>|`Dim qty`|<span data-ttu-id="fb806-230">[Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)がオフ (既定値) の場合、変数は `Nothing`に設定されます。</span><span class="sxs-lookup"><span data-stu-id="fb806-230">If [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="fb806-231">`Option Strict` がオンの場合、コンパイル時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="fb806-231">If `Option Strict` is on, a compile-time error occurs.</span></span>|
|<span data-ttu-id="fb806-232">いいえ</span><span class="sxs-lookup"><span data-stu-id="fb806-232">No</span></span>|<span data-ttu-id="fb806-233">はい</span><span class="sxs-lookup"><span data-stu-id="fb806-233">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="fb806-234">[オプションの推論](../../../visual-basic/language-reference/statements/option-infer-statement.md)が on (既定値) の場合、変数は初期化子のデータ型を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="fb806-234">If [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="fb806-235">「[ローカル型の推定](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb806-235">See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="fb806-236">`Option Infer` がオフで、`Option Strict` がオフの場合、変数は `Object` のデータ型になります。</span><span class="sxs-lookup"><span data-stu-id="fb806-236">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="fb806-237">`Option Infer` がオフで、`Option Strict` がオンの場合、コンパイル時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="fb806-237">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|
|<span data-ttu-id="fb806-238">はい</span><span class="sxs-lookup"><span data-stu-id="fb806-238">Yes</span></span>|<span data-ttu-id="fb806-239">いいえ</span><span class="sxs-lookup"><span data-stu-id="fb806-239">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="fb806-240">変数は、データ型の既定値に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="fb806-240">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="fb806-241">このセクションで後述する表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb806-241">See the table later in this section.</span></span>|
|<span data-ttu-id="fb806-242">はい</span><span class="sxs-lookup"><span data-stu-id="fb806-242">Yes</span></span>|<span data-ttu-id="fb806-243">はい</span><span class="sxs-lookup"><span data-stu-id="fb806-243">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="fb806-244">初期化子のデータ型を指定したデータ型に変換できない場合は、コンパイル時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="fb806-244">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|

<span data-ttu-id="fb806-245">データ型を指定しても初期化子を指定しなかった場合は、Visual Basic 変数をそのデータ型の既定値に初期化します。</span><span class="sxs-lookup"><span data-stu-id="fb806-245">If you specify a data type but do not specify an initializer, Visual Basic initializes the variable to the default value for its data type.</span></span> <span data-ttu-id="fb806-246">既定の初期化値を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="fb806-246">The following table shows the default initialization values.</span></span>

|<span data-ttu-id="fb806-247">データ型</span><span class="sxs-lookup"><span data-stu-id="fb806-247">Data type</span></span>|<span data-ttu-id="fb806-248">既定値</span><span class="sxs-lookup"><span data-stu-id="fb806-248">Default value</span></span>|
|---|---|
|<span data-ttu-id="fb806-249">すべての数値型 (`Byte` と `SByte`を含む)</span><span class="sxs-lookup"><span data-stu-id="fb806-249">All numeric types (including `Byte` and `SByte`)</span></span>|<span data-ttu-id="fb806-250">0</span><span class="sxs-lookup"><span data-stu-id="fb806-250">0</span></span>|
|`Char`|<span data-ttu-id="fb806-251">バイナリ0</span><span class="sxs-lookup"><span data-stu-id="fb806-251">Binary 0</span></span>|
|<span data-ttu-id="fb806-252">すべての参照型 (`Object`、`String`、すべての配列を含む)</span><span class="sxs-lookup"><span data-stu-id="fb806-252">All reference types (including `Object`, `String`, and all arrays)</span></span>|`Nothing`|
|`Boolean`|`False`|
|`Date`|<span data-ttu-id="fb806-253">12:00 年1月1日の午前 (午前 01/01/0001 12:00:00 時)</span><span class="sxs-lookup"><span data-stu-id="fb806-253">12:00 AM of January 1 of the year 1 (01/01/0001 12:00:00 AM)</span></span>|

<span data-ttu-id="fb806-254">構造体の各要素は、個別の変数であるかのように初期化されます。</span><span class="sxs-lookup"><span data-stu-id="fb806-254">Each element of a structure is initialized as if it were a separate variable.</span></span> <span data-ttu-id="fb806-255">配列の長さを宣言するが、その要素を初期化しない場合、各要素は個別の変数であるかのように初期化されます。</span><span class="sxs-lookup"><span data-stu-id="fb806-255">If you declare the length of an array but do not initialize its elements, each element is initialized as if it were a separate variable.</span></span>

## <a name="static-local-variable-lifetime"></a><span data-ttu-id="fb806-256">静的ローカル変数の有効期間</span><span class="sxs-lookup"><span data-stu-id="fb806-256">Static Local Variable Lifetime</span></span>

<span data-ttu-id="fb806-257">`Static` ローカル変数の有効期間は、宣言されているプロシージャよりも長くなります。</span><span class="sxs-lookup"><span data-stu-id="fb806-257">A `Static` local variable has a longer lifetime than that of the procedure in which it is declared.</span></span> <span data-ttu-id="fb806-258">変数の有効期間の境界は、プロシージャが宣言されている場所と `Shared`かどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="fb806-258">The boundaries of the variable's lifetime depend on where the procedure is declared and whether it is `Shared`.</span></span>

|<span data-ttu-id="fb806-259">プロシージャの宣言</span><span class="sxs-lookup"><span data-stu-id="fb806-259">Procedure declaration</span></span>|<span data-ttu-id="fb806-260">変数の初期化</span><span class="sxs-lookup"><span data-stu-id="fb806-260">Variable initialized</span></span>|<span data-ttu-id="fb806-261">既存の変数の停止</span><span class="sxs-lookup"><span data-stu-id="fb806-261">Variable stops existing</span></span>|
|---|---|---|
|<span data-ttu-id="fb806-262">モジュール内</span><span class="sxs-lookup"><span data-stu-id="fb806-262">In a module</span></span>|<span data-ttu-id="fb806-263">プロシージャが初めて呼び出されたとき</span><span class="sxs-lookup"><span data-stu-id="fb806-263">The first time the procedure is called</span></span>|<span data-ttu-id="fb806-264">プログラムの実行を停止したとき</span><span class="sxs-lookup"><span data-stu-id="fb806-264">When your program stops execution</span></span>|
|<span data-ttu-id="fb806-265">クラスまたは構造体では、プロシージャは `Shared`</span><span class="sxs-lookup"><span data-stu-id="fb806-265">In a class or structure, procedure is `Shared`</span></span>|<span data-ttu-id="fb806-266">プロシージャが最初に呼び出されたときに、特定のインスタンスまたはクラスまたは構造体自体で呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="fb806-266">The first time the procedure is called either on a specific instance or on the class or structure itself</span></span>|<span data-ttu-id="fb806-267">プログラムの実行を停止したとき</span><span class="sxs-lookup"><span data-stu-id="fb806-267">When your program stops execution</span></span>|
|<span data-ttu-id="fb806-268">クラスまたは構造体では、プロシージャは `Shared` ません。</span><span class="sxs-lookup"><span data-stu-id="fb806-268">In a class or structure, procedure isn't `Shared`</span></span>|<span data-ttu-id="fb806-269">特定のインスタンスで最初にプロシージャが呼び出されたとき</span><span class="sxs-lookup"><span data-stu-id="fb806-269">The first time the procedure is called on a specific instance</span></span>|<span data-ttu-id="fb806-270">インスタンスがガベージコレクション (GC) 用に解放されたとき</span><span class="sxs-lookup"><span data-stu-id="fb806-270">When the instance is released for garbage collection (GC)</span></span>|

## <a name="attributes-and-modifiers"></a><span data-ttu-id="fb806-271">属性と修飾子</span><span class="sxs-lookup"><span data-stu-id="fb806-271">Attributes and Modifiers</span></span>

<span data-ttu-id="fb806-272">属性は、ローカル変数ではなくメンバー変数にのみ適用できます。</span><span class="sxs-lookup"><span data-stu-id="fb806-272">You can apply attributes only to member variables, not to local variables.</span></span> <span data-ttu-id="fb806-273">属性は、アセンブリのメタデータに情報を提供します。これは、ローカル変数などの一時的なストレージには意味がありません。</span><span class="sxs-lookup"><span data-stu-id="fb806-273">An attribute contributes information to the assembly's metadata, which is not meaningful for temporary storage such as local variables.</span></span>

<span data-ttu-id="fb806-274">モジュールレベルでは、`Static` 修飾子を使用してメンバー変数を宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="fb806-274">At module level, you cannot use the `Static` modifier to declare member variables.</span></span> <span data-ttu-id="fb806-275">プロシージャレベルでは、`Shared`、`Shadows`、`ReadOnly`、`WithEvents`、または任意のアクセス修飾子を使用してローカル変数を宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="fb806-275">At procedure level, you cannot use `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, or any access modifiers to declare local variables.</span></span>

<span data-ttu-id="fb806-276">`accessmodifier`を指定することによって、変数にアクセスできるコードを指定できます。</span><span class="sxs-lookup"><span data-stu-id="fb806-276">You can specify what code can access a variable by supplying an `accessmodifier`.</span></span> <span data-ttu-id="fb806-277">クラスおよびモジュールメンバー変数 (プロシージャ以外) では、既定でプライベートアクセスが使用され、構造体メンバー変数は既定でパブリックアクセスになります。</span><span class="sxs-lookup"><span data-stu-id="fb806-277">Class and module member variables (outside any procedure) default to private access, and structure member variables default to public access.</span></span> <span data-ttu-id="fb806-278">アクセス修飾子を使用してこれらのアクセス レベルを調整できます。</span><span class="sxs-lookup"><span data-stu-id="fb806-278">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="fb806-279">ローカル変数 (プロシージャ内) では、アクセス修飾子を使用できません。</span><span class="sxs-lookup"><span data-stu-id="fb806-279">You cannot use access modifiers on local variables (inside a procedure).</span></span>

<span data-ttu-id="fb806-280">`WithEvents` は、プロシージャ内のローカル変数ではなく、メンバー変数に対してのみ指定できます。</span><span class="sxs-lookup"><span data-stu-id="fb806-280">You can specify `WithEvents` only on member variables, not on local variables inside a procedure.</span></span> <span data-ttu-id="fb806-281">`WithEvents`を指定する場合、変数のデータ型は、`Object`ではなく、特定のクラス型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb806-281">If you specify `WithEvents`, the data type of the variable must be a specific class type, not `Object`.</span></span> <span data-ttu-id="fb806-282">`WithEvents`で配列を宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="fb806-282">You cannot declare an array with `WithEvents`.</span></span> <span data-ttu-id="fb806-283">イベントの詳細については、「 [events](../../../visual-basic/programming-guide/language-features/events/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb806-283">For more information about events, see [Events](../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fb806-284">クラス、構造体、またはモジュールの外部のコードでは、メンバー変数の名前を、そのクラス、構造体、またはモジュールの名前で修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb806-284">Code outside a class, structure, or module must qualify a member variable's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="fb806-285">プロシージャまたはブロックの外側のコードは、そのプロシージャまたはブロック内のローカル変数を参照できません。</span><span class="sxs-lookup"><span data-stu-id="fb806-285">Code outside a procedure or block cannot refer to any local variables within that procedure or block.</span></span>

## <a name="releasing-managed-resources"></a><span data-ttu-id="fb806-286">マネージリソースの解放</span><span class="sxs-lookup"><span data-stu-id="fb806-286">Releasing Managed Resources</span></span>

<span data-ttu-id="fb806-287">.NET Framework ガベージコレクターは、追加のコーディングなしでマネージリソースを破棄します。</span><span class="sxs-lookup"><span data-stu-id="fb806-287">The .NET Framework garbage collector disposes of managed resources without any extra coding on your part.</span></span> <span data-ttu-id="fb806-288">ただし、ガベージコレクターを待機するのではなく、マネージリソースを強制的に破棄することができます。</span><span class="sxs-lookup"><span data-stu-id="fb806-288">However, you can force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>

<span data-ttu-id="fb806-289">クラスが特に貴重なリソース (データベース接続やファイルハンドルなど) を保持している場合は、次のガベージコレクションが使用されなくなったクラスインスタンスをクリーンアップするまで待機することはできません。</span><span class="sxs-lookup"><span data-stu-id="fb806-289">If a class holds onto a particularly valuable and scarce resource (such as a database connection or file handle), you might not want to wait until the next garbage collection to clean up a class instance that's no longer in use.</span></span> <span data-ttu-id="fb806-290">クラスは、ガベージコレクションの前にリソースを解放する手段を提供するために、<xref:System.IDisposable> インターフェイスを実装できます。</span><span class="sxs-lookup"><span data-stu-id="fb806-290">A class may implement the <xref:System.IDisposable> interface to provide a way to release resources before a garbage collection.</span></span> <span data-ttu-id="fb806-291">このインターフェイスを実装するクラスは、重要なリソースを直ちに解放するために呼び出すことができる `Dispose` メソッドを公開します。</span><span class="sxs-lookup"><span data-stu-id="fb806-291">A class that implements that interface exposes a `Dispose` method that can be called to force valuable resources to be released immediately.</span></span>

<span data-ttu-id="fb806-292">`Using` ステートメントは、リソースを取得し、一連のステートメントを実行して、リソースを破棄するプロセスを自動化します。</span><span class="sxs-lookup"><span data-stu-id="fb806-292">The `Using` statement automates the process of acquiring a resource, executing a set of statements, and then disposing of the resource.</span></span> <span data-ttu-id="fb806-293">ただし、リソースは <xref:System.IDisposable> インターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb806-293">However, the resource must implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="fb806-294">詳細については、「[sing ステートメント](../../../visual-basic/language-reference/statements/using-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb806-294">For more information, see [Using Statement](../../../visual-basic/language-reference/statements/using-statement.md).</span></span>

## <a name="example"></a><span data-ttu-id="fb806-295">例</span><span class="sxs-lookup"><span data-stu-id="fb806-295">Example</span></span>

<span data-ttu-id="fb806-296">次の例では、さまざまなオプションを使用して `Dim` ステートメントを使用して変数を宣言しています。</span><span class="sxs-lookup"><span data-stu-id="fb806-296">The following example declares variables by using the `Dim` statement with various options.</span></span>

[!code-vb[VbVbalrStatements#141](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#141)]

## <a name="example"></a><span data-ttu-id="fb806-297">例</span><span class="sxs-lookup"><span data-stu-id="fb806-297">Example</span></span>

<span data-ttu-id="fb806-298">次の例では、1から30までの素数を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="fb806-298">The following example lists the prime numbers between 1 and 30.</span></span> <span data-ttu-id="fb806-299">ローカル変数のスコープについては、「コードコメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb806-299">The scope of local variables is described in code comments.</span></span>

[!code-vb[VbVbalrStatements#142](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#142)]

## <a name="example"></a><span data-ttu-id="fb806-300">例</span><span class="sxs-lookup"><span data-stu-id="fb806-300">Example</span></span>

<span data-ttu-id="fb806-301">次の例では、`speedValue` 変数がクラスレベルで宣言されています。</span><span class="sxs-lookup"><span data-stu-id="fb806-301">In the following example, the `speedValue` variable is declared at the class level.</span></span> <span data-ttu-id="fb806-302">`Private` キーワードは、変数を宣言するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="fb806-302">The `Private` keyword is used to declare the variable.</span></span> <span data-ttu-id="fb806-303">変数には、`Car` クラスの任意のプロシージャからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fb806-303">The variable can be accessed by any procedure in the `Car` class.</span></span>

[!code-vb[VbVbalrStatements#144](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#144)]

[!code-vb[VbVbalrStatements#145](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#145)]

## <a name="see-also"></a><span data-ttu-id="fb806-304">関連項目</span><span class="sxs-lookup"><span data-stu-id="fb806-304">See also</span></span>

- [<span data-ttu-id="fb806-305">Const ステートメント</span><span class="sxs-lookup"><span data-stu-id="fb806-305">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="fb806-306">ReDim ステートメント</span><span class="sxs-lookup"><span data-stu-id="fb806-306">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="fb806-307">Option Explicit ステートメント</span><span class="sxs-lookup"><span data-stu-id="fb806-307">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="fb806-308">Option Infer ステートメント</span><span class="sxs-lookup"><span data-stu-id="fb806-308">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="fb806-309">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="fb806-309">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- <span data-ttu-id="fb806-310">[[コンパイル] ページ、プロジェクト デザイナー (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="fb806-310">[Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)</span></span>
- [<span data-ttu-id="fb806-311">変数宣言</span><span class="sxs-lookup"><span data-stu-id="fb806-311">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="fb806-312">配列</span><span class="sxs-lookup"><span data-stu-id="fb806-312">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="fb806-313">オブジェクト初期化子 : 名前付きの型と匿名型</span><span class="sxs-lookup"><span data-stu-id="fb806-313">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="fb806-314">匿名型</span><span class="sxs-lookup"><span data-stu-id="fb806-314">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="fb806-315">オブジェクト初期化子 : 名前付きの型と匿名型</span><span class="sxs-lookup"><span data-stu-id="fb806-315">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="fb806-316">方法 : オブジェクト初期化子を使用してオブジェクトを宣言する</span><span class="sxs-lookup"><span data-stu-id="fb806-316">How to: Declare an Object by Using an Object Initializer</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
- [<span data-ttu-id="fb806-317">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="fb806-317">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
