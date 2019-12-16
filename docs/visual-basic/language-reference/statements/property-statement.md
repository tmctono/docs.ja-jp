---
title: Property ステートメント
ms.date: 05/12/2018
f1_keywords:
- vb.PropertySet
- vb.Property
- vb.PropertyGet
helpviewer_keywords:
- Property statement [Visual Basic]
- default modifier
- property procedures [Visual Basic], Property statements
- Property keyword [Visual Basic]
ms.assetid: 3155edaf-8ebd-45c6-9cef-11d5d2dc8d38
ms.openlocfilehash: 80bce2442d96ecb9c548a88c8e5ee44c6258473b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346758"
---
# <a name="property-statement"></a><span data-ttu-id="8d3e1-102">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="8d3e1-102">Property Statement</span></span>

<span data-ttu-id="8d3e1-103">プロパティの名前、およびプロパティの値を格納および取得するために使用されるプロパティプロシージャを宣言します。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-103">Declares the name of a property, and the property procedures used to store and retrieve the value of the property.</span></span>

## <a name="syntax"></a><span data-ttu-id="8d3e1-104">構文</span><span class="sxs-lookup"><span data-stu-id="8d3e1-104">Syntax</span></span>

```vb
[ <attributelist> ] [ Default ] [ accessmodifier ]
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ] [ Iterator ]
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]
    [ <attributelist> ] [ accessmodifier ] Get
        [ statements ]
    End Get
    [ <attributelist> ] [ accessmodifier ] Set ( ByVal value As returntype [, parameterlist ] )
        [ statements ]
    End Set
End Property
- or -
[ <attributelist> ] [ Default ] [ accessmodifier ]
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ]
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]
```

## <a name="parts"></a><span data-ttu-id="8d3e1-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="8d3e1-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="8d3e1-106">任意。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-106">Optional.</span></span> <span data-ttu-id="8d3e1-107">このプロパティまたは `Get` または `Set` プロシージャに適用される属性の一覧。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-107">List of attributes that apply to this property or `Get` or `Set` procedure.</span></span> <span data-ttu-id="8d3e1-108">「[属性リスト](attribute-list.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-108">See [Attribute List](attribute-list.md).</span></span>

- `Default`

  <span data-ttu-id="8d3e1-109">任意。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-109">Optional.</span></span> <span data-ttu-id="8d3e1-110">このプロパティが、定義されているクラスまたは構造体の既定のプロパティであることを指定します。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-110">Specifies that this property is the default property for the class or structure on which it is defined.</span></span> <span data-ttu-id="8d3e1-111">既定のプロパティはパラメーターを受け取る必要があり、プロパティ名を指定せずに設定および取得できます。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-111">Default properties must accept parameters and can be set and retrieved without specifying the property name.</span></span> <span data-ttu-id="8d3e1-112">プロパティを `Default`として宣言する場合、プロパティまたはプロパティプロシージャのいずれかで `Private` を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-112">If you declare the property as `Default`, you cannot use `Private` on the property or on either of its property procedures.</span></span>

- `accessmodifier`

  <span data-ttu-id="8d3e1-113">`Property` ステートメントでは省略可能で、`Get` ステートメントと `Set` ステートメントのうちの1つでも指定できます。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-113">Optional on the `Property` statement and on at most one of the `Get` and `Set` statements.</span></span> <span data-ttu-id="8d3e1-114">次のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-114">Can be one of the following:</span></span>

  - [<span data-ttu-id="8d3e1-115">Public</span><span class="sxs-lookup"><span data-stu-id="8d3e1-115">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="8d3e1-116">Protected</span><span class="sxs-lookup"><span data-stu-id="8d3e1-116">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="8d3e1-117">Friend</span><span class="sxs-lookup"><span data-stu-id="8d3e1-117">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="8d3e1-118">Private</span><span class="sxs-lookup"><span data-stu-id="8d3e1-118">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="8d3e1-119">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="8d3e1-119">Protected Friend</span></span>](../modifiers/protected-friend.md)

  - [<span data-ttu-id="8d3e1-120">Private Protected</span><span class="sxs-lookup"><span data-stu-id="8d3e1-120">Private Protected</span></span>](../modifiers/private-protected.md)

  <span data-ttu-id="8d3e1-121">「[Visual Basic でのアクセス レベル](../../programming-guide/language-features/declared-elements/access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-121">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `propertymodifiers`

  <span data-ttu-id="8d3e1-122">任意。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-122">Optional.</span></span> <span data-ttu-id="8d3e1-123">次のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-123">Can be one of the following:</span></span>

  - [<span data-ttu-id="8d3e1-124">Overloads</span><span class="sxs-lookup"><span data-stu-id="8d3e1-124">Overloads</span></span>](../modifiers/overloads.md)

  - [<span data-ttu-id="8d3e1-125">Overrides</span><span class="sxs-lookup"><span data-stu-id="8d3e1-125">Overrides</span></span>](../modifiers/overrides.md)

  - [<span data-ttu-id="8d3e1-126">Overridable</span><span class="sxs-lookup"><span data-stu-id="8d3e1-126">Overridable</span></span>](../modifiers/overridable.md)

  - [<span data-ttu-id="8d3e1-127">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="8d3e1-127">NotOverridable</span></span>](../modifiers/notoverridable.md)

  - [<span data-ttu-id="8d3e1-128">MyBase</span><span class="sxs-lookup"><span data-stu-id="8d3e1-128">MustOverride</span></span>](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="8d3e1-129">任意。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-129">Optional.</span></span> <span data-ttu-id="8d3e1-130">「[Shared](../modifiers/shared.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-130">See [Shared](../modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="8d3e1-131">任意。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-131">Optional.</span></span> <span data-ttu-id="8d3e1-132">「[Shadows](../modifiers/shadows.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-132">See [Shadows](../modifiers/shadows.md).</span></span>

- `ReadOnly`

  <span data-ttu-id="8d3e1-133">任意。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-133">Optional.</span></span> <span data-ttu-id="8d3e1-134">「[ReadOnly](../modifiers/readonly.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-134">See [ReadOnly](../modifiers/readonly.md).</span></span>

- `WriteOnly`

  <span data-ttu-id="8d3e1-135">任意。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-135">Optional.</span></span> <span data-ttu-id="8d3e1-136">「[WriteOnly](../modifiers/writeonly.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-136">See [WriteOnly](../modifiers/writeonly.md).</span></span>

- `Iterator`

  <span data-ttu-id="8d3e1-137">任意。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-137">Optional.</span></span> <span data-ttu-id="8d3e1-138">「[Iterator](../modifiers/iterator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-138">See [Iterator](../modifiers/iterator.md).</span></span>

- `name`

  <span data-ttu-id="8d3e1-139">必須。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-139">Required.</span></span> <span data-ttu-id="8d3e1-140">プロパティ名。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-140">Name of the property.</span></span> <span data-ttu-id="8d3e1-141">「[Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-141">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

- `parameterlist`

  <span data-ttu-id="8d3e1-142">任意。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-142">Optional.</span></span> <span data-ttu-id="8d3e1-143">このプロパティのパラメーターを表すローカル変数名の一覧と、`Set` プロシージャの追加パラメーター。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-143">List of local variable names representing the parameters of this property, and possible additional parameters of the `Set` procedure.</span></span> <span data-ttu-id="8d3e1-144">「[パラメーターリスト](parameter-list.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-144">See [Parameter List](parameter-list.md).</span></span>

- `returntype`

  <span data-ttu-id="8d3e1-145">`Option Strict` が `On`の場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-145">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="8d3e1-146">このプロパティによって返される値のデータ型。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-146">Data type of the value returned by this property.</span></span>

- `Implements`

  <span data-ttu-id="8d3e1-147">任意。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-147">Optional.</span></span> <span data-ttu-id="8d3e1-148">このプロパティが1つ以上のプロパティを実装することを示します。各プロパティは、このプロパティのクラスまたは構造体を含むインターフェイスで定義されています。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-148">Indicates that this property implements one or more properties, each one defined in an interface implemented by this property's containing class or structure.</span></span> <span data-ttu-id="8d3e1-149">「[Implements ステートメント](implements-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-149">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="8d3e1-150">`Implements` を指定する場合は、必ず指定します。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-150">Required if `Implements` is supplied.</span></span> <span data-ttu-id="8d3e1-151">実装されているプロパティの一覧。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-151">List of properties being implemented.</span></span>

  `implementedproperty [ , implementedproperty ... ]`

  <span data-ttu-id="8d3e1-152">`implementedproperty` の構文と指定項目は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-152">Each `implementedproperty` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="8d3e1-153">要素</span><span class="sxs-lookup"><span data-stu-id="8d3e1-153">Part</span></span>|<span data-ttu-id="8d3e1-154">説明</span><span class="sxs-lookup"><span data-stu-id="8d3e1-154">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="8d3e1-155">必須。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-155">Required.</span></span> <span data-ttu-id="8d3e1-156">このプロパティのクラスまたは構造体によって実装されるインターフェイスの名前。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-156">Name of an interface implemented by this property's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="8d3e1-157">必須。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-157">Required.</span></span> <span data-ttu-id="8d3e1-158">プロパティが定義されている名前 `interface`です。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-158">Name by which the property is defined in `interface`.</span></span>|

- `Get`

  <span data-ttu-id="8d3e1-159">任意。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-159">Optional.</span></span> <span data-ttu-id="8d3e1-160">プロパティが `ReadOnly`としてマークされている場合は必須。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-160">Required if the property is marked `ReadOnly`.</span></span> <span data-ttu-id="8d3e1-161">プロパティの値を返すために使用される `Get` プロパティプロシージャを開始します。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-161">Starts a `Get` property procedure that is used to return the value of the property.</span></span>  <span data-ttu-id="8d3e1-162">`Get` ステートメントは、[自動実装プロパティ](../../programming-guide/language-features/procedures/auto-implemented-properties.md)では使用されません。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-162">The `Get` statement is not used with [auto-implemented properties](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

- `statements`

  <span data-ttu-id="8d3e1-163">任意。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-163">Optional.</span></span> <span data-ttu-id="8d3e1-164">`Get` または `Set` プロシージャ内で実行するステートメントのブロック。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-164">Block of statements to run within the `Get` or `Set` procedure.</span></span>

- `End Get`

  <span data-ttu-id="8d3e1-165">`Get` プロパティプロシージャを終了します。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-165">Terminates the `Get` property procedure.</span></span>

- `Set`

  <span data-ttu-id="8d3e1-166">任意。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-166">Optional.</span></span> <span data-ttu-id="8d3e1-167">プロパティが `WriteOnly`としてマークされている場合は必須。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-167">Required if the property is marked `WriteOnly`.</span></span> <span data-ttu-id="8d3e1-168">プロパティの値を格納するために使用される `Set` プロパティプロシージャを開始します。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-168">Starts a `Set` property procedure that is used to store the value of the property.</span></span>  <span data-ttu-id="8d3e1-169">`Set` ステートメントは、[自動実装プロパティ](../../programming-guide/language-features/procedures/auto-implemented-properties.md)では使用されません。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-169">The `Set` statement is not used with [auto-implemented properties](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

- `End Set`

  <span data-ttu-id="8d3e1-170">`Set` プロパティプロシージャを終了します。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-170">Terminates the `Set` property procedure.</span></span>

- `End Property`

  <span data-ttu-id="8d3e1-171">このプロパティの定義を終了します。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-171">Terminates the definition of this property.</span></span>

## <a name="remarks"></a><span data-ttu-id="8d3e1-172">コメント</span><span class="sxs-lookup"><span data-stu-id="8d3e1-172">Remarks</span></span>

<span data-ttu-id="8d3e1-173">`Property` ステートメントでは、プロパティの宣言が導入されています。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-173">The `Property` statement introduces the declaration of a property.</span></span> <span data-ttu-id="8d3e1-174">プロパティは、`Get` プロシージャ (読み取り専用)、`Set` プロシージャ (書き込み専用)、またはその両方 (読み取り/書き込み) を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-174">A property can have a `Get` procedure (read only), a `Set` procedure (write only), or both (read-write).</span></span> <span data-ttu-id="8d3e1-175">自動実装プロパティを使用する場合は、`Get` と `Set` の手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-175">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="8d3e1-176">詳細については、「[自動実装プロパティ](../../programming-guide/language-features/procedures/auto-implemented-properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-176">For more information, see [Auto-Implemented Properties](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

<span data-ttu-id="8d3e1-177">`Property` はクラスレベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-177">You can use `Property` only at class level.</span></span> <span data-ttu-id="8d3e1-178">つまり、プロパティの*宣言コンテキスト*はクラス、構造体、モジュール、またはインターフェイスである必要があり、ソースファイル、名前空間、プロシージャ、またはブロックにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-178">This means the *declaration context* for a property must be a class, structure, module, or interface, and cannot be a source file, namespace, procedure, or block.</span></span> <span data-ttu-id="8d3e1-179">詳細については、「[宣言コンテキストと既定のアクセス レベル](declaration-contexts-and-default-access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-179">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="8d3e1-180">既定では、プロパティはパブリックアクセスを使用します。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-180">By default, properties use public access.</span></span> <span data-ttu-id="8d3e1-181">`Property` ステートメントでアクセス修飾子を使用してプロパティのアクセスレベルを調整できます。また、必要に応じて、プロパティプロシージャの1つをより制限の厳しいアクセスレベルに調整することもできます。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-181">You can adjust a property's access level with an access modifier on the `Property` statement, and you can optionally adjust one of its property procedures to a more restrictive access level.</span></span>

<span data-ttu-id="8d3e1-182">Visual Basic は、プロパティの割り当て時に `Set` プロシージャにパラメーターを渡します。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-182">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="8d3e1-183">`Set`のパラメーターを指定しない場合、統合開発環境 (IDE) は `value`という名前の暗黙的なパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-183">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="8d3e1-184">このパラメーターは、プロパティに割り当てられる値を保持します。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-184">This parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="8d3e1-185">通常、この値はプライベートローカル変数に格納し、`Get` プロシージャが呼び出されるたびに返されます。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-185">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>

## <a name="rules"></a><span data-ttu-id="8d3e1-186">ルール</span><span class="sxs-lookup"><span data-stu-id="8d3e1-186">Rules</span></span>

- <span data-ttu-id="8d3e1-187">**混合アクセスレベル。**</span><span class="sxs-lookup"><span data-stu-id="8d3e1-187">**Mixed Access Levels.**</span></span> <span data-ttu-id="8d3e1-188">読み取り/書き込みプロパティを定義する場合は、必要に応じて、`Get` または `Set` のいずれかのプロシージャに対して異なるアクセスレベルを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-188">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="8d3e1-189">この場合、プロシージャのアクセスレベルは、プロパティのアクセスレベルよりも制限されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-189">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="8d3e1-190">たとえば、プロパティが `Friend`として宣言されている場合は、`Set` プロシージャ `Private`を宣言できますが、`Public`は宣言できません。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-190">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>

  <span data-ttu-id="8d3e1-191">`ReadOnly` または `WriteOnly` プロパティを定義する場合、1つのプロパティプロシージャ (それぞれ`Get` または `Set`) が、すべてのプロパティを表します。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-191">If you are defining a `ReadOnly` or `WriteOnly` property, the single property procedure (`Get` or `Set`, respectively) represents all of the property.</span></span> <span data-ttu-id="8d3e1-192">このようなプロシージャに対して異なるアクセスレベルを宣言することはできません。これは、プロパティに2つのアクセスレベルが設定されるためです。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-192">You cannot declare a different access level for such a procedure, because that would set two access levels for the property.</span></span>

- <span data-ttu-id="8d3e1-193">**戻り値の型。**</span><span class="sxs-lookup"><span data-stu-id="8d3e1-193">**Return Type.**</span></span> <span data-ttu-id="8d3e1-194">`Property` ステートメントでは、返される値のデータ型を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-194">The `Property` statement can declare the data type of the value it returns.</span></span> <span data-ttu-id="8d3e1-195">任意のデータ型を指定することも、列挙型、構造体、クラス、またはインターフェイスの名前を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-195">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>

  <span data-ttu-id="8d3e1-196">`returntype`を指定しない場合、プロパティは `Object`を返します。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-196">If you do not specify `returntype`, the property returns `Object`.</span></span>

- <span data-ttu-id="8d3e1-197">**ション.**</span><span class="sxs-lookup"><span data-stu-id="8d3e1-197">**Implementation.**</span></span> <span data-ttu-id="8d3e1-198">このプロパティで `Implements` キーワードが使用されている場合、その親クラスまたは構造体には、その `Class` または `Structure` ステートメントの直後にある `Implements` ステートメントが必要です。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-198">If this property uses the `Implements` keyword, the containing class or structure must have an `Implements` statement immediately following its `Class` or `Structure` statement.</span></span> <span data-ttu-id="8d3e1-199">`Implements` ステートメントには、`implementslist`で指定された各インターフェイスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-199">The `Implements` statement must include each interface specified in `implementslist`.</span></span> <span data-ttu-id="8d3e1-200">ただし、インターフェイスが `Property` を定義するときに使用する名前 (`definedname`) は、このプロパティの名前と同じである必要はありません (`name`)。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-200">However, the name by which an interface defines the `Property` (in `definedname`) does not have to be the same as the name of this property (in `name`).</span></span>

## <a name="behavior"></a><span data-ttu-id="8d3e1-201">動作</span><span class="sxs-lookup"><span data-stu-id="8d3e1-201">Behavior</span></span>

- <span data-ttu-id="8d3e1-202">**プロパティプロシージャからを返します。**</span><span class="sxs-lookup"><span data-stu-id="8d3e1-202">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="8d3e1-203">`Get` または `Set` プロシージャが呼び出し元のコードに戻ると、そのプロシージャを呼び出したステートメントの後のステートメントで実行が続行されます。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-203">When the `Get` or `Set` procedure returns to the calling code, execution continues with the statement following the statement that invoked it.</span></span>

  <span data-ttu-id="8d3e1-204">`Exit Property` ステートメントおよび `Return` ステートメントでは、プロパティプロシージャがすぐに終了します。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-204">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="8d3e1-205">プロシージャ内の任意の場所で任意の数の `Exit Property` および `Return` ステートメントを使用できます。また、`Exit Property` と `Return` のステートメントを混在させることができます。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-205">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>

- <span data-ttu-id="8d3e1-206">**戻り値。**</span><span class="sxs-lookup"><span data-stu-id="8d3e1-206">**Return Value.**</span></span> <span data-ttu-id="8d3e1-207">`Get` プロシージャから値を返すには、プロパティ名に値を割り当てるか、`Return` ステートメントに値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-207">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a `Return` statement.</span></span> <span data-ttu-id="8d3e1-208">次の例では、プロパティ名 `quoteForTheDay` に戻り値を割り当て、`Exit Property` ステートメントを使用してを返します。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-208">The following example assigns the return value to the property name `quoteForTheDay` and then uses the `Exit Property` statement to return.</span></span>

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]

  <span data-ttu-id="8d3e1-209">`name`に値を割り当てずに `Exit Property` を使用する場合、`Get` プロシージャはプロパティのデータ型の既定値を返します。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-209">If you use `Exit Property` without assigning a value to `name`, the `Get` procedure returns the default value for the property's data type.</span></span>

  <span data-ttu-id="8d3e1-210">同時に `Return` ステートメントによって、`Get` プロシージャの戻り値が割り当てられ、プロシージャが終了します。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-210">The `Return` statement at the same time assigns the `Get` procedure return value and exits the procedure.</span></span> <span data-ttu-id="8d3e1-211">この例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-211">The following example shows this.</span></span>

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]

## <a name="example"></a><span data-ttu-id="8d3e1-212">例</span><span class="sxs-lookup"><span data-stu-id="8d3e1-212">Example</span></span>

<span data-ttu-id="8d3e1-213">次の例では、クラスのプロパティを宣言しています。</span><span class="sxs-lookup"><span data-stu-id="8d3e1-213">The following example declares a property in a class.</span></span>

[!code-vb[VbVbalrStatements#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#51)]

## <a name="see-also"></a><span data-ttu-id="8d3e1-214">関連項目</span><span class="sxs-lookup"><span data-stu-id="8d3e1-214">See also</span></span>

- [<span data-ttu-id="8d3e1-215">自動実装プロパティ</span><span class="sxs-lookup"><span data-stu-id="8d3e1-215">Auto-Implemented Properties</span></span>](../../programming-guide/language-features/procedures/auto-implemented-properties.md)
- [<span data-ttu-id="8d3e1-216">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="8d3e1-216">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="8d3e1-217">Get ステートメント</span><span class="sxs-lookup"><span data-stu-id="8d3e1-217">Get Statement</span></span>](get-statement.md)
- [<span data-ttu-id="8d3e1-218">Set ステートメント</span><span class="sxs-lookup"><span data-stu-id="8d3e1-218">Set Statement</span></span>](set-statement.md)
- [<span data-ttu-id="8d3e1-219">パラメーター リスト</span><span class="sxs-lookup"><span data-stu-id="8d3e1-219">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="8d3e1-220">Shared</span><span class="sxs-lookup"><span data-stu-id="8d3e1-220">Default</span></span>](../modifiers/default.md)
