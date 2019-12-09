---
title: Sub ステートメント
ms.date: 05/12/2018
f1_keywords:
- vb.Sub
helpviewer_keywords:
- Public keyword [Visual Basic], Sub statements
- procedures [Visual Basic], creating
- declaring procedures [Visual Basic], Sub statement
- arguments [Visual Basic], Sub procedures
- As keyword [Visual Basic], Sub statements
- Optional keyword [Visual Basic], Sub statements
- declarations [Visual Basic], procedures
- Sub keyword [Visual Basic]
- Handles keyword [Visual Basic], Sub statements
- Protected Friend keyword [Visual Basic]
- ParamArray keyword [Visual Basic], Sub statements
- Implements keyword [Visual Basic], Sub statements
- Sub statement [Visual Basic]
- subroutines
- ByRef keyword [Visual Basic], Sub statements
- Sub procedures [Visual Basic], Sub statement
- recursive procedures
- Private keyword [Visual Basic], Sub statements
- Friend keyword [Visual Basic], Sub statements
- Exit statement [Visual Basic], Sub statements
- procedures [Visual Basic], Sub
- End keyword [Visual Basic], Sub statements
- ByVal keyword [Visual Basic], Sub statements
- Visual Basic code, Sub procedures
ms.assetid: e347d700-d06c-405b-b302-e9b1edb57dfc
ms.openlocfilehash: da498a5e0a3633eb98882aaed145fcd21ab169fd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346437"
---
# <a name="sub-statement-visual-basic"></a><span data-ttu-id="9dc24-102">Sub ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9dc24-102">Sub Statement (Visual Basic)</span></span>

<span data-ttu-id="9dc24-103">`Sub` プロシージャを定義する名前、パラメーター、およびコードを宣言します。</span><span class="sxs-lookup"><span data-stu-id="9dc24-103">Declares the name, parameters, and code that define a `Sub` procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="9dc24-104">構文</span><span class="sxs-lookup"><span data-stu-id="9dc24-104">Syntax</span></span>

```vb
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Sub ]
    [ statements ]
End Sub
```

## <a name="parts"></a><span data-ttu-id="9dc24-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="9dc24-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="9dc24-106">省略可。</span><span class="sxs-lookup"><span data-stu-id="9dc24-106">Optional.</span></span> <span data-ttu-id="9dc24-107">「[属性リスト](attribute-list.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dc24-107">See [Attribute List](attribute-list.md).</span></span>

- `Partial`

  <span data-ttu-id="9dc24-108">省略可。</span><span class="sxs-lookup"><span data-stu-id="9dc24-108">Optional.</span></span> <span data-ttu-id="9dc24-109">部分メソッドの定義を示します。</span><span class="sxs-lookup"><span data-stu-id="9dc24-109">Indicates definition of a partial method.</span></span> <span data-ttu-id="9dc24-110">「[部分メソッド](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dc24-110">See [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span></span>

- `accessmodifier`

  <span data-ttu-id="9dc24-111">省略可。</span><span class="sxs-lookup"><span data-stu-id="9dc24-111">Optional.</span></span> <span data-ttu-id="9dc24-112">次のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="9dc24-112">Can be one of the following:</span></span>

  - [<span data-ttu-id="9dc24-113">Public</span><span class="sxs-lookup"><span data-stu-id="9dc24-113">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="9dc24-114">Protected</span><span class="sxs-lookup"><span data-stu-id="9dc24-114">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="9dc24-115">Friend</span><span class="sxs-lookup"><span data-stu-id="9dc24-115">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="9dc24-116">Private</span><span class="sxs-lookup"><span data-stu-id="9dc24-116">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="9dc24-117">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="9dc24-117">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

  - [<span data-ttu-id="9dc24-118">Private Protected</span><span class="sxs-lookup"><span data-stu-id="9dc24-118">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

  <span data-ttu-id="9dc24-119">「 [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dc24-119">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `proceduremodifiers`

  <span data-ttu-id="9dc24-120">省略可。</span><span class="sxs-lookup"><span data-stu-id="9dc24-120">Optional.</span></span> <span data-ttu-id="9dc24-121">次のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="9dc24-121">Can be one of the following:</span></span>

  - [<span data-ttu-id="9dc24-122">Overloads</span><span class="sxs-lookup"><span data-stu-id="9dc24-122">Overloads</span></span>](../modifiers/overloads.md)

  - [<span data-ttu-id="9dc24-123">Overrides</span><span class="sxs-lookup"><span data-stu-id="9dc24-123">Overrides</span></span>](../modifiers/overrides.md)

  - [<span data-ttu-id="9dc24-124">Overridable</span><span class="sxs-lookup"><span data-stu-id="9dc24-124">Overridable</span></span>](../modifiers/overridable.md)

  - [<span data-ttu-id="9dc24-125">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="9dc24-125">NotOverridable</span></span>](../modifiers/notoverridable.md)

  - [<span data-ttu-id="9dc24-126">MyBase</span><span class="sxs-lookup"><span data-stu-id="9dc24-126">MustOverride</span></span>](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="9dc24-127">省略可。</span><span class="sxs-lookup"><span data-stu-id="9dc24-127">Optional.</span></span> <span data-ttu-id="9dc24-128">「[Shared](../modifiers/shared.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dc24-128">See [Shared](../modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="9dc24-129">省略可。</span><span class="sxs-lookup"><span data-stu-id="9dc24-129">Optional.</span></span> <span data-ttu-id="9dc24-130">「[Shadows](../modifiers/shadows.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dc24-130">See [Shadows](../modifiers/shadows.md).</span></span>

- `Async`

  <span data-ttu-id="9dc24-131">省略可。</span><span class="sxs-lookup"><span data-stu-id="9dc24-131">Optional.</span></span> <span data-ttu-id="9dc24-132">「 [Async](../modifiers/async.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dc24-132">See [Async](../modifiers/async.md).</span></span>

- `name`

  <span data-ttu-id="9dc24-133">必須。</span><span class="sxs-lookup"><span data-stu-id="9dc24-133">Required.</span></span> <span data-ttu-id="9dc24-134">プロシージャの名前。</span><span class="sxs-lookup"><span data-stu-id="9dc24-134">Name of the procedure.</span></span> <span data-ttu-id="9dc24-135">「 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dc24-135">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span> <span data-ttu-id="9dc24-136">クラスのコンストラクタープロシージャを作成するには、`Sub` プロシージャの名前を `New` キーワードに設定します。</span><span class="sxs-lookup"><span data-stu-id="9dc24-136">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="9dc24-137">詳細については、「[オブジェクトの有効期間: オブジェクトの作成方法と破棄方法](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dc24-137">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>

- `typeparamlist`

  <span data-ttu-id="9dc24-138">省略可。</span><span class="sxs-lookup"><span data-stu-id="9dc24-138">Optional.</span></span> <span data-ttu-id="9dc24-139">ジェネリックプロシージャの型パラメーターのリスト。</span><span class="sxs-lookup"><span data-stu-id="9dc24-139">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="9dc24-140">[型リスト](type-list.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dc24-140">See [Type List](type-list.md).</span></span>

- `parameterlist`

  <span data-ttu-id="9dc24-141">省略可。</span><span class="sxs-lookup"><span data-stu-id="9dc24-141">Optional.</span></span> <span data-ttu-id="9dc24-142">このプロシージャのパラメーターを表すローカル変数名の一覧。</span><span class="sxs-lookup"><span data-stu-id="9dc24-142">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="9dc24-143">「[パラメーターリスト](parameter-list.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dc24-143">See [Parameter List](parameter-list.md).</span></span>

- `Implements`

  <span data-ttu-id="9dc24-144">省略可。</span><span class="sxs-lookup"><span data-stu-id="9dc24-144">Optional.</span></span> <span data-ttu-id="9dc24-145">このプロシージャが1つ以上の `Sub` プロシージャを実装することを示します。各プロシージャは、このプロシージャのクラスまたは構造体を含むインターフェイスで定義されています。</span><span class="sxs-lookup"><span data-stu-id="9dc24-145">Indicates that this procedure implements one or more `Sub` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="9dc24-146">「 [Implements ステートメント](implements-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dc24-146">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="9dc24-147">`Implements` を指定する場合は、必ず指定します。</span><span class="sxs-lookup"><span data-stu-id="9dc24-147">Required if `Implements` is supplied.</span></span> <span data-ttu-id="9dc24-148">実装される `Sub` プロシージャのリストです。</span><span class="sxs-lookup"><span data-stu-id="9dc24-148">List of `Sub` procedures being implemented.</span></span>

  `implementedprocedure [ , implementedprocedure ... ]`

  <span data-ttu-id="9dc24-149">`implementedprocedure` の構文と指定項目は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9dc24-149">Each `implementedprocedure` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="9dc24-150">要素</span><span class="sxs-lookup"><span data-stu-id="9dc24-150">Part</span></span>|<span data-ttu-id="9dc24-151">説明</span><span class="sxs-lookup"><span data-stu-id="9dc24-151">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="9dc24-152">必須。</span><span class="sxs-lookup"><span data-stu-id="9dc24-152">Required.</span></span> <span data-ttu-id="9dc24-153">このプロシージャのクラスまたは構造体によって実装されるインターフェイスの名前。</span><span class="sxs-lookup"><span data-stu-id="9dc24-153">Name of an interface implemented by this procedure's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="9dc24-154">必須。</span><span class="sxs-lookup"><span data-stu-id="9dc24-154">Required.</span></span> <span data-ttu-id="9dc24-155">`interface` の中でプロシージャを定義するために使用する名前。</span><span class="sxs-lookup"><span data-stu-id="9dc24-155">Name by which the procedure is defined in `interface`.</span></span>|

- `Handles`

  <span data-ttu-id="9dc24-156">省略可。</span><span class="sxs-lookup"><span data-stu-id="9dc24-156">Optional.</span></span> <span data-ttu-id="9dc24-157">このプロシージャが1つ以上の特定のイベントを処理できることを示します。</span><span class="sxs-lookup"><span data-stu-id="9dc24-157">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="9dc24-158">「[Handles](handles-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dc24-158">See [Handles](handles-clause.md).</span></span>

- `eventlist`

  <span data-ttu-id="9dc24-159">`Handles` を指定する場合は、必ず指定します。</span><span class="sxs-lookup"><span data-stu-id="9dc24-159">Required if `Handles` is supplied.</span></span> <span data-ttu-id="9dc24-160">このプロシージャが処理するイベントの一覧です。</span><span class="sxs-lookup"><span data-stu-id="9dc24-160">List of events this procedure handles.</span></span>

  `eventspecifier [ , eventspecifier ... ]`

  <span data-ttu-id="9dc24-161">`eventspecifier` の構文と指定項目は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9dc24-161">Each `eventspecifier` has the following syntax and parts:</span></span>

  `eventvariable.event`

  |<span data-ttu-id="9dc24-162">要素</span><span class="sxs-lookup"><span data-stu-id="9dc24-162">Part</span></span>|<span data-ttu-id="9dc24-163">説明</span><span class="sxs-lookup"><span data-stu-id="9dc24-163">Description</span></span>|
  |---|---|
  |`eventvariable`|<span data-ttu-id="9dc24-164">必須。</span><span class="sxs-lookup"><span data-stu-id="9dc24-164">Required.</span></span> <span data-ttu-id="9dc24-165">イベントを発生させるクラスまたは構造体のデータ型で宣言されたオブジェクト変数。</span><span class="sxs-lookup"><span data-stu-id="9dc24-165">Object variable declared with the data type of the class or structure that raises the event.</span></span>|
  |`event`|<span data-ttu-id="9dc24-166">必須。</span><span class="sxs-lookup"><span data-stu-id="9dc24-166">Required.</span></span> <span data-ttu-id="9dc24-167">このプロシージャが処理するイベントの名前。</span><span class="sxs-lookup"><span data-stu-id="9dc24-167">Name of the event this procedure handles.</span></span>|

- `statements`

  <span data-ttu-id="9dc24-168">省略可。</span><span class="sxs-lookup"><span data-stu-id="9dc24-168">Optional.</span></span> <span data-ttu-id="9dc24-169">このプロシージャ内で実行するステートメントのブロック。</span><span class="sxs-lookup"><span data-stu-id="9dc24-169">Block of statements to run within this procedure.</span></span>

- `End Sub`

  <span data-ttu-id="9dc24-170">このプロシージャの定義を終了します。</span><span class="sxs-lookup"><span data-stu-id="9dc24-170">Terminates the definition of this procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="9dc24-171">コメント</span><span class="sxs-lookup"><span data-stu-id="9dc24-171">Remarks</span></span>

<span data-ttu-id="9dc24-172">すべての実行可能コードは、プロシージャ内になければなりません。</span><span class="sxs-lookup"><span data-stu-id="9dc24-172">All executable code must be inside a procedure.</span></span> <span data-ttu-id="9dc24-173">呼び出し元のコードに値を返さないようにする場合は、`Sub` プロシージャを使用します。</span><span class="sxs-lookup"><span data-stu-id="9dc24-173">Use a `Sub` procedure when you don't want to return a value to the calling code.</span></span> <span data-ttu-id="9dc24-174">値を返す場合は、`Function` プロシージャを使用します。</span><span class="sxs-lookup"><span data-stu-id="9dc24-174">Use a `Function` procedure when you want to return a value.</span></span>

## <a name="defining-a-sub-procedure"></a><span data-ttu-id="9dc24-175">Sub プロシージャの定義</span><span class="sxs-lookup"><span data-stu-id="9dc24-175">Defining a Sub Procedure</span></span>

<span data-ttu-id="9dc24-176">`Sub` プロシージャは、モジュールレベルでのみ定義できます。</span><span class="sxs-lookup"><span data-stu-id="9dc24-176">You can define a `Sub` procedure only at the module level.</span></span> <span data-ttu-id="9dc24-177">したがって、サブプロシージャの宣言コンテキストは、クラス、構造体、モジュール、またはインターフェイスにする必要があり、ソースファイル、名前空間、プロシージャ、またはブロックにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9dc24-177">The declaration context for a sub procedure must, therefore, be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="9dc24-178">詳細については、「[宣言コンテキストと既定のアクセス レベル](declaration-contexts-and-default-access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dc24-178">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="9dc24-179">`Sub` プロシージャは、既定でパブリックアクセスになります。</span><span class="sxs-lookup"><span data-stu-id="9dc24-179">`Sub` procedures default to public access.</span></span> <span data-ttu-id="9dc24-180">アクセス修飾子を使用して、アクセスレベルを調整できます。</span><span class="sxs-lookup"><span data-stu-id="9dc24-180">You can adjust their access levels by using the access modifiers.</span></span>

<span data-ttu-id="9dc24-181">プロシージャが `Implements` キーワードを使用している場合、含んでいるクラスまたは構造体には、その `Class` または `Structure` ステートメントの直後にある `Implements` ステートメントが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dc24-181">If the procedure uses the `Implements` keyword, the containing class or structure must have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="9dc24-182">`Implements` ステートメントには、`implementslist`で指定されている各インターフェイスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dc24-182">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="9dc24-183">ただし、インターフェイスが `Sub` (`definedname`) を定義する際には、このプロシージャの名前 (`name`) と一致する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9dc24-183">However, the name by which an interface defines the `Sub` (in `definedname`) doesn't have to match the name of this procedure (in `name`).</span></span>

## <a name="returning-from-a-sub-procedure"></a><span data-ttu-id="9dc24-184">Sub プロシージャからの戻り</span><span class="sxs-lookup"><span data-stu-id="9dc24-184">Returning from a Sub Procedure</span></span>

<span data-ttu-id="9dc24-185">`Sub` プロシージャが呼び出し元のコードに戻ると、ステートメントを呼び出したステートメントの後のステートメントで実行が続行されます。</span><span class="sxs-lookup"><span data-stu-id="9dc24-185">When a `Sub` procedure returns to the calling code, execution continues with the statement after the statement that called it.</span></span>

<span data-ttu-id="9dc24-186">次の例は、`Sub` プロシージャからの戻り値を示しています。</span><span class="sxs-lookup"><span data-stu-id="9dc24-186">The following example shows a return from a `Sub` procedure.</span></span>

```vb
Sub mySub(ByVal q As String)
    Return
End Sub
```

<span data-ttu-id="9dc24-187">`Exit Sub` ステートメントおよび `Return` ステートメントを行うと、`Sub` プロシージャからすぐに終了します。</span><span class="sxs-lookup"><span data-stu-id="9dc24-187">The `Exit Sub` and `Return` statements cause an immediate exit from a `Sub` procedure.</span></span> <span data-ttu-id="9dc24-188">プロシージャ内の任意の場所で任意の数の `Exit Sub` および `Return` ステートメントを使用できます。また、`Exit Sub` と `Return` のステートメントを混在させることができます。</span><span class="sxs-lookup"><span data-stu-id="9dc24-188">Any number of `Exit Sub` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Sub` and `Return` statements.</span></span>

## <a name="calling-a-sub-procedure"></a><span data-ttu-id="9dc24-189">Sub プロシージャの呼び出し</span><span class="sxs-lookup"><span data-stu-id="9dc24-189">Calling a Sub Procedure</span></span>

<span data-ttu-id="9dc24-190">`Sub` プロシージャを呼び出すには、ステートメントでプロシージャ名を使用し、その名前の後にかっこで囲んだ引数リストを指定します。</span><span class="sxs-lookup"><span data-stu-id="9dc24-190">You call a `Sub` procedure by using the procedure name in a statement and then following that name with its argument list in parentheses.</span></span> <span data-ttu-id="9dc24-191">かっこを省略できるのは、引数を指定しない場合のみです。</span><span class="sxs-lookup"><span data-stu-id="9dc24-191">You can omit the parentheses only if you don't supply any arguments.</span></span> <span data-ttu-id="9dc24-192">ただし、常にかっこを含めると、コードが読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="9dc24-192">However, your code is more readable if you always include the parentheses.</span></span>

<span data-ttu-id="9dc24-193">`Sub` プロシージャと `Function` プロシージャは、パラメーターを持つことができ、一連のステートメントを実行できます。</span><span class="sxs-lookup"><span data-stu-id="9dc24-193">A `Sub` procedure and a `Function` procedure  can have parameters and perform a series of statements.</span></span> <span data-ttu-id="9dc24-194">ただし、`Function` プロシージャは値を返し、`Sub` プロシージャは返しません。</span><span class="sxs-lookup"><span data-stu-id="9dc24-194">However, a `Function` procedure returns a value, and a `Sub` procedure doesn't.</span></span> <span data-ttu-id="9dc24-195">したがって、式の中で `Sub` プロシージャを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="9dc24-195">Therefore, you can't use a `Sub` procedure in an expression.</span></span>

<span data-ttu-id="9dc24-196">`Sub` プロシージャを呼び出すときに `Call` キーワードを使用することはできますが、ほとんどの場合、そのキーワードは推奨されません。</span><span class="sxs-lookup"><span data-stu-id="9dc24-196">You can use the `Call` keyword when you call a `Sub` procedure, but that keyword isn't recommended for most uses.</span></span> <span data-ttu-id="9dc24-197">詳細については、「 [Call ステートメント](call-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dc24-197">For more information, see [Call Statement](call-statement.md).</span></span>

<span data-ttu-id="9dc24-198">Visual Basic は、内部効率を向上させるために算術式を再配置することがあります。</span><span class="sxs-lookup"><span data-stu-id="9dc24-198">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="9dc24-199">そのため、引数リストに他のプロシージャを呼び出す式が含まれている場合は、それらの式が特定の順序で呼び出されると想定しないでください。</span><span class="sxs-lookup"><span data-stu-id="9dc24-199">For that reason, if your argument list includes expressions that call other procedures, you shouldn't assume that those expressions will be called in a particular order.</span></span>

## <a name="async-sub-procedures"></a><span data-ttu-id="9dc24-200">非同期サブプロシージャ</span><span class="sxs-lookup"><span data-stu-id="9dc24-200">Async Sub Procedures</span></span>

<span data-ttu-id="9dc24-201">非同期機能を使用すると、明示的なコールバックを使用したり、複数の関数やラムダ式にコードを手動で分割したりせずに、非同期関数を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="9dc24-201">By using the Async feature, you can invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>

<span data-ttu-id="9dc24-202">プロシージャに[Async](../modifiers/async.md)修飾子を指定した場合は、プロシージャで[Await](../../../visual-basic/language-reference/operators/await-operator.md)演算子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9dc24-202">If you mark a procedure with the [Async](../modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the procedure.</span></span> <span data-ttu-id="9dc24-203">コントロールが `Async` プロシージャ内の `Await` 式に到達すると、コントロールは呼び出し元に戻り、待機中のタスクが完了するまで、プロシージャの進行状況は中断されます。</span><span class="sxs-lookup"><span data-stu-id="9dc24-203">When control reaches an `Await` expression in the `Async` procedure, control returns to the caller, and progress in the procedure is suspended until the awaited task completes.</span></span> <span data-ttu-id="9dc24-204">タスクが完了すると、プロシージャで実行を再開できます。</span><span class="sxs-lookup"><span data-stu-id="9dc24-204">When the task is complete, execution can resume in the procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="9dc24-205">`Async` プロシージャは、まだ完了していない最初の待機中のオブジェクトが検出された場合、または `Async` プロシージャの最後に到達した場合に、呼び出し元に戻ります。</span><span class="sxs-lookup"><span data-stu-id="9dc24-205">An `Async` procedure returns to the caller when either the first awaited object that’s not yet complete is encountered or the end of the `Async` procedure is reached, whichever occurs first.</span></span>

<span data-ttu-id="9dc24-206">[関数ステートメント](function-statement.md)を `Async` 修飾子でマークすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9dc24-206">You can also mark a [Function Statement](function-statement.md) with the `Async` modifier.</span></span> <span data-ttu-id="9dc24-207">`Async` 関数は、<xref:System.Threading.Tasks.Task%601> または <xref:System.Threading.Tasks.Task>の戻り値の型を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="9dc24-207">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="9dc24-208">このトピックの後半の例では、<xref:System.Threading.Tasks.Task%601>の戻り値の型を持つ `Async` 関数を示します。</span><span class="sxs-lookup"><span data-stu-id="9dc24-208">An example later in this topic shows an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span>

<span data-ttu-id="9dc24-209">`Async` の `Sub` プロシージャは、主に、値を返すことができないイベントハンドラーに使用されます。</span><span class="sxs-lookup"><span data-stu-id="9dc24-209">`Async` `Sub` procedures are primarily used for event handlers, where a value can't be returned.</span></span> <span data-ttu-id="9dc24-210">`Async` `Sub` プロシージャは待機できません。また、`Async` の `Sub` プロシージャの呼び出し元は、`Sub` プロシージャがスローする例外をキャッチできません。</span><span class="sxs-lookup"><span data-stu-id="9dc24-210">An `Async` `Sub` procedure can't be awaited, and the caller of an `Async` `Sub` procedure can't catch exceptions that the `Sub` procedure throws.</span></span>

<span data-ttu-id="9dc24-211">`Async` プロシージャで[ByRef](../modifiers/byref.md)パラメーターを宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="9dc24-211">An `Async` procedure can't declare any [ByRef](../modifiers/byref.md) parameters.</span></span>

<span data-ttu-id="9dc24-212">`Async` の手順の詳細については、「 [async および Await を使用した非同期プログラミング](../../../visual-basic/programming-guide/concepts/async/index.md)」、「非同期[プログラムでの制御フロー](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)」、および「非同期の[戻り値の型](../../../visual-basic/programming-guide/concepts/async/async-return-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dc24-212">For more information about `Async` procedures, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>

## <a name="example"></a><span data-ttu-id="9dc24-213">例</span><span class="sxs-lookup"><span data-stu-id="9dc24-213">Example</span></span>

<span data-ttu-id="9dc24-214">次の例では、`Sub` ステートメントを使用して、`Sub` プロシージャの本体を形成する名前、パラメーター、およびコードを定義します。</span><span class="sxs-lookup"><span data-stu-id="9dc24-214">The following example uses the `Sub` statement to define the name, parameters, and code that form the body of a `Sub` procedure.</span></span>

[!code-vb[VbVbalrStatements#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#58)]

## <a name="example"></a><span data-ttu-id="9dc24-215">例</span><span class="sxs-lookup"><span data-stu-id="9dc24-215">Example</span></span>

<span data-ttu-id="9dc24-216">次の例では、`DelayAsync` は、戻り値の型が <xref:System.Threading.Tasks.Task%601>の `Async` `Function` です。</span><span class="sxs-lookup"><span data-stu-id="9dc24-216">In the following example, `DelayAsync` is an `Async` `Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="9dc24-217">`DelayAsync` には、整数を返す `Return` ステートメントがあります。</span><span class="sxs-lookup"><span data-stu-id="9dc24-217">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="9dc24-218">したがって、`DelayAsync` の関数宣言には、`Task(Of Integer)`の戻り値の型を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dc24-218">Therefore, the function declaration of `DelayAsync` must have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="9dc24-219">戻り値の型が `Task(Of Integer)`ので、次のステートメントに `Dim result As Integer = Await delayTask`示すように、`DoSomethingAsync` で `Await` 式を評価すると整数が生成されます。</span><span class="sxs-lookup"><span data-stu-id="9dc24-219">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer, as the following statement shows: `Dim result As Integer = Await delayTask`.</span></span>

<span data-ttu-id="9dc24-220">`startButton_Click` プロシージャは、`Async Sub` プロシージャの一例です。</span><span class="sxs-lookup"><span data-stu-id="9dc24-220">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="9dc24-221">`DoSomethingAsync` は `Async` 関数であるため、次のステートメントに示すように、`DoSomethingAsync` を呼び出すためのタスクを待機する必要があります。 `Await DoSomethingAsync()`。</span><span class="sxs-lookup"><span data-stu-id="9dc24-221">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement shows: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="9dc24-222">`startButton_Click` `Sub` プロシージャには `Await` 式があるため、`Async` 修飾子を使用して定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dc24-222">The `startButton_Click` `Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="9dc24-223">参照</span><span class="sxs-lookup"><span data-stu-id="9dc24-223">See also</span></span>

- [<span data-ttu-id="9dc24-224">Implements ステートメント</span><span class="sxs-lookup"><span data-stu-id="9dc24-224">Implements Statement</span></span>](implements-statement.md)
- [<span data-ttu-id="9dc24-225">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="9dc24-225">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="9dc24-226">パラメーター リスト</span><span class="sxs-lookup"><span data-stu-id="9dc24-226">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="9dc24-227">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="9dc24-227">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="9dc24-228">Call ステートメント</span><span class="sxs-lookup"><span data-stu-id="9dc24-228">Call Statement</span></span>](call-statement.md)
- [<span data-ttu-id="9dc24-229">Of</span><span class="sxs-lookup"><span data-stu-id="9dc24-229">Of</span></span>](of-clause.md)
- [<span data-ttu-id="9dc24-230">パラメーター配列</span><span class="sxs-lookup"><span data-stu-id="9dc24-230">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
- [<span data-ttu-id="9dc24-231">方法 : ジェネリック クラスを使用する</span><span class="sxs-lookup"><span data-stu-id="9dc24-231">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="9dc24-232">プロシージャのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="9dc24-232">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [<span data-ttu-id="9dc24-233">部分メソッド</span><span class="sxs-lookup"><span data-stu-id="9dc24-233">Partial Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
