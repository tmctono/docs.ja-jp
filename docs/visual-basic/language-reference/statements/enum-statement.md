---
title: Enum ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Enum
helpviewer_keywords:
- enumerated constants [Visual Basic]
- Enum statement [Visual Basic]
- Private keyword [Visual Basic], Enum statements
- Public keyword [Visual Basic], in Enum statement
- variables [Visual Basic], enumeration
- constants [Visual Basic], enumerated
ms.assetid: a45e51f1-65ff-48e1-bf32-79130f137377
ms.openlocfilehash: be1780b00b4d58964e1de5ec199cb80dc0f9dba5
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583400"
---
# <a name="enum-statement-visual-basic"></a><span data-ttu-id="d45f1-102">Enum ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d45f1-102">Enum Statement (Visual Basic)</span></span>

<span data-ttu-id="d45f1-103">列挙体を宣言し、そのメンバーの値を定義します。</span><span class="sxs-lookup"><span data-stu-id="d45f1-103">Declares an enumeration and defines the values of its members.</span></span>

## <a name="syntax"></a><span data-ttu-id="d45f1-104">構文</span><span class="sxs-lookup"><span data-stu-id="d45f1-104">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ]  [ Shadows ]
Enum enumerationname [ As datatype ]
   memberlist
End Enum
```

## <a name="parts"></a><span data-ttu-id="d45f1-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="d45f1-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="d45f1-106">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="d45f1-106">Optional.</span></span> <span data-ttu-id="d45f1-107">この列挙に適用される属性のリスト。</span><span class="sxs-lookup"><span data-stu-id="d45f1-107">List of attributes that apply to this enumeration.</span></span> <span data-ttu-id="d45f1-108">[属性リスト](../../../visual-basic/language-reference/statements/attribute-list.md)は山かっこ ("`<`" と "`>`") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="d45f1-108">You must enclose the [attribute list](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>

  <span data-ttu-id="d45f1-109">@No__t_0 属性は、列挙体のインスタンスの値に複数の列挙体メンバーを含めることができ、各メンバーが列挙値のビットフィールドを表すことができることを示します。</span><span class="sxs-lookup"><span data-stu-id="d45f1-109">The <xref:System.FlagsAttribute> attribute indicates that the value of an instance of the enumeration can include multiple enumeration members, and that each member represents a bit field in the enumeration value.</span></span>

- `accessmodifier`

  <span data-ttu-id="d45f1-110">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="d45f1-110">Optional.</span></span> <span data-ttu-id="d45f1-111">この列挙体にアクセスできるコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="d45f1-111">Specifies what code can access this enumeration.</span></span> <span data-ttu-id="d45f1-112">次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="d45f1-112">Can be one of the following:</span></span>

  - [<span data-ttu-id="d45f1-113">Public</span><span class="sxs-lookup"><span data-stu-id="d45f1-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)

  - [<span data-ttu-id="d45f1-114">Protected</span><span class="sxs-lookup"><span data-stu-id="d45f1-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)

  - [<span data-ttu-id="d45f1-115">Friend</span><span class="sxs-lookup"><span data-stu-id="d45f1-115">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)

  - [<span data-ttu-id="d45f1-116">Private</span><span class="sxs-lookup"><span data-stu-id="d45f1-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)

  - [<span data-ttu-id="d45f1-117">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="d45f1-117">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

  - [<span data-ttu-id="d45f1-118">Private Protected</span><span class="sxs-lookup"><span data-stu-id="d45f1-118">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

- `Shadows`

  <span data-ttu-id="d45f1-119">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="d45f1-119">Optional.</span></span> <span data-ttu-id="d45f1-120">この列挙体が、基底クラスで同じ名前を持つプログラミング要素、またはオーバーロードされた要素のセットを直しして非表示にすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="d45f1-120">Specifies that this enumeration redeclares and hides an identically named programming element, or set of overloaded elements, in a base class.</span></span> <span data-ttu-id="d45f1-121">[Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)は、そのメンバーではなく、列挙自体にのみ指定できます。</span><span class="sxs-lookup"><span data-stu-id="d45f1-121">You can specify [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) only on the enumeration itself, not on any of its members.</span></span>

- `enumerationname`

  <span data-ttu-id="d45f1-122">必須です。</span><span class="sxs-lookup"><span data-stu-id="d45f1-122">Required.</span></span> <span data-ttu-id="d45f1-123">列挙体の名前。</span><span class="sxs-lookup"><span data-stu-id="d45f1-123">Name of the enumeration.</span></span> <span data-ttu-id="d45f1-124">有効な名前の詳細については、「宣言された[要素名](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d45f1-124">For information on valid names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

- `datatype`

  <span data-ttu-id="d45f1-125">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="d45f1-125">Optional.</span></span> <span data-ttu-id="d45f1-126">列挙型とそのすべてのメンバーのデータ型。</span><span class="sxs-lookup"><span data-stu-id="d45f1-126">Data type of the enumeration and all its members.</span></span>

- `memberlist`

  <span data-ttu-id="d45f1-127">必須です。</span><span class="sxs-lookup"><span data-stu-id="d45f1-127">Required.</span></span> <span data-ttu-id="d45f1-128">このステートメントで宣言されているメンバー定数の一覧。</span><span class="sxs-lookup"><span data-stu-id="d45f1-128">List of member constants being declared in this statement.</span></span> <span data-ttu-id="d45f1-129">個々のソースコード行に複数のメンバーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d45f1-129">Multiple members appear on individual source code lines.</span></span>

  <span data-ttu-id="d45f1-130">各 `member` には、次の構文と部分があります。 `[<attribute list>] member name [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="d45f1-130">Each `member` has the following syntax and parts: `[<attribute list>] member name [ = initializer ]`</span></span>

  |<span data-ttu-id="d45f1-131">パーツ</span><span class="sxs-lookup"><span data-stu-id="d45f1-131">Part</span></span>|<span data-ttu-id="d45f1-132">説明</span><span class="sxs-lookup"><span data-stu-id="d45f1-132">Description</span></span>|
  |---|---|
  |`membername`|<span data-ttu-id="d45f1-133">必須です。</span><span class="sxs-lookup"><span data-stu-id="d45f1-133">Required.</span></span> <span data-ttu-id="d45f1-134">このメンバーの名前。</span><span class="sxs-lookup"><span data-stu-id="d45f1-134">Name of this member.</span></span>|
  |`initializer`|<span data-ttu-id="d45f1-135">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="d45f1-135">Optional.</span></span> <span data-ttu-id="d45f1-136">コンパイル時に評価され、このメンバーに割り当てられる式。</span><span class="sxs-lookup"><span data-stu-id="d45f1-136">Expression that is evaluated at compile time and assigned to this member.</span></span>|

- <span data-ttu-id="d45f1-137">`End` `Enum`</span><span class="sxs-lookup"><span data-stu-id="d45f1-137">`End` `Enum`</span></span>

  <span data-ttu-id="d45f1-138">`Enum` ブロックを終了します。</span><span class="sxs-lookup"><span data-stu-id="d45f1-138">Terminates the `Enum` block.</span></span>

## <a name="remarks"></a><span data-ttu-id="d45f1-139">Remarks</span><span class="sxs-lookup"><span data-stu-id="d45f1-139">Remarks</span></span>

<span data-ttu-id="d45f1-140">論理的に相互に関連付けられている変化しない値のセットがある場合は、それらを列挙体でまとめて定義できます。</span><span class="sxs-lookup"><span data-stu-id="d45f1-140">If you have a set of unchanging values that are logically related to each other, you can define them together in an enumeration.</span></span> <span data-ttu-id="d45f1-141">これにより、列挙体とそのメンバーにわかりやすい名前が提供され、その値よりも覚えやすくなります。</span><span class="sxs-lookup"><span data-stu-id="d45f1-141">This provides meaningful names for the enumeration and its members, which are easier to remember than their values.</span></span> <span data-ttu-id="d45f1-142">その後、コード内のさまざまな場所で列挙メンバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d45f1-142">You can then use the enumeration members in many places in your code.</span></span>

<span data-ttu-id="d45f1-143">列挙を使用する利点は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d45f1-143">The benefits of using enumerations include the following:</span></span>

- <span data-ttu-id="d45f1-144">数値の転置またはミスによって発生するエラーを減らします。</span><span class="sxs-lookup"><span data-stu-id="d45f1-144">Reduces errors caused by transposing or mistyping numbers.</span></span>

- <span data-ttu-id="d45f1-145">では、将来の値の変更が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="d45f1-145">Makes it easy to change values in the future.</span></span>

- <span data-ttu-id="d45f1-146">コードを読みやすくするため、エラーが発生する可能性は低くなります。</span><span class="sxs-lookup"><span data-stu-id="d45f1-146">Makes code easier to read, which means it is less likely that errors will be introduced.</span></span>

- <span data-ttu-id="d45f1-147">上位互換性を確保します。</span><span class="sxs-lookup"><span data-stu-id="d45f1-147">Ensures forward compatibility.</span></span> <span data-ttu-id="d45f1-148">列挙型を使用する場合、後でメンバー名に対応する値を変更すると、コードが失敗する可能性は低くなります。</span><span class="sxs-lookup"><span data-stu-id="d45f1-148">If you use enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>

<span data-ttu-id="d45f1-149">列挙体には、名前、基になるデータ型、およびメンバーのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d45f1-149">An enumeration has a name, an underlying data type, and a set of members.</span></span> <span data-ttu-id="d45f1-150">各メンバーは定数を表します。</span><span class="sxs-lookup"><span data-stu-id="d45f1-150">Each member represents a constant.</span></span>

<span data-ttu-id="d45f1-151">プロシージャ以外のクラス、構造体、モジュール、またはインターフェイスレベルで宣言された列挙型は、*メンバー列挙*型です。</span><span class="sxs-lookup"><span data-stu-id="d45f1-151">An enumeration declared at class, structure, module, or interface level, outside any procedure, is a *member enumeration*.</span></span> <span data-ttu-id="d45f1-152">これは、それを宣言するクラス、構造体、モジュール、またはインターフェイスのメンバーです。</span><span class="sxs-lookup"><span data-stu-id="d45f1-152">It is a member of the class, structure, module, or interface that declares it.</span></span>

<span data-ttu-id="d45f1-153">メンバー列挙体には、クラス、構造体、モジュール、またはインターフェイス内のどこからでもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d45f1-153">Member enumerations can be accessed from anywhere within their class, structure, module, or interface.</span></span> <span data-ttu-id="d45f1-154">クラス、構造体、またはモジュールの外部のコードでは、メンバーの列挙体の名前を、そのクラス、構造体、またはモジュールの名前で修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d45f1-154">Code outside a class, structure, or module must qualify a member enumeration's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="d45f1-155">[インポート](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)ステートメントをソースファイルに追加することで、完全修飾名を使用する必要がないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="d45f1-155">You can avoid the need to use fully qualified names by adding an [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) statement to the source file.</span></span>

<span data-ttu-id="d45f1-156">名前空間レベルで、任意のクラス、構造体、モジュール、またはインターフェイスの外側で宣言された列挙型は、それが出現する名前空間のメンバーになります。</span><span class="sxs-lookup"><span data-stu-id="d45f1-156">An enumeration declared at namespace level, outside any class, structure, module, or interface, is a member of the namespace in which it appears.</span></span>

<span data-ttu-id="d45f1-157">列挙体の*宣言コンテキスト*は、ソースファイル、名前空間、クラス、構造体、モジュール、またはインターフェイスである必要があり、プロシージャにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d45f1-157">The *declaration context* for an enumeration must be a source file, namespace, class, structure, module, or interface, and cannot be a procedure.</span></span> <span data-ttu-id="d45f1-158">詳細については、「[宣言コンテキストと既定のアクセス レベル](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d45f1-158">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="d45f1-159">列挙体全体に属性を適用することはできますが、メンバーには個別には適用できません。</span><span class="sxs-lookup"><span data-stu-id="d45f1-159">You can apply attributes to an enumeration as a whole, but not to its members individually.</span></span> <span data-ttu-id="d45f1-160">属性は、アセンブリのメタデータに情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d45f1-160">An attribute contributes information to the assembly's metadata.</span></span>

## <a name="data-type"></a><span data-ttu-id="d45f1-161">データの種類</span><span class="sxs-lookup"><span data-stu-id="d45f1-161">Data Type</span></span>

<span data-ttu-id="d45f1-162">@No__t_0 ステートメントでは、列挙体のデータ型を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="d45f1-162">The `Enum` statement can declare the data type of an enumeration.</span></span> <span data-ttu-id="d45f1-163">各メンバーは、列挙体のデータ型を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d45f1-163">Each member takes the enumeration's data type.</span></span> <span data-ttu-id="d45f1-164">@No__t_0、`Integer`、`Long`、`SByte`、`Short`、`UInteger`、`ULong`、`UShort` を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d45f1-164">You can specify `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort`.</span></span>

<span data-ttu-id="d45f1-165">列挙に `datatype` を指定しない場合、各メンバーはその `initializer` のデータ型を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d45f1-165">If you do not specify `datatype` for the enumeration, each member takes the data type of its `initializer`.</span></span> <span data-ttu-id="d45f1-166">@No__t_0 と `initializer` の両方を指定する場合、`initializer` のデータ型は `datatype` に変換可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d45f1-166">If you specify both `datatype` and `initializer`, the data type of `initializer` must be convertible to `datatype`.</span></span> <span data-ttu-id="d45f1-167">@No__t_0 も `initializer` も存在しない場合、データ型は既定で `Integer` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d45f1-167">If neither `datatype` nor `initializer` is present, the data type defaults to `Integer`.</span></span>

## <a name="initializing-members"></a><span data-ttu-id="d45f1-168">メンバーの初期化</span><span class="sxs-lookup"><span data-stu-id="d45f1-168">Initializing Members</span></span>

<span data-ttu-id="d45f1-169">@No__t_0 ステートメントで `memberlist` で選択したメンバーの内容を初期化できます。</span><span class="sxs-lookup"><span data-stu-id="d45f1-169">The `Enum` statement can initialize the contents of selected members in `memberlist`.</span></span> <span data-ttu-id="d45f1-170">@No__t_0 を使用して、メンバーに割り当てられる式を指定します。</span><span class="sxs-lookup"><span data-stu-id="d45f1-170">You use `initializer` to supply an expression to be assigned to the member.</span></span>

<span data-ttu-id="d45f1-171">メンバーに `initializer` を指定しなかった場合は、Visual Basic 0 (`memberlist` の最初の `member`)、または直前の `member` の値より大きい値に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="d45f1-171">If you do not specify `initializer` for a member, Visual Basic initializes it either to zero (if it is the first `member` in `memberlist`), or to a value greater by one than that of the immediately preceding `member`.</span></span>

<span data-ttu-id="d45f1-172">各 `initializer` に用意されている式には、リテラル、既に定義されている他の定数、およびこの列挙の前のメンバーを含む定義済みの列挙型メンバーの任意の組み合わせを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d45f1-172">The expression supplied in each `initializer` can be any combination of literals, other constants that are already defined, and enumeration members that are already defined, including a previous member of this enumeration.</span></span> <span data-ttu-id="d45f1-173">算術演算子と論理演算子を使用すると、このような要素を組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="d45f1-173">You can use arithmetic and logical operators to combine such elements.</span></span>

<span data-ttu-id="d45f1-174">@No__t_0 では、変数または関数を使用できません。</span><span class="sxs-lookup"><span data-stu-id="d45f1-174">You cannot use variables or functions in `initializer`.</span></span> <span data-ttu-id="d45f1-175">ただし、`CByte` や `CShort` などの変換キーワードを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d45f1-175">However, you can use conversion keywords such as `CByte` and `CShort`.</span></span> <span data-ttu-id="d45f1-176">定数 `String` または `Char` 引数を使用して呼び出す場合は、コンパイル時に評価できるため、`AscW` を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d45f1-176">You can also use `AscW` if you call it with a constant `String` or `Char` argument, since that can be evaluated at compile time.</span></span>

<span data-ttu-id="d45f1-177">列挙体に浮動小数点値を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="d45f1-177">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="d45f1-178">メンバーに浮動小数点値が割り当てられていて `Option Strict` が on に設定されている場合、コンパイラエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="d45f1-178">If a member is assigned a floating-point value and `Option Strict` is set to on, a compiler error occurs.</span></span> <span data-ttu-id="d45f1-179">@No__t_0 がオフの場合、値は自動的に `Enum` の種類に変換されます。</span><span class="sxs-lookup"><span data-stu-id="d45f1-179">If `Option Strict` is off, the value is automatically converted to the `Enum` type.</span></span>

<span data-ttu-id="d45f1-180">メンバーの値が、基になるデータ型で許容される範囲を超えている場合、またはメンバーが基になるデータ型で許容される最大値に初期化されている場合、コンパイラはエラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="d45f1-180">If the value of a member exceeds the allowable range for the underlying data type, or if you initialize any member to the maximum value allowed by the underlying data type, the compiler reports an error.</span></span>

## <a name="modifiers"></a><span data-ttu-id="d45f1-181">修飾子</span><span class="sxs-lookup"><span data-stu-id="d45f1-181">Modifiers</span></span>

<span data-ttu-id="d45f1-182">クラス、構造体、モジュール、およびインターフェイスメンバーの列挙型は、既定でパブリックアクセスに設定されています。</span><span class="sxs-lookup"><span data-stu-id="d45f1-182">Class, structure, module, and interface member enumerations default to public access.</span></span> <span data-ttu-id="d45f1-183">アクセス修飾子を使用してこれらのアクセス レベルを調整できます。</span><span class="sxs-lookup"><span data-stu-id="d45f1-183">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="d45f1-184">名前空間メンバーの列挙は、既定で friend アクセスに設定されています。</span><span class="sxs-lookup"><span data-stu-id="d45f1-184">Namespace member enumerations default to friend access.</span></span> <span data-ttu-id="d45f1-185">アクセスレベルはパブリックに調整できますが、プライベートまたは保護することはできません。</span><span class="sxs-lookup"><span data-stu-id="d45f1-185">You can adjust their access levels to public, but not to private or protected.</span></span> <span data-ttu-id="d45f1-186">詳細については、「 [Visual Basic のアクセスレベル](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d45f1-186">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="d45f1-187">すべての列挙メンバーにはパブリックアクセスがあり、それらのメンバーに対してアクセス修飾子を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d45f1-187">All enumeration members have public access, and you cannot use any access modifiers on them.</span></span> <span data-ttu-id="d45f1-188">ただし、列挙自体のアクセスレベルがより制限されている場合は、指定された列挙アクセスレベルが優先されます。</span><span class="sxs-lookup"><span data-stu-id="d45f1-188">However, if the enumeration itself has a more restricted access level, the specified enumeration access level takes precedence.</span></span>

<span data-ttu-id="d45f1-189">既定では、すべての列挙型とそのフィールドは定数です。</span><span class="sxs-lookup"><span data-stu-id="d45f1-189">By default, all enumerations are types and their fields are constants.</span></span> <span data-ttu-id="d45f1-190">したがって、列挙型またはそのメンバーを宣言するときに、`Shared`、`Static`、および `ReadOnly` キーワードを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d45f1-190">Therefore the `Shared`, `Static`, and `ReadOnly` keywords cannot be used when declaring an enumeration or its members.</span></span>

## <a name="assigning-multiple-values"></a><span data-ttu-id="d45f1-191">複数の値の割り当て</span><span class="sxs-lookup"><span data-stu-id="d45f1-191">Assigning Multiple Values</span></span>

<span data-ttu-id="d45f1-192">列挙型は、通常、相互に排他的な値を表します。</span><span class="sxs-lookup"><span data-stu-id="d45f1-192">Enumerations typically represent mutually exclusive values.</span></span> <span data-ttu-id="d45f1-193">@No__t_1 宣言に <xref:System.FlagsAttribute> 属性を含めることにより、複数の値を列挙型のインスタンスに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d45f1-193">By including the <xref:System.FlagsAttribute> attribute in the `Enum` declaration, you can instead assign multiple values to an instance of the enumeration.</span></span> <span data-ttu-id="d45f1-194">@No__t_0 属性は、列挙型をビットフィールド、つまりフラグのセットとして扱うことを指定します。</span><span class="sxs-lookup"><span data-stu-id="d45f1-194">The <xref:System.FlagsAttribute> attribute specifies that the enumeration be treated as a bit field, that is, a set of flags.</span></span> <span data-ttu-id="d45f1-195">これらは*ビットごと*の列挙体と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="d45f1-195">These are called *bitwise* enumerations.</span></span>

<span data-ttu-id="d45f1-196">@No__t_0 属性を使用して列挙体を宣言する場合は、値に対して2の累乗 (1、2、4、8、16など) を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d45f1-196">When you declare an enumeration by using the <xref:System.FlagsAttribute> attribute, we recommend that you use powers of 2, that is, 1, 2, 4, 8, 16, and so on, for the values.</span></span> <span data-ttu-id="d45f1-197">また、"None" は、値が0のメンバーの名前にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d45f1-197">We also recommend that "None" be the name of a member whose value is 0.</span></span> <span data-ttu-id="d45f1-198">その他のガイドラインについては、「<xref:System.FlagsAttribute>」および「<xref:System.Enum>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d45f1-198">For additional guidelines, see <xref:System.FlagsAttribute> and <xref:System.Enum>.</span></span>

## <a name="example"></a><span data-ttu-id="d45f1-199">例</span><span class="sxs-lookup"><span data-stu-id="d45f1-199">Example</span></span>

<span data-ttu-id="d45f1-200">`Enum` ステートメントを使用する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d45f1-200">The following example shows how to use the `Enum` statement.</span></span> <span data-ttu-id="d45f1-201">メンバーは、`Medium` ではなく `EggSizeEnum.Medium` と呼ばれることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d45f1-201">Note that the member is referred to as `EggSizeEnum.Medium`, and not as `Medium`.</span></span>

[!code-vb[VbEnumsTask#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#41)]

## <a name="example"></a><span data-ttu-id="d45f1-202">例</span><span class="sxs-lookup"><span data-stu-id="d45f1-202">Example</span></span>

<span data-ttu-id="d45f1-203">次の例のメソッドは、`Egg` クラスの外側にあります。</span><span class="sxs-lookup"><span data-stu-id="d45f1-203">The method in the following example is outside the `Egg` class.</span></span> <span data-ttu-id="d45f1-204">したがって、`EggSizeEnum` は完全に `Egg.EggSizeEnum` として修飾されます。</span><span class="sxs-lookup"><span data-stu-id="d45f1-204">Therefore, `EggSizeEnum` is fully qualified as `Egg.EggSizeEnum`.</span></span>

[!code-vb[VbEnumsTask#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#42)]

## <a name="example"></a><span data-ttu-id="d45f1-205">例</span><span class="sxs-lookup"><span data-stu-id="d45f1-205">Example</span></span>

<span data-ttu-id="d45f1-206">次の例では、`Enum` ステートメントを使用して、関連する一連の名前付き定数値を定義します。</span><span class="sxs-lookup"><span data-stu-id="d45f1-206">The following example uses the `Enum` statement to define a related set of named constant values.</span></span> <span data-ttu-id="d45f1-207">この場合、値は、データベースのデータ入力フォームをデザインするために選択できる色です。</span><span class="sxs-lookup"><span data-stu-id="d45f1-207">In this case, the values are colors you might choose to design data entry forms for a database.</span></span>

[!code-vb[VbEnumsTask#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#30)]

## <a name="example"></a><span data-ttu-id="d45f1-208">例</span><span class="sxs-lookup"><span data-stu-id="d45f1-208">Example</span></span>

<span data-ttu-id="d45f1-209">次の例は、正と負の両方の値を含む値を示しています。</span><span class="sxs-lookup"><span data-stu-id="d45f1-209">The following example shows values that include both positive and negative numbers.</span></span>

[!code-vb[VbEnumsTask#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#31)]

## <a name="example"></a><span data-ttu-id="d45f1-210">例</span><span class="sxs-lookup"><span data-stu-id="d45f1-210">Example</span></span>

<span data-ttu-id="d45f1-211">次の例では、`As` 句を使用して、列挙型の `datatype` を指定しています。</span><span class="sxs-lookup"><span data-stu-id="d45f1-211">In the following example, an `As` clause is used to specify the `datatype` of an enumeration.</span></span>

[!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]

## <a name="example"></a><span data-ttu-id="d45f1-212">例</span><span class="sxs-lookup"><span data-stu-id="d45f1-212">Example</span></span>

<span data-ttu-id="d45f1-213">ビットごとの列挙体を使用する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="d45f1-213">The following example shows how to use a bitwise enumeration.</span></span> <span data-ttu-id="d45f1-214">ビットごとの列挙体のインスタンスに複数の値を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d45f1-214">Multiple values can be assigned to an instance of a bitwise enumeration.</span></span> <span data-ttu-id="d45f1-215">@No__t_0 宣言には <xref:System.FlagsAttribute> 属性が含まれています。これは、列挙体をフラグのセットとして処理できることを示します。</span><span class="sxs-lookup"><span data-stu-id="d45f1-215">The `Enum` declaration includes the <xref:System.FlagsAttribute> attribute, which indicates that the enumeration can be treated as a set of flags.</span></span>

[!code-vb[VbEnumsTask#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#61)]

## <a name="example"></a><span data-ttu-id="d45f1-216">例</span><span class="sxs-lookup"><span data-stu-id="d45f1-216">Example</span></span>

<span data-ttu-id="d45f1-217">次の例では、列挙体を反復処理します。</span><span class="sxs-lookup"><span data-stu-id="d45f1-217">The following example iterates through an enumeration.</span></span> <span data-ttu-id="d45f1-218">@No__t_0 メソッドを使用して、列挙からメンバー名の配列を取得し、<xref:System.Enum.GetValues%2A> してメンバー値の配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="d45f1-218">It uses the <xref:System.Enum.GetNames%2A> method to retrieve an array of member names from the enumeration, and <xref:System.Enum.GetValues%2A> to retrieve an array of member values.</span></span>

[!code-vb[VbEnumsTask#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#51)]

## <a name="see-also"></a><span data-ttu-id="d45f1-219">関連項目</span><span class="sxs-lookup"><span data-stu-id="d45f1-219">See also</span></span>

- <xref:System.Enum>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [<span data-ttu-id="d45f1-220">Const ステートメント</span><span class="sxs-lookup"><span data-stu-id="d45f1-220">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="d45f1-221">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="d45f1-221">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="d45f1-222">暗黙の型変換と明示的な型変換</span><span class="sxs-lookup"><span data-stu-id="d45f1-222">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="d45f1-223">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="d45f1-223">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="d45f1-224">定数と列挙体</span><span class="sxs-lookup"><span data-stu-id="d45f1-224">Constants and Enumerations</span></span>](../../../visual-basic/language-reference/constants-and-enumerations.md)
