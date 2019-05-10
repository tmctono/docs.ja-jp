---
title: Dim ステートメント (Visual Basic)
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
ms.openlocfilehash: 5a16060efc45cc0642aa6612d02644e252cd53d9
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64751800"
---
# <a name="dim-statement-visual-basic"></a><span data-ttu-id="e9988-102">Dim ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e9988-102">Dim Statement (Visual Basic)</span></span>

<span data-ttu-id="e9988-103">宣言し、1 つまたは複数の変数の記憶域を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e9988-103">Declares and allocates storage space for one or more variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="e9988-104">構文</span><span class="sxs-lookup"><span data-stu-id="e9988-104">Syntax</span></span>

```
[ <attributelist> ] [ accessmodifier ] [[ Shared ] [ Shadows ] | [ Static ]] [ ReadOnly ]
Dim [ WithEvents ] variablelist
```

## <a name="parts"></a><span data-ttu-id="e9988-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="e9988-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="e9988-106">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e9988-106">Optional.</span></span> <span data-ttu-id="e9988-107">参照してください[属性リスト](../../../visual-basic/language-reference/statements/attribute-list.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9988-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>

- `accessmodifier`

  <span data-ttu-id="e9988-108">任意。</span><span class="sxs-lookup"><span data-stu-id="e9988-108">Optional.</span></span> <span data-ttu-id="e9988-109">次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="e9988-109">Can be one of the following:</span></span>

  - [<span data-ttu-id="e9988-110">Public</span><span class="sxs-lookup"><span data-stu-id="e9988-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)

  - [<span data-ttu-id="e9988-111">Protected</span><span class="sxs-lookup"><span data-stu-id="e9988-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)

  - [<span data-ttu-id="e9988-112">Friend</span><span class="sxs-lookup"><span data-stu-id="e9988-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)

  - [<span data-ttu-id="e9988-113">Private</span><span class="sxs-lookup"><span data-stu-id="e9988-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)

  - [<span data-ttu-id="e9988-114">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="e9988-114">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

  - [<span data-ttu-id="e9988-115">Private Protected</span><span class="sxs-lookup"><span data-stu-id="e9988-115">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

  <span data-ttu-id="e9988-116">「 [Visual Basic でのアクセス レベル](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9988-116">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `Shared`

  <span data-ttu-id="e9988-117">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e9988-117">Optional.</span></span> <span data-ttu-id="e9988-118">参照してください[共有](../../../visual-basic/language-reference/modifiers/shared.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9988-118">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="e9988-119">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e9988-119">Optional.</span></span> <span data-ttu-id="e9988-120">参照してください[Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9988-120">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>

- `Static`

  <span data-ttu-id="e9988-121">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e9988-121">Optional.</span></span> <span data-ttu-id="e9988-122">参照してください[静的](../../../visual-basic/language-reference/modifiers/static.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9988-122">See [Static](../../../visual-basic/language-reference/modifiers/static.md).</span></span>

- `ReadOnly`

  <span data-ttu-id="e9988-123">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e9988-123">Optional.</span></span> <span data-ttu-id="e9988-124">参照してください[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9988-124">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>

- `WithEvents`

<span data-ttu-id="e9988-125">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e9988-125">Optional.</span></span> <span data-ttu-id="e9988-126">これらはイベントを発生させるクラスのインスタンスを参照するオブジェクト変数であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="e9988-126">Specifies that these are object variables that refer to instances of a class that can raise events.</span></span> <span data-ttu-id="e9988-127">参照してください[WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9988-127">See [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).</span></span>

- `variablelist`

  <span data-ttu-id="e9988-128">必須。</span><span class="sxs-lookup"><span data-stu-id="e9988-128">Required.</span></span> <span data-ttu-id="e9988-129">このステートメントで宣言されている変数の一覧。</span><span class="sxs-lookup"><span data-stu-id="e9988-129">List of variables being declared in this statement.</span></span>

  `variable [ , variable ... ]`

  <span data-ttu-id="e9988-130">`variable` の構文と指定項目は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e9988-130">Each `variable` has the following syntax and parts:</span></span>

  <span data-ttu-id="e9988-131">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="e9988-131">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span></span>

  |<span data-ttu-id="e9988-132">パーツ</span><span class="sxs-lookup"><span data-stu-id="e9988-132">Part</span></span>|<span data-ttu-id="e9988-133">説明</span><span class="sxs-lookup"><span data-stu-id="e9988-133">Description</span></span>|
  |---|---|
  |`variablename`|<span data-ttu-id="e9988-134">必須。</span><span class="sxs-lookup"><span data-stu-id="e9988-134">Required.</span></span> <span data-ttu-id="e9988-135">変数名。</span><span class="sxs-lookup"><span data-stu-id="e9988-135">Name of the variable.</span></span> <span data-ttu-id="e9988-136">「 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9988-136">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|
  |`boundslist`|<span data-ttu-id="e9988-137">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e9988-137">Optional.</span></span> <span data-ttu-id="e9988-138">配列変数の各次元の境界の一覧です。</span><span class="sxs-lookup"><span data-stu-id="e9988-138">List of bounds of each dimension of an array variable.</span></span>|
  |`New`|<span data-ttu-id="e9988-139">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e9988-139">Optional.</span></span> <span data-ttu-id="e9988-140">クラスの新しいインスタンスを作成時に、`Dim`ステートメントが実行されています。</span><span class="sxs-lookup"><span data-stu-id="e9988-140">Creates a new instance of the class when the `Dim` statement runs.</span></span>|
  |`datatype`|<span data-ttu-id="e9988-141">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e9988-141">Optional.</span></span> <span data-ttu-id="e9988-142">変数のデータ型。</span><span class="sxs-lookup"><span data-stu-id="e9988-142">Data type of the variable.</span></span>|
  |`With`|<span data-ttu-id="e9988-143">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e9988-143">Optional.</span></span> <span data-ttu-id="e9988-144">オブジェクト初期化子リストが導入されています。</span><span class="sxs-lookup"><span data-stu-id="e9988-144">Introduces the object initializer list.</span></span>|
  |`propertyname`|<span data-ttu-id="e9988-145">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e9988-145">Optional.</span></span> <span data-ttu-id="e9988-146">クラスのプロパティの名前のインスタンスを行っています。</span><span class="sxs-lookup"><span data-stu-id="e9988-146">The name of a property in the class you are making an instance of.</span></span>|
  |`propinitializer`|<span data-ttu-id="e9988-147">後に必要な`propertyname`=。</span><span class="sxs-lookup"><span data-stu-id="e9988-147">Required after `propertyname` =.</span></span> <span data-ttu-id="e9988-148">式が評価され、プロパティ名に割り当てられているです。</span><span class="sxs-lookup"><span data-stu-id="e9988-148">The expression that is evaluated and assigned to the property name.</span></span>|
  |`initializer`|<span data-ttu-id="e9988-149">省略可能な場合`New`が指定されていません。</span><span class="sxs-lookup"><span data-stu-id="e9988-149">Optional if `New` is not specified.</span></span> <span data-ttu-id="e9988-150">評価され、作成時にその変数に代入する式。</span><span class="sxs-lookup"><span data-stu-id="e9988-150">Expression that is evaluated and assigned to the variable when it is created.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e9988-151">Remarks</span><span class="sxs-lookup"><span data-stu-id="e9988-151">Remarks</span></span>

<span data-ttu-id="e9988-152">Visual Basic コンパイラを使用して、`Dim`ステートメント、変数のデータ型と変数にアクセスできるコードなどの他の情報を決定します。</span><span class="sxs-lookup"><span data-stu-id="e9988-152">The Visual Basic compiler uses the `Dim` statement to determine the variable's data type and other information, such as what code can access the variable.</span></span> <span data-ttu-id="e9988-153">次の例を保持する変数の宣言、`Integer`値。</span><span class="sxs-lookup"><span data-stu-id="e9988-153">The following example declares a variable to hold an `Integer` value.</span></span>

```vb
Dim numberOfStudents As Integer
```

<span data-ttu-id="e9988-154">任意のデータ型または列挙型、構造体、クラス、インターフェイスの名前を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="e9988-154">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>

```vb
Dim finished As Boolean
Dim monitorBox As System.Windows.Forms.Form
```

<span data-ttu-id="e9988-155">使用する参照型の場合、`New`データ型で、クラスの新しいインスタンスを作成または構造体のキーワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="e9988-155">For a reference type, you use the `New` keyword to create a new instance of the class or structure that is specified by the data type.</span></span> <span data-ttu-id="e9988-156">使用する場合`New`、初期化子式を使用しません。</span><span class="sxs-lookup"><span data-stu-id="e9988-156">If you use `New`, you do not use an initializer expression.</span></span> <span data-ttu-id="e9988-157">代わりに、変数の作成元となるクラスのコンス トラクターに必要な場合は、引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="e9988-157">Instead, you supply arguments, if they are required, to the constructor of the class from which you are creating the variable.</span></span>

```vb
Dim bottomLabel As New System.Windows.Forms.Label
```

<span data-ttu-id="e9988-158">プロシージャ、ブロック、クラス、構造体、またはモジュール内の変数を宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="e9988-158">You can declare a variable in a procedure, block, class, structure, or module.</span></span> <span data-ttu-id="e9988-159">ソース ファイル、名前空間、またはインターフェイスの変数を宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="e9988-159">You cannot declare a variable in a source file, namespace, or interface.</span></span> <span data-ttu-id="e9988-160">詳細については、「[宣言コンテキストと既定のアクセス レベル](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9988-160">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="e9988-161">プロシージャの外部のモジュール レベルで宣言されている変数は、*メンバー変数*または*フィールド*します。</span><span class="sxs-lookup"><span data-stu-id="e9988-161">A variable that is declared at module level, outside any procedure, is a *member variable* or *field*.</span></span> <span data-ttu-id="e9988-162">メンバー変数は、そのクラス、構造体、またはモジュール全体にわたってスコープになります。</span><span class="sxs-lookup"><span data-stu-id="e9988-162">Member variables are in scope throughout their class, structure, or module.</span></span> <span data-ttu-id="e9988-163">プロシージャ レベルで宣言されている変数は、*ローカル変数*します。</span><span class="sxs-lookup"><span data-stu-id="e9988-163">A variable that is declared at procedure level is a *local variable*.</span></span> <span data-ttu-id="e9988-164">ローカル変数は、そのプロシージャまたはブロック内でのみスコープになります。</span><span class="sxs-lookup"><span data-stu-id="e9988-164">Local variables are in scope only within their procedure or block.</span></span>

<span data-ttu-id="e9988-165">次のアクセス修飾子を使用して、プロシージャの外部変数の宣言: `Public`、 `Protected`、 `Friend`、 `Protected Friend`、および`Private`します。</span><span class="sxs-lookup"><span data-stu-id="e9988-165">The following access modifiers are used to declare variables outside a procedure: `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private`.</span></span> <span data-ttu-id="e9988-166">詳細については、[ Visual Basic のアクセス レベル](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9988-166">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="e9988-167">`Dim`キーワードが省略可能、通常、次の修飾子のいずれかを指定する場合を省略して: `Public`、 `Protected`、 `Friend`、 `Protected Friend`、 `Private`、 `Shared`、 `Shadows`、 `Static`、`ReadOnly`、または`WithEvents`します。</span><span class="sxs-lookup"><span data-stu-id="e9988-167">The `Dim` keyword is optional and usually omitted if you specify any of the following modifiers: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, or `WithEvents`.</span></span>

```vb
Public maximumAllowed As Double
Protected Friend currentUserName As String
Private salary As Decimal
Static runningTotal As Integer
```

<span data-ttu-id="e9988-168">場合`Option Explicit`はコンパイラ on (既定値) を使用するすべての変数の宣言が必要です。</span><span class="sxs-lookup"><span data-stu-id="e9988-168">If `Option Explicit` is on (the default), the compiler requires a declaration for every variable you use.</span></span> <span data-ttu-id="e9988-169">詳細については、次を参照してください。 [Option Explicit ステートメント](../../../visual-basic/language-reference/statements/option-explicit-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9988-169">For more information, see [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md).</span></span>

## <a name="specifying-an-initial-value"></a><span data-ttu-id="e9988-170">初期値を指定します。</span><span class="sxs-lookup"><span data-stu-id="e9988-170">Specifying an Initial Value</span></span>

<span data-ttu-id="e9988-171">作成時にその変数に値を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e9988-171">You can assign a value to a variable when it is created.</span></span> <span data-ttu-id="e9988-172">使用する値型の場合、*初期化子*変数に割り当てられる式を指定します。</span><span class="sxs-lookup"><span data-stu-id="e9988-172">For a value type, you use an *initializer* to supply an expression to be assigned to the variable.</span></span> <span data-ttu-id="e9988-173">式は、コンパイル時に計算できる定数に評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9988-173">The expression must evaluate to a constant that can be calculated at compile time.</span></span>

```vb
Dim quantity As Integer = 10
Dim message As String = "Just started"
```

<span data-ttu-id="e9988-174">初期化子が指定され、データ型がで指定されていない場合、`As`句、*型推論*初期化子からのデータ型を推定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="e9988-174">If an initializer is specified and a data type is not specified in an `As` clause, *type inference* is used to infer the data type from the initializer.</span></span> <span data-ttu-id="e9988-175">次の例では、どちらも`num1`と`num2`整数として厳密に型指定します。</span><span class="sxs-lookup"><span data-stu-id="e9988-175">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span> <span data-ttu-id="e9988-176">2 番目の宣言では、型の推定は、値は 3 から型を推測します。</span><span class="sxs-lookup"><span data-stu-id="e9988-176">In the second declaration, type inference infers the type from the value 3.</span></span>

```vb
' Use explicit typing.
Dim num1 As Integer = 3

' Use local type inference.
Dim num2 = 3
```

<span data-ttu-id="e9988-177">型の推定は、プロシージャ レベルで適用されます。</span><span class="sxs-lookup"><span data-stu-id="e9988-177">Type inference applies at the procedure level.</span></span> <span data-ttu-id="e9988-178">クラス、構造体、モジュール、またはインターフェイスのプロシージャの外側は適用されません。</span><span class="sxs-lookup"><span data-stu-id="e9988-178">It does not apply outside a procedure in a class, structure, module, or interface.</span></span> <span data-ttu-id="e9988-179">型の推定に関する詳細については、次を参照してください。 [Option Infer ステートメント](../../../visual-basic/language-reference/statements/option-infer-statement.md)と[ローカル型推論](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9988-179">For more information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>

<span data-ttu-id="e9988-180">データ型または初期化子が指定されていないときの動作については、次を参照してください。[既定のデータ型と値](../../../visual-basic/language-reference/statements/dim-statement.md#default)このトピックで後述します。</span><span class="sxs-lookup"><span data-stu-id="e9988-180">For information about what happens when a data type or initializer is not specified, see [Default Data Types and Values](../../../visual-basic/language-reference/statements/dim-statement.md#default) later in this topic.</span></span>

<span data-ttu-id="e9988-181">使用することができます、*オブジェクト初期化子*を名前付きの匿名型のインスタンスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="e9988-181">You can use an *object initializer* to declare instances of named and anonymous types.</span></span> <span data-ttu-id="e9988-182">インスタンスを作成する次のコードを`Student`クラスし、プロパティを初期化するために、オブジェクト初期化子を使用します。</span><span class="sxs-lookup"><span data-stu-id="e9988-182">The following code creates an instance of a `Student` class and uses an object initializer to initialize properties.</span></span>

```vb
Dim student1 As New Student With {.First = "Michael",
                                  .Last = "Tucker"}
```

<span data-ttu-id="e9988-183">オブジェクト初期化子の詳細については、次を参照してください。[方法。オブジェクト初期化子を使用してオブジェクトを宣言](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)、[オブジェクト初期化子。名前付きの匿名型](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)、および[匿名型](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9988-183">For more information about object initializers, see [How to: Declare an Object by Using an Object Initializer](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), and [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>

## <a name="declaring-multiple-variables"></a><span data-ttu-id="e9988-184">複数の変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="e9988-184">Declaring Multiple Variables</span></span>

<span data-ttu-id="e9988-185">かっこで囲んで、それぞれの次の各配列名の変数名を指定する 1 つの宣言ステートメントで複数の変数を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="e9988-185">You can declare several variables in one declaration statement, specifying the variable name for each one, and following each array name with parentheses.</span></span> <span data-ttu-id="e9988-186">複数の変数を指定するときは、コンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="e9988-186">Multiple variables are separated by commas.</span></span>

```vb
Dim lastTime, nextTime, allTimes() As Date
```

<span data-ttu-id="e9988-187">いずれかで 1 つ以上の変数を宣言する場合`As`句では、そのグループの変数の初期化子を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="e9988-187">If you declare more than one variable with one `As` clause, you cannot supply an initializer for that group of variables.</span></span>

<span data-ttu-id="e9988-188">異なる変数に異なるデータ型を指定するには、個別を使用して`As`を宣言する変数ごとの句。</span><span class="sxs-lookup"><span data-stu-id="e9988-188">You can specify different data types for different variables by using a separate `As` clause for each variable you declare.</span></span> <span data-ttu-id="e9988-189">各変数は、最初に指定されたデータ型を受け取る`As`句の後に発生したその`variablename`部分。</span><span class="sxs-lookup"><span data-stu-id="e9988-189">Each variable takes the data type specified in the first `As` clause encountered after its `variablename` part.</span></span>

```vb
Dim a, b, c As Single, x, y As Double, i As Integer
' a, b, and c are all Single; x and y are both Double
```

## <a name="arrays"></a><span data-ttu-id="e9988-190">配列</span><span class="sxs-lookup"><span data-stu-id="e9988-190">Arrays</span></span>

<span data-ttu-id="e9988-191">保持する変数を宣言することができます、*配列*、複数の値を保持することができます。</span><span class="sxs-lookup"><span data-stu-id="e9988-191">You can declare a variable to hold an *array*, which can hold multiple values.</span></span> <span data-ttu-id="e9988-192">次の変数は配列を保持することを指定するその`variablename`かっこですぐにします。</span><span class="sxs-lookup"><span data-stu-id="e9988-192">To specify that a variable holds an array, follow its `variablename` immediately with parentheses.</span></span> <span data-ttu-id="e9988-193">配列の詳細については、「[配列](../../../visual-basic/programming-guide/language-features/arrays/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9988-193">For more information about arrays, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>

<span data-ttu-id="e9988-194">配列の各次元の上限と下限を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="e9988-194">You can specify the lower and upper bound of each dimension of an array.</span></span> <span data-ttu-id="e9988-195">これを行うには、`boundslist`かっこで囲んでいます。</span><span class="sxs-lookup"><span data-stu-id="e9988-195">To do this, include a `boundslist` inside the parentheses.</span></span> <span data-ttu-id="e9988-196">各ディメンションに対して、`boundslist`上限と下限の境界、必要に応じてを指定します。</span><span class="sxs-lookup"><span data-stu-id="e9988-196">For each dimension, the `boundslist` specifies the upper bound and optionally the lower bound.</span></span> <span data-ttu-id="e9988-197">下限の境界は常に、0、ですか、指定するかどうか。</span><span class="sxs-lookup"><span data-stu-id="e9988-197">The lower bound is always zero, whether you specify it or not.</span></span> <span data-ttu-id="e9988-198">各インデックスは 0 ~ 上限値によって異なります。</span><span class="sxs-lookup"><span data-stu-id="e9988-198">Each index can vary from zero through its upper bound value.</span></span>

<span data-ttu-id="e9988-199">次の 2 つのステートメントは同等です。</span><span class="sxs-lookup"><span data-stu-id="e9988-199">The following two statements are equivalent.</span></span> <span data-ttu-id="e9988-200">各ステートメントは、21 の配列を宣言します。`Integer`要素。</span><span class="sxs-lookup"><span data-stu-id="e9988-200">Each statement declares an array of 21 `Integer` elements.</span></span> <span data-ttu-id="e9988-201">配列にアクセスするときに 0 ~ 20 のインデックスと異なることができます。</span><span class="sxs-lookup"><span data-stu-id="e9988-201">When you access the array, the index can vary from 0 through 20.</span></span>

```vb
Dim totals(20) As Integer
Dim totals(0 To 20) As Integer
```

<span data-ttu-id="e9988-202">次のステートメントは、2 次元配列の型を宣言します`Double`します。</span><span class="sxs-lookup"><span data-stu-id="e9988-202">The following statement declares a two-dimensional array of type `Double`.</span></span> <span data-ttu-id="e9988-203">配列には、6 列 (5 + 1) 各の行 (3 + 1) 4 があります。</span><span class="sxs-lookup"><span data-stu-id="e9988-203">The array has 4 rows (3 + 1) of 6 columns (5 + 1) each.</span></span> <span data-ttu-id="e9988-204">上限の次元の長さではなく、インデックスの最大値を表すことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e9988-204">Note that an upper bound represents the highest possible value for the index, not the length of the dimension.</span></span> <span data-ttu-id="e9988-205">次元の長さは、上限の境界と 1 つです。</span><span class="sxs-lookup"><span data-stu-id="e9988-205">The length of the dimension is the upper bound plus one.</span></span>

```vb
Dim matrix2(3, 5) As Double
```

<span data-ttu-id="e9988-206">配列は、1 から 32 次元ができます。</span><span class="sxs-lookup"><span data-stu-id="e9988-206">An array can have from 1 to 32 dimensions.</span></span>

<span data-ttu-id="e9988-207">すべての境界に配列の宣言では空白にしておきます。</span><span class="sxs-lookup"><span data-stu-id="e9988-207">You can leave all the bounds blank in an array declaration.</span></span> <span data-ttu-id="e9988-208">これを行う場合は、配列が指定すると、ディメンションの数が初期化されていません。</span><span class="sxs-lookup"><span data-stu-id="e9988-208">If you do this, the array has the number of dimensions you specify, but it is uninitialized.</span></span> <span data-ttu-id="e9988-209">値を持つ、`Nothing`少なくとも初期化するまでの一部の要素。</span><span class="sxs-lookup"><span data-stu-id="e9988-209">It has a value of `Nothing` until you initialize at least some of its elements.</span></span> <span data-ttu-id="e9988-210">`Dim`ステートメントは、すべてのディメンションまたはディメンションがありませんのいずれかの境界を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9988-210">The `Dim` statement must specify bounds either for all dimensions or for no dimensions.</span></span>

```vb
' Declare an array with blank array bounds.
Dim messages() As String
' Initialize the array.
ReDim messages(4)
```

<span data-ttu-id="e9988-211">配列に 1 つ以上のディメンションがある場合は、ディメンションの数を示すかっこ間にコンマを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9988-211">If the array has more than one dimension, you must include commas between the parentheses to indicate the number of dimensions.</span></span>

```vb
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte
```

<span data-ttu-id="e9988-212">宣言することができます、*長さ 0 の配列*を-1 と配列の次元のいずれかを宣言することで。</span><span class="sxs-lookup"><span data-stu-id="e9988-212">You can declare a *zero-length array* by declaring one of the array's dimensions to be -1.</span></span> <span data-ttu-id="e9988-213">長さ 0 の配列を保持する変数は、値を持たない`Nothing`します。</span><span class="sxs-lookup"><span data-stu-id="e9988-213">A variable that holds a zero-length array does not have the value `Nothing`.</span></span> <span data-ttu-id="e9988-214">長さ 0 の配列には、共通言語ランタイムの一部の関数が必要です。</span><span class="sxs-lookup"><span data-stu-id="e9988-214">Zero-length arrays are required by certain common language runtime functions.</span></span> <span data-ttu-id="e9988-215">このような配列にアクセスしようとすると、ランタイム例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="e9988-215">If you try to access such an array, a runtime exception occurs.</span></span> <span data-ttu-id="e9988-216">詳細については、次を参照してください。[配列](../../../visual-basic/programming-guide/language-features/arrays/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9988-216">For more information, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>

<span data-ttu-id="e9988-217">配列の値を初期化するには、配列リテラルを使用します。</span><span class="sxs-lookup"><span data-stu-id="e9988-217">You can initialize the values of an array by using an array literal.</span></span> <span data-ttu-id="e9988-218">これを行うには、初期化値を中かっこで囲みます (`{}`)。</span><span class="sxs-lookup"><span data-stu-id="e9988-218">To do this, surround the initialization values with braces (`{}`).</span></span>

```vb
Dim longArray() As Long = {0, 1, 2, 3}
```

<span data-ttu-id="e9988-219">多次元配列は、各次元の初期化は、外側のディメンションの中かっこで囲まれます。</span><span class="sxs-lookup"><span data-stu-id="e9988-219">For multidimensional arrays, the initialization for each separate dimension is enclosed in braces in the outer dimension.</span></span> <span data-ttu-id="e9988-220">要素は、行優先順で指定されます。</span><span class="sxs-lookup"><span data-stu-id="e9988-220">The elements are specified in row-major order.</span></span>

```vb
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}
```

<span data-ttu-id="e9988-221">配列リテラルの詳細については、次を参照してください。[配列](../../../visual-basic/programming-guide/language-features/arrays/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9988-221">For more information about array literals, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>

## <a name="default"></a> <span data-ttu-id="e9988-222">既定のデータ型し、値</span><span class="sxs-lookup"><span data-stu-id="e9988-222">Default Data Types and Values</span></span>

<span data-ttu-id="e9988-223">次の表では、`Dim` ステートメントのデータ型と初期化子を指定するさまざまな組み合わせの結果を示します。</span><span class="sxs-lookup"><span data-stu-id="e9988-223">The following table describes the results of various combinations of specifying the data type and initializer in a `Dim` statement.</span></span>

|<span data-ttu-id="e9988-224">データ型が指定されているか</span><span class="sxs-lookup"><span data-stu-id="e9988-224">Data type specified?</span></span>|<span data-ttu-id="e9988-225">初期化子が指定されているか</span><span class="sxs-lookup"><span data-stu-id="e9988-225">Initializer specified?</span></span>|<span data-ttu-id="e9988-226">例</span><span class="sxs-lookup"><span data-stu-id="e9988-226">Example</span></span>|<span data-ttu-id="e9988-227">結果</span><span class="sxs-lookup"><span data-stu-id="e9988-227">Result</span></span>|
|---|---|---|---|
|<span data-ttu-id="e9988-228">いいえ</span><span class="sxs-lookup"><span data-stu-id="e9988-228">No</span></span>|<span data-ttu-id="e9988-229">いいえ</span><span class="sxs-lookup"><span data-stu-id="e9988-229">No</span></span>|`Dim qty`|<span data-ttu-id="e9988-230">場合[Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)に設定されている変数 off (既定)、`Nothing`します。</span><span class="sxs-lookup"><span data-stu-id="e9988-230">If [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="e9988-231">`Option Strict` がオンの場合、コンパイル時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="e9988-231">If `Option Strict` is on, a compile-time error occurs.</span></span>|
|<span data-ttu-id="e9988-232">Ｘ</span><span class="sxs-lookup"><span data-stu-id="e9988-232">No</span></span>|<span data-ttu-id="e9988-233">[はい]</span><span class="sxs-lookup"><span data-stu-id="e9988-233">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="e9988-234">場合[Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) (既定値) では、変数は、データが初期化子の型します。</span><span class="sxs-lookup"><span data-stu-id="e9988-234">If [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="e9988-235">参照してください[ローカル型推論](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9988-235">See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="e9988-236">`Option Infer` がオフで、`Option Strict` がオフの場合、変数は `Object` のデータ型になります。</span><span class="sxs-lookup"><span data-stu-id="e9988-236">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="e9988-237">`Option Infer` がオフで、`Option Strict` がオンの場合、コンパイル時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="e9988-237">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|
|<span data-ttu-id="e9988-238">[はい]</span><span class="sxs-lookup"><span data-stu-id="e9988-238">Yes</span></span>|<span data-ttu-id="e9988-239">いいえ</span><span class="sxs-lookup"><span data-stu-id="e9988-239">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="e9988-240">変数は、データ型の既定値に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="e9988-240">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="e9988-241">このセクションの後半の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9988-241">See the table later in this section.</span></span>|
|<span data-ttu-id="e9988-242">[はい]</span><span class="sxs-lookup"><span data-stu-id="e9988-242">Yes</span></span>|<span data-ttu-id="e9988-243">[はい]</span><span class="sxs-lookup"><span data-stu-id="e9988-243">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="e9988-244">初期化子のデータ型を指定したデータ型に変換できない場合は、コンパイル時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="e9988-244">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|

<span data-ttu-id="e9988-245">データ型を指定して、初期化子を指定しない場合、Visual Basic には、データ型の既定値に変数を初期化します。</span><span class="sxs-lookup"><span data-stu-id="e9988-245">If you specify a data type but do not specify an initializer, Visual Basic initializes the variable to the default value for its data type.</span></span> <span data-ttu-id="e9988-246">次の表は、既定の初期値を示します。</span><span class="sxs-lookup"><span data-stu-id="e9988-246">The following table shows the default initialization values.</span></span>

|<span data-ttu-id="e9988-247">データの種類</span><span class="sxs-lookup"><span data-stu-id="e9988-247">Data type</span></span>|<span data-ttu-id="e9988-248">既定値</span><span class="sxs-lookup"><span data-stu-id="e9988-248">Default value</span></span>|
|---|---|
|<span data-ttu-id="e9988-249">すべての数値型 (など`Byte`と`SByte`)</span><span class="sxs-lookup"><span data-stu-id="e9988-249">All numeric types (including `Byte` and `SByte`)</span></span>|<span data-ttu-id="e9988-250">0</span><span class="sxs-lookup"><span data-stu-id="e9988-250">0</span></span>|
|`Char`|<span data-ttu-id="e9988-251">バイナリ 0</span><span class="sxs-lookup"><span data-stu-id="e9988-251">Binary 0</span></span>|
|<span data-ttu-id="e9988-252">すべての参照型 (など`Object`、`String`とすべての配列)</span><span class="sxs-lookup"><span data-stu-id="e9988-252">All reference types (including `Object`, `String`, and all arrays)</span></span>|`Nothing`|
|`Boolean`|`False`|
|`Date`|<span data-ttu-id="e9988-253">1 年 1 月 1 日の 12時 00分 AM (01/01/0001 12時 00分: 00 AM)</span><span class="sxs-lookup"><span data-stu-id="e9988-253">12:00 AM of January 1 of the year 1 (01/01/0001 12:00:00 AM)</span></span>|

<span data-ttu-id="e9988-254">構造体の各要素は、個別の変数として初期化されます。</span><span class="sxs-lookup"><span data-stu-id="e9988-254">Each element of a structure is initialized as if it were a separate variable.</span></span> <span data-ttu-id="e9988-255">配列の長さを宣言する場合は、その要素を初期化できません、各要素は、別個の変数の場合と同様に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="e9988-255">If you declare the length of an array but do not initialize its elements, each element is initialized as if it were a separate variable.</span></span>

## <a name="static-local-variable-lifetime"></a><span data-ttu-id="e9988-256">静的ローカル変数有効期間</span><span class="sxs-lookup"><span data-stu-id="e9988-256">Static Local Variable Lifetime</span></span>

<span data-ttu-id="e9988-257">A`Static`ローカル変数が宣言されているプロシージャの場合よりも有効期間が長くなります。</span><span class="sxs-lookup"><span data-stu-id="e9988-257">A `Static` local variable has a longer lifetime than that of the procedure in which it is declared.</span></span> <span data-ttu-id="e9988-258">変数の有効期間の境界は、プロシージャが宣言されていると、かどうかによって異なります。`Shared`します。</span><span class="sxs-lookup"><span data-stu-id="e9988-258">The boundaries of the variable's lifetime depend on where the procedure is declared and whether it is `Shared`.</span></span>

|<span data-ttu-id="e9988-259">プロシージャの宣言</span><span class="sxs-lookup"><span data-stu-id="e9988-259">Procedure declaration</span></span>|<span data-ttu-id="e9988-260">初期化された変数</span><span class="sxs-lookup"><span data-stu-id="e9988-260">Variable initialized</span></span>|<span data-ttu-id="e9988-261">既存の変数を停止します</span><span class="sxs-lookup"><span data-stu-id="e9988-261">Variable stops existing</span></span>|
|---|---|---|
|<span data-ttu-id="e9988-262">モジュールで</span><span class="sxs-lookup"><span data-stu-id="e9988-262">In a module</span></span>|<span data-ttu-id="e9988-263">最初に、プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="e9988-263">The first time the procedure is called</span></span>|<span data-ttu-id="e9988-264">プログラムが実行を停止します</span><span class="sxs-lookup"><span data-stu-id="e9988-264">When your program stops execution</span></span>|
|<span data-ttu-id="e9988-265">手順は、クラスまたは構造体では、します。 `Shared`</span><span class="sxs-lookup"><span data-stu-id="e9988-265">In a class or structure, procedure is `Shared`</span></span>|<span data-ttu-id="e9988-266">最初に特定のインスタンスまたはクラスまたは構造体自体のプロシージャが呼び出されます</span><span class="sxs-lookup"><span data-stu-id="e9988-266">The first time the procedure is called either on a specific instance or on the class or structure itself</span></span>|<span data-ttu-id="e9988-267">プログラムが実行を停止します</span><span class="sxs-lookup"><span data-stu-id="e9988-267">When your program stops execution</span></span>|
|<span data-ttu-id="e9988-268">クラスまたは構造体では、プロシージャがないです。 `Shared`</span><span class="sxs-lookup"><span data-stu-id="e9988-268">In a class or structure, procedure isn't `Shared`</span></span>|<span data-ttu-id="e9988-269">最初に、プロシージャは特定のインスタンスで呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e9988-269">The first time the procedure is called on a specific instance</span></span>|<span data-ttu-id="e9988-270">ガベージ コレクション (GC) のインスタンスを解放する場合</span><span class="sxs-lookup"><span data-stu-id="e9988-270">When the instance is released for garbage collection (GC)</span></span>|

## <a name="attributes-and-modifiers"></a><span data-ttu-id="e9988-271">属性と修飾子</span><span class="sxs-lookup"><span data-stu-id="e9988-271">Attributes and Modifiers</span></span>

<span data-ttu-id="e9988-272">ローカル変数ではなく、メンバー変数にのみ、属性を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="e9988-272">You can apply attributes only to member variables, not to local variables.</span></span> <span data-ttu-id="e9988-273">属性は、ローカル変数などの一時的なストレージの意味はないアセンブリのメタデータに情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e9988-273">An attribute contributes information to the assembly's metadata, which is not meaningful for temporary storage such as local variables.</span></span>

<span data-ttu-id="e9988-274">モジュール レベルで使用することはできません、`Static`メンバー変数を宣言する修飾子。</span><span class="sxs-lookup"><span data-stu-id="e9988-274">At module level, you cannot use the `Static` modifier to declare member variables.</span></span> <span data-ttu-id="e9988-275">プロシージャ レベルで使用することはできません`Shared`、 `Shadows`、 `ReadOnly`、 `WithEvents`、またはのいずれかのアクセス修飾子をローカル変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="e9988-275">At procedure level, you cannot use `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, or any access modifiers to declare local variables.</span></span>

<span data-ttu-id="e9988-276">指定することによって、変数にアクセスできるコードを指定することができます、`accessmodifier`します。</span><span class="sxs-lookup"><span data-stu-id="e9988-276">You can specify what code can access a variable by supplying an `accessmodifier`.</span></span> <span data-ttu-id="e9988-277">プライベート アクセスは、クラスとモジュールのメンバー (プロシージャ) の外部変数既定と構造体メンバー変数の既定のパブリック アクセスにします。</span><span class="sxs-lookup"><span data-stu-id="e9988-277">Class and module member variables (outside any procedure) default to private access, and structure member variables default to public access.</span></span> <span data-ttu-id="e9988-278">アクセス修飾子を使用してこれらのアクセス レベルを調整できます。</span><span class="sxs-lookup"><span data-stu-id="e9988-278">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="e9988-279">(プロシージャ) 内のローカル変数にアクセス修飾子を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e9988-279">You cannot use access modifiers on local variables (inside a procedure).</span></span>

<span data-ttu-id="e9988-280">指定できる`WithEvents`メンバー変数でのみ、プロシージャ内のローカル変数ではなく。</span><span class="sxs-lookup"><span data-stu-id="e9988-280">You can specify `WithEvents` only on member variables, not on local variables inside a procedure.</span></span> <span data-ttu-id="e9988-281">指定した場合`WithEvents`、変数のデータ型がない、特定のクラス型をある必要があります`Object`します。</span><span class="sxs-lookup"><span data-stu-id="e9988-281">If you specify `WithEvents`, the data type of the variable must be a specific class type, not `Object`.</span></span> <span data-ttu-id="e9988-282">配列を宣言することはできません`WithEvents`します。</span><span class="sxs-lookup"><span data-stu-id="e9988-282">You cannot declare an array with `WithEvents`.</span></span> <span data-ttu-id="e9988-283">イベントの詳細については、次を参照してください。[イベント](../../../visual-basic/programming-guide/language-features/events/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9988-283">For more information about events, see [Events](../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e9988-284">コード、クラスの外部で構造体、またはモジュール修飾する必要があります、クラス、構造体、モジュールの名前を持つメンバー変数の名前。</span><span class="sxs-lookup"><span data-stu-id="e9988-284">Code outside a class, structure, or module must qualify a member variable's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="e9988-285">コードの外部プロシージャまたはブロックは、そのプロシージャまたはブロック内のローカル変数を参照できません。</span><span class="sxs-lookup"><span data-stu-id="e9988-285">Code outside a procedure or block cannot refer to any local variables within that procedure or block.</span></span>

## <a name="releasing-managed-resources"></a><span data-ttu-id="e9988-286">マネージ リソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="e9988-286">Releasing Managed Resources</span></span>

<span data-ttu-id="e9988-287">ユーザー側で余分なコーディングなしに、.NET Framework のガベージ コレクターがマネージ リソースを破棄します。</span><span class="sxs-lookup"><span data-stu-id="e9988-287">The .NET Framework garbage collector disposes of managed resources without any extra coding on your part.</span></span> <span data-ttu-id="e9988-288">ただし、ガベージ コレクターを待つのではなくマネージ リソースの破棄を強制できます。</span><span class="sxs-lookup"><span data-stu-id="e9988-288">However, you can force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>

<span data-ttu-id="e9988-289">クラスは、特に役に立つと不足しているリソース (データベース接続やファイル ハンドル) などの上に保持している場合、次のガベージ コレクションで使用できなくなったクラスのインスタンスをクリーンアップするまでお待ちたくないです。</span><span class="sxs-lookup"><span data-stu-id="e9988-289">If a class holds onto a particularly valuable and scarce resource (such as a database connection or file handle), you might not want to wait until the next garbage collection to clean up a class instance that's no longer in use.</span></span> <span data-ttu-id="e9988-290">クラスを実装、<xref:System.IDisposable>ガベージ コレクションの前にリソースを解放する手段を提供するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="e9988-290">A class may implement the <xref:System.IDisposable> interface to provide a way to release resources before a garbage collection.</span></span> <span data-ttu-id="e9988-291">そのインターフェイスを実装するクラスは、公開、`Dispose`メソッドをすぐに解放するためのリソースの強制的に呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="e9988-291">A class that implements that interface exposes a `Dispose` method that can be called to force valuable resources to be released immediately.</span></span>

<span data-ttu-id="e9988-292">`Using`ステートメントは、リソースの取得、一連のステートメントを実行して、リソースを破棄し、プロセスを自動化します。</span><span class="sxs-lookup"><span data-stu-id="e9988-292">The `Using` statement automates the process of acquiring a resource, executing a set of statements, and then disposing of the resource.</span></span> <span data-ttu-id="e9988-293">ただし、リソースを実装する必要があります、<xref:System.IDisposable>インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="e9988-293">However, the resource must implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="e9988-294">詳細については、[Using ステートメント](../../../visual-basic/language-reference/statements/using-statement.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9988-294">For more information, see [Using Statement](../../../visual-basic/language-reference/statements/using-statement.md).</span></span>

## <a name="example"></a><span data-ttu-id="e9988-295">例</span><span class="sxs-lookup"><span data-stu-id="e9988-295">Example</span></span>

<span data-ttu-id="e9988-296">次の例では、変数を宣言を使用して、`Dim`さまざまなオプションを使用してステートメントです。</span><span class="sxs-lookup"><span data-stu-id="e9988-296">The following example declares variables by using the `Dim` statement with various options.</span></span>

[!code-vb[VbVbalrStatements#141](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#141)]

## <a name="example"></a><span data-ttu-id="e9988-297">例</span><span class="sxs-lookup"><span data-stu-id="e9988-297">Example</span></span>

<span data-ttu-id="e9988-298">次の例は、1 ~ 30 の素数を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="e9988-298">The following example lists the prime numbers between 1 and 30.</span></span> <span data-ttu-id="e9988-299">コードのコメントは、ローカル変数のスコープを説明します。</span><span class="sxs-lookup"><span data-stu-id="e9988-299">The scope of local variables is described in code comments.</span></span>

[!code-vb[VbVbalrStatements#142](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#142)]

## <a name="example"></a><span data-ttu-id="e9988-300">例</span><span class="sxs-lookup"><span data-stu-id="e9988-300">Example</span></span>

<span data-ttu-id="e9988-301">次の例では、`speedValue`クラス レベルの変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="e9988-301">In the following example, the `speedValue` variable is declared at the class level.</span></span> <span data-ttu-id="e9988-302">`Private`キーワードの使用を変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="e9988-302">The `Private` keyword is used to declare the variable.</span></span> <span data-ttu-id="e9988-303">変数の任意のプロシージャからアクセスできる、`Car`クラス。</span><span class="sxs-lookup"><span data-stu-id="e9988-303">The variable can be accessed by any procedure in the `Car` class.</span></span>

[!code-vb[VbVbalrStatements#144](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#144)]

[!code-vb[VbVbalrStatements#145](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#145)]

## <a name="see-also"></a><span data-ttu-id="e9988-304">関連項目</span><span class="sxs-lookup"><span data-stu-id="e9988-304">See also</span></span>

- [<span data-ttu-id="e9988-305">Const ステートメント</span><span class="sxs-lookup"><span data-stu-id="e9988-305">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="e9988-306">ReDim ステートメント</span><span class="sxs-lookup"><span data-stu-id="e9988-306">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="e9988-307">Option Explicit ステートメント</span><span class="sxs-lookup"><span data-stu-id="e9988-307">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="e9988-308">Option Infer ステートメント</span><span class="sxs-lookup"><span data-stu-id="e9988-308">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="e9988-309">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="e9988-309">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- <span data-ttu-id="e9988-310">[[コンパイル] ページ、プロジェクト デザイナー (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="e9988-310">[Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)</span></span>
- [<span data-ttu-id="e9988-311">変数宣言</span><span class="sxs-lookup"><span data-stu-id="e9988-311">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="e9988-312">配列</span><span class="sxs-lookup"><span data-stu-id="e9988-312">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="e9988-313">オブジェクト初期化子:名前付きの匿名型</span><span class="sxs-lookup"><span data-stu-id="e9988-313">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="e9988-314">匿名型</span><span class="sxs-lookup"><span data-stu-id="e9988-314">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="e9988-315">オブジェクト初期化子:名前付きの匿名型</span><span class="sxs-lookup"><span data-stu-id="e9988-315">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="e9988-316">方法: オブジェクト初期化子を使用してオブジェクトを宣言します。</span><span class="sxs-lookup"><span data-stu-id="e9988-316">How to: Declare an Object by Using an Object Initializer</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
- [<span data-ttu-id="e9988-317">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="e9988-317">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
