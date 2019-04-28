---
title: Function ステートメント (Visual Basic)
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
ms.openlocfilehash: dffe67d1c31b0fe7c037839ba0588793a461f276
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638059"
---
# <a name="function-statement-visual-basic"></a><span data-ttu-id="e4171-102">Function ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e4171-102">Function Statement (Visual Basic)</span></span>

<span data-ttu-id="e4171-103">宣言名、パラメーター、および定義するコードを`Function`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="e4171-103">Declares the name, parameters, and code that define a `Function` procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="e4171-104">構文</span><span class="sxs-lookup"><span data-stu-id="e4171-104">Syntax</span></span>

```
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Function ]
    [ statements ]
End Function
```

## <a name="parts"></a><span data-ttu-id="e4171-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="e4171-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="e4171-106">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e4171-106">Optional.</span></span> <span data-ttu-id="e4171-107">参照してください[属性リスト](attribute-list.md)します。</span><span class="sxs-lookup"><span data-stu-id="e4171-107">See [Attribute List](attribute-list.md).</span></span>

- `accessmodifier`

  <span data-ttu-id="e4171-108">任意。</span><span class="sxs-lookup"><span data-stu-id="e4171-108">Optional.</span></span> <span data-ttu-id="e4171-109">次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4171-109">Can be one of the following:</span></span>

  - [<span data-ttu-id="e4171-110">Public</span><span class="sxs-lookup"><span data-stu-id="e4171-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)

  - [<span data-ttu-id="e4171-111">Protected</span><span class="sxs-lookup"><span data-stu-id="e4171-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)

  - [<span data-ttu-id="e4171-112">Friend</span><span class="sxs-lookup"><span data-stu-id="e4171-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)

  - [<span data-ttu-id="e4171-113">Private</span><span class="sxs-lookup"><span data-stu-id="e4171-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)

  - [<span data-ttu-id="e4171-114">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="e4171-114">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

  - [<span data-ttu-id="e4171-115">Private Protected</span><span class="sxs-lookup"><span data-stu-id="e4171-115">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

  <span data-ttu-id="e4171-116">「 [Visual Basic でのアクセス レベル](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4171-116">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `proceduremodifiers`

  <span data-ttu-id="e4171-117">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e4171-117">Optional.</span></span> <span data-ttu-id="e4171-118">次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4171-118">Can be one of the following:</span></span>

  - [<span data-ttu-id="e4171-119">Overloads</span><span class="sxs-lookup"><span data-stu-id="e4171-119">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)

  - [<span data-ttu-id="e4171-120">Overrides</span><span class="sxs-lookup"><span data-stu-id="e4171-120">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)

  - [<span data-ttu-id="e4171-121">Overridable</span><span class="sxs-lookup"><span data-stu-id="e4171-121">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)

  - [<span data-ttu-id="e4171-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="e4171-122">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)

  - [<span data-ttu-id="e4171-123">MustOverride</span><span class="sxs-lookup"><span data-stu-id="e4171-123">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="e4171-124">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e4171-124">Optional.</span></span> <span data-ttu-id="e4171-125">参照してください[共有](../../../visual-basic/language-reference/modifiers/shared.md)します。</span><span class="sxs-lookup"><span data-stu-id="e4171-125">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="e4171-126">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e4171-126">Optional.</span></span> <span data-ttu-id="e4171-127">参照してください[Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)します。</span><span class="sxs-lookup"><span data-stu-id="e4171-127">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>

- `Async`

  <span data-ttu-id="e4171-128">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e4171-128">Optional.</span></span> <span data-ttu-id="e4171-129">参照してください[Async](../../../visual-basic/language-reference/modifiers/async.md)します。</span><span class="sxs-lookup"><span data-stu-id="e4171-129">See [Async](../../../visual-basic/language-reference/modifiers/async.md).</span></span>

- `Iterator`

  <span data-ttu-id="e4171-130">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e4171-130">Optional.</span></span> <span data-ttu-id="e4171-131">参照してください[反復子](../../../visual-basic/language-reference/modifiers/iterator.md)します。</span><span class="sxs-lookup"><span data-stu-id="e4171-131">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>

- `name`

  <span data-ttu-id="e4171-132">必須。</span><span class="sxs-lookup"><span data-stu-id="e4171-132">Required.</span></span> <span data-ttu-id="e4171-133">プロシージャの名前。</span><span class="sxs-lookup"><span data-stu-id="e4171-133">Name of the procedure.</span></span> <span data-ttu-id="e4171-134">「 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4171-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

- `typeparamlist`

  <span data-ttu-id="e4171-135">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e4171-135">Optional.</span></span> <span data-ttu-id="e4171-136">ジェネリック プロシージャの型パラメーターの一覧。</span><span class="sxs-lookup"><span data-stu-id="e4171-136">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="e4171-137">参照してください[一覧を入力する](type-list.md)します。</span><span class="sxs-lookup"><span data-stu-id="e4171-137">See [Type List](type-list.md).</span></span>

- `parameterlist`

  <span data-ttu-id="e4171-138">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e4171-138">Optional.</span></span> <span data-ttu-id="e4171-139">このプロシージャのパラメーターを表すローカル変数名の一覧。</span><span class="sxs-lookup"><span data-stu-id="e4171-139">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="e4171-140">参照してください[パラメーター リスト](parameter-list.md)します。</span><span class="sxs-lookup"><span data-stu-id="e4171-140">See [Parameter List](parameter-list.md).</span></span>

- `returntype`

  <span data-ttu-id="e4171-141">場合に、必ず`Option Strict`は`On`します。</span><span class="sxs-lookup"><span data-stu-id="e4171-141">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="e4171-142">このプロシージャによって返される値のデータ型。</span><span class="sxs-lookup"><span data-stu-id="e4171-142">Data type of the value returned by this procedure.</span></span>

- `Implements`

  <span data-ttu-id="e4171-143">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e4171-143">Optional.</span></span> <span data-ttu-id="e4171-144">この手順が 1 つまたは複数を実装することを示します`Function`手順、この手順の包含クラスまたは構造体によって実装されるインターフェイスで定義されている 1 つずつです。</span><span class="sxs-lookup"><span data-stu-id="e4171-144">Indicates that this procedure implements one or more `Function` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="e4171-145">参照してください[ステートメントを実装](implements-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="e4171-145">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="e4171-146">`Implements` を指定する場合は、必ず指定します。</span><span class="sxs-lookup"><span data-stu-id="e4171-146">Required if `Implements` is supplied.</span></span> <span data-ttu-id="e4171-147">実装される `Function` プロシージャのリストです。</span><span class="sxs-lookup"><span data-stu-id="e4171-147">List of `Function` procedures being implemented.</span></span>

  `implementedprocedure [ , implementedprocedure ... ]`

  <span data-ttu-id="e4171-148">`implementedprocedure` の構文と指定項目は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e4171-148">Each `implementedprocedure` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="e4171-149">パーツ</span><span class="sxs-lookup"><span data-stu-id="e4171-149">Part</span></span>|<span data-ttu-id="e4171-150">説明</span><span class="sxs-lookup"><span data-stu-id="e4171-150">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="e4171-151">必須。</span><span class="sxs-lookup"><span data-stu-id="e4171-151">Required.</span></span> <span data-ttu-id="e4171-152">このプロシージャによって実装されるインターフェイスの名前を含むクラスまたは構造体。</span><span class="sxs-lookup"><span data-stu-id="e4171-152">Name of an interface implemented by this procedure's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="e4171-153">必須。</span><span class="sxs-lookup"><span data-stu-id="e4171-153">Required.</span></span> <span data-ttu-id="e4171-154">`interface` の中でプロシージャを定義するために使用する名前。</span><span class="sxs-lookup"><span data-stu-id="e4171-154">Name by which the procedure is defined in `interface`.</span></span>|

- `Handles`

  <span data-ttu-id="e4171-155">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e4171-155">Optional.</span></span> <span data-ttu-id="e4171-156">この手順が 1 つまたは複数の特定のイベントを処理できることを示します。</span><span class="sxs-lookup"><span data-stu-id="e4171-156">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="e4171-157">参照してください[処理](handles-clause.md)します。</span><span class="sxs-lookup"><span data-stu-id="e4171-157">See [Handles](handles-clause.md).</span></span>

- `eventlist`

  <span data-ttu-id="e4171-158">`Handles` を指定する場合は、必ず指定します。</span><span class="sxs-lookup"><span data-stu-id="e4171-158">Required if `Handles` is supplied.</span></span> <span data-ttu-id="e4171-159">このプロシージャを処理するイベントの一覧です。</span><span class="sxs-lookup"><span data-stu-id="e4171-159">List of events this procedure handles.</span></span>

  `eventspecifier [ , eventspecifier ... ]`

  <span data-ttu-id="e4171-160">`eventspecifier` の構文と指定項目は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e4171-160">Each `eventspecifier` has the following syntax and parts:</span></span>

  `eventvariable.event`

  |<span data-ttu-id="e4171-161">パーツ</span><span class="sxs-lookup"><span data-stu-id="e4171-161">Part</span></span>|<span data-ttu-id="e4171-162">説明</span><span class="sxs-lookup"><span data-stu-id="e4171-162">Description</span></span>|
  |---|---|
  |`eventvariable`|<span data-ttu-id="e4171-163">必須。</span><span class="sxs-lookup"><span data-stu-id="e4171-163">Required.</span></span> <span data-ttu-id="e4171-164">オブジェクト変数がクラスまたはイベントを発生させる構造体のデータ型で宣言されています。</span><span class="sxs-lookup"><span data-stu-id="e4171-164">Object variable declared with the data type of the class or structure that raises the event.</span></span>|
  |`event`|<span data-ttu-id="e4171-165">必須。</span><span class="sxs-lookup"><span data-stu-id="e4171-165">Required.</span></span> <span data-ttu-id="e4171-166">このプロシージャを処理するイベントの名前。</span><span class="sxs-lookup"><span data-stu-id="e4171-166">Name of the event this procedure handles.</span></span>|

- `statements`

  <span data-ttu-id="e4171-167">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e4171-167">Optional.</span></span> <span data-ttu-id="e4171-168">この手順内で実行されるステートメントのブロックです。</span><span class="sxs-lookup"><span data-stu-id="e4171-168">Block of statements to be executed within this procedure.</span></span>

- `End Function`

  <span data-ttu-id="e4171-169">このプロシージャの定義を終了します。</span><span class="sxs-lookup"><span data-stu-id="e4171-169">Terminates the definition of this procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="e4171-170">Remarks</span><span class="sxs-lookup"><span data-stu-id="e4171-170">Remarks</span></span>

<span data-ttu-id="e4171-171">プロシージャ内にあるすべての実行可能コードがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4171-171">All executable code must be inside a procedure.</span></span> <span data-ttu-id="e4171-172">さらに、各手順では、クラス、構造体またはクラス、構造体、またはモジュールとして参照されるモジュール内で宣言されます。</span><span class="sxs-lookup"><span data-stu-id="e4171-172">Each procedure, in turn, is declared within a class, a structure, or a module that is referred to as the containing class, structure, or module.</span></span>

<span data-ttu-id="e4171-173">呼び出し元のコードに値を返すには使用、`Function`プロシージャです。 それ以外の場合、使用、`Sub`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="e4171-173">To return a value to the calling code, use a `Function` procedure; otherwise, use a `Sub` procedure.</span></span>

## <a name="defining-a-function"></a><span data-ttu-id="e4171-174">関数を定義します。</span><span class="sxs-lookup"><span data-stu-id="e4171-174">Defining a Function</span></span>

<span data-ttu-id="e4171-175">定義することができます、`Function`モジュール レベルでのみプロシージャ。</span><span class="sxs-lookup"><span data-stu-id="e4171-175">You can define a `Function` procedure only at the module level.</span></span> <span data-ttu-id="e4171-176">そのため、関数の宣言のコンテキストでは、クラス、構造体、モジュールの場合、またはインターフェイスである必要があり、ソース ファイル、名前空間、プロシージャ、またはブロックすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e4171-176">Therefore, the declaration context for a function must be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="e4171-177">詳細については、「[宣言コンテキストと既定のアクセス レベル](declaration-contexts-and-default-access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4171-177">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="e4171-178">`Function` パブリック アクセスに既定のプロシージャ。</span><span class="sxs-lookup"><span data-stu-id="e4171-178">`Function` procedures default to public access.</span></span> <span data-ttu-id="e4171-179">アクセス修飾子を使用してこれらのアクセス レベルを調整できます。</span><span class="sxs-lookup"><span data-stu-id="e4171-179">You can adjust their access levels with the access modifiers.</span></span>

<span data-ttu-id="e4171-180">A`Function`プロシージャがプロシージャが返す値のデータ型を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="e4171-180">A `Function` procedure can declare the data type of the value that the procedure returns.</span></span> <span data-ttu-id="e4171-181">任意のデータ型または列挙型、構造体、クラスまたはインターフェイスの名前を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="e4171-181">You can specify any data type or the name of an enumeration, a structure, a class, or an interface.</span></span> <span data-ttu-id="e4171-182">指定しない場合、`returntype`パラメーター、プロシージャを返します`Object`します。</span><span class="sxs-lookup"><span data-stu-id="e4171-182">If you don't specify the `returntype` parameter, the procedure returns `Object`.</span></span>

<span data-ttu-id="e4171-183">この手順で使用する場合、`Implements`キーワードを含むクラスまたは構造体があります、`Implements`直後に続くステートメント、`Class`または`Structure`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="e4171-183">If this procedure uses the `Implements` keyword, the containing class or structure must also have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="e4171-184">`Implements`ステートメントで指定されている各インターフェイスを含める必要があります`implementslist`します。</span><span class="sxs-lookup"><span data-stu-id="e4171-184">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="e4171-185">ただし、インターフェイスを定義する名前、 `Function` (で`definedname`) この手順の名前と一致する必要はありません (で`name`)。</span><span class="sxs-lookup"><span data-stu-id="e4171-185">However, the name by which an interface defines the `Function` (in `definedname`) doesn't need to match the name of this procedure (in `name`).</span></span>

> [!NOTE]
> <span data-ttu-id="e4171-186">関数をインライン式を定義するのにラムダ式を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="e4171-186">You can use lambda expressions to define function expressions inline.</span></span> <span data-ttu-id="e4171-187">詳細については、次を参照してください。[関数式](../../../visual-basic/language-reference/operators/function-expression.md)と[ラムダ式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)します。</span><span class="sxs-lookup"><span data-stu-id="e4171-187">For more information, see [Function Expression](../../../visual-basic/language-reference/operators/function-expression.md) and [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>

## <a name="returning-from-a-function"></a><span data-ttu-id="e4171-188">関数から戻る</span><span class="sxs-lookup"><span data-stu-id="e4171-188">Returning from a Function</span></span>

<span data-ttu-id="e4171-189">ときに、`Function`プロシージャを呼び出したステートメントに続くステートメントを使用して、プロシージャは、呼び出し元のコードに返す、実行が続行します。</span><span class="sxs-lookup"><span data-stu-id="e4171-189">When the `Function` procedure returns to the calling code, execution continues with the statement that follows the statement that called the procedure.</span></span>

<span data-ttu-id="e4171-190">関数から値を返す、関数名に値を割り当てるか、含めることで、`Return`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="e4171-190">To return a value from a function, you can either assign the value to the function name or include it in a `Return` statement.</span></span>

<span data-ttu-id="e4171-191">`Return`ステートメントは、同時に戻り値を割り当てるし、として次の例は、関数を終了します。</span><span class="sxs-lookup"><span data-stu-id="e4171-191">The `Return` statement simultaneously assigns the return value and exits the function, as the following example shows.</span></span>

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

<span data-ttu-id="e4171-192">次の例では、関数名に、戻り値を割り当てて`myFunction`しを使用して、`Exit Function`ステートメントに戻ります。</span><span class="sxs-lookup"><span data-stu-id="e4171-192">The following example assigns the return value to the function name `myFunction` and then uses the `Exit Function` statement to return.</span></span>

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

<span data-ttu-id="e4171-193">`Exit Function`と`Return`ステートメントからすぐに終了が発生する、`Function`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="e4171-193">The `Exit Function` and `Return` statements cause an immediate exit from a `Function` procedure.</span></span> <span data-ttu-id="e4171-194">任意の数の`Exit Function`と`Return`ステートメントは、手順では、どこでも表示でき、組み合わせることができます`Exit Function`と`Return`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="e4171-194">Any number of `Exit Function` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Function` and `Return` statements.</span></span>

<span data-ttu-id="e4171-195">使用する場合`Exit Function`値を割り当てることがなく`name`、プロシージャがで指定されているデータ型の既定値を返します`returntype`します。</span><span class="sxs-lookup"><span data-stu-id="e4171-195">If you use `Exit Function` without assigning a value to `name`, the procedure returns the default value for the data type that's specified in `returntype`.</span></span> <span data-ttu-id="e4171-196">場合`returntype`が指定されていない、プロシージャが返す`Nothing`の既定値は`Object`します。</span><span class="sxs-lookup"><span data-stu-id="e4171-196">If `returntype` isn't specified, the procedure returns `Nothing`, which is the default value for `Object`.</span></span>

## <a name="calling-a-function"></a><span data-ttu-id="e4171-197">関数の呼び出し</span><span class="sxs-lookup"><span data-stu-id="e4171-197">Calling a Function</span></span>

<span data-ttu-id="e4171-198">呼び出す、`Function`プロシージャ名、式の中で、かっこで囲まれた引数のリストを使用してプロシージャ。</span><span class="sxs-lookup"><span data-stu-id="e4171-198">You call a `Function` procedure by using the procedure name, followed by the argument list in parentheses, in an expression.</span></span> <span data-ttu-id="e4171-199">任意の引数を指定していない場合にのみかっこを省略することができます。</span><span class="sxs-lookup"><span data-stu-id="e4171-199">You can omit the parentheses only if you aren't supplying any arguments.</span></span> <span data-ttu-id="e4171-200">ただし、コードが常にかっこが含まれる場合より読みやすいです。</span><span class="sxs-lookup"><span data-stu-id="e4171-200">However, your code is more readable if you always include the parentheses.</span></span>

<span data-ttu-id="e4171-201">呼び出す、`Function`プロシージャなどの任意のライブラリを呼び出すことと同じ方法関数`Sqrt`、 `Cos`、または`ChrW`します。</span><span class="sxs-lookup"><span data-stu-id="e4171-201">You call a `Function` procedure the same way that you call any library function such as `Sqrt`, `Cos`, or `ChrW`.</span></span>

<span data-ttu-id="e4171-202">使用して関数を呼び出すことも、`Call`キーワード。</span><span class="sxs-lookup"><span data-stu-id="e4171-202">You can also call a function by using the `Call` keyword.</span></span> <span data-ttu-id="e4171-203">その場合は、戻り値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="e4171-203">In that case, the return value is ignored.</span></span> <span data-ttu-id="e4171-204">使用、`Call`キーワードはほとんどの場合にお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="e4171-204">Use of the `Call` keyword isn't recommended in most cases.</span></span> <span data-ttu-id="e4171-205">詳細については、次を参照してください。 [Call ステートメント](call-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="e4171-205">For more information, see [Call Statement](call-statement.md).</span></span>

<span data-ttu-id="e4171-206">Visual Basic では、算術式内部の効率を向上させることがあります再配置します。</span><span class="sxs-lookup"><span data-stu-id="e4171-206">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="e4171-207">そのため、使用しないでください、`Function`算術式、関数には、同じ式内の変数の値が変更されたときの手順。</span><span class="sxs-lookup"><span data-stu-id="e4171-207">For that reason, you shouldn't use a `Function` procedure in an arithmetic expression when the function changes the value of variables in the same expression.</span></span>

## <a name="async-functions"></a><span data-ttu-id="e4171-208">非同期関数</span><span class="sxs-lookup"><span data-stu-id="e4171-208">Async Functions</span></span>

<span data-ttu-id="e4171-209">*Async*機能は、明示的なコールバックの使用や複数の関数またはラムダ式、コードを手動で分割せず、非同期関数を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="e4171-209">The *Async* feature allows you to invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>

<span data-ttu-id="e4171-210">持つ関数をマークする場合、 [Async](../../../visual-basic/language-reference/modifiers/async.md)修飾子を使用できます、 [Await](../../../visual-basic/language-reference/operators/await-operator.md)関数に演算子。</span><span class="sxs-lookup"><span data-stu-id="e4171-210">If you mark a function with the [Async](../../../visual-basic/language-reference/modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the function.</span></span> <span data-ttu-id="e4171-211">コントロールに達すると、`Await`内の式、`Async`関数は、呼び出し元に制御が戻ります、関数の進行状況が待機中のタスクが完了するまで中断されます。</span><span class="sxs-lookup"><span data-stu-id="e4171-211">When control reaches an `Await` expression in the `Async` function, control returns to the caller, and progress in the function is suspended until the awaited task completes.</span></span> <span data-ttu-id="e4171-212">タスクが完了したら、関数の実行を再開できます。</span><span class="sxs-lookup"><span data-stu-id="e4171-212">When the task is complete, execution can resume in the function.</span></span>

> [!NOTE]
> <span data-ttu-id="e4171-213">`Async`がまだ完了していない最初の待機中のオブジェクトを検出するかとに、プロシージャが、呼び出し元に返すまたはの末尾に達して、`Async`プロシージャか早い方です。</span><span class="sxs-lookup"><span data-stu-id="e4171-213">An `Async` procedure returns to the caller when either it encounters the first awaited object that’s not yet complete, or it gets to the end of the `Async` procedure, whichever occurs first.</span></span>

<span data-ttu-id="e4171-214">`Async`関数の戻り値の型を持つことができます<xref:System.Threading.Tasks.Task%601>または<xref:System.Threading.Tasks.Task>します。</span><span class="sxs-lookup"><span data-stu-id="e4171-214">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="e4171-215">例、`Async`関数の戻り値の型を持つ<xref:System.Threading.Tasks.Task%601>以下に示します。</span><span class="sxs-lookup"><span data-stu-id="e4171-215">An example of an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601> is provided below.</span></span>

<span data-ttu-id="e4171-216">`Async`関数を宣言できません[ByRef](../../../visual-basic/language-reference/modifiers/byref.md)パラメーター。</span><span class="sxs-lookup"><span data-stu-id="e4171-216">An `Async` function cannot declare any [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parameters.</span></span>

<span data-ttu-id="e4171-217">A [Sub ステートメント](sub-statement.md)でもマークされることができます、`Async`修飾子。</span><span class="sxs-lookup"><span data-stu-id="e4171-217">A [Sub Statement](sub-statement.md) can also be marked with the `Async` modifier.</span></span> <span data-ttu-id="e4171-218">これは主に使用、イベント ハンドラーの値を返すことができません。</span><span class="sxs-lookup"><span data-stu-id="e4171-218">This is primarily used for event handlers, where a value cannot be returned.</span></span> <span data-ttu-id="e4171-219">`Async` `Sub`プロシージャを待機することはできませんし、呼び出し元の`Async``Sub`プロシージャによってスローされる例外をキャッチできません、`Sub`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="e4171-219">An `Async` `Sub` procedure can't be awaited, and the caller of an `Async` `Sub` procedure can't catch exceptions that are thrown by the `Sub` procedure.</span></span>

<span data-ttu-id="e4171-220">詳細については`Async`関数を参照してください[Async および Await を使用した非同期プログラミング](../../../visual-basic/programming-guide/concepts/async/index.md)、[非同期プログラムにおける制御フロー](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)、および[Async 戻り値の型](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="e4171-220">For more information about `Async` functions, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>

## <a name="iterator-functions"></a><span data-ttu-id="e4171-221">反復子関数</span><span class="sxs-lookup"><span data-stu-id="e4171-221">Iterator Functions</span></span>

<span data-ttu-id="e4171-222">*反復子*関数は、リストや配列など、コレクションに対するカスタム イテレーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="e4171-222">An *iterator* function performs a custom iteration over a collection, such as a list or array.</span></span> <span data-ttu-id="e4171-223">反復子関数を使用して、 [Yield](yield-statement.md)ステートメントを一度に 1 つの各要素を返します。</span><span class="sxs-lookup"><span data-stu-id="e4171-223">An iterator function uses the [Yield](yield-statement.md) statement to return each element one at a time.</span></span> <span data-ttu-id="e4171-224">ときに、 [Yield](yield-statement.md)ステートメントに達すると、コード内の現在の場所が記憶されます。</span><span class="sxs-lookup"><span data-stu-id="e4171-224">When a [Yield](yield-statement.md) statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="e4171-225">次回、iterator 関数が呼び出されると、この位置から実行が再開されます。</span><span class="sxs-lookup"><span data-stu-id="e4171-225">Execution is restarted from that location the next time the iterator function is called.</span></span>

<span data-ttu-id="e4171-226">使用して、クライアント コードから反復子を呼び出す、[ごとにしています.[次へ]](for-each-next-statement.md)ステートメント。</span><span class="sxs-lookup"><span data-stu-id="e4171-226">You call an iterator from client code by using a [For Each…Next](for-each-next-statement.md) statement.</span></span>

<span data-ttu-id="e4171-227">反復子関数の戻り値の型は、 <xref:System.Collections.IEnumerable>、 <xref:System.Collections.Generic.IEnumerable%601>、 <xref:System.Collections.IEnumerator>、または<xref:System.Collections.Generic.IEnumerator%601>します。</span><span class="sxs-lookup"><span data-stu-id="e4171-227">The return type of an iterator function can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>

<span data-ttu-id="e4171-228">詳細については、「 [反復子](../../programming-guide/concepts/iterators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4171-228">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>

## <a name="example"></a><span data-ttu-id="e4171-229">例</span><span class="sxs-lookup"><span data-stu-id="e4171-229">Example</span></span>

<span data-ttu-id="e4171-230">次の例では、`Function`宣言名、パラメーター、およびコードの本体を形成するステートメントを`Function`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="e4171-230">The following example uses the `Function` statement to declare the name, parameters, and code that form the body of a `Function` procedure.</span></span> <span data-ttu-id="e4171-231">`ParamArray`修飾子により、可変個の引数を受け入れるように機能します。</span><span class="sxs-lookup"><span data-stu-id="e4171-231">The `ParamArray` modifier enables the function to accept a variable number of arguments.</span></span>

[!code-vb[VbVbalrStatements#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#25)]

## <a name="example"></a><span data-ttu-id="e4171-232">例</span><span class="sxs-lookup"><span data-stu-id="e4171-232">Example</span></span>

<span data-ttu-id="e4171-233">次の例では、前の例で宣言された関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e4171-233">The following example invokes the function declared in the preceding example.</span></span>

[!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]

## <a name="example"></a><span data-ttu-id="e4171-234">例</span><span class="sxs-lookup"><span data-stu-id="e4171-234">Example</span></span>

<span data-ttu-id="e4171-235">次の例では、`DelayAsync`は、 `Async` `Function`の戻り値の型を持つ<xref:System.Threading.Tasks.Task%601>します。</span><span class="sxs-lookup"><span data-stu-id="e4171-235">In the following example, `DelayAsync` is an `Async` `Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="e4171-236">`DelayAsync` には、整数を返す `Return` ステートメントがあります。</span><span class="sxs-lookup"><span data-stu-id="e4171-236">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="e4171-237">そのため、関数の宣言の`DelayAsync`の戻り値の型を指定する必要があります`Task(Of Integer)`します。</span><span class="sxs-lookup"><span data-stu-id="e4171-237">Therefore the function declaration of `DelayAsync` needs to have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="e4171-238">戻り値の型である`Task(Of Integer)`の評価、`Await`式`DoSomethingAsync`整数が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e4171-238">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer.</span></span> <span data-ttu-id="e4171-239">これはこのステートメントで示されています:`Dim result As Integer = Await delayTask`します。</span><span class="sxs-lookup"><span data-stu-id="e4171-239">This is demonstrated in this statement: `Dim result As Integer = Await delayTask`.</span></span>

<span data-ttu-id="e4171-240">`startButton_Click`プロシージャの例に示します、`Async Sub`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="e4171-240">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="e4171-241">`DoSomethingAsync`は、`Async`関数では、タスクへの呼び出しを`DoSomethingAsync`、次のステートメントに示す待機する必要があります:`Await DoSomethingAsync()`します。</span><span class="sxs-lookup"><span data-stu-id="e4171-241">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement demonstrates: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="e4171-242">`startButton_Click` `Sub`でプロシージャを定義する必要があります、`Async`修飾子があるため、`Await`式。</span><span class="sxs-lookup"><span data-stu-id="e4171-242">The `startButton_Click` `Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="e4171-243">関連項目</span><span class="sxs-lookup"><span data-stu-id="e4171-243">See also</span></span>

- [<span data-ttu-id="e4171-244">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="e4171-244">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="e4171-245">Function プロシージャ</span><span class="sxs-lookup"><span data-stu-id="e4171-245">Function Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)
- [<span data-ttu-id="e4171-246">パラメーター リスト</span><span class="sxs-lookup"><span data-stu-id="e4171-246">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="e4171-247">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="e4171-247">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="e4171-248">Call ステートメント</span><span class="sxs-lookup"><span data-stu-id="e4171-248">Call Statement</span></span>](call-statement.md)
- [<span data-ttu-id="e4171-249">Of</span><span class="sxs-lookup"><span data-stu-id="e4171-249">Of</span></span>](of-clause.md)
- [<span data-ttu-id="e4171-250">パラメーター配列</span><span class="sxs-lookup"><span data-stu-id="e4171-250">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
- [<span data-ttu-id="e4171-251">方法: ジェネリック クラスを使用する</span><span class="sxs-lookup"><span data-stu-id="e4171-251">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="e4171-252">プロシージャのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="e4171-252">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [<span data-ttu-id="e4171-253">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="e4171-253">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="e4171-254">Function 式</span><span class="sxs-lookup"><span data-stu-id="e4171-254">Function Expression</span></span>](../../../visual-basic/language-reference/operators/function-expression.md)
