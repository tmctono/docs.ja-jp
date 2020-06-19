---
title: Function ステートメント
ms.date: 05/12/2018
f1_keywords:
- vb.Function
helpviewer_keywords:
- procedures [Visual Basic], creating
- Function procedures [Visual Basic], Function statement syntax
- functions [Visual Basic], function procedures
- ParamArray keyword [Visual Basic], Function statements
- Private keyword [Visual Basic], Function statements
- declarations [Visual Basic], procedures
- procedures [Visual Basic], declaration
- Public keyword [Visual Basic], in Function statement
- ByVal keyword [Visual Basic], Function statements
- procedures [Visual Basic], recursive
- Implements keyword [Visual Basic], Function statements
- procedures [Visual Basic], returning values
- Exit statement [Visual Basic], in Function procedures
- recursive procedures
- As keyword [Visual Basic], in Function statement
- Optional keyword [Visual Basic], Function statements
- Function statement [Visual Basic]
- Visual Basic code, Function procedures
- procedures [Visual Basic], function
- ByRef keyword [Visual Basic], Function statements
- Friend keyword [Visual Basic], Function statements
- End keyword [Visual Basic], Function statements
- Handles keyword [Visual Basic], Function statements
ms.assetid: a4497077-0f46-4ede-a27f-9e8670df52b9
ms.openlocfilehash: 49cf4fead2c5594b7ac6815f82fea0dc995ea436
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404629"
---
# <a name="function-statement-visual-basic"></a><span data-ttu-id="10256-102">Function ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="10256-102">Function Statement (Visual Basic)</span></span>

<span data-ttu-id="10256-103">`Function` プロシージャを定義する名前、パラメーター、およびコードを宣言します。</span><span class="sxs-lookup"><span data-stu-id="10256-103">Declares the name, parameters, and code that define a `Function` procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="10256-104">構文</span><span class="sxs-lookup"><span data-stu-id="10256-104">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Function ]
    [ statements ]
End Function
```

## <a name="parts"></a><span data-ttu-id="10256-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="10256-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="10256-106">任意。</span><span class="sxs-lookup"><span data-stu-id="10256-106">Optional.</span></span> <span data-ttu-id="10256-107">「[属性リスト](attribute-list.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10256-107">See [Attribute List](attribute-list.md).</span></span>

- `accessmodifier`

  <span data-ttu-id="10256-108">任意。</span><span class="sxs-lookup"><span data-stu-id="10256-108">Optional.</span></span> <span data-ttu-id="10256-109">次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="10256-109">Can be one of the following:</span></span>

  - [<span data-ttu-id="10256-110">Public</span><span class="sxs-lookup"><span data-stu-id="10256-110">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="10256-111">Protected</span><span class="sxs-lookup"><span data-stu-id="10256-111">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="10256-112">Friend</span><span class="sxs-lookup"><span data-stu-id="10256-112">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="10256-113">Private</span><span class="sxs-lookup"><span data-stu-id="10256-113">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="10256-114">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="10256-114">Protected Friend</span></span>](../modifiers/protected-friend.md)

  - [<span data-ttu-id="10256-115">Private Protected</span><span class="sxs-lookup"><span data-stu-id="10256-115">Private Protected</span></span>](../modifiers/private-protected.md)

  <span data-ttu-id="10256-116">「 [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10256-116">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `proceduremodifiers`

  <span data-ttu-id="10256-117">任意。</span><span class="sxs-lookup"><span data-stu-id="10256-117">Optional.</span></span> <span data-ttu-id="10256-118">次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="10256-118">Can be one of the following:</span></span>

  - [<span data-ttu-id="10256-119">Overloads</span><span class="sxs-lookup"><span data-stu-id="10256-119">Overloads</span></span>](../modifiers/overloads.md)

  - [<span data-ttu-id="10256-120">Overrides</span><span class="sxs-lookup"><span data-stu-id="10256-120">Overrides</span></span>](../modifiers/overrides.md)

  - [<span data-ttu-id="10256-121">Overridable</span><span class="sxs-lookup"><span data-stu-id="10256-121">Overridable</span></span>](../modifiers/overridable.md)

  - [<span data-ttu-id="10256-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="10256-122">NotOverridable</span></span>](../modifiers/notoverridable.md)

  - [<span data-ttu-id="10256-123">MustOverride</span><span class="sxs-lookup"><span data-stu-id="10256-123">MustOverride</span></span>](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="10256-124">任意。</span><span class="sxs-lookup"><span data-stu-id="10256-124">Optional.</span></span> <span data-ttu-id="10256-125">「[Shared](../modifiers/shared.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10256-125">See [Shared](../modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="10256-126">任意。</span><span class="sxs-lookup"><span data-stu-id="10256-126">Optional.</span></span> <span data-ttu-id="10256-127">「[Shadows](../modifiers/shadows.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10256-127">See [Shadows](../modifiers/shadows.md).</span></span>

- `Async`

  <span data-ttu-id="10256-128">任意。</span><span class="sxs-lookup"><span data-stu-id="10256-128">Optional.</span></span> <span data-ttu-id="10256-129">「[Async](../modifiers/async.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10256-129">See [Async](../modifiers/async.md).</span></span>

- `Iterator`

  <span data-ttu-id="10256-130">任意。</span><span class="sxs-lookup"><span data-stu-id="10256-130">Optional.</span></span> <span data-ttu-id="10256-131">「[Iterator](../modifiers/iterator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10256-131">See [Iterator](../modifiers/iterator.md).</span></span>

- `name`

  <span data-ttu-id="10256-132">必須です。</span><span class="sxs-lookup"><span data-stu-id="10256-132">Required.</span></span> <span data-ttu-id="10256-133">プロシージャの名前。</span><span class="sxs-lookup"><span data-stu-id="10256-133">Name of the procedure.</span></span> <span data-ttu-id="10256-134">「 [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10256-134">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

- `typeparamlist`

  <span data-ttu-id="10256-135">任意。</span><span class="sxs-lookup"><span data-stu-id="10256-135">Optional.</span></span> <span data-ttu-id="10256-136">ジェネリック プロシージャの型パラメーターの一覧。</span><span class="sxs-lookup"><span data-stu-id="10256-136">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="10256-137">「[型リスト](type-list.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10256-137">See [Type List](type-list.md).</span></span>

- `parameterlist`

  <span data-ttu-id="10256-138">任意。</span><span class="sxs-lookup"><span data-stu-id="10256-138">Optional.</span></span> <span data-ttu-id="10256-139">このプロシージャのパラメーターを表すローカル変数名の一覧。</span><span class="sxs-lookup"><span data-stu-id="10256-139">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="10256-140">「[パラメーターの一覧](parameter-list.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10256-140">See [Parameter List](parameter-list.md).</span></span>

- `returntype`

  <span data-ttu-id="10256-141">`Option Strict` が `On` の場合は必ず指定します。</span><span class="sxs-lookup"><span data-stu-id="10256-141">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="10256-142">このプロシージャによって返される値のデータ型。</span><span class="sxs-lookup"><span data-stu-id="10256-142">Data type of the value returned by this procedure.</span></span>

- `Implements`

  <span data-ttu-id="10256-143">任意。</span><span class="sxs-lookup"><span data-stu-id="10256-143">Optional.</span></span> <span data-ttu-id="10256-144">それぞれこのプロシージャの含まれているクラスまたは構造体によって実装されたインターフェイスに定義されている、1 つ以上の `Function` プロシージャを、このプロシージャが実装することを示します。</span><span class="sxs-lookup"><span data-stu-id="10256-144">Indicates that this procedure implements one or more `Function` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="10256-145">「[Implements ステートメント](implements-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10256-145">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="10256-146">`Implements` を指定する場合は、必ず指定します。</span><span class="sxs-lookup"><span data-stu-id="10256-146">Required if `Implements` is supplied.</span></span> <span data-ttu-id="10256-147">実装される `Function` プロシージャのリストです。</span><span class="sxs-lookup"><span data-stu-id="10256-147">List of `Function` procedures being implemented.</span></span>

  `implementedprocedure [ , implementedprocedure ... ]`

  <span data-ttu-id="10256-148">`implementedprocedure` の構文と指定項目は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="10256-148">Each `implementedprocedure` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="10256-149">パーツ</span><span class="sxs-lookup"><span data-stu-id="10256-149">Part</span></span>|<span data-ttu-id="10256-150">説明</span><span class="sxs-lookup"><span data-stu-id="10256-150">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="10256-151">必須です。</span><span class="sxs-lookup"><span data-stu-id="10256-151">Required.</span></span> <span data-ttu-id="10256-152">このプロシージャの含まれているクラスまたは構造体によって実装されたインターフェイスの名前。</span><span class="sxs-lookup"><span data-stu-id="10256-152">Name of an interface implemented by this procedure's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="10256-153">必須です。</span><span class="sxs-lookup"><span data-stu-id="10256-153">Required.</span></span> <span data-ttu-id="10256-154">`interface` の中でプロシージャを定義するために使用する名前。</span><span class="sxs-lookup"><span data-stu-id="10256-154">Name by which the procedure is defined in `interface`.</span></span>|

- `Handles`

  <span data-ttu-id="10256-155">任意。</span><span class="sxs-lookup"><span data-stu-id="10256-155">Optional.</span></span> <span data-ttu-id="10256-156">このプロシージャで 1 つ以上の特定のイベントを処理できることを示します。</span><span class="sxs-lookup"><span data-stu-id="10256-156">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="10256-157">「[Handles](handles-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10256-157">See [Handles](handles-clause.md).</span></span>

- `eventlist`

  <span data-ttu-id="10256-158">`Handles` を指定する場合は、必ず指定します。</span><span class="sxs-lookup"><span data-stu-id="10256-158">Required if `Handles` is supplied.</span></span> <span data-ttu-id="10256-159">このプロシージャで処理するイベントの一覧。</span><span class="sxs-lookup"><span data-stu-id="10256-159">List of events this procedure handles.</span></span>

  `eventspecifier [ , eventspecifier ... ]`

  <span data-ttu-id="10256-160">`eventspecifier` の構文と指定項目は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="10256-160">Each `eventspecifier` has the following syntax and parts:</span></span>

  `eventvariable.event`

  |<span data-ttu-id="10256-161">パーツ</span><span class="sxs-lookup"><span data-stu-id="10256-161">Part</span></span>|<span data-ttu-id="10256-162">説明</span><span class="sxs-lookup"><span data-stu-id="10256-162">Description</span></span>|
  |---|---|
  |`eventvariable`|<span data-ttu-id="10256-163">必須です。</span><span class="sxs-lookup"><span data-stu-id="10256-163">Required.</span></span> <span data-ttu-id="10256-164">イベントを発生させるクラスまたは構造体のデータ型で宣言されたオブジェクト変数。</span><span class="sxs-lookup"><span data-stu-id="10256-164">Object variable declared with the data type of the class or structure that raises the event.</span></span>|
  |`event`|<span data-ttu-id="10256-165">必須です。</span><span class="sxs-lookup"><span data-stu-id="10256-165">Required.</span></span> <span data-ttu-id="10256-166">このプロシージャで処理するイベントの名前。</span><span class="sxs-lookup"><span data-stu-id="10256-166">Name of the event this procedure handles.</span></span>|

- `statements`

  <span data-ttu-id="10256-167">任意。</span><span class="sxs-lookup"><span data-stu-id="10256-167">Optional.</span></span> <span data-ttu-id="10256-168">このプロシージャ内で実行されるステートメントのブロック。</span><span class="sxs-lookup"><span data-stu-id="10256-168">Block of statements to be executed within this procedure.</span></span>

- `End Function`

  <span data-ttu-id="10256-169">このプロシージャの定義を終了します。</span><span class="sxs-lookup"><span data-stu-id="10256-169">Terminates the definition of this procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="10256-170">Remarks</span><span class="sxs-lookup"><span data-stu-id="10256-170">Remarks</span></span>

<span data-ttu-id="10256-171">すべての実行可能コードは、プロシージャ内になければなりません。</span><span class="sxs-lookup"><span data-stu-id="10256-171">All executable code must be inside a procedure.</span></span> <span data-ttu-id="10256-172">さらに各プロシージャは、含んでいるクラス、構造体、またはモジュールと呼ばれるクラス、構造体、またはモジュール内で宣言します。</span><span class="sxs-lookup"><span data-stu-id="10256-172">Each procedure, in turn, is declared within a class, a structure, or a module that is referred to as the containing class, structure, or module.</span></span>

<span data-ttu-id="10256-173">呼び出し元のコードに値を返すには、`Function` プロシージャを使用します。それ以外の場合は、`Sub` プロシージャを使用します。</span><span class="sxs-lookup"><span data-stu-id="10256-173">To return a value to the calling code, use a `Function` procedure; otherwise, use a `Sub` procedure.</span></span>

## <a name="defining-a-function"></a><span data-ttu-id="10256-174">関数の定義</span><span class="sxs-lookup"><span data-stu-id="10256-174">Defining a Function</span></span>

<span data-ttu-id="10256-175">`Function` プロシージャは、モジュール レベルでのみ定義できます。</span><span class="sxs-lookup"><span data-stu-id="10256-175">You can define a `Function` procedure only at the module level.</span></span> <span data-ttu-id="10256-176">そのため、関数の宣言コンテキストは、クラス、構造体、モジュール、インターフェイスにする必要があり、ソース ファイル、名前空間、プロシージャ、ブロックにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="10256-176">Therefore, the declaration context for a function must be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="10256-177">詳細については、「[宣言コンテキストと既定のアクセス レベル](declaration-contexts-and-default-access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10256-177">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="10256-178">`Function` プロシージャは、既定でパブリック アクセスに設定されます。</span><span class="sxs-lookup"><span data-stu-id="10256-178">`Function` procedures default to public access.</span></span> <span data-ttu-id="10256-179">アクセス修飾子を使用してこれらのアクセス レベルを調整できます。</span><span class="sxs-lookup"><span data-stu-id="10256-179">You can adjust their access levels with the access modifiers.</span></span>

<span data-ttu-id="10256-180">`Function` プロシージャでは、プロシージャが返す値のデータ型を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="10256-180">A `Function` procedure can declare the data type of the value that the procedure returns.</span></span> <span data-ttu-id="10256-181">任意のデータ型や、列挙、構造体、クラス、またはインターフェイスの名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="10256-181">You can specify any data type or the name of an enumeration, a structure, a class, or an interface.</span></span> <span data-ttu-id="10256-182">`returntype` パラメーターを指定しない場合、プロシージャから `Object` が返されます。</span><span class="sxs-lookup"><span data-stu-id="10256-182">If you don't specify the `returntype` parameter, the procedure returns `Object`.</span></span>

<span data-ttu-id="10256-183">このプロシージャで `Implements` キーワードを使用している場合、含まれているクラスまたは構造体にも、その `Class` または `Structure` ステートメントの直後に `Implements` ステートメントが必要です。</span><span class="sxs-lookup"><span data-stu-id="10256-183">If this procedure uses the `Implements` keyword, the containing class or structure must also have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="10256-184">`Implements` ステートメントには、`implementslist` で指定された各インターフェイスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="10256-184">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="10256-185">ただし、インターフェイスで `Function` を定義するときに使用する名前 (`definedname`) は、このプロシージャの名前 (`name`) に一致している必要はありません。</span><span class="sxs-lookup"><span data-stu-id="10256-185">However, the name by which an interface defines the `Function` (in `definedname`) doesn't need to match the name of this procedure (in `name`).</span></span>

> [!NOTE]
> <span data-ttu-id="10256-186">ラムダ式を使用して、関数式をインラインで定義できます。</span><span class="sxs-lookup"><span data-stu-id="10256-186">You can use lambda expressions to define function expressions inline.</span></span> <span data-ttu-id="10256-187">詳細については、「[関数式](../operators/function-expression.md)」と「[ラムダ式](../../programming-guide/language-features/procedures/lambda-expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10256-187">For more information, see [Function Expression](../operators/function-expression.md) and [Lambda Expressions](../../programming-guide/language-features/procedures/lambda-expressions.md).</span></span>

## <a name="returning-from-a-function"></a><span data-ttu-id="10256-188">関数からの復帰</span><span class="sxs-lookup"><span data-stu-id="10256-188">Returning from a Function</span></span>

<span data-ttu-id="10256-189">`Function` プロシージャが呼び出し元のコードに戻ると、実行は、プロシージャを呼び出したステートメントの後のステートメントから続行されます。</span><span class="sxs-lookup"><span data-stu-id="10256-189">When the `Function` procedure returns to the calling code, execution continues with the statement that follows the statement that called the procedure.</span></span>

<span data-ttu-id="10256-190">関数から値を返すには、関数名に値を代入するか、`Return` ステートメントに値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="10256-190">To return a value from a function, you can either assign the value to the function name or include it in a `Return` statement.</span></span>

<span data-ttu-id="10256-191">`Return` ステートメントでは、次の例に示すように、戻り値を代入して、同時に関数を終了します。</span><span class="sxs-lookup"><span data-stu-id="10256-191">The `Return` statement simultaneously assigns the return value and exits the function, as the following example shows.</span></span>

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

<span data-ttu-id="10256-192">次の例では、関数名 `myFunction` に戻り値を代入してから、`Exit Function` ステートメントを使用して戻ります。</span><span class="sxs-lookup"><span data-stu-id="10256-192">The following example assigns the return value to the function name `myFunction` and then uses the `Exit Function` statement to return.</span></span>

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

<span data-ttu-id="10256-193">`Exit Function` および `Return` ステートメントでは、`Function` プロシージャがすぐに終了します。</span><span class="sxs-lookup"><span data-stu-id="10256-193">The `Exit Function` and `Return` statements cause an immediate exit from a `Function` procedure.</span></span> <span data-ttu-id="10256-194">任意の数の `Exit Function` および `Return` ステートメントをプロシージャ内の任意の場所に記述でき、`Exit Function` ステートメントと `Return` ステートメントを混在させることができます。</span><span class="sxs-lookup"><span data-stu-id="10256-194">Any number of `Exit Function` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Function` and `Return` statements.</span></span>

<span data-ttu-id="10256-195">`name` に値を代入せずに `Exit Function` を使用すると、プロシージャから、`returntype` に指定したデータ型の既定値が返されます。</span><span class="sxs-lookup"><span data-stu-id="10256-195">If you use `Exit Function` without assigning a value to `name`, the procedure returns the default value for the data type that's specified in `returntype`.</span></span> <span data-ttu-id="10256-196">`returntype` を指定していない場合、プロシージャから `Nothing` が返されます。これは `Object` の既定値です。</span><span class="sxs-lookup"><span data-stu-id="10256-196">If `returntype` isn't specified, the procedure returns `Nothing`, which is the default value for `Object`.</span></span>

## <a name="calling-a-function"></a><span data-ttu-id="10256-197">関数の呼び出し</span><span class="sxs-lookup"><span data-stu-id="10256-197">Calling a Function</span></span>

<span data-ttu-id="10256-198">`Function` プロシージャを呼び出すには、式の中でプロシージャ名の後にかっこで囲んだ引数リストを使用します。</span><span class="sxs-lookup"><span data-stu-id="10256-198">You call a `Function` procedure by using the procedure name, followed by the argument list in parentheses, in an expression.</span></span> <span data-ttu-id="10256-199">引数を指定しない場合に限り、かっこを省略できます。</span><span class="sxs-lookup"><span data-stu-id="10256-199">You can omit the parentheses only if you aren't supplying any arguments.</span></span> <span data-ttu-id="10256-200">ただし、常にかっこを含めると、コードが読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="10256-200">However, your code is more readable if you always include the parentheses.</span></span>

<span data-ttu-id="10256-201">`Function` プロシージャは、`Sqrt`、`Cos`、`ChrW` などの任意のライブラリ関数を呼び出すのと同じ方法で呼び出します。</span><span class="sxs-lookup"><span data-stu-id="10256-201">You call a `Function` procedure the same way that you call any library function such as `Sqrt`, `Cos`, or `ChrW`.</span></span>

<span data-ttu-id="10256-202">`Call` キーワードを使用して関数を呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="10256-202">You can also call a function by using the `Call` keyword.</span></span> <span data-ttu-id="10256-203">その場合、戻り値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="10256-203">In that case, the return value is ignored.</span></span> <span data-ttu-id="10256-204">ほとんどの場合に `Call` キーワードを使用しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="10256-204">Use of the `Call` keyword isn't recommended in most cases.</span></span> <span data-ttu-id="10256-205">詳細については、「[Call ステートメント](call-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10256-205">For more information, see [Call Statement](call-statement.md).</span></span>

<span data-ttu-id="10256-206">Visual Basic では、内部効率を高めるために算術式が再配置されることがあります。</span><span class="sxs-lookup"><span data-stu-id="10256-206">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="10256-207">そのため、関数で同じ式内の変数の値を変更する場合は、算術式で `Function` プロシージャを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="10256-207">For that reason, you shouldn't use a `Function` procedure in an arithmetic expression when the function changes the value of variables in the same expression.</span></span>

## <a name="async-functions"></a><span data-ttu-id="10256-208">Async 関数</span><span class="sxs-lookup"><span data-stu-id="10256-208">Async Functions</span></span>

<span data-ttu-id="10256-209">*Async* 機能を使用することによって、明示的なコールバックを使用せずに、または複数の関数やラムダ式にわたって手動でコードを分割することなく、非同期メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="10256-209">The *Async* feature allows you to invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>

<span data-ttu-id="10256-210">関数を [Async](../modifiers/async.md) 修飾子でマークすると、その関数で [Await](../operators/await-operator.md) 演算子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="10256-210">If you mark a function with the [Async](../modifiers/async.md) modifier, you can use the [Await](../operators/await-operator.md) operator in the function.</span></span> <span data-ttu-id="10256-211">制御が `Async` 関数の `Await` 式に到達すると、制御が呼び出し元に戻り、待機中のタスクが完了するまで関数の進行が中断されます。</span><span class="sxs-lookup"><span data-stu-id="10256-211">When control reaches an `Await` expression in the `Async` function, control returns to the caller, and progress in the function is suspended until the awaited task completes.</span></span> <span data-ttu-id="10256-212">タスクが完了すると、関数で実行を再開できます。</span><span class="sxs-lookup"><span data-stu-id="10256-212">When the task is complete, execution can resume in the function.</span></span>

> [!NOTE]
> <span data-ttu-id="10256-213">`Async` プロシージャは、まだ完了していない待機中の最初のオブジェクトが検出されるか、または `Async` プロシージャの最後に達するか、どちらか先に発生したときに、呼び出し元に戻ります。</span><span class="sxs-lookup"><span data-stu-id="10256-213">An `Async` procedure returns to the caller when either it encounters the first awaited object that’s not yet complete, or it gets to the end of the `Async` procedure, whichever occurs first.</span></span>

<span data-ttu-id="10256-214">`Async` 関数の戻り値の型には、<xref:System.Threading.Tasks.Task%601> または <xref:System.Threading.Tasks.Task> を指定できます。</span><span class="sxs-lookup"><span data-stu-id="10256-214">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="10256-215">戻り値の型が <xref:System.Threading.Tasks.Task%601> の `Async` 関数の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="10256-215">An example of an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601> is provided below.</span></span>

<span data-ttu-id="10256-216">`Async` 関数で、[ByRef](../modifiers/byref.md) パラメーターを宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="10256-216">An `Async` function cannot declare any [ByRef](../modifiers/byref.md) parameters.</span></span>

<span data-ttu-id="10256-217">[Sub ステートメント](sub-statement.md) を、`Async` 修飾子でマークすることもできます。</span><span class="sxs-lookup"><span data-stu-id="10256-217">A [Sub Statement](sub-statement.md) can also be marked with the `Async` modifier.</span></span> <span data-ttu-id="10256-218">これは主に、値を返すことができないイベント ハンドラーに使用します。</span><span class="sxs-lookup"><span data-stu-id="10256-218">This is primarily used for event handlers, where a value cannot be returned.</span></span> <span data-ttu-id="10256-219">`Async` `Sub` プロシージャは待機できず、`Async` `Sub` プロシージャの呼び出し元は、`Sub` プロシージャによってスローされた例外をキャッチできません。</span><span class="sxs-lookup"><span data-stu-id="10256-219">An `Async` `Sub` procedure can't be awaited, and the caller of an `Async` `Sub` procedure can't catch exceptions that are thrown by the `Sub` procedure.</span></span>

<span data-ttu-id="10256-220">`Async` 関数の詳細については、「[Async および Await を使用した非同期プログラミング](../../programming-guide/concepts/async/index.md)」、「[非同期プログラムにおける制御フロー](../../programming-guide/concepts/async/control-flow-in-async-programs.md)」、「[非同期の戻り値の型](../../programming-guide/concepts/async/async-return-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10256-220">For more information about `Async` functions, see [Asynchronous Programming with Async and Await](../../programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../programming-guide/concepts/async/async-return-types.md).</span></span>

## <a name="iterator-functions"></a><span data-ttu-id="10256-221">iterator 関数</span><span class="sxs-lookup"><span data-stu-id="10256-221">Iterator Functions</span></span>

<span data-ttu-id="10256-222">*iterator* 関数は、リストや配列など、コレクションに対するカスタムの反復を実行します。</span><span class="sxs-lookup"><span data-stu-id="10256-222">An *iterator* function performs a custom iteration over a collection, such as a list or array.</span></span> <span data-ttu-id="10256-223">iterator 関数は、[Yield](yield-statement.md) ステートメントを使用して、各要素を 1 回に 1 つ返します。</span><span class="sxs-lookup"><span data-stu-id="10256-223">An iterator function uses the [Yield](yield-statement.md) statement to return each element one at a time.</span></span> <span data-ttu-id="10256-224">[Yield](yield-statement.md) ステートメントに達すると、コードの現在の場所が記憶されます。</span><span class="sxs-lookup"><span data-stu-id="10256-224">When a [Yield](yield-statement.md) statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="10256-225">次回、iterator 関数が呼び出されると、この位置から実行が再開されます。</span><span class="sxs-lookup"><span data-stu-id="10256-225">Execution is restarted from that location the next time the iterator function is called.</span></span>

<span data-ttu-id="10256-226">[For Each...Next](for-each-next-statement.md) ステートメントを使用して、クライアント コードから反復子を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="10256-226">You call an iterator from client code by using a [For Each…Next](for-each-next-statement.md) statement.</span></span>

<span data-ttu-id="10256-227">iterator 関数の戻り値の型には、<xref:System.Collections.IEnumerable>、<xref:System.Collections.Generic.IEnumerable%601>、<xref:System.Collections.IEnumerator>、または <xref:System.Collections.Generic.IEnumerator%601> を指定できます。</span><span class="sxs-lookup"><span data-stu-id="10256-227">The return type of an iterator function can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>

<span data-ttu-id="10256-228">詳細については、「 [反復子](../../programming-guide/concepts/iterators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10256-228">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>

## <a name="example"></a><span data-ttu-id="10256-229">例</span><span class="sxs-lookup"><span data-stu-id="10256-229">Example</span></span>

<span data-ttu-id="10256-230">次の例では、`Function` ステートメントを使用して、`Function` プロシージャの本体を形成する名前、パラメーター、およびコードを宣言しています。</span><span class="sxs-lookup"><span data-stu-id="10256-230">The following example uses the `Function` statement to declare the name, parameters, and code that form the body of a `Function` procedure.</span></span> <span data-ttu-id="10256-231">`ParamArray` 修飾子を使用すると、関数では可変数の引数を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="10256-231">The `ParamArray` modifier enables the function to accept a variable number of arguments.</span></span>

[!code-vb[VbVbalrStatements#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#25)]

## <a name="example"></a><span data-ttu-id="10256-232">例</span><span class="sxs-lookup"><span data-stu-id="10256-232">Example</span></span>

<span data-ttu-id="10256-233">次の例では、前の例で宣言した関数を呼び出しています。</span><span class="sxs-lookup"><span data-stu-id="10256-233">The following example invokes the function declared in the preceding example.</span></span>

[!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]

## <a name="example"></a><span data-ttu-id="10256-234">例</span><span class="sxs-lookup"><span data-stu-id="10256-234">Example</span></span>

<span data-ttu-id="10256-235">次の例で、`DelayAsync` は、戻り値の型が <xref:System.Threading.Tasks.Task%601> である `Async` `Function` です。</span><span class="sxs-lookup"><span data-stu-id="10256-235">In the following example, `DelayAsync` is an `Async` `Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="10256-236">`DelayAsync` には、整数を返す `Return` ステートメントがあります。</span><span class="sxs-lookup"><span data-stu-id="10256-236">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="10256-237">そのため、`DelayAsync` の関数宣言では、戻り値の型を `Task(Of Integer)` にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="10256-237">Therefore the function declaration of `DelayAsync` needs to have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="10256-238">戻り値の型が `Task(Of Integer)` であるため、`DoSomethingAsync` 内の `Await` 式を評価すると整数が生成されます。</span><span class="sxs-lookup"><span data-stu-id="10256-238">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer.</span></span> <span data-ttu-id="10256-239">これは、ステートメント `Dim result As Integer = Await delayTask` に示しています。</span><span class="sxs-lookup"><span data-stu-id="10256-239">This is demonstrated in this statement: `Dim result As Integer = Await delayTask`.</span></span>

<span data-ttu-id="10256-240">`startButton_Click` プロシージャは、`Async Sub` プロシージャの一例です。</span><span class="sxs-lookup"><span data-stu-id="10256-240">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="10256-241">`DoSomethingAsync` が `Async` 関数であるため、`DoSomethingAsync` を呼び出すタスクは、`Await DoSomethingAsync()` ステートメントに示すように、待機させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="10256-241">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement demonstrates: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="10256-242">`startButton_Click` `Sub` プロシージャは、`Await` 式を使用しているため、`Async` 修飾子を使用して定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10256-242">The `startButton_Click` `Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="10256-243">関連項目</span><span class="sxs-lookup"><span data-stu-id="10256-243">See also</span></span>

- [<span data-ttu-id="10256-244">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="10256-244">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="10256-245">Function プロシージャ</span><span class="sxs-lookup"><span data-stu-id="10256-245">Function Procedures</span></span>](../../programming-guide/language-features/procedures/function-procedures.md)
- [<span data-ttu-id="10256-246">パラメーター リスト</span><span class="sxs-lookup"><span data-stu-id="10256-246">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="10256-247">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="10256-247">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="10256-248">Call ステートメント</span><span class="sxs-lookup"><span data-stu-id="10256-248">Call Statement</span></span>](call-statement.md)
- [<span data-ttu-id="10256-249">Of</span><span class="sxs-lookup"><span data-stu-id="10256-249">Of</span></span>](of-clause.md)
- [<span data-ttu-id="10256-250">パラメーター配列</span><span class="sxs-lookup"><span data-stu-id="10256-250">Parameter Arrays</span></span>](../../programming-guide/language-features/procedures/parameter-arrays.md)
- [<span data-ttu-id="10256-251">方法: ジェネリック クラスを使用する</span><span class="sxs-lookup"><span data-stu-id="10256-251">How to: Use a Generic Class</span></span>](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="10256-252">プロシージャのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="10256-252">Troubleshooting Procedures</span></span>](../../programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [<span data-ttu-id="10256-253">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="10256-253">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="10256-254">Function 式</span><span class="sxs-lookup"><span data-stu-id="10256-254">Function Expression</span></span>](../operators/function-expression.md)
