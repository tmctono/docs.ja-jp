---
title: 構造体
description: F# 構造体について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: 1e9652cc4776e4d1d52eb20e41b6dd87a6c5ba05
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401125"
---
# <a name="structures"></a><span data-ttu-id="9e252-103">構造体</span><span class="sxs-lookup"><span data-stu-id="9e252-103">Structures</span></span>

<span data-ttu-id="9e252-104">*構造体*は、データ量が少なく単純な動作を持つ型のクラスよりも効率的なコンパクト オブジェクト型です。</span><span class="sxs-lookup"><span data-stu-id="9e252-104">A *structure* is a compact object type that can be more efficient than a class for types that have a small amount of data and simple behavior.</span></span>

## <a name="syntax"></a><span data-ttu-id="9e252-105">構文</span><span class="sxs-lookup"><span data-stu-id="9e252-105">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    struct
        type-definition-elements-and-members
    end
// or
[ attributes ]
[<StructAttribute>]
type [accessibility-modifier] type-name =
    type-definition-elements-and-members
```

## <a name="remarks"></a><span data-ttu-id="9e252-106">解説</span><span class="sxs-lookup"><span data-stu-id="9e252-106">Remarks</span></span>

<span data-ttu-id="9e252-107">構造体は*値型*です。</span><span class="sxs-lookup"><span data-stu-id="9e252-107">Structures are *value types*, which means that they are stored directly on the stack or, when they are used as fields or array elements, inline in the parent type.</span></span> <span data-ttu-id="9e252-108">クラスやレコードとは異なり、構造体のセマンティクスは値渡しです。</span><span class="sxs-lookup"><span data-stu-id="9e252-108">Unlike classes and records, structures have pass-by-value semantics.</span></span> <span data-ttu-id="9e252-109">これは、主にアクセスおよびコピーが頻繁に行われるデータの小規模な集約に有用であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="9e252-109">This means that they are useful primarily for small aggregates of data that are accessed and copied frequently.</span></span>

<span data-ttu-id="9e252-110">上記の構文では、2 つの形式が示されています。</span><span class="sxs-lookup"><span data-stu-id="9e252-110">In the previous syntax, two forms are shown.</span></span> <span data-ttu-id="9e252-111">1 番目のものは軽量構文ではないものの、頻繁に使用されます。これは、`struct` キーワードと `end` キーワードを使用する場合に、2 番目のものに出現する `StructAttribute` 属性を省略できるためです。</span><span class="sxs-lookup"><span data-stu-id="9e252-111">The first is not the lightweight syntax, but it is nevertheless frequently used because, when you use the `struct` and `end` keywords, you can omit the `StructAttribute` attribute, which appears in the second form.</span></span> <span data-ttu-id="9e252-112">`StructAttribute` は省略して単に `Struct` とすることができます。</span><span class="sxs-lookup"><span data-stu-id="9e252-112">You can abbreviate `StructAttribute` to just `Struct`.</span></span>

<span data-ttu-id="9e252-113">前*の構文の型定義要素とメンバー*は、メンバーの宣言と定義を表します。</span><span class="sxs-lookup"><span data-stu-id="9e252-113">The *type-definition-elements-and-members* in the previous syntax represents member declarations and definitions.</span></span> <span data-ttu-id="9e252-114">構造体にはコンス トラクター、可変フィールド、および不変フィールドを含めることができ、メンバーとインターフェイス実装を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="9e252-114">Structures can have constructors and mutable and immutable fields, and they can declare members and interface implementations.</span></span> <span data-ttu-id="9e252-115">詳細については、「[メンバー](./members/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e252-115">For more information, see [Members](./members/index.md).</span></span>

<span data-ttu-id="9e252-116">構造体は、継承に参加することも、`let` または `do` バインディングを含めることも、それ自身の型のフィールドを再帰的に含めることもできません (ただし、それ自身の型を参照する参照セルを含めることができます)。</span><span class="sxs-lookup"><span data-stu-id="9e252-116">Structures cannot participate in inheritance, cannot contain `let` or `do` bindings, and cannot recursively contain fields of their own type (although they can contain reference cells that reference their own type).</span></span>

<span data-ttu-id="9e252-117">構造体では `let` バインディングは使用できないため、`val` キーワードを使用して構造体のフィールドを宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e252-117">Because structures do not allow `let` bindings, you must declare fields in structures by using the `val` keyword.</span></span> <span data-ttu-id="9e252-118">`val` キーワードではフィールドとその型が定義されますが、初期化は実行できません。</span><span class="sxs-lookup"><span data-stu-id="9e252-118">The `val` keyword defines a field and its type but does not allow initialization.</span></span> <span data-ttu-id="9e252-119">代わりに、`val` 宣言がゼロまたは null に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="9e252-119">Instead, `val` declarations are initialized to zero or null.</span></span> <span data-ttu-id="9e252-120">このため、暗黙のコンストラクター (宣言で構造体名の直後に指定されるパラメーター) を含む構造体では、`val` 宣言に `DefaultValue` 属性で注釈を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e252-120">For this reason, structures that have an implicit constructor (that is, parameters that are given immediately after the structure name in the declaration) require that `val` declarations be annotated with the `DefaultValue` attribute.</span></span> <span data-ttu-id="9e252-121">定義されたコンストラクターを含む構造体でも、ゼロ初期化がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9e252-121">Structures that have a defined constructor still support zero-initialization.</span></span> <span data-ttu-id="9e252-122">したがって、`DefaultValue` 属性は、このようなゼロ値がフィールドに対して有効であることの宣言になります。</span><span class="sxs-lookup"><span data-stu-id="9e252-122">Therefore, the `DefaultValue` attribute is a declaration that such a zero value is valid for the field.</span></span> <span data-ttu-id="9e252-123">構造体の暗黙的なコンストラクターでは動作は実行されません。これは、`let` バインディングと `do` バインディングがその型では許可されていないためですが、渡された暗黙のコンストラクターのパラメーター値はプライベート フィールドとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="9e252-123">Implicit constructors for structures do not perform any actions because `let` and `do` bindings aren’t allowed on the type, but the implicit constructor parameter values passed in are available as private fields.</span></span>

<span data-ttu-id="9e252-124">明示的なコンストラクターにフィールド値の初期化が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9e252-124">Explicit constructors might involve initialization of field values.</span></span> <span data-ttu-id="9e252-125">明示的なコンストラクターを含む構造体がある場合も、ゼロ初期化がサポートされます。ただし、明示的なコンストラクターと競合するため、`DefaultValue` 宣言では `val` 属性を使用しません。</span><span class="sxs-lookup"><span data-stu-id="9e252-125">When you have a structure that has an explicit constructor, it still supports zero-initialization; however, you do not use the `DefaultValue` attribute on the `val` declarations because it conflicts with the explicit constructor.</span></span> <span data-ttu-id="9e252-126">宣言の詳細`val`については、「[明示的なフィールド:`val`キーワード](./members/explicit-fields-the-val-keyword.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e252-126">For more information about `val` declarations, see [Explicit Fields: The `val` Keyword](./members/explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="9e252-127">構造体では属性およびアクセシビリティ修飾子が許可されており、その他の型と同じ規則に従います。</span><span class="sxs-lookup"><span data-stu-id="9e252-127">Attributes and accessibility modifiers are allowed on structures, and follow the same rules as those for other types.</span></span> <span data-ttu-id="9e252-128">詳細については、「[属性](attributes.md)と[アクセス制御](access-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e252-128">For more information, see [Attributes](attributes.md) and [Access Control](access-control.md).</span></span>

<span data-ttu-id="9e252-129">次のコード例は構造体の定義を示しています。</span><span class="sxs-lookup"><span data-stu-id="9e252-129">The following code examples illustrate structure definitions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="byreflike-structs"></a><span data-ttu-id="9e252-130">構造体</span><span class="sxs-lookup"><span data-stu-id="9e252-130">ByRefLike structs</span></span>

<span data-ttu-id="9e252-131">like セマンティクスに`byref`準拠できる独自の構造体を定義できます。 [Byrefs](byrefs.md)</span><span class="sxs-lookup"><span data-stu-id="9e252-131">You can define your own structs that can adhere to `byref`-like semantics: see [Byrefs](byrefs.md) for more information.</span></span> <span data-ttu-id="9e252-132">これは<xref:System.Runtime.CompilerServices.IsByRefLikeAttribute>属性で行われます。</span><span class="sxs-lookup"><span data-stu-id="9e252-132">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="9e252-133">`IsByRefLike`は を`Struct`意味しません。</span><span class="sxs-lookup"><span data-stu-id="9e252-133">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="9e252-134">両方とも型に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e252-134">Both must be present on the type.</span></span>

<span data-ttu-id="9e252-135">F#`byref`の "-like" 構造体は、スタックにバインドされた値型です。</span><span class="sxs-lookup"><span data-stu-id="9e252-135">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="9e252-136">マネージ ヒープには割り当てが行きまとい。</span><span class="sxs-lookup"><span data-stu-id="9e252-136">It is never allocated on the managed heap.</span></span> <span data-ttu-id="9e252-137">`byref`-like 構造体は、有効期間と非キャプチャに関する強力なチェックのセットで実施される、高性能プログラミングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9e252-137">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="9e252-138">ルールは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9e252-138">The rules are:</span></span>

- <span data-ttu-id="9e252-139">関数パラメーター、メソッドパラメーター、ローカル変数、メソッドの戻り値として使用できます。</span><span class="sxs-lookup"><span data-stu-id="9e252-139">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
- <span data-ttu-id="9e252-140">クラスの静的メンバーまたはインスタンス メンバー、または通常の構造体にはできません。</span><span class="sxs-lookup"><span data-stu-id="9e252-140">They cannot be static or instance members of a class or normal struct.</span></span>
- <span data-ttu-id="9e252-141">これらの関数は、どのクロージャ構造`async`(メソッドまたはラムダ式) でもキャプチャできません。</span><span class="sxs-lookup"><span data-stu-id="9e252-141">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
- <span data-ttu-id="9e252-142">ジェネリック パラメーターとして使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="9e252-142">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="9e252-143">これらのルールは、使用を非常に強く制限しますが、安全な方法で高性能コンピューティングの約束を果たすために行います。</span><span class="sxs-lookup"><span data-stu-id="9e252-143">Although these rules very strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="readonly-structs"></a><span data-ttu-id="9e252-144">ReadOnly 構造体</span><span class="sxs-lookup"><span data-stu-id="9e252-144">ReadOnly structs</span></span>

<span data-ttu-id="9e252-145">属性を使用して構造体にアコーズを<xref:System.Runtime.CompilerServices.IsReadOnlyAttribute>付けることができます。</span><span class="sxs-lookup"><span data-stu-id="9e252-145">You can annotate structs with the <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> attribute.</span></span> <span data-ttu-id="9e252-146">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9e252-146">For example:</span></span>

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="9e252-147">`IsReadOnly`は を`Struct`意味しません。</span><span class="sxs-lookup"><span data-stu-id="9e252-147">`IsReadOnly` does not imply `Struct`.</span></span> <span data-ttu-id="9e252-148">構造体を持つには、両方`IsReadOnly`を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e252-148">You must add both to have an `IsReadOnly` struct.</span></span>

<span data-ttu-id="9e252-149">この属性を使用すると、F# と C# がそれぞれと`inref<'T>`を扱うように`in ref`知らせるメタデータが生成されます。</span><span class="sxs-lookup"><span data-stu-id="9e252-149">Use of this attribute emits metadata letting F# and C# know to treat it as `inref<'T>` and `in ref`, respectively.</span></span>

<span data-ttu-id="9e252-150">読み取り専用構造体の中で変更可能な値を定義すると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="9e252-150">Defining a mutable value inside of a readonly struct produces an error.</span></span>

## <a name="struct-records-and-discriminated-unions"></a><span data-ttu-id="9e252-151">構造体レコードと判別共用体</span><span class="sxs-lookup"><span data-stu-id="9e252-151">Struct Records and Discriminated Unions</span></span>

<span data-ttu-id="9e252-152">この`[<Struct>]`属性を使用して[、レコード](records.md)および[判別共用体](discriminated-unions.md)を構造体として表すことができます。</span><span class="sxs-lookup"><span data-stu-id="9e252-152">You can represent [Records](records.md) and [Discriminated Unions](discriminated-unions.md) as structs with the `[<Struct>]` attribute.</span></span>  <span data-ttu-id="9e252-153">詳細については、各記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9e252-153">See each article to learn more.</span></span>

## <a name="see-also"></a><span data-ttu-id="9e252-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e252-154">See also</span></span>

- [<span data-ttu-id="9e252-155">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="9e252-155">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="9e252-156">クラス</span><span class="sxs-lookup"><span data-stu-id="9e252-156">Classes</span></span>](classes.md)
- [<span data-ttu-id="9e252-157">レコード</span><span class="sxs-lookup"><span data-stu-id="9e252-157">Records</span></span>](records.md)
- [<span data-ttu-id="9e252-158">メンバー</span><span class="sxs-lookup"><span data-stu-id="9e252-158">Members</span></span>](./members/index.md)
