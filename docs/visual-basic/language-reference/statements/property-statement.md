---
title: Property Statement
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
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346758"
---
# <a name="property-statement"></a><span data-ttu-id="1954c-102">Property Statement</span><span class="sxs-lookup"><span data-stu-id="1954c-102">Property Statement</span></span>

<span data-ttu-id="1954c-103">プロパティの名前、およびプロパティの値を格納して取得するために使用されるプロパティ プロシージャを宣言します。</span><span class="sxs-lookup"><span data-stu-id="1954c-103">Declares the name of a property, and the property procedures used to store and retrieve the value of the property.</span></span>

## <a name="syntax"></a><span data-ttu-id="1954c-104">構文</span><span class="sxs-lookup"><span data-stu-id="1954c-104">Syntax</span></span>

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

## <a name="parts"></a><span data-ttu-id="1954c-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="1954c-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="1954c-106">任意。</span><span class="sxs-lookup"><span data-stu-id="1954c-106">Optional.</span></span> <span data-ttu-id="1954c-107">このプロパティか、`Get` または `Set` プロシージャに適用される属性の一覧です。</span><span class="sxs-lookup"><span data-stu-id="1954c-107">List of attributes that apply to this property or `Get` or `Set` procedure.</span></span> <span data-ttu-id="1954c-108">「[属性リスト](attribute-list.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1954c-108">See [Attribute List](attribute-list.md).</span></span>

- `Default`

  <span data-ttu-id="1954c-109">任意。</span><span class="sxs-lookup"><span data-stu-id="1954c-109">Optional.</span></span> <span data-ttu-id="1954c-110">このプロパティが、定義されているクラスまたは構造体の既定のプロパティであることを指定します。</span><span class="sxs-lookup"><span data-stu-id="1954c-110">Specifies that this property is the default property for the class or structure on which it is defined.</span></span> <span data-ttu-id="1954c-111">既定のプロパティはパラメーターを受け取る必要があり、プロパティ名を指定せずに設定および取得できます。</span><span class="sxs-lookup"><span data-stu-id="1954c-111">Default properties must accept parameters and can be set and retrieved without specifying the property name.</span></span> <span data-ttu-id="1954c-112">プロパティを `Default` として宣言する場合、プロパティで、またはそのプロパティ プロシージャのいずれかで `Private` を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="1954c-112">If you declare the property as `Default`, you cannot use `Private` on the property or on either of its property procedures.</span></span>

- `accessmodifier`

  <span data-ttu-id="1954c-113">`Property` ステートメントで、および `Get` ステートメントと `Set` ステートメントのうちのいずれかで省略可能です。</span><span class="sxs-lookup"><span data-stu-id="1954c-113">Optional on the `Property` statement and on at most one of the `Get` and `Set` statements.</span></span> <span data-ttu-id="1954c-114">次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="1954c-114">Can be one of the following:</span></span>

  - [<span data-ttu-id="1954c-115">Public</span><span class="sxs-lookup"><span data-stu-id="1954c-115">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="1954c-116">Protected</span><span class="sxs-lookup"><span data-stu-id="1954c-116">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="1954c-117">Friend</span><span class="sxs-lookup"><span data-stu-id="1954c-117">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="1954c-118">Private</span><span class="sxs-lookup"><span data-stu-id="1954c-118">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="1954c-119">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="1954c-119">Protected Friend</span></span>](../modifiers/protected-friend.md)

  - [<span data-ttu-id="1954c-120">Private Protected</span><span class="sxs-lookup"><span data-stu-id="1954c-120">Private Protected</span></span>](../modifiers/private-protected.md)

  <span data-ttu-id="1954c-121">「 [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1954c-121">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `propertymodifiers`

  <span data-ttu-id="1954c-122">任意。</span><span class="sxs-lookup"><span data-stu-id="1954c-122">Optional.</span></span> <span data-ttu-id="1954c-123">次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="1954c-123">Can be one of the following:</span></span>

  - [<span data-ttu-id="1954c-124">Overloads</span><span class="sxs-lookup"><span data-stu-id="1954c-124">Overloads</span></span>](../modifiers/overloads.md)

  - [<span data-ttu-id="1954c-125">Overrides</span><span class="sxs-lookup"><span data-stu-id="1954c-125">Overrides</span></span>](../modifiers/overrides.md)

  - [<span data-ttu-id="1954c-126">Overridable</span><span class="sxs-lookup"><span data-stu-id="1954c-126">Overridable</span></span>](../modifiers/overridable.md)

  - [<span data-ttu-id="1954c-127">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="1954c-127">NotOverridable</span></span>](../modifiers/notoverridable.md)

  - [<span data-ttu-id="1954c-128">MustOverride</span><span class="sxs-lookup"><span data-stu-id="1954c-128">MustOverride</span></span>](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="1954c-129">任意。</span><span class="sxs-lookup"><span data-stu-id="1954c-129">Optional.</span></span> <span data-ttu-id="1954c-130">「[Shared](../modifiers/shared.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1954c-130">See [Shared](../modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="1954c-131">任意。</span><span class="sxs-lookup"><span data-stu-id="1954c-131">Optional.</span></span> <span data-ttu-id="1954c-132">「[Shadows](../modifiers/shadows.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1954c-132">See [Shadows](../modifiers/shadows.md).</span></span>

- `ReadOnly`

  <span data-ttu-id="1954c-133">任意。</span><span class="sxs-lookup"><span data-stu-id="1954c-133">Optional.</span></span> <span data-ttu-id="1954c-134">「[ReadOnly](../modifiers/readonly.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1954c-134">See [ReadOnly](../modifiers/readonly.md).</span></span>

- `WriteOnly`

  <span data-ttu-id="1954c-135">任意。</span><span class="sxs-lookup"><span data-stu-id="1954c-135">Optional.</span></span> <span data-ttu-id="1954c-136">「[WriteOnly](../modifiers/writeonly.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1954c-136">See [WriteOnly](../modifiers/writeonly.md).</span></span>

- `Iterator`

  <span data-ttu-id="1954c-137">任意。</span><span class="sxs-lookup"><span data-stu-id="1954c-137">Optional.</span></span> <span data-ttu-id="1954c-138">「[反復子](../modifiers/iterator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1954c-138">See [Iterator](../modifiers/iterator.md).</span></span>

- `name`

  <span data-ttu-id="1954c-139">必須です。</span><span class="sxs-lookup"><span data-stu-id="1954c-139">Required.</span></span> <span data-ttu-id="1954c-140">プロパティ名。</span><span class="sxs-lookup"><span data-stu-id="1954c-140">Name of the property.</span></span> <span data-ttu-id="1954c-141">「 [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1954c-141">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

- `parameterlist`

  <span data-ttu-id="1954c-142">任意。</span><span class="sxs-lookup"><span data-stu-id="1954c-142">Optional.</span></span> <span data-ttu-id="1954c-143">このプロパティのパラメーターと、`Set` プロシージャの指定できるその他のパラメーターを表すローカル変数名の一覧です。</span><span class="sxs-lookup"><span data-stu-id="1954c-143">List of local variable names representing the parameters of this property, and possible additional parameters of the `Set` procedure.</span></span> <span data-ttu-id="1954c-144">[パラメーター リスト](parameter-list.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1954c-144">See [Parameter List](parameter-list.md).</span></span>

- `returntype`

  <span data-ttu-id="1954c-145">`Option Strict` が `On` の場合は必ず指定します。</span><span class="sxs-lookup"><span data-stu-id="1954c-145">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="1954c-146">このプロパティによって返される値のデータ型。</span><span class="sxs-lookup"><span data-stu-id="1954c-146">Data type of the value returned by this property.</span></span>

- `Implements`

  <span data-ttu-id="1954c-147">任意。</span><span class="sxs-lookup"><span data-stu-id="1954c-147">Optional.</span></span> <span data-ttu-id="1954c-148">このプロパティが、それぞれがこのプロパティの含まれているクラスまたは構造体によって実装されたインターフェイスに定義されている、1 つ以上のプロパティを実装することを示します。</span><span class="sxs-lookup"><span data-stu-id="1954c-148">Indicates that this property implements one or more properties, each one defined in an interface implemented by this property's containing class or structure.</span></span> <span data-ttu-id="1954c-149">「[Implements ステートメント](implements-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1954c-149">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="1954c-150">`Implements` を指定する場合は、必ず指定します。</span><span class="sxs-lookup"><span data-stu-id="1954c-150">Required if `Implements` is supplied.</span></span> <span data-ttu-id="1954c-151">実装されるプロパティの一覧です。</span><span class="sxs-lookup"><span data-stu-id="1954c-151">List of properties being implemented.</span></span>

  `implementedproperty [ , implementedproperty ... ]`

  <span data-ttu-id="1954c-152">`implementedproperty` の構文と指定項目は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1954c-152">Each `implementedproperty` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="1954c-153">パーツ</span><span class="sxs-lookup"><span data-stu-id="1954c-153">Part</span></span>|<span data-ttu-id="1954c-154">説明</span><span class="sxs-lookup"><span data-stu-id="1954c-154">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="1954c-155">必須です。</span><span class="sxs-lookup"><span data-stu-id="1954c-155">Required.</span></span> <span data-ttu-id="1954c-156">このプロパティの含まれているクラスまたは構造体によって実装されたインターフェイスの名前です。</span><span class="sxs-lookup"><span data-stu-id="1954c-156">Name of an interface implemented by this property's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="1954c-157">必須です。</span><span class="sxs-lookup"><span data-stu-id="1954c-157">Required.</span></span> <span data-ttu-id="1954c-158">`interface` の中でプロパティを定義するために使用する名前です。</span><span class="sxs-lookup"><span data-stu-id="1954c-158">Name by which the property is defined in `interface`.</span></span>|

- `Get`

  <span data-ttu-id="1954c-159">任意。</span><span class="sxs-lookup"><span data-stu-id="1954c-159">Optional.</span></span> <span data-ttu-id="1954c-160">プロパティが `ReadOnly` とマークされている場合は、必ず指定します。</span><span class="sxs-lookup"><span data-stu-id="1954c-160">Required if the property is marked `ReadOnly`.</span></span> <span data-ttu-id="1954c-161">プロパティの値を返すために使用される `Get` プロパティ プロシージャを開始します。</span><span class="sxs-lookup"><span data-stu-id="1954c-161">Starts a `Get` property procedure that is used to return the value of the property.</span></span>  <span data-ttu-id="1954c-162">`Get` ステートメントは、[自動実装プロパティ](../../programming-guide/language-features/procedures/auto-implemented-properties.md)と一緒には使用されません。</span><span class="sxs-lookup"><span data-stu-id="1954c-162">The `Get` statement is not used with [auto-implemented properties](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

- `statements`

  <span data-ttu-id="1954c-163">任意。</span><span class="sxs-lookup"><span data-stu-id="1954c-163">Optional.</span></span> <span data-ttu-id="1954c-164">`Get` または `Set` プロシージャ内で実行するためのステートメントのブロック。</span><span class="sxs-lookup"><span data-stu-id="1954c-164">Block of statements to run within the `Get` or `Set` procedure.</span></span>

- `End Get`

  <span data-ttu-id="1954c-165">`Get` プロパティ プロシージャを終了します。</span><span class="sxs-lookup"><span data-stu-id="1954c-165">Terminates the `Get` property procedure.</span></span>

- `Set`

  <span data-ttu-id="1954c-166">任意。</span><span class="sxs-lookup"><span data-stu-id="1954c-166">Optional.</span></span> <span data-ttu-id="1954c-167">プロパティが `WriteOnly` とマークされている場合は、必ず指定します。</span><span class="sxs-lookup"><span data-stu-id="1954c-167">Required if the property is marked `WriteOnly`.</span></span> <span data-ttu-id="1954c-168">プロパティの値を格納するために使用される `Set` プロパティ プロシージャを開始します。</span><span class="sxs-lookup"><span data-stu-id="1954c-168">Starts a `Set` property procedure that is used to store the value of the property.</span></span>  <span data-ttu-id="1954c-169">`Set` ステートメントは、[自動実装プロパティ](../../programming-guide/language-features/procedures/auto-implemented-properties.md)と一緒には使用されません。</span><span class="sxs-lookup"><span data-stu-id="1954c-169">The `Set` statement is not used with [auto-implemented properties](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

- `End Set`

  <span data-ttu-id="1954c-170">`Set` プロパティ プロシージャを終了します。</span><span class="sxs-lookup"><span data-stu-id="1954c-170">Terminates the `Set` property procedure.</span></span>

- `End Property`

  <span data-ttu-id="1954c-171">このプロパティの定義を終了します。</span><span class="sxs-lookup"><span data-stu-id="1954c-171">Terminates the definition of this property.</span></span>

## <a name="remarks"></a><span data-ttu-id="1954c-172">Remarks</span><span class="sxs-lookup"><span data-stu-id="1954c-172">Remarks</span></span>

<span data-ttu-id="1954c-173">`Property` ステートメントは、プロパティの宣言を導入します。</span><span class="sxs-lookup"><span data-stu-id="1954c-173">The `Property` statement introduces the declaration of a property.</span></span> <span data-ttu-id="1954c-174">プロパティには `Get` プロシージャ (読み取り専用)、`Set` プロシージャ (書き込み専用)、またはその両方 (読み取り/書き込み) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1954c-174">A property can have a `Get` procedure (read only), a `Set` procedure (write only), or both (read-write).</span></span> <span data-ttu-id="1954c-175">自動実装プロパティを使用する場合は、`Get` プロシージャと `Set` プロシージャを省略できます。</span><span class="sxs-lookup"><span data-stu-id="1954c-175">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="1954c-176">詳細については、「[自動実装プロパティ](../../programming-guide/language-features/procedures/auto-implemented-properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1954c-176">For more information, see [Auto-Implemented Properties](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

<span data-ttu-id="1954c-177">`Property` は、クラス レベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="1954c-177">You can use `Property` only at class level.</span></span> <span data-ttu-id="1954c-178">つまり、プロパティの*宣言コンテキスト*は、クラス、構造体、モジュール、またはインターフェイスであることが必要で、ソース ファイル、名前空間、プロシージャ、ブロックでは宣言できません。</span><span class="sxs-lookup"><span data-stu-id="1954c-178">This means the *declaration context* for a property must be a class, structure, module, or interface, and cannot be a source file, namespace, procedure, or block.</span></span> <span data-ttu-id="1954c-179">詳細については、「[宣言コンテキストと既定のアクセス レベル](declaration-contexts-and-default-access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1954c-179">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="1954c-180">既定では、プロパティはパブリック アクセスを使用します。</span><span class="sxs-lookup"><span data-stu-id="1954c-180">By default, properties use public access.</span></span> <span data-ttu-id="1954c-181">`Property` ステートメントでアクセス修飾子を使用してプロパティのアクセス レベルを調整できます。また、必要に応じて、そのプロパティ プロシージャの 1 つをより制限の厳しいアクセス レベルに調整することもできます。</span><span class="sxs-lookup"><span data-stu-id="1954c-181">You can adjust a property's access level with an access modifier on the `Property` statement, and you can optionally adjust one of its property procedures to a more restrictive access level.</span></span>

<span data-ttu-id="1954c-182">Visual Basic は、プロパティの割り当て時に `Set` プロシージャにパラメーターを渡します。</span><span class="sxs-lookup"><span data-stu-id="1954c-182">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="1954c-183">`Set` のパラメーターを指定しない場合、統合開発環境 (IDE) では `value` という名前の暗黙的なパラメーターが使用されます。</span><span class="sxs-lookup"><span data-stu-id="1954c-183">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="1954c-184">このパラメーターは、プロパティに割り当てられる値を保持します。</span><span class="sxs-lookup"><span data-stu-id="1954c-184">This parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="1954c-185">通常はこの値をプライベート ローカル変数に格納し、これは `Get` プロシージャが呼び出されるたびに返されます。</span><span class="sxs-lookup"><span data-stu-id="1954c-185">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>

## <a name="rules"></a><span data-ttu-id="1954c-186">ルール</span><span class="sxs-lookup"><span data-stu-id="1954c-186">Rules</span></span>

- <span data-ttu-id="1954c-187">**混合アクセス レベル。**</span><span class="sxs-lookup"><span data-stu-id="1954c-187">**Mixed Access Levels.**</span></span> <span data-ttu-id="1954c-188">読み取り/書き込みプロパティを定義する場合は、必要に応じて、`Get` または `Set` のいずれかのプロシージャに対して異なるアクセス レベルを指定できますが、両方に対して指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="1954c-188">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="1954c-189">この場合、プロシージャのアクセス レベルは、プロパティのアクセス レベルよりも制限されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1954c-189">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="1954c-190">たとえば、プロパティが `Friend` として宣言されている場合は、`Set` プロシージャを、`Public` ではなく `Private` として宣言できます。</span><span class="sxs-lookup"><span data-stu-id="1954c-190">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>

  <span data-ttu-id="1954c-191">`ReadOnly` または `WriteOnly` プロパティを定義する場合、1 つのプロパティ プロシージャ (それぞれ `Get` または `Set`) がプロパティのすべてを表します。</span><span class="sxs-lookup"><span data-stu-id="1954c-191">If you are defining a `ReadOnly` or `WriteOnly` property, the single property procedure (`Get` or `Set`, respectively) represents all of the property.</span></span> <span data-ttu-id="1954c-192">このようなプロシージャに対して異なるアクセス レベルを宣言することはできません。これは、プロパティに 2 つのアクセス レベルが設定されるためです。</span><span class="sxs-lookup"><span data-stu-id="1954c-192">You cannot declare a different access level for such a procedure, because that would set two access levels for the property.</span></span>

- <span data-ttu-id="1954c-193">**戻り値の型。**</span><span class="sxs-lookup"><span data-stu-id="1954c-193">**Return Type.**</span></span> <span data-ttu-id="1954c-194">`Property` ステートメントは、返される値のデータ型を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="1954c-194">The `Property` statement can declare the data type of the value it returns.</span></span> <span data-ttu-id="1954c-195">任意のデータ型や、列挙、構造体、クラス、またはインターフェイスの名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1954c-195">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>

  <span data-ttu-id="1954c-196">`returntype` を指定しない場合、プロパティは `Object` を返します。</span><span class="sxs-lookup"><span data-stu-id="1954c-196">If you do not specify `returntype`, the property returns `Object`.</span></span>

- <span data-ttu-id="1954c-197">**実装。**</span><span class="sxs-lookup"><span data-stu-id="1954c-197">**Implementation.**</span></span> <span data-ttu-id="1954c-198">このプロパティで `Implements` キーワードが使用されている場合、含まれているクラスまたは構造体には、その `Class` または `Structure` ステートメントの直後に `Implements` ステートメントが必要です。</span><span class="sxs-lookup"><span data-stu-id="1954c-198">If this property uses the `Implements` keyword, the containing class or structure must have an `Implements` statement immediately following its `Class` or `Structure` statement.</span></span> <span data-ttu-id="1954c-199">`Implements` ステートメントには、`implementslist` で指定された各インターフェイスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="1954c-199">The `Implements` statement must include each interface specified in `implementslist`.</span></span> <span data-ttu-id="1954c-200">ただし、インターフェイスが `Property` を定義するときに使用する名前 (`definedname`) は、このプロパティの名前と同じである必要はありません (`name`)。</span><span class="sxs-lookup"><span data-stu-id="1954c-200">However, the name by which an interface defines the `Property` (in `definedname`) does not have to be the same as the name of this property (in `name`).</span></span>

## <a name="behavior"></a><span data-ttu-id="1954c-201">動作</span><span class="sxs-lookup"><span data-stu-id="1954c-201">Behavior</span></span>

- <span data-ttu-id="1954c-202">**プロパティ プロシージャからの復帰。**</span><span class="sxs-lookup"><span data-stu-id="1954c-202">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="1954c-203">`Get` または `Set` プロシージャから呼び出し元のコードに返されると、実行は、それを呼び出したステートメントの後のステートメントを使用して続行されます。</span><span class="sxs-lookup"><span data-stu-id="1954c-203">When the `Get` or `Set` procedure returns to the calling code, execution continues with the statement following the statement that invoked it.</span></span>

  <span data-ttu-id="1954c-204">`Exit Property` および `Return` ステートメントでは、プロパティ プロシージャがすぐに終了します。</span><span class="sxs-lookup"><span data-stu-id="1954c-204">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="1954c-205">任意の数の `Exit Property` および `Return` ステートメントをプロシージャ内の任意の場所に記述でき、`Exit Property` ステートメントと `Return` ステートメントを混在させることができます。</span><span class="sxs-lookup"><span data-stu-id="1954c-205">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>

- <span data-ttu-id="1954c-206">**戻り値。**</span><span class="sxs-lookup"><span data-stu-id="1954c-206">**Return Value.**</span></span> <span data-ttu-id="1954c-207">`Get` プロシージャから値を返すには、プロパティ名に値を割り当てるか、`Return` ステートメントに値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1954c-207">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a `Return` statement.</span></span> <span data-ttu-id="1954c-208">次の例では、プロパティ名 `quoteForTheDay` に戻り値を割り当ててから、`Exit Property` ステートメントを使用して返します。</span><span class="sxs-lookup"><span data-stu-id="1954c-208">The following example assigns the return value to the property name `quoteForTheDay` and then uses the `Exit Property` statement to return.</span></span>

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]

  <span data-ttu-id="1954c-209">`name` に値を割り当てずに `Exit Property` を使用すると、`Get` プロシージャは、プロパティのデータ型の既定値を返します。</span><span class="sxs-lookup"><span data-stu-id="1954c-209">If you use `Exit Property` without assigning a value to `name`, the `Get` procedure returns the default value for the property's data type.</span></span>

  <span data-ttu-id="1954c-210">同時に、`Return` ステートメントによって `Get` プロシージャの戻り値が割り当てられ、プロシージャが終了します。</span><span class="sxs-lookup"><span data-stu-id="1954c-210">The `Return` statement at the same time assigns the `Get` procedure return value and exits the procedure.</span></span> <span data-ttu-id="1954c-211">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1954c-211">The following example shows this.</span></span>

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]

## <a name="example"></a><span data-ttu-id="1954c-212">例</span><span class="sxs-lookup"><span data-stu-id="1954c-212">Example</span></span>

<span data-ttu-id="1954c-213">次の例では、クラス内にプロパティを宣言しています。</span><span class="sxs-lookup"><span data-stu-id="1954c-213">The following example declares a property in a class.</span></span>

[!code-vb[VbVbalrStatements#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#51)]

## <a name="see-also"></a><span data-ttu-id="1954c-214">関連項目</span><span class="sxs-lookup"><span data-stu-id="1954c-214">See also</span></span>

- [<span data-ttu-id="1954c-215">自動実装プロパティ</span><span class="sxs-lookup"><span data-stu-id="1954c-215">Auto-Implemented Properties</span></span>](../../programming-guide/language-features/procedures/auto-implemented-properties.md)
- [<span data-ttu-id="1954c-216">クラスとオブジェクト</span><span class="sxs-lookup"><span data-stu-id="1954c-216">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="1954c-217">Get ステートメント</span><span class="sxs-lookup"><span data-stu-id="1954c-217">Get Statement</span></span>](get-statement.md)
- [<span data-ttu-id="1954c-218">Set ステートメント</span><span class="sxs-lookup"><span data-stu-id="1954c-218">Set Statement</span></span>](set-statement.md)
- [<span data-ttu-id="1954c-219">パラメーター リスト</span><span class="sxs-lookup"><span data-stu-id="1954c-219">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="1954c-220">default</span><span class="sxs-lookup"><span data-stu-id="1954c-220">Default</span></span>](../modifiers/default.md)
