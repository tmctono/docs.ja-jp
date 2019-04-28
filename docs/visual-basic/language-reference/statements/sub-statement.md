---
title: Sub ステートメント (Visual Basic)
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
ms.openlocfilehash: ab94865f4881b40b38f67eb40d2f9fa2e1982af8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783839"
---
# <a name="sub-statement-visual-basic"></a><span data-ttu-id="75963-102">Sub ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75963-102">Sub Statement (Visual Basic)</span></span>

<span data-ttu-id="75963-103">宣言名、パラメーター、および定義するコードを`Sub`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="75963-103">Declares the name, parameters, and code that define a `Sub` procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="75963-104">構文</span><span class="sxs-lookup"><span data-stu-id="75963-104">Syntax</span></span>

```
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Sub ]
    [ statements ]
End Sub
```

## <a name="parts"></a><span data-ttu-id="75963-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="75963-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="75963-106">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="75963-106">Optional.</span></span> <span data-ttu-id="75963-107">参照してください[属性リスト](attribute-list.md)します。</span><span class="sxs-lookup"><span data-stu-id="75963-107">See [Attribute List](attribute-list.md).</span></span>

- `Partial`

  <span data-ttu-id="75963-108">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="75963-108">Optional.</span></span> <span data-ttu-id="75963-109">部分メソッドの定義を示します。</span><span class="sxs-lookup"><span data-stu-id="75963-109">Indicates definition of a partial method.</span></span> <span data-ttu-id="75963-110">参照してください[部分メソッド](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)します。</span><span class="sxs-lookup"><span data-stu-id="75963-110">See [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span></span>

- `accessmodifier`

  <span data-ttu-id="75963-111">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="75963-111">Optional.</span></span> <span data-ttu-id="75963-112">次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="75963-112">Can be one of the following:</span></span>

  - [<span data-ttu-id="75963-113">Public</span><span class="sxs-lookup"><span data-stu-id="75963-113">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="75963-114">Protected</span><span class="sxs-lookup"><span data-stu-id="75963-114">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="75963-115">Friend</span><span class="sxs-lookup"><span data-stu-id="75963-115">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="75963-116">Private</span><span class="sxs-lookup"><span data-stu-id="75963-116">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="75963-117">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="75963-117">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

  - [<span data-ttu-id="75963-118">Private Protected</span><span class="sxs-lookup"><span data-stu-id="75963-118">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

  <span data-ttu-id="75963-119">「 [Visual Basic でのアクセス レベル](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75963-119">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `proceduremodifiers`

  <span data-ttu-id="75963-120">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="75963-120">Optional.</span></span> <span data-ttu-id="75963-121">次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="75963-121">Can be one of the following:</span></span>

  - [<span data-ttu-id="75963-122">Overloads</span><span class="sxs-lookup"><span data-stu-id="75963-122">Overloads</span></span>](../modifiers/overloads.md)

  - [<span data-ttu-id="75963-123">Overrides</span><span class="sxs-lookup"><span data-stu-id="75963-123">Overrides</span></span>](../modifiers/overrides.md)

  - [<span data-ttu-id="75963-124">Overridable</span><span class="sxs-lookup"><span data-stu-id="75963-124">Overridable</span></span>](../modifiers/overridable.md)

  - [<span data-ttu-id="75963-125">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="75963-125">NotOverridable</span></span>](../modifiers/notoverridable.md)

  - [<span data-ttu-id="75963-126">MustOverride</span><span class="sxs-lookup"><span data-stu-id="75963-126">MustOverride</span></span>](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="75963-127">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="75963-127">Optional.</span></span> <span data-ttu-id="75963-128">参照してください[共有](../modifiers/shared.md)します。</span><span class="sxs-lookup"><span data-stu-id="75963-128">See [Shared](../modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="75963-129">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="75963-129">Optional.</span></span> <span data-ttu-id="75963-130">参照してください[Shadows](../modifiers/shadows.md)します。</span><span class="sxs-lookup"><span data-stu-id="75963-130">See [Shadows](../modifiers/shadows.md).</span></span>

- `Async`

  <span data-ttu-id="75963-131">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="75963-131">Optional.</span></span> <span data-ttu-id="75963-132">参照してください[Async](../modifiers/async.md)します。</span><span class="sxs-lookup"><span data-stu-id="75963-132">See [Async](../modifiers/async.md).</span></span>

- `name`

  <span data-ttu-id="75963-133">必須。</span><span class="sxs-lookup"><span data-stu-id="75963-133">Required.</span></span> <span data-ttu-id="75963-134">プロシージャの名前。</span><span class="sxs-lookup"><span data-stu-id="75963-134">Name of the procedure.</span></span> <span data-ttu-id="75963-135">「 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75963-135">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span> <span data-ttu-id="75963-136">クラスのコンス トラクターのプロシージャを作成するには、設定の名前、`Sub`する手順、`New`キーワード。</span><span class="sxs-lookup"><span data-stu-id="75963-136">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="75963-137">詳細については、次を参照してください。[オブジェクトの有効期間。オブジェクトの作成し、破棄方法](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)します。</span><span class="sxs-lookup"><span data-stu-id="75963-137">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>

- `typeparamlist`

  <span data-ttu-id="75963-138">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="75963-138">Optional.</span></span> <span data-ttu-id="75963-139">ジェネリック プロシージャの型パラメーターの一覧。</span><span class="sxs-lookup"><span data-stu-id="75963-139">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="75963-140">参照してください[一覧を入力する](type-list.md)します。</span><span class="sxs-lookup"><span data-stu-id="75963-140">See [Type List](type-list.md).</span></span>

- `parameterlist`

  <span data-ttu-id="75963-141">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="75963-141">Optional.</span></span> <span data-ttu-id="75963-142">このプロシージャのパラメーターを表すローカル変数名の一覧。</span><span class="sxs-lookup"><span data-stu-id="75963-142">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="75963-143">参照してください[パラメーター リスト](parameter-list.md)します。</span><span class="sxs-lookup"><span data-stu-id="75963-143">See [Parameter List](parameter-list.md).</span></span>

- `Implements`

  <span data-ttu-id="75963-144">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="75963-144">Optional.</span></span> <span data-ttu-id="75963-145">この手順が 1 つまたは複数を実装することを示します`Sub`手順、この手順の包含クラスまたは構造体によって実装されるインターフェイスで定義されている 1 つずつです。</span><span class="sxs-lookup"><span data-stu-id="75963-145">Indicates that this procedure implements one or more `Sub` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="75963-146">参照してください[ステートメントを実装](implements-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="75963-146">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="75963-147">`Implements` を指定する場合は、必ず指定します。</span><span class="sxs-lookup"><span data-stu-id="75963-147">Required if `Implements` is supplied.</span></span> <span data-ttu-id="75963-148">実装される `Sub` プロシージャのリストです。</span><span class="sxs-lookup"><span data-stu-id="75963-148">List of `Sub` procedures being implemented.</span></span>

  `implementedprocedure [ , implementedprocedure ... ]`

  <span data-ttu-id="75963-149">`implementedprocedure` の構文と指定項目は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="75963-149">Each `implementedprocedure` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="75963-150">パーツ</span><span class="sxs-lookup"><span data-stu-id="75963-150">Part</span></span>|<span data-ttu-id="75963-151">説明</span><span class="sxs-lookup"><span data-stu-id="75963-151">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="75963-152">必須。</span><span class="sxs-lookup"><span data-stu-id="75963-152">Required.</span></span> <span data-ttu-id="75963-153">このプロシージャによって実装されるインターフェイスの名前を含むクラスまたは構造体。</span><span class="sxs-lookup"><span data-stu-id="75963-153">Name of an interface implemented by this procedure's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="75963-154">必須。</span><span class="sxs-lookup"><span data-stu-id="75963-154">Required.</span></span> <span data-ttu-id="75963-155">`interface` の中でプロシージャを定義するために使用する名前。</span><span class="sxs-lookup"><span data-stu-id="75963-155">Name by which the procedure is defined in `interface`.</span></span>|

- `Handles`

  <span data-ttu-id="75963-156">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="75963-156">Optional.</span></span> <span data-ttu-id="75963-157">この手順が 1 つまたは複数の特定のイベントを処理できることを示します。</span><span class="sxs-lookup"><span data-stu-id="75963-157">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="75963-158">参照してください[処理](handles-clause.md)します。</span><span class="sxs-lookup"><span data-stu-id="75963-158">See [Handles](handles-clause.md).</span></span>

- `eventlist`

  <span data-ttu-id="75963-159">`Handles` を指定する場合は、必ず指定します。</span><span class="sxs-lookup"><span data-stu-id="75963-159">Required if `Handles` is supplied.</span></span> <span data-ttu-id="75963-160">このプロシージャを処理するイベントの一覧です。</span><span class="sxs-lookup"><span data-stu-id="75963-160">List of events this procedure handles.</span></span>

  `eventspecifier [ , eventspecifier ... ]`

  <span data-ttu-id="75963-161">`eventspecifier` の構文と指定項目は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="75963-161">Each `eventspecifier` has the following syntax and parts:</span></span>

  `eventvariable.event`

  |<span data-ttu-id="75963-162">パーツ</span><span class="sxs-lookup"><span data-stu-id="75963-162">Part</span></span>|<span data-ttu-id="75963-163">説明</span><span class="sxs-lookup"><span data-stu-id="75963-163">Description</span></span>|
  |---|---|
  |`eventvariable`|<span data-ttu-id="75963-164">必須。</span><span class="sxs-lookup"><span data-stu-id="75963-164">Required.</span></span> <span data-ttu-id="75963-165">オブジェクト変数がクラスまたはイベントを発生させる構造体のデータ型で宣言されています。</span><span class="sxs-lookup"><span data-stu-id="75963-165">Object variable declared with the data type of the class or structure that raises the event.</span></span>|
  |`event`|<span data-ttu-id="75963-166">必須。</span><span class="sxs-lookup"><span data-stu-id="75963-166">Required.</span></span> <span data-ttu-id="75963-167">このプロシージャを処理するイベントの名前。</span><span class="sxs-lookup"><span data-stu-id="75963-167">Name of the event this procedure handles.</span></span>|

- `statements`

  <span data-ttu-id="75963-168">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="75963-168">Optional.</span></span> <span data-ttu-id="75963-169">このプロシージャ内で実行するステートメントのブロック。</span><span class="sxs-lookup"><span data-stu-id="75963-169">Block of statements to run within this procedure.</span></span>

- `End Sub`

  <span data-ttu-id="75963-170">このプロシージャの定義を終了します。</span><span class="sxs-lookup"><span data-stu-id="75963-170">Terminates the definition of this procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="75963-171">Remarks</span><span class="sxs-lookup"><span data-stu-id="75963-171">Remarks</span></span>

<span data-ttu-id="75963-172">プロシージャ内にあるすべての実行可能コードがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="75963-172">All executable code must be inside a procedure.</span></span> <span data-ttu-id="75963-173">使用して、`Sub`呼び出し元のコードに値を返すしたくない場合、プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="75963-173">Use a `Sub` procedure when you don't want to return a value to the calling code.</span></span> <span data-ttu-id="75963-174">使用して、`Function`値を取得する場合のプロシージャです。</span><span class="sxs-lookup"><span data-stu-id="75963-174">Use a `Function` procedure when you want to return a value.</span></span>

## <a name="defining-a-sub-procedure"></a><span data-ttu-id="75963-175">Sub プロシージャの定義</span><span class="sxs-lookup"><span data-stu-id="75963-175">Defining a Sub Procedure</span></span>

<span data-ttu-id="75963-176">定義することができます、`Sub`モジュール レベルでのみプロシージャ。</span><span class="sxs-lookup"><span data-stu-id="75963-176">You can define a `Sub` procedure only at the module level.</span></span> <span data-ttu-id="75963-177">Sub プロシージャの宣言のコンテキストでは、クラス、構造体、モジュールの場合、またはインターフェイスにする必要があります、そのため、およびソース ファイル、名前空間、プロシージャ、またはブロックすることはできません。</span><span class="sxs-lookup"><span data-stu-id="75963-177">The declaration context for a sub procedure must, therefore, be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="75963-178">詳細については、「[宣言コンテキストと既定のアクセス レベル](declaration-contexts-and-default-access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75963-178">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="75963-179">`Sub` パブリック アクセスに既定のプロシージャ。</span><span class="sxs-lookup"><span data-stu-id="75963-179">`Sub` procedures default to public access.</span></span> <span data-ttu-id="75963-180">アクセス修飾子を使用して、そのアクセス レベルを調整できます。</span><span class="sxs-lookup"><span data-stu-id="75963-180">You can adjust their access levels by using the access modifiers.</span></span>

<span data-ttu-id="75963-181">プロシージャで使用する場合、`Implements`キーワードを含むクラスまたは構造体があります、`Implements`直後に続くステートメント、`Class`または`Structure`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="75963-181">If the procedure uses the `Implements` keyword, the containing class or structure must have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="75963-182">`Implements`ステートメントで指定されている各インターフェイスを含める必要があります`implementslist`します。</span><span class="sxs-lookup"><span data-stu-id="75963-182">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="75963-183">ただし、インターフェイスを定義する名前、 `Sub` (で`definedname`) この手順の名前と一致する必要はありません (で`name`)。</span><span class="sxs-lookup"><span data-stu-id="75963-183">However, the name by which an interface defines the `Sub` (in `definedname`) doesn't have to match the name of this procedure (in `name`).</span></span>

## <a name="returning-from-a-sub-procedure"></a><span data-ttu-id="75963-184">Sub プロシージャから戻る</span><span class="sxs-lookup"><span data-stu-id="75963-184">Returning from a Sub Procedure</span></span>

<span data-ttu-id="75963-185">ときに、`Sub`ステートメントを呼び出した後のステートメントと、プロシージャは、呼び出し元のコードに返す、実行が継続します。</span><span class="sxs-lookup"><span data-stu-id="75963-185">When a `Sub` procedure returns to the calling code, execution continues with the statement after the statement that called it.</span></span>

<span data-ttu-id="75963-186">次の例からの戻り値を示しています、`Sub`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="75963-186">The following example shows a return from a `Sub` procedure.</span></span>

```vb
Sub mySub(ByVal q As String)
    Return
End Sub
```

<span data-ttu-id="75963-187">`Exit Sub`と`Return`ステートメントからすぐに終了が発生する、`Sub`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="75963-187">The `Exit Sub` and `Return` statements cause an immediate exit from a `Sub` procedure.</span></span> <span data-ttu-id="75963-188">任意の数の`Exit Sub`と`Return`ステートメントは、手順では、どこでも表示でき、組み合わせることができます`Exit Sub`と`Return`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="75963-188">Any number of `Exit Sub` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Sub` and `Return` statements.</span></span>

## <a name="calling-a-sub-procedure"></a><span data-ttu-id="75963-189">Sub プロシージャの呼び出し</span><span class="sxs-lookup"><span data-stu-id="75963-189">Calling a Sub Procedure</span></span>

<span data-ttu-id="75963-190">呼び出す、`Sub`ステートメントでは、プロシージャ名を使用し、その引数リストをかっこで使用してその名前でプロシージャ。</span><span class="sxs-lookup"><span data-stu-id="75963-190">You call a `Sub` procedure by using the procedure name in a statement and then following that name with its argument list in parentheses.</span></span> <span data-ttu-id="75963-191">引数を指定しない場合にのみかっこを省略することができます。</span><span class="sxs-lookup"><span data-stu-id="75963-191">You can omit the parentheses only if you don't supply any arguments.</span></span> <span data-ttu-id="75963-192">ただし、コードが常にかっこが含まれる場合より読みやすいです。</span><span class="sxs-lookup"><span data-stu-id="75963-192">However, your code is more readable if you always include the parentheses.</span></span>

<span data-ttu-id="75963-193">A`Sub`プロシージャと`Function`プロシージャがパラメーターを指定して、一連のステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="75963-193">A `Sub` procedure and a `Function` procedure  can have parameters and perform a series of statements.</span></span> <span data-ttu-id="75963-194">ただし、`Function`値、およびプロシージャを返します。`Sub`プロシージャがありません。</span><span class="sxs-lookup"><span data-stu-id="75963-194">However, a `Function` procedure returns a value, and a `Sub` procedure doesn't.</span></span> <span data-ttu-id="75963-195">そのため、使用することはできません、`Sub`式の中でプロシージャ。</span><span class="sxs-lookup"><span data-stu-id="75963-195">Therefore, you can't use a `Sub` procedure in an expression.</span></span>

<span data-ttu-id="75963-196">使用することができます、`Call`を呼び出すときに、キーワード、`Sub`プロシージャが、そのキーワードが、ほとんどの用途についてはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="75963-196">You can use the `Call` keyword when you call a `Sub` procedure, but that keyword isn't recommended for most uses.</span></span> <span data-ttu-id="75963-197">詳細については、次を参照してください。 [Call ステートメント](call-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="75963-197">For more information, see [Call Statement](call-statement.md).</span></span>

<span data-ttu-id="75963-198">Visual Basic では、算術式内部の効率を向上させることがあります再配置します。</span><span class="sxs-lookup"><span data-stu-id="75963-198">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="75963-199">そのため、引数リストには、他のプロシージャを呼び出す式が含まれている場合とは考えないでくださいの式が特定の順序で呼び出されることです。</span><span class="sxs-lookup"><span data-stu-id="75963-199">For that reason, if your argument list includes expressions that call other procedures, you shouldn't assume that those expressions will be called in a particular order.</span></span>

## <a name="async-sub-procedures"></a><span data-ttu-id="75963-200">Async Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="75963-200">Async Sub Procedures</span></span>

<span data-ttu-id="75963-201">非同期機能を使用すると、明示的なコールバックの使用や複数の関数またはラムダ式、コードを手動で分割することがなく非同期関数を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="75963-201">By using the Async feature, you can invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>

<span data-ttu-id="75963-202">プロシージャを設定する場合、 [Async](../modifiers/async.md)修飾子を使用できます、 [Await](../../../visual-basic/language-reference/operators/await-operator.md)プロシージャ内の演算子。</span><span class="sxs-lookup"><span data-stu-id="75963-202">If you mark a procedure with the [Async](../modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the procedure.</span></span> <span data-ttu-id="75963-203">コントロールに達すると、`Await`内の式、`Async`プロシージャは、呼び出し元に制御が戻ります、待機中のタスクが完了するまでの手順で進行状況が中断されます。</span><span class="sxs-lookup"><span data-stu-id="75963-203">When control reaches an `Await` expression in the `Async` procedure, control returns to the caller, and progress in the procedure is suspended until the awaited task completes.</span></span> <span data-ttu-id="75963-204">タスクが完了したら、プロシージャの実行を再開できます。</span><span class="sxs-lookup"><span data-stu-id="75963-204">When the task is complete, execution can resume in the procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="75963-205">`Async`プロシージャ行末またはか最初待機中のオブジェクトはまだ完了が発生した場合、呼び出し元に返す、`Async`プロシージャに達すると、どちらが最初に発生します。</span><span class="sxs-lookup"><span data-stu-id="75963-205">An `Async` procedure returns to the caller when either the first awaited object that’s not yet complete is encountered or the end of the `Async` procedure is reached, whichever occurs first.</span></span>

<span data-ttu-id="75963-206">マークすることも、[関数ステートメント](function-statement.md)で、`Async`修飾子。</span><span class="sxs-lookup"><span data-stu-id="75963-206">You can also mark a [Function Statement](function-statement.md) with the `Async` modifier.</span></span> <span data-ttu-id="75963-207">`Async`関数の戻り値の型を持つことができます<xref:System.Threading.Tasks.Task%601>または<xref:System.Threading.Tasks.Task>します。</span><span class="sxs-lookup"><span data-stu-id="75963-207">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="75963-208">たとえば後でこのトピックでは、`Async`関数の戻り値の型を持つ<xref:System.Threading.Tasks.Task%601>します。</span><span class="sxs-lookup"><span data-stu-id="75963-208">An example later in this topic shows an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span>

<span data-ttu-id="75963-209">`Async` `Sub` プロシージャは、主に、値を返すことができない、イベント ハンドラーを使用します。</span><span class="sxs-lookup"><span data-stu-id="75963-209">`Async` `Sub` procedures are primarily used for event handlers, where a value can't be returned.</span></span> <span data-ttu-id="75963-210">`Async` `Sub`プロシージャを待機できません、呼び出し元の`Async``Sub`プロシージャは、例外をキャッチできませんが、`Sub`プロシージャがスローされます。</span><span class="sxs-lookup"><span data-stu-id="75963-210">An `Async` `Sub` procedure can't be awaited, and the caller of an `Async` `Sub` procedure can't catch exceptions that the `Sub` procedure throws.</span></span>

<span data-ttu-id="75963-211">`Async`プロシージャは、いずれかを宣言できません[ByRef](../modifiers/byref.md)パラメーター。</span><span class="sxs-lookup"><span data-stu-id="75963-211">An `Async` procedure can't declare any [ByRef](../modifiers/byref.md) parameters.</span></span>

<span data-ttu-id="75963-212">詳細については`Async`手順についてを参照してください[Async および Await を使用した非同期プログラミング](../../../visual-basic/programming-guide/concepts/async/index.md)、[非同期プログラムにおける制御フロー](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)、および[Async 戻り値の型](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="75963-212">For more information about `Async` procedures, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>

## <a name="example"></a><span data-ttu-id="75963-213">例</span><span class="sxs-lookup"><span data-stu-id="75963-213">Example</span></span>

<span data-ttu-id="75963-214">次の例では、`Sub`名、パラメーター、およびの本体を形成するコードを定義するステートメントを`Sub`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="75963-214">The following example uses the `Sub` statement to define the name, parameters, and code that form the body of a `Sub` procedure.</span></span>

[!code-vb[VbVbalrStatements#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#58)]

## <a name="example"></a><span data-ttu-id="75963-215">例</span><span class="sxs-lookup"><span data-stu-id="75963-215">Example</span></span>

<span data-ttu-id="75963-216">次の例では、`DelayAsync`は、 `Async` `Function`の戻り値の型を持つ<xref:System.Threading.Tasks.Task%601>します。</span><span class="sxs-lookup"><span data-stu-id="75963-216">In the following example, `DelayAsync` is an `Async` `Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="75963-217">`DelayAsync` には、整数を返す `Return` ステートメントがあります。</span><span class="sxs-lookup"><span data-stu-id="75963-217">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="75963-218">したがって、関数宣言の`DelayAsync`の戻り値の型があります。`Task(Of Integer)`します。</span><span class="sxs-lookup"><span data-stu-id="75963-218">Therefore, the function declaration of `DelayAsync` must have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="75963-219">戻り値の型である`Task(Of Integer)`の評価、`Await`式`DoSomethingAsync`として次のステートメントに示す、整数が生成されます:`Dim result As Integer = Await delayTask`します。</span><span class="sxs-lookup"><span data-stu-id="75963-219">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer, as the following statement shows: `Dim result As Integer = Await delayTask`.</span></span>

<span data-ttu-id="75963-220">`startButton_Click`プロシージャの例に示します、`Async Sub`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="75963-220">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="75963-221">`DoSomethingAsync`は、`Async`関数では、タスクへの呼び出しを`DoSomethingAsync`として次のステートメントの表示を待機する必要があります:`Await DoSomethingAsync()`します。</span><span class="sxs-lookup"><span data-stu-id="75963-221">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement shows: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="75963-222">`startButton_Click` `Sub`でプロシージャを定義する必要があります、`Async`修飾子があるため、`Await`式。</span><span class="sxs-lookup"><span data-stu-id="75963-222">The `startButton_Click` `Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="75963-223">関連項目</span><span class="sxs-lookup"><span data-stu-id="75963-223">See also</span></span>

- [<span data-ttu-id="75963-224">Implements ステートメント</span><span class="sxs-lookup"><span data-stu-id="75963-224">Implements Statement</span></span>](implements-statement.md)
- [<span data-ttu-id="75963-225">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="75963-225">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="75963-226">パラメーター リスト</span><span class="sxs-lookup"><span data-stu-id="75963-226">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="75963-227">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="75963-227">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="75963-228">Call ステートメント</span><span class="sxs-lookup"><span data-stu-id="75963-228">Call Statement</span></span>](call-statement.md)
- [<span data-ttu-id="75963-229">Of</span><span class="sxs-lookup"><span data-stu-id="75963-229">Of</span></span>](of-clause.md)
- [<span data-ttu-id="75963-230">パラメーター配列</span><span class="sxs-lookup"><span data-stu-id="75963-230">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
- [<span data-ttu-id="75963-231">方法: ジェネリック クラスを使用する</span><span class="sxs-lookup"><span data-stu-id="75963-231">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="75963-232">プロシージャのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="75963-232">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [<span data-ttu-id="75963-233">部分メソッド</span><span class="sxs-lookup"><span data-stu-id="75963-233">Partial Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
