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
ms.openlocfilehash: e50b79c31c92ac116d6c82bcececba3340894d74
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404175"
---
# <a name="sub-statement-visual-basic"></a><span data-ttu-id="7adc6-102">Sub ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7adc6-102">Sub Statement (Visual Basic)</span></span>

<span data-ttu-id="7adc6-103">`Sub` プロシージャを定義する名前、パラメーター、およびコードを宣言します。</span><span class="sxs-lookup"><span data-stu-id="7adc6-103">Declares the name, parameters, and code that define a `Sub` procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="7adc6-104">構文</span><span class="sxs-lookup"><span data-stu-id="7adc6-104">Syntax</span></span>

```vb
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Sub ]
    [ statements ]
End Sub
```

## <a name="parts"></a><span data-ttu-id="7adc6-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="7adc6-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="7adc6-106">任意。</span><span class="sxs-lookup"><span data-stu-id="7adc6-106">Optional.</span></span> <span data-ttu-id="7adc6-107">「[属性リスト](attribute-list.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7adc6-107">See [Attribute List](attribute-list.md).</span></span>

- `Partial`

  <span data-ttu-id="7adc6-108">任意。</span><span class="sxs-lookup"><span data-stu-id="7adc6-108">Optional.</span></span> <span data-ttu-id="7adc6-109">部分メソッドの定義を示します。</span><span class="sxs-lookup"><span data-stu-id="7adc6-109">Indicates definition of a partial method.</span></span> <span data-ttu-id="7adc6-110">「[部分メソッド](../../programming-guide/language-features/procedures/partial-methods.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7adc6-110">See [Partial Methods](../../programming-guide/language-features/procedures/partial-methods.md).</span></span>

- `accessmodifier`

  <span data-ttu-id="7adc6-111">任意。</span><span class="sxs-lookup"><span data-stu-id="7adc6-111">Optional.</span></span> <span data-ttu-id="7adc6-112">次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="7adc6-112">Can be one of the following:</span></span>

  - [<span data-ttu-id="7adc6-113">Public</span><span class="sxs-lookup"><span data-stu-id="7adc6-113">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="7adc6-114">Protected</span><span class="sxs-lookup"><span data-stu-id="7adc6-114">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="7adc6-115">Friend</span><span class="sxs-lookup"><span data-stu-id="7adc6-115">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="7adc6-116">Private</span><span class="sxs-lookup"><span data-stu-id="7adc6-116">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="7adc6-117">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="7adc6-117">Protected Friend</span></span>](../modifiers/protected-friend.md)

  - [<span data-ttu-id="7adc6-118">Private Protected</span><span class="sxs-lookup"><span data-stu-id="7adc6-118">Private Protected</span></span>](../modifiers/private-protected.md)

  <span data-ttu-id="7adc6-119">「 [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7adc6-119">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `proceduremodifiers`

  <span data-ttu-id="7adc6-120">任意。</span><span class="sxs-lookup"><span data-stu-id="7adc6-120">Optional.</span></span> <span data-ttu-id="7adc6-121">次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="7adc6-121">Can be one of the following:</span></span>

  - [<span data-ttu-id="7adc6-122">Overloads</span><span class="sxs-lookup"><span data-stu-id="7adc6-122">Overloads</span></span>](../modifiers/overloads.md)

  - [<span data-ttu-id="7adc6-123">Overrides</span><span class="sxs-lookup"><span data-stu-id="7adc6-123">Overrides</span></span>](../modifiers/overrides.md)

  - [<span data-ttu-id="7adc6-124">Overridable</span><span class="sxs-lookup"><span data-stu-id="7adc6-124">Overridable</span></span>](../modifiers/overridable.md)

  - [<span data-ttu-id="7adc6-125">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="7adc6-125">NotOverridable</span></span>](../modifiers/notoverridable.md)

  - [<span data-ttu-id="7adc6-126">MustOverride</span><span class="sxs-lookup"><span data-stu-id="7adc6-126">MustOverride</span></span>](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="7adc6-127">任意。</span><span class="sxs-lookup"><span data-stu-id="7adc6-127">Optional.</span></span> <span data-ttu-id="7adc6-128">「[Shared](../modifiers/shared.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7adc6-128">See [Shared](../modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="7adc6-129">任意。</span><span class="sxs-lookup"><span data-stu-id="7adc6-129">Optional.</span></span> <span data-ttu-id="7adc6-130">「[Shadows](../modifiers/shadows.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7adc6-130">See [Shadows](../modifiers/shadows.md).</span></span>

- `Async`

  <span data-ttu-id="7adc6-131">任意。</span><span class="sxs-lookup"><span data-stu-id="7adc6-131">Optional.</span></span> <span data-ttu-id="7adc6-132">「[Async](../modifiers/async.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7adc6-132">See [Async](../modifiers/async.md).</span></span>

- `name`

  <span data-ttu-id="7adc6-133">必須です。</span><span class="sxs-lookup"><span data-stu-id="7adc6-133">Required.</span></span> <span data-ttu-id="7adc6-134">プロシージャの名前。</span><span class="sxs-lookup"><span data-stu-id="7adc6-134">Name of the procedure.</span></span> <span data-ttu-id="7adc6-135">「 [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7adc6-135">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span> <span data-ttu-id="7adc6-136">クラスのコンストラクター プロシージャを作成するには、`Sub` プロシージャの名前を `New` キーワードに設定します。</span><span class="sxs-lookup"><span data-stu-id="7adc6-136">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="7adc6-137">詳細については、以下をご覧ください: [オブジェクトの有効期間: オブジェクトの作成と破棄](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)</span><span class="sxs-lookup"><span data-stu-id="7adc6-137">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>

- `typeparamlist`

  <span data-ttu-id="7adc6-138">任意。</span><span class="sxs-lookup"><span data-stu-id="7adc6-138">Optional.</span></span> <span data-ttu-id="7adc6-139">ジェネリック プロシージャの型パラメーターの一覧。</span><span class="sxs-lookup"><span data-stu-id="7adc6-139">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="7adc6-140">「[型リスト](type-list.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7adc6-140">See [Type List](type-list.md).</span></span>

- `parameterlist`

  <span data-ttu-id="7adc6-141">任意。</span><span class="sxs-lookup"><span data-stu-id="7adc6-141">Optional.</span></span> <span data-ttu-id="7adc6-142">このプロシージャのパラメーターを表すローカル変数名の一覧。</span><span class="sxs-lookup"><span data-stu-id="7adc6-142">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="7adc6-143">「[パラメーターの一覧](parameter-list.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7adc6-143">See [Parameter List](parameter-list.md).</span></span>

- `Implements`

  <span data-ttu-id="7adc6-144">任意。</span><span class="sxs-lookup"><span data-stu-id="7adc6-144">Optional.</span></span> <span data-ttu-id="7adc6-145">それぞれこのプロシージャの含まれているクラスまたは構造体によって実装されたインターフェイスに定義されている、1 つ以上の `Sub` プロシージャを、このプロシージャが実装することを示します。</span><span class="sxs-lookup"><span data-stu-id="7adc6-145">Indicates that this procedure implements one or more `Sub` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="7adc6-146">「[Implements ステートメント](implements-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7adc6-146">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="7adc6-147">`Implements` を指定する場合は、必ず指定します。</span><span class="sxs-lookup"><span data-stu-id="7adc6-147">Required if `Implements` is supplied.</span></span> <span data-ttu-id="7adc6-148">実装される `Sub` プロシージャのリストです。</span><span class="sxs-lookup"><span data-stu-id="7adc6-148">List of `Sub` procedures being implemented.</span></span>

  `implementedprocedure [ , implementedprocedure ... ]`

  <span data-ttu-id="7adc6-149">`implementedprocedure` の構文と指定項目は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7adc6-149">Each `implementedprocedure` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="7adc6-150">パーツ</span><span class="sxs-lookup"><span data-stu-id="7adc6-150">Part</span></span>|<span data-ttu-id="7adc6-151">説明</span><span class="sxs-lookup"><span data-stu-id="7adc6-151">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="7adc6-152">必須です。</span><span class="sxs-lookup"><span data-stu-id="7adc6-152">Required.</span></span> <span data-ttu-id="7adc6-153">このプロシージャの含まれているクラスまたは構造体によって実装されたインターフェイスの名前。</span><span class="sxs-lookup"><span data-stu-id="7adc6-153">Name of an interface implemented by this procedure's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="7adc6-154">必須です。</span><span class="sxs-lookup"><span data-stu-id="7adc6-154">Required.</span></span> <span data-ttu-id="7adc6-155">`interface` の中でプロシージャを定義するために使用する名前。</span><span class="sxs-lookup"><span data-stu-id="7adc6-155">Name by which the procedure is defined in `interface`.</span></span>|

- `Handles`

  <span data-ttu-id="7adc6-156">任意。</span><span class="sxs-lookup"><span data-stu-id="7adc6-156">Optional.</span></span> <span data-ttu-id="7adc6-157">このプロシージャで 1 つ以上の特定のイベントを処理できることを示します。</span><span class="sxs-lookup"><span data-stu-id="7adc6-157">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="7adc6-158">「[Handles](handles-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7adc6-158">See [Handles](handles-clause.md).</span></span>

- `eventlist`

  <span data-ttu-id="7adc6-159">`Handles` を指定する場合は、必ず指定します。</span><span class="sxs-lookup"><span data-stu-id="7adc6-159">Required if `Handles` is supplied.</span></span> <span data-ttu-id="7adc6-160">このプロシージャで処理するイベントの一覧。</span><span class="sxs-lookup"><span data-stu-id="7adc6-160">List of events this procedure handles.</span></span>

  `eventspecifier [ , eventspecifier ... ]`

  <span data-ttu-id="7adc6-161">`eventspecifier` の構文と指定項目は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7adc6-161">Each `eventspecifier` has the following syntax and parts:</span></span>

  `eventvariable.event`

  |<span data-ttu-id="7adc6-162">パーツ</span><span class="sxs-lookup"><span data-stu-id="7adc6-162">Part</span></span>|<span data-ttu-id="7adc6-163">説明</span><span class="sxs-lookup"><span data-stu-id="7adc6-163">Description</span></span>|
  |---|---|
  |`eventvariable`|<span data-ttu-id="7adc6-164">必須です。</span><span class="sxs-lookup"><span data-stu-id="7adc6-164">Required.</span></span> <span data-ttu-id="7adc6-165">イベントを発生させるクラスまたは構造体のデータ型で宣言されたオブジェクト変数。</span><span class="sxs-lookup"><span data-stu-id="7adc6-165">Object variable declared with the data type of the class or structure that raises the event.</span></span>|
  |`event`|<span data-ttu-id="7adc6-166">必須です。</span><span class="sxs-lookup"><span data-stu-id="7adc6-166">Required.</span></span> <span data-ttu-id="7adc6-167">このプロシージャで処理するイベントの名前。</span><span class="sxs-lookup"><span data-stu-id="7adc6-167">Name of the event this procedure handles.</span></span>|

- `statements`

  <span data-ttu-id="7adc6-168">任意。</span><span class="sxs-lookup"><span data-stu-id="7adc6-168">Optional.</span></span> <span data-ttu-id="7adc6-169">このプロシージャ内で実行するステートメントのブロック。</span><span class="sxs-lookup"><span data-stu-id="7adc6-169">Block of statements to run within this procedure.</span></span>

- `End Sub`

  <span data-ttu-id="7adc6-170">このプロシージャの定義を終了します。</span><span class="sxs-lookup"><span data-stu-id="7adc6-170">Terminates the definition of this procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="7adc6-171">Remarks</span><span class="sxs-lookup"><span data-stu-id="7adc6-171">Remarks</span></span>

<span data-ttu-id="7adc6-172">すべての実行可能コードは、プロシージャ内になければなりません。</span><span class="sxs-lookup"><span data-stu-id="7adc6-172">All executable code must be inside a procedure.</span></span> <span data-ttu-id="7adc6-173">呼び出し元のコードに値を返さない場合は、`Sub` プロシージャを使用します。</span><span class="sxs-lookup"><span data-stu-id="7adc6-173">Use a `Sub` procedure when you don't want to return a value to the calling code.</span></span> <span data-ttu-id="7adc6-174">値を返す場合は、`Function` プロシージャを使用します。</span><span class="sxs-lookup"><span data-stu-id="7adc6-174">Use a `Function` procedure when you want to return a value.</span></span>

## <a name="defining-a-sub-procedure"></a><span data-ttu-id="7adc6-175">Sub プロシージャの定義</span><span class="sxs-lookup"><span data-stu-id="7adc6-175">Defining a Sub Procedure</span></span>

<span data-ttu-id="7adc6-176">`Sub` プロシージャは、モジュール レベルでのみ定義できます。</span><span class="sxs-lookup"><span data-stu-id="7adc6-176">You can define a `Sub` procedure only at the module level.</span></span> <span data-ttu-id="7adc6-177">そのため、Sub プロシージャの宣言コンテキストはクラス、構造体、モジュール、インターフェイスにする必要があり、ソース ファイル、名前空間、プロシージャ、ブロックにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7adc6-177">The declaration context for a sub procedure must, therefore, be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="7adc6-178">詳細については、「[宣言コンテキストと既定のアクセス レベル](declaration-contexts-and-default-access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7adc6-178">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="7adc6-179">`Sub` プロシージャは、既定でパブリック アクセスに設定されます。</span><span class="sxs-lookup"><span data-stu-id="7adc6-179">`Sub` procedures default to public access.</span></span> <span data-ttu-id="7adc6-180">アクセス修飾子を使用してこれらのアクセス レベルを調整できます。</span><span class="sxs-lookup"><span data-stu-id="7adc6-180">You can adjust their access levels by using the access modifiers.</span></span>

<span data-ttu-id="7adc6-181">プロシージャで `Implements` キーワードが使用されている場合、含まれているクラスまたは構造体には、その `Class` または `Structure` ステートメントの直後に `Implements` ステートメントが必要です。</span><span class="sxs-lookup"><span data-stu-id="7adc6-181">If the procedure uses the `Implements` keyword, the containing class or structure must have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="7adc6-182">`Implements` ステートメントには、`implementslist` で指定された各インターフェイスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="7adc6-182">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="7adc6-183">ただし、インターフェイスで `Sub` を定義するときに使用する名前 (`definedname`) は、このプロシージャの名前 (`name`) に一致している必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7adc6-183">However, the name by which an interface defines the `Sub` (in `definedname`) doesn't have to match the name of this procedure (in `name`).</span></span>

## <a name="returning-from-a-sub-procedure"></a><span data-ttu-id="7adc6-184">Sub プロシージャからの復帰</span><span class="sxs-lookup"><span data-stu-id="7adc6-184">Returning from a Sub Procedure</span></span>

<span data-ttu-id="7adc6-185">`Sub` プロシージャから呼び出し元のコードに返されると、実行は、それを呼び出したステートメントの後のステートメントから続行されます。</span><span class="sxs-lookup"><span data-stu-id="7adc6-185">When a `Sub` procedure returns to the calling code, execution continues with the statement after the statement that called it.</span></span>

<span data-ttu-id="7adc6-186">次の例は、`Sub` プロシージャからの戻り値を示しています。</span><span class="sxs-lookup"><span data-stu-id="7adc6-186">The following example shows a return from a `Sub` procedure.</span></span>

```vb
Sub mySub(ByVal q As String)
    Return
End Sub
```

<span data-ttu-id="7adc6-187">`Exit Sub` および `Return` ステートメントでは、`Sub` プロシージャがすぐに終了します。</span><span class="sxs-lookup"><span data-stu-id="7adc6-187">The `Exit Sub` and `Return` statements cause an immediate exit from a `Sub` procedure.</span></span> <span data-ttu-id="7adc6-188">任意の数の `Exit Sub` および `Return` ステートメントをプロシージャ内の任意の場所に記述でき、`Exit Sub` ステートメントと `Return` ステートメントを混在させることができます。</span><span class="sxs-lookup"><span data-stu-id="7adc6-188">Any number of `Exit Sub` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Sub` and `Return` statements.</span></span>

## <a name="calling-a-sub-procedure"></a><span data-ttu-id="7adc6-189">Sub プロシージャの呼び出し</span><span class="sxs-lookup"><span data-stu-id="7adc6-189">Calling a Sub Procedure</span></span>

<span data-ttu-id="7adc6-190">`Sub` プロシージャを呼び出すには、ステートメントでプロシージャ名を使用し、その名前の後にかっこで囲んだ引数リストを指定します。</span><span class="sxs-lookup"><span data-stu-id="7adc6-190">You call a `Sub` procedure by using the procedure name in a statement and then following that name with its argument list in parentheses.</span></span> <span data-ttu-id="7adc6-191">引数を指定しない場合のみ、かっこを省略できます。</span><span class="sxs-lookup"><span data-stu-id="7adc6-191">You can omit the parentheses only if you don't supply any arguments.</span></span> <span data-ttu-id="7adc6-192">ただし、常にかっこを含めると、コードが読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="7adc6-192">However, your code is more readable if you always include the parentheses.</span></span>

<span data-ttu-id="7adc6-193">`Sub` プロシージャと `Function` プロシージャは、パラメーターを持つことができ、一連のステートメントを実行できます。</span><span class="sxs-lookup"><span data-stu-id="7adc6-193">A `Sub` procedure and a `Function` procedure  can have parameters and perform a series of statements.</span></span> <span data-ttu-id="7adc6-194">ただし、`Function` プロシージャは値を返し、`Sub` プロシージャは返しません。</span><span class="sxs-lookup"><span data-stu-id="7adc6-194">However, a `Function` procedure returns a value, and a `Sub` procedure doesn't.</span></span> <span data-ttu-id="7adc6-195">そのため、式の中で `Sub` プロシージャを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="7adc6-195">Therefore, you can't use a `Sub` procedure in an expression.</span></span>

<span data-ttu-id="7adc6-196">`Sub` プロシージャを呼び出すときに `Call` キーワードを使用できますが、ほとんどの用途で、そのキーワードは推奨されません。</span><span class="sxs-lookup"><span data-stu-id="7adc6-196">You can use the `Call` keyword when you call a `Sub` procedure, but that keyword isn't recommended for most uses.</span></span> <span data-ttu-id="7adc6-197">詳細については、「[Call ステートメント](call-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7adc6-197">For more information, see [Call Statement](call-statement.md).</span></span>

<span data-ttu-id="7adc6-198">Visual Basic では、内部効率を高めるために算術式が再配置されることがあります。</span><span class="sxs-lookup"><span data-stu-id="7adc6-198">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="7adc6-199">そのため、引数リストに他のプロシージャを呼び出す式が含まれている場合は、それらの式が特定の順序で呼び出されることを前提としないでください。</span><span class="sxs-lookup"><span data-stu-id="7adc6-199">For that reason, if your argument list includes expressions that call other procedures, you shouldn't assume that those expressions will be called in a particular order.</span></span>

## <a name="async-sub-procedures"></a><span data-ttu-id="7adc6-200">Async Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="7adc6-200">Async Sub Procedures</span></span>

<span data-ttu-id="7adc6-201">Async 機能を使用することによって、明示的なコールバックを使用せずに、または複数のメソッドやラムダ式にわたって手動でコードを分割することなく、非同期関数を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="7adc6-201">By using the Async feature, you can invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>

<span data-ttu-id="7adc6-202">プロシージャに [Async](../modifiers/async.md) 修飾子を付けると、そのプロシージャで [Await](../operators/await-operator.md) 演算子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7adc6-202">If you mark a procedure with the [Async](../modifiers/async.md) modifier, you can use the [Await](../operators/await-operator.md) operator in the procedure.</span></span> <span data-ttu-id="7adc6-203">制御が `Async` プロシージャの `Await` 式に到達すると、制御が呼び出し元に戻り、待機中のタスクが完了するまでプロシージャの進行が中断されます。</span><span class="sxs-lookup"><span data-stu-id="7adc6-203">When control reaches an `Await` expression in the `Async` procedure, control returns to the caller, and progress in the procedure is suspended until the awaited task completes.</span></span> <span data-ttu-id="7adc6-204">タスクが完了すると、プロシージャで実行を再開できます。</span><span class="sxs-lookup"><span data-stu-id="7adc6-204">When the task is complete, execution can resume in the procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="7adc6-205">`Async` プロシージャは、まだ完了していない待機中の最初のオブジェクトが検出されるか、または `Async` プロシージャの最後に達するか、どちらか先に発生したときに、呼び出し元に戻ります。</span><span class="sxs-lookup"><span data-stu-id="7adc6-205">An `Async` procedure returns to the caller when either the first awaited object that’s not yet complete is encountered or the end of the `Async` procedure is reached, whichever occurs first.</span></span>

<span data-ttu-id="7adc6-206">また、`Async` 修飾子で、[Function ステートメント](function-statement.md)をマークすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7adc6-206">You can also mark a [Function Statement](function-statement.md) with the `Async` modifier.</span></span> <span data-ttu-id="7adc6-207">`Async` 関数の戻り値の型には、<xref:System.Threading.Tasks.Task%601> または <xref:System.Threading.Tasks.Task> を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7adc6-207">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="7adc6-208">このトピックの後述の例では、<xref:System.Threading.Tasks.Task%601> の戻り値の型を持つ `Async` 関数を示します。</span><span class="sxs-lookup"><span data-stu-id="7adc6-208">An example later in this topic shows an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span>

<span data-ttu-id="7adc6-209">`Async` `Sub` プロシージャは、主にイベント ハンドラーで使用し、その場合、値を返すことはできません。</span><span class="sxs-lookup"><span data-stu-id="7adc6-209">`Async` `Sub` procedures are primarily used for event handlers, where a value can't be returned.</span></span> <span data-ttu-id="7adc6-210">`Async` `Sub` プロシージャは待機できず、`Async` `Sub` プロシージャの呼び出し元では、`Sub` プロシージャがスローする例外をキャッチできません。</span><span class="sxs-lookup"><span data-stu-id="7adc6-210">An `Async` `Sub` procedure can't be awaited, and the caller of an `Async` `Sub` procedure can't catch exceptions that the `Sub` procedure throws.</span></span>

<span data-ttu-id="7adc6-211">`Async` プロシージャでは、[ByRef](../modifiers/byref.md) パラメーターを宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="7adc6-211">An `Async` procedure can't declare any [ByRef](../modifiers/byref.md) parameters.</span></span>

<span data-ttu-id="7adc6-212">`Async` プロシージャの詳細については、「[Async および Await を使用した非同期プログラミング](../../programming-guide/concepts/async/index.md)」、「[非同期プログラムにおける制御フロー](../../programming-guide/concepts/async/control-flow-in-async-programs.md)」、「[非同期の戻り値の型](../../programming-guide/concepts/async/async-return-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7adc6-212">For more information about `Async` procedures, see [Asynchronous Programming with Async and Await](../../programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../programming-guide/concepts/async/async-return-types.md).</span></span>

## <a name="example"></a><span data-ttu-id="7adc6-213">例</span><span class="sxs-lookup"><span data-stu-id="7adc6-213">Example</span></span>

<span data-ttu-id="7adc6-214">次の例では、`Sub` ステートメントを使用して、`Sub` プロシージャの本体を形成する名前、パラメーター、およびコードを定義しています。</span><span class="sxs-lookup"><span data-stu-id="7adc6-214">The following example uses the `Sub` statement to define the name, parameters, and code that form the body of a `Sub` procedure.</span></span>

[!code-vb[VbVbalrStatements#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#58)]

## <a name="example"></a><span data-ttu-id="7adc6-215">例</span><span class="sxs-lookup"><span data-stu-id="7adc6-215">Example</span></span>

<span data-ttu-id="7adc6-216">次の例で、`DelayAsync` は、戻り値の型が <xref:System.Threading.Tasks.Task%601> である `Async` `Function` です。</span><span class="sxs-lookup"><span data-stu-id="7adc6-216">In the following example, `DelayAsync` is an `Async` `Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="7adc6-217">`DelayAsync` には、整数を返す `Return` ステートメントがあります。</span><span class="sxs-lookup"><span data-stu-id="7adc6-217">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="7adc6-218">そのため、`DelayAsync` の関数宣言では、戻り値の型を `Task(Of Integer)` とする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7adc6-218">Therefore, the function declaration of `DelayAsync` must have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="7adc6-219">戻り値の型が `Task(Of Integer)` であるため、ステートメント `Dim result As Integer = Await delayTask` に示すように、`DoSomethingAsync` 内の `Await` 式を評価すると、整数が生成されます。</span><span class="sxs-lookup"><span data-stu-id="7adc6-219">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer, as the following statement shows: `Dim result As Integer = Await delayTask`.</span></span>

<span data-ttu-id="7adc6-220">`startButton_Click` プロシージャは、`Async Sub` プロシージャの一例です。</span><span class="sxs-lookup"><span data-stu-id="7adc6-220">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="7adc6-221">`DoSomethingAsync` が `Async` 関数であるため、ステートメント `Await DoSomethingAsync()` に示すように、`DoSomethingAsync` を呼び出すタスクは、待機させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7adc6-221">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement shows: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="7adc6-222">`startButton_Click` `Sub` プロシージャは、`Await` 式を使用しているため、`Async` 修飾子を使用して定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7adc6-222">The `startButton_Click` `Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="7adc6-223">関連項目</span><span class="sxs-lookup"><span data-stu-id="7adc6-223">See also</span></span>

- [<span data-ttu-id="7adc6-224">Implements ステートメント</span><span class="sxs-lookup"><span data-stu-id="7adc6-224">Implements Statement</span></span>](implements-statement.md)
- [<span data-ttu-id="7adc6-225">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="7adc6-225">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="7adc6-226">パラメーター リスト</span><span class="sxs-lookup"><span data-stu-id="7adc6-226">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="7adc6-227">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="7adc6-227">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="7adc6-228">Call ステートメント</span><span class="sxs-lookup"><span data-stu-id="7adc6-228">Call Statement</span></span>](call-statement.md)
- [<span data-ttu-id="7adc6-229">Of</span><span class="sxs-lookup"><span data-stu-id="7adc6-229">Of</span></span>](of-clause.md)
- [<span data-ttu-id="7adc6-230">パラメーター配列</span><span class="sxs-lookup"><span data-stu-id="7adc6-230">Parameter Arrays</span></span>](../../programming-guide/language-features/procedures/parameter-arrays.md)
- [<span data-ttu-id="7adc6-231">方法: ジェネリック クラスを使用する</span><span class="sxs-lookup"><span data-stu-id="7adc6-231">How to: Use a Generic Class</span></span>](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="7adc6-232">プロシージャのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="7adc6-232">Troubleshooting Procedures</span></span>](../../programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [<span data-ttu-id="7adc6-233">部分メソッド</span><span class="sxs-lookup"><span data-stu-id="7adc6-233">Partial Methods</span></span>](../../programming-guide/language-features/procedures/partial-methods.md)
