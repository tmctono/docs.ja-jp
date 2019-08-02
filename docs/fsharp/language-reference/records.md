---
title: レコード
description: レコードがF#名前付きの値の単純な集計を表す方法について説明します。メンバーを使用することもできます。
ms.date: 06/09/2019
ms.openlocfilehash: d92a1a7517e5b05ee687926df29f33fab123b4dd
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627286"
---
# <a name="records"></a><span data-ttu-id="80972-103">レコード</span><span class="sxs-lookup"><span data-stu-id="80972-103">Records</span></span>

<span data-ttu-id="80972-104">レコードは、名前付きの値の単純な集合を表しており、オプションでメンバーを含みます。</span><span class="sxs-lookup"><span data-stu-id="80972-104">Records represent simple aggregates of named values, optionally with members.</span></span> <span data-ttu-id="80972-105">構造体と参照型のどちらでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="80972-105">They can either be structs or reference types.</span></span>  <span data-ttu-id="80972-106">既定では、これらは参照型です。</span><span class="sxs-lookup"><span data-stu-id="80972-106">They are reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="80972-107">構文</span><span class="sxs-lookup"><span data-stu-id="80972-107">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] typename =
    { [ mutable ] label1 : type1;
      [ mutable ] label2 : type2;
      ... }
    [ member-list ]
```

## <a name="remarks"></a><span data-ttu-id="80972-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="80972-108">Remarks</span></span>

<span data-ttu-id="80972-109">前の構文では、 *typename*はレコード型の名前、 *label1*と*label2*は*ラベル*と呼ばれる値の名前、type1 と*type1*はこれらの値の型です。</span><span class="sxs-lookup"><span data-stu-id="80972-109">In the previous syntax, *typename* is the name of the record type, *label1* and *label2* are names of values, referred to as *labels*, and *type1* and *type2* are the types of these values.</span></span> <span data-ttu-id="80972-110">*メンバーリスト*は、型のメンバーの省略可能なリストです。</span><span class="sxs-lookup"><span data-stu-id="80972-110">*member-list* is the optional list of members for the type.</span></span>  <span data-ttu-id="80972-111">属性を使用し`[<Struct>]`て、参照型であるレコードではなく、構造体レコードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="80972-111">You can use the `[<Struct>]` attribute to create a struct record rather than a record which is a reference type.</span></span>

<span data-ttu-id="80972-112">次に例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="80972-112">Following are some examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1901.fs)]

<span data-ttu-id="80972-113">各ラベルが個別の行にある場合、セミコロンは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="80972-113">When each label is on a separate line, the semicolon is optional.</span></span>

<span data-ttu-id="80972-114">*レコード式*と呼ばれる式に値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="80972-114">You can set values in expressions known as *record expressions*.</span></span> <span data-ttu-id="80972-115">コンパイラは、使用されているラベルから型を推測します (ラベルが他のレコードの種類とは十分に異なる場合)。</span><span class="sxs-lookup"><span data-stu-id="80972-115">The compiler infers the type from the labels used (if the labels are sufficiently distinct from those of other record types).</span></span> <span data-ttu-id="80972-116">中かっこ ({}) は、レコード式を囲みます。</span><span class="sxs-lookup"><span data-stu-id="80972-116">Braces ({ }) enclose the record expression.</span></span> <span data-ttu-id="80972-117">次のコードは、 `x` `y`とと`z`いうラベルを持つ3つの float 要素を持つレコードを初期化するレコード式を示しています。</span><span class="sxs-lookup"><span data-stu-id="80972-117">The following code shows a record expression that initializes a record with three float elements with labels `x`, `y` and `z`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1907.fs)]

<span data-ttu-id="80972-118">同じラベルを持つ別の型が存在する可能性がある場合は、短縮形を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="80972-118">Do not use the shortened form if there could be another type that also has the same labels.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1903.fs)]

<span data-ttu-id="80972-119">最後に宣言された型のラベルは、以前に宣言された型よりも`mypoint3D` `Point3D`優先されます。したがって、前の例では、はと推論されます。</span><span class="sxs-lookup"><span data-stu-id="80972-119">The labels of the most recently declared type take precedence over those of the previously declared type, so in the preceding example, `mypoint3D` is inferred to be `Point3D`.</span></span> <span data-ttu-id="80972-120">レコードの種類は、次のコードのように明示的に指定できます。</span><span class="sxs-lookup"><span data-stu-id="80972-120">You can explicitly specify the record type, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1908.fs)]

<span data-ttu-id="80972-121">メソッドは、クラス型の場合と同様に、レコード型に対して定義できます。</span><span class="sxs-lookup"><span data-stu-id="80972-121">Methods can be defined for record types just as for class types.</span></span>

## <a name="creating-records-by-using-record-expressions"></a><span data-ttu-id="80972-122">レコード式を使用したレコードの作成</span><span class="sxs-lookup"><span data-stu-id="80972-122">Creating Records by Using Record Expressions</span></span>

<span data-ttu-id="80972-123">レコードで定義されているラベルを使用して、レコードを初期化できます。</span><span class="sxs-lookup"><span data-stu-id="80972-123">You can initialize records by using the labels that are defined in the record.</span></span> <span data-ttu-id="80972-124">これを行う式は、*レコード式*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="80972-124">An expression that does this is referred to as a *record expression*.</span></span> <span data-ttu-id="80972-125">中かっこを使用してレコード式を囲み、セミコロンを区切り記号として使用します。</span><span class="sxs-lookup"><span data-stu-id="80972-125">Use braces to enclose the record expression and use the semicolon as a delimiter.</span></span>

<span data-ttu-id="80972-126">次の例では、レコードを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="80972-126">The following example shows how to create a record.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1904.fs)]

<span data-ttu-id="80972-127">レコード式の最後のフィールドの後のセミコロン、および型定義では、フィールドがすべて1行にあるかどうかにかかわらず、省略可能です。</span><span class="sxs-lookup"><span data-stu-id="80972-127">The semicolons after the last field in the record expression and in the type definition are optional, regardless of whether the fields are all in one line.</span></span>

<span data-ttu-id="80972-128">レコードを作成するときは、各フィールドに値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80972-128">When you create a record, you must supply values for each field.</span></span> <span data-ttu-id="80972-129">任意のフィールドについて、初期化式の他のフィールドの値を参照することはできません。</span><span class="sxs-lookup"><span data-stu-id="80972-129">You cannot refer to the values of other fields in the initialization expression for any field.</span></span>

<span data-ttu-id="80972-130">次のコードでは、の`myRecord2`型はフィールドの名前から推論されます。</span><span class="sxs-lookup"><span data-stu-id="80972-130">In the following code, the type of `myRecord2` is inferred from the names of the fields.</span></span> <span data-ttu-id="80972-131">必要に応じて、型名を明示的に指定できます。</span><span class="sxs-lookup"><span data-stu-id="80972-131">Optionally, you can specify the type name explicitly.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="80972-132">別の形式のレコードの構築は、既存のレコードをコピーする必要があり、フィールド値の一部を変更する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="80972-132">Another form of record construction can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span> <span data-ttu-id="80972-133">次のコード行はこれを示しています。</span><span class="sxs-lookup"><span data-stu-id="80972-133">The following line of code illustrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

<span data-ttu-id="80972-134">この形式のレコード式は、レコードの*コピーと更新の式*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="80972-134">This form of the record expression is called the *copy and update record expression*.</span></span>

<span data-ttu-id="80972-135">既定では、レコードは変更できません。ただし、コピーと更新の式を使用して、変更されたレコードを簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="80972-135">Records are immutable by default; however, you can easily create modified records by using a copy and update expression.</span></span> <span data-ttu-id="80972-136">また、変更可能なフィールドを明示的に指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="80972-136">You can also explicitly specify a mutable field.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1909.fs)]

<span data-ttu-id="80972-137">レコードフィールドで DefaultValue 属性を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="80972-137">Don't use the DefaultValue attribute with record fields.</span></span> <span data-ttu-id="80972-138">より適切な方法は、既定値に初期化されるフィールドを持つレコードの既定のインスタンスを定義し、コピーと更新のレコード式を使用して、既定値とは異なるフィールドを設定することです。</span><span class="sxs-lookup"><span data-stu-id="80972-138">A better approach is to define default instances of records with fields that are initialized to default values and then use a copy and update record expression to set any fields that differ from the default values.</span></span>

```fsharp
// Rather than use [<DefaultValue>], define a default record.
type MyRecord =
    { Field1 : int
      Field2 : int }

let defaultRecord1 = { Field1 = 0; Field2 = 0 }
let defaultRecord2 = { Field1 = 1; Field2 = 25 }

// Use the with keyword to populate only a few chosen fields
// and leave the rest with default values.
let rr3 = { defaultRecord1 with Field2 = 42 }
```

## <a name="creating-mutually-recursive-records"></a><span data-ttu-id="80972-139">相互再帰的なレコードの作成</span><span class="sxs-lookup"><span data-stu-id="80972-139">Creating Mutually Recursive Records</span></span>

<span data-ttu-id="80972-140">レコードを作成するときに、後で定義する別の型に依存するように設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="80972-140">Sometime when creating a record, you may want to have it depend on another type that you would like to define afterwards.</span></span> <span data-ttu-id="80972-141">レコードの種類が相互に再帰的に定義されている場合を除き、コンパイルエラーになります。</span><span class="sxs-lookup"><span data-stu-id="80972-141">This is a compile error unless you define the record types to be mutually recursive.</span></span>

<span data-ttu-id="80972-142">同時に再帰的なレコードを定義`and`するには、キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="80972-142">Defining mutually recursive records is done with the `and` keyword.</span></span> <span data-ttu-id="80972-143">これにより、2つ以上のレコードの種類をリンクすることができます。</span><span class="sxs-lookup"><span data-stu-id="80972-143">This lets you link 2 or more record types together.</span></span>

<span data-ttu-id="80972-144">たとえば、次のコードでは、 `Person`と`Address`型が相互に再帰的に定義されています。</span><span class="sxs-lookup"><span data-stu-id="80972-144">For example, the following code defines a `Person` and `Address` type as mutually recursive:</span></span>

```fsharp
// Create a Person type and use the Address type that is not defined
type Person =
  { Name: string
    Age: int
    Address: Address }
// Define the Address type which is used in the Person record
and Address =
  { Line1: string
    Line2: string
    PostCode: string }
```

<span data-ttu-id="80972-145">`and`キーワードを使用せずに前の例を定義すると、コンパイルされません。</span><span class="sxs-lookup"><span data-stu-id="80972-145">If you were to define the previous example without the `and` keyword, then it would not compile.</span></span> <span data-ttu-id="80972-146">相互再帰的な定義にはキーワードが必要です。`and`</span><span class="sxs-lookup"><span data-stu-id="80972-146">The `and` keyword is required for mutually recursive definitions.</span></span>

## <a name="pattern-matching-with-records"></a><span data-ttu-id="80972-147">レコードを使用したパターンマッチ</span><span class="sxs-lookup"><span data-stu-id="80972-147">Pattern Matching with Records</span></span>

<span data-ttu-id="80972-148">レコードは、パターンマッチングで使用できます。</span><span class="sxs-lookup"><span data-stu-id="80972-148">Records can be used with pattern matching.</span></span> <span data-ttu-id="80972-149">一部のフィールドを明示的に指定し、一致が発生したときに割り当てられる他のフィールドの変数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="80972-149">You can specify some fields explicitly and provide variables for other fields that will be assigned when a match occurs.</span></span> <span data-ttu-id="80972-150">これを次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="80972-150">The following code example illustrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1910.fs)]

<span data-ttu-id="80972-151">このコードの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="80972-151">The output of this code is as follows.</span></span>

```
Point is at the origin.
Point is on the x-axis. Value is 100.000000.
Point is at (10.000000, 0.000000, -1.000000).
```

## <a name="differences-between-records-and-classes"></a><span data-ttu-id="80972-152">レコードとクラスの違い</span><span class="sxs-lookup"><span data-stu-id="80972-152">Differences Between Records and Classes</span></span>

<span data-ttu-id="80972-153">レコードフィールドは、プロパティとして自動的に公開され、レコードの作成とコピーに使用されるという点でクラスとは異なります。</span><span class="sxs-lookup"><span data-stu-id="80972-153">Record fields differ from classes in that they are automatically exposed as properties, and they are used in the creation and copying of records.</span></span> <span data-ttu-id="80972-154">レコードの構築も、クラスの構築とは異なります。</span><span class="sxs-lookup"><span data-stu-id="80972-154">Record construction also differs from class construction.</span></span> <span data-ttu-id="80972-155">レコード型では、コンストラクターを定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="80972-155">In a record type, you cannot define a constructor.</span></span> <span data-ttu-id="80972-156">代わりに、このトピックで説明する構築構文が適用されます。</span><span class="sxs-lookup"><span data-stu-id="80972-156">Instead, the construction syntax described in this topic applies.</span></span> <span data-ttu-id="80972-157">クラスには、コンストラクターのパラメーター、フィールド、およびプロパティの間に直接的な関係はありません。</span><span class="sxs-lookup"><span data-stu-id="80972-157">Classes have no direct relationship between constructor parameters, fields, and properties.</span></span>

<span data-ttu-id="80972-158">Union 型や structure 型と同様に、レコードには構造的等価性のセマンティクスがあります。</span><span class="sxs-lookup"><span data-stu-id="80972-158">Like union and structure types, records have structural equality semantics.</span></span> <span data-ttu-id="80972-159">クラスには参照等値セマンティクスがあります。</span><span class="sxs-lookup"><span data-stu-id="80972-159">Classes have reference equality semantics.</span></span> <span data-ttu-id="80972-160">次のコード例はこの処理方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="80972-160">The following code example demonstrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1911.fs)]

<span data-ttu-id="80972-161">このコードの出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="80972-161">The output of this code is as follows:</span></span>

```
The records are equal.
```

<span data-ttu-id="80972-162">クラスを使用して同じコードを記述した場合、2つのクラスオブジェクトは等しくなります。これは、2つの値がヒープ上の2つのオブジェクトを表し、 `System.Object.Equals`アドレスのみが比較されるためです (クラス型がメソッドをオーバーライドする場合を除きます)。</span><span class="sxs-lookup"><span data-stu-id="80972-162">If you write the same code with classes, the two class objects would be unequal because the two values would represent two objects on the heap and only the addresses would be compared (unless the class type overrides the `System.Object.Equals` method).</span></span>

<span data-ttu-id="80972-163">レコードの参照の等価性が必要な場合は`[<ReferenceEquality>]` 、レコードの上に属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="80972-163">If you need reference equality for records, add the attribute `[<ReferenceEquality>]` above the record.</span></span>

## <a name="see-also"></a><span data-ttu-id="80972-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="80972-164">See also</span></span>

- [<span data-ttu-id="80972-165">F# の型</span><span class="sxs-lookup"><span data-stu-id="80972-165">F# Types</span></span>](fsharp-types.md)
- [<span data-ttu-id="80972-166">クラス</span><span class="sxs-lookup"><span data-stu-id="80972-166">Classes</span></span>](classes.md)
- [<span data-ttu-id="80972-167">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="80972-167">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="80972-168">参照-等値</span><span class="sxs-lookup"><span data-stu-id="80972-168">Reference-Equality</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.referenceequalityattribute-class-%5bfsharp%5d)
- [<span data-ttu-id="80972-169">パターン一致</span><span class="sxs-lookup"><span data-stu-id="80972-169">Pattern Matching</span></span>](pattern-matching.md)
