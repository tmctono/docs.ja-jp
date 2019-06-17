---
title: 匿名のレコード
description: コンストラクトを使用して、データの操作に役立つ言語機能、匿名のレコードを使用する方法について説明します。
ms.date: 06/12/2019
ms.openlocfilehash: e576210d4fb76ccfd09f8feb157ef4542aa94ccf
ms.sourcegitcommit: c4dfe37032c64a1fba2cc3d5947550d79f95e3b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2019
ms.locfileid: "67041806"
---
# <a name="anonymous-records"></a><span data-ttu-id="543d3-103">匿名のレコード</span><span class="sxs-lookup"><span data-stu-id="543d3-103">Anonymous Records</span></span>

<span data-ttu-id="543d3-104">匿名のレコードは、単純な集計の名前付きの値を使用する前に宣言する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="543d3-104">Anonymous records are simple aggregates of named values that don't need to be declared before use.</span></span> <span data-ttu-id="543d3-105">構造体、または参照型として宣言できます。</span><span class="sxs-lookup"><span data-stu-id="543d3-105">You can declare them as either structs or reference types.</span></span> <span data-ttu-id="543d3-106">既定では参照型です。</span><span class="sxs-lookup"><span data-stu-id="543d3-106">They're reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="543d3-107">構文</span><span class="sxs-lookup"><span data-stu-id="543d3-107">Syntax</span></span>

<span data-ttu-id="543d3-108">次の例では、匿名のレコードの構文を示します。</span><span class="sxs-lookup"><span data-stu-id="543d3-108">The following examples demonstrate the anonymous record syntax.</span></span> <span data-ttu-id="543d3-109">項目の区切りとして`[item]`は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="543d3-109">Items delimited as `[item]` are optional.</span></span>

```fsharp
// Construct an anonymous record
let value-name = [struct] {| Label1: Type1; Label2: Type2; ...|}

// Use an anonymous record as a type parameter
let value-name = Type-Name<[struct] {| Label1: Type1; Label2: Type2; ...|}>

// Define a parameter with an anonymous record as input
let function-name (arg-name: [struct] {| Label1: Type1; Label2: Type2; ...|}) ...
```

## <a name="basic-usage"></a><span data-ttu-id="543d3-110">基本的な使用方法</span><span class="sxs-lookup"><span data-stu-id="543d3-110">Basic usage</span></span>

<span data-ttu-id="543d3-111">匿名のレコードが最適なとして考えるF#レコードの種類をインスタンス化する前に宣言する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="543d3-111">Anonymous records are best thought of as F# record types that don't need to be declared before instantiation.</span></span>

<span data-ttu-id="543d3-112">たとえば、ここで、関数とやり取りする方法が生成されます匿名のレコード。</span><span class="sxs-lookup"><span data-stu-id="543d3-112">For example, here how you can interact with a function that produces an anonymous record:</span></span>

```fsharp

open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    {| Diameter = d; Area = a; Circumference = c |}

let r = 2.0
let stats = getCircleStats r
printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
    r stats.Diameter stats.Area stats.Circumference
```

<span data-ttu-id="543d3-113">次の例の展開では、前に、`printCircleStats`匿名のレコードの入力として受け取る関数。</span><span class="sxs-lookup"><span data-stu-id="543d3-113">The following example expands on the previous one with a `printCircleStats` function that takes an anonymous record as input:</span></span>

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    {| Diameter = d; Area = a; Circumference = c |}

let printCircleStats r (stats: {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

let r = 2.0
let stats = getCircleStats r
printCircleStats r stats
```

<span data-ttu-id="543d3-114">呼び出す`printCircleStats`匿名のレコード種類の入力の型はコンパイルに失敗すると、同じ「形状」がないとします。</span><span class="sxs-lookup"><span data-stu-id="543d3-114">Calling `printCircleStats` with any anonymous record type that doesn't have the same "shape" as the input type will fail to compile:</span></span>

```fsharp
printCircleStats r {| Diameter = 2.0; Area = 4.0; MyCircumference = 12.566371 |}
// Two anonymous record types have mismatched sets of field names
// '["Area"; "Circumference"; "Diameter"]' and '["Area"; "Diameter"; "MyCircumference"]'
```

## <a name="struct-anonymous-records"></a><span data-ttu-id="543d3-115">構造体の匿名のレコード</span><span class="sxs-lookup"><span data-stu-id="543d3-115">Struct anonymous records</span></span>

<span data-ttu-id="543d3-116">匿名のレコードは、構造体で、オプションとして定義することも`struct`キーワード。</span><span class="sxs-lookup"><span data-stu-id="543d3-116">Anonymous records can also be defined as struct with the optional `struct` keyword.</span></span> <span data-ttu-id="543d3-117">構造体の匿名のレコードの作成と、前の例を次の例には。</span><span class="sxs-lookup"><span data-stu-id="543d3-117">The following example augments the previous one by producing and consuming a struct anonymous record:</span></span>

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    // Note that the keyword comes before the '{| |}' brace pair
    struct {| Area = a; Circumference = c; Diameter = d |}

// the 'struct' keyword also comes before the '{| |}' brace pair when declaring the parameter type
let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

let r = 2.0
let stats = getCircleStats r
printCircleStats r stats
```

### <a name="structness-inference"></a><span data-ttu-id="543d3-118">Structness の推論</span><span class="sxs-lookup"><span data-stu-id="543d3-118">Structness inference</span></span>

<span data-ttu-id="543d3-119">構造体の匿名のレコードについても、「structness の推定」を指定する必要がない場所、`struct`呼び出しサイトにキーワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="543d3-119">Struct anonymous records also allow for "structness inference" where you do not need to specify the `struct` keyword at the call site.</span></span> <span data-ttu-id="543d3-120">Elide するこの例で、`struct`キーワードを呼び出すときに`printCircleStats`:</span><span class="sxs-lookup"><span data-stu-id="543d3-120">In this example, you elide the `struct` keyword when calling `printCircleStats`:</span></span>

```fsharp

let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

printCircleStats r {| Area = 4.0; Circumference = 12.6; Diameter = 12.6 |}
```

<span data-ttu-id="543d3-121">逆のパターンで指定する`struct`入力の型が構造体の匿名レコードの場合にコンパイルに失敗します。</span><span class="sxs-lookup"><span data-stu-id="543d3-121">The reverse pattern - specifying `struct` when the input type is not a struct anonymous record - will fail to compile.</span></span>

## <a name="embedding-anonymous-records-within-other-types"></a><span data-ttu-id="543d3-122">その他の種類内の匿名のレコードの埋め込み</span><span class="sxs-lookup"><span data-stu-id="543d3-122">Embedding anonymous records within other types</span></span>

<span data-ttu-id="543d3-123">宣言すると便利な[判別共用体](discriminated-unions.md)がの場合はレコード。</span><span class="sxs-lookup"><span data-stu-id="543d3-123">It's useful to declare [discriminated unions](discriminated-unions.md) whose cases are records.</span></span> <span data-ttu-id="543d3-124">レコード内のデータが判別共用体と同じ型の場合は、相互に再帰すべての種類を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="543d3-124">But if the data in the records is the same type as the discriminated union, you must define all types as mutually recursive.</span></span> <span data-ttu-id="543d3-125">匿名のレコードを使用してこの制限を回避できます。</span><span class="sxs-lookup"><span data-stu-id="543d3-125">Using anonymous records avoids this restriction.</span></span> <span data-ttu-id="543d3-126">例は、次に上にあるパターンと一致する型と関数。</span><span class="sxs-lookup"><span data-stu-id="543d3-126">What follows is an example type and function that pattern matches over it:</span></span>

```fsharp
type FullName = { FirstName: string; LastName: string }

// Note that using a named for Manager and Executive would require mutually recursive definitions.
type Employee =
    | Engineer of FullName
    | Manager of {| Name: FullName; Reports: Employee list |}
    | Executive of {| Name: FullName; Reports: Employee list; Assistant: Employee |}

let getFirstName e =
    match e with
    | Engineer fullName -> fullName.FirstName
    | Manager m -> m.Name.FirstName
    | Executive ex -> ex.Name.FirstName
```

## <a name="copy-and-update-expressions"></a><span data-ttu-id="543d3-127">コピーして、式の更新</span><span class="sxs-lookup"><span data-stu-id="543d3-127">Copy and update expressions</span></span>

<span data-ttu-id="543d3-128">匿名のレコードでの構築をサポートする[コピーして、式を更新](copy-and-update-record-expressions.md)します。</span><span class="sxs-lookup"><span data-stu-id="543d3-128">Anonymous records support construction with [copy and update expressions](copy-and-update-record-expressions.md).</span></span> <span data-ttu-id="543d3-129">たとえば、ここでは、1 つの既存のコピーを匿名のレコードの新しいインスタンスを作成する方法のデータ。</span><span class="sxs-lookup"><span data-stu-id="543d3-129">For example, here's how you can construct a new instance of an anonymous record that copies an existing one's data:</span></span>

```fsharp
let data = {| X = 1; Y = 2 |}
let data' = {| data with Y = 3 |}
```

<span data-ttu-id="543d3-130">ただし、名前付きのレコードとは異なり匿名のレコード、コピーではまったく別のフォームを構築し、式を更新できます。</span><span class="sxs-lookup"><span data-stu-id="543d3-130">However, unlike named records, anonymous records allow you to construct entirely different forms with copy and update expressions.</span></span> <span data-ttu-id="543d3-131">次の例は、前の例から同じ匿名レコードを受け取り、新しい匿名のレコードに展開すること。</span><span class="sxs-lookup"><span data-stu-id="543d3-131">The follow example takes the same anonymous record from the previous example and expands it into a new anonymous record:</span></span>

```fsharp
let data = {| X = 1; Y = 2 |}
let expandedData = {| data with Z = 3 |} // Gives {| X=1; Y=2; Z=3 |}
```

<span data-ttu-id="543d3-132">名前付きのレコードのインスタンスからの匿名のレコードを作成することもします。</span><span class="sxs-lookup"><span data-stu-id="543d3-132">It is also possible to construct anonymous records from instances of named records:</span></span>

```fsharp
type R = { X: int }
let data = { X = 1 }
let data' = {| data with Y = 2 |} // Gives {| X=1; Y=2 |}
```

<span data-ttu-id="543d3-133">参照と構造体の匿名のレコードとの間データをコピーすることもできます。</span><span class="sxs-lookup"><span data-stu-id="543d3-133">You can also copy data to and from reference and struct anonymous records:</span></span>

```fsharp
// Copy data from a reference record into a struct anonymous record
type R1 = { X: int }
let r1 = { X = 1 }

let data1 = struct {| r1 with Y = 1 |}

// Copy data from a struct record into a reference anonymous record
[<Struct>]
type R2 = { X: int }
let r2 = { X = 1 }

let data2 = {| r1 with Y = 1 |}

// Copy the reference anonymous record data into a struct anonymous record
let data3 = struct {| data2 with Z = r2.X |}
```

## <a name="properties-of-anonymous-records"></a><span data-ttu-id="543d3-134">匿名のレコードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="543d3-134">Properties of anonymous records</span></span>

<span data-ttu-id="543d3-135">匿名のレコードでは、さまざまな使用方法を完全に理解に不可欠な特性があります。</span><span class="sxs-lookup"><span data-stu-id="543d3-135">Anonymous records have a number of characteristics that are essential to fully understanding how they can be used.</span></span>

### <a name="anonymous-records-are-nominal"></a><span data-ttu-id="543d3-136">匿名のレコードが標準</span><span class="sxs-lookup"><span data-stu-id="543d3-136">Anonymous records are nominal</span></span>

<span data-ttu-id="543d3-137">匿名のレコードが[標準型](https://en.wikipedia.org/wiki/Nominal_type_system)します。</span><span class="sxs-lookup"><span data-stu-id="543d3-137">Anonymous records are [nominal types](https://en.wikipedia.org/wiki/Nominal_type_system).</span></span> <span data-ttu-id="543d3-138">という名前とは考えて[レコード](records.md)事前宣言を必要としない種類 (これは、公称も)。</span><span class="sxs-lookup"><span data-stu-id="543d3-138">They are best thought as named [record](records.md) types (which are also nominal) that do not require an up-front declaration.</span></span>

<span data-ttu-id="543d3-139">匿名のレコードの 2 つの宣言は次の例を検討してください。</span><span class="sxs-lookup"><span data-stu-id="543d3-139">Consider the following example with two anonymous record declarations:</span></span>

```fsharp
let x = {| X = 1 |}
let y = {| Y = 1 |}
```

<span data-ttu-id="543d3-140">`x`と`y`値が異なる型であるし、は相互に互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="543d3-140">The `x` and `y` values have different types and are not compatible with one another.</span></span> <span data-ttu-id="543d3-141">等値性が解除され、同等ではありません。</span><span class="sxs-lookup"><span data-stu-id="543d3-141">They are not equatable and they are not comparable.</span></span> <span data-ttu-id="543d3-142">これを示すためには、名前付きのレコードを同等検討してください。</span><span class="sxs-lookup"><span data-stu-id="543d3-142">To illustrate this, consider a named record equivalent:</span></span>

```fsharp
type X = { X: int }
type Y = { Y: int }

let x = { X = 1 }
let y = { Y = 1 }
```

<span data-ttu-id="543d3-143">型と同等のグループまたは比較に関連しているときに、対応する名前付きのレコードと比較した場合、匿名のレコードに関する本質的に異なるものはないです。</span><span class="sxs-lookup"><span data-stu-id="543d3-143">There isn't anything inherently different about anonymous records when compared with their named record equivalents when concerning type equivalency or comparison.</span></span>

### <a name="anonymous-records-use-structural-equality-and-comparison"></a><span data-ttu-id="543d3-144">匿名のレコードを使用して、構造的等値と比較</span><span class="sxs-lookup"><span data-stu-id="543d3-144">Anonymous records use structural equality and comparison</span></span>

<span data-ttu-id="543d3-145">レコードの種類と同様に匿名のレコードは、構造的等値性と比較します。</span><span class="sxs-lookup"><span data-stu-id="543d3-145">Like record types, anonymous records are structurally equatable and comparable.</span></span> <span data-ttu-id="543d3-146">これは、すべての構成要素の型をサポートして等値と比較のようなレコードの種類の場合は true のみ。</span><span class="sxs-lookup"><span data-stu-id="543d3-146">This is only true if all constituent types support equality and comparison, like with record types.</span></span> <span data-ttu-id="543d3-147">等値または比較をサポートするには、2 つの匿名のレコードは、同じ「形状」する必要があります。</span><span class="sxs-lookup"><span data-stu-id="543d3-147">To support equality or comparison, two anonymous records must have the same "shape".</span></span>

```fsharp
{| a = 1+1 |} = {| a = 2 |} // true
{| a = 1+1 |} > {| a = 1 |} // true

// error FS0001: Two anonymous record types have mismatched sets of field names '["a"]' and '["a"; "b"]'
{| a = 1 + 1 |} = {| a = 2;  b = 1|}
```

### <a name="anonymous-records-are-serializable"></a><span data-ttu-id="543d3-148">匿名のレコードはシリアル化</span><span class="sxs-lookup"><span data-stu-id="543d3-148">Anonymous records are serializable</span></span>

<span data-ttu-id="543d3-149">名前付きのレコードを含む場合と同様、匿名のレコードをシリアル化することができます。</span><span class="sxs-lookup"><span data-stu-id="543d3-149">You can serialize anonymous records just as you can with named records.</span></span> <span data-ttu-id="543d3-150">例を次に示しますを使用して[Newtonsoft.Json](https://www.nuget.org/packages/Newtonsoft.Json/):</span><span class="sxs-lookup"><span data-stu-id="543d3-150">Here is an example using [Newtonsoft.Json](https://www.nuget.org/packages/Newtonsoft.Json/):</span></span>

```fsharp
open Newtonsoft.Json

let phillip = {| name="Phillip"; age=28 |}
JsonConvert.SerializeObject(phillip)

let phillip = JsonConvert.DeserializeObject<{|name: string; age: int|}>(str)
printfn "Name: %s Age: %d" phillip.name phillip.age
```

<span data-ttu-id="543d3-151">匿名のレコードは、シリアル化または逆シリアル化型を事前にドメインを定義することがなく、ネットワーク経由で軽量のデータを送信するために便利です。</span><span class="sxs-lookup"><span data-stu-id="543d3-151">Anonymous records are useful for sending lightweight data over a network without the need to define a domain for your serialized/deserialized types up front.</span></span>

### <a name="anonymous-records-interoperate-with-c-anonymous-types"></a><span data-ttu-id="543d3-152">匿名のレコードとの相互運用C#匿名型</span><span class="sxs-lookup"><span data-stu-id="543d3-152">Anonymous records interoperate with C# anonymous types</span></span>

<span data-ttu-id="543d3-153">使用を必要とする .NET API を使用することは[C#匿名型](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="543d3-153">It is possible to use a .NET API that requires the use of [C# anonymous types](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span> <span data-ttu-id="543d3-154">C#匿名型は匿名のレコードを使用して相互に簡単です。</span><span class="sxs-lookup"><span data-stu-id="543d3-154">C# anonymous types are trivial to interoperate with by using anonymous records.</span></span> <span data-ttu-id="543d3-155">次の例では、匿名のレコードを使用して呼び出す方法を示しています、 [LINQ](../../csharp/programming-guide/concepts/linq/index.md)オーバー ロードを匿名型を必要とします。</span><span class="sxs-lookup"><span data-stu-id="543d3-155">The following example shows how to use anonymous records to call a [LINQ](../../csharp/programming-guide/concepts/linq/index.md) overload that requires an anonymous type:</span></span>

```fsharp
open System.Linq

let names = [ "Ana"; "Felipe"; "Emilia"]
let nameGrouping = names.Select(fun n -> {| Name = n; FirstLetter = n.[0] |})
for ng in nameGrouping do
    printfn "%s has first letter %c" ng.Name ng.FirstLetter
```

<span data-ttu-id="543d3-156">さまざまな .NET 全体で使用される匿名型を渡すことの使用を要求する他の Api があります。</span><span class="sxs-lookup"><span data-stu-id="543d3-156">There are a multitude of other APIs used throughout .NET that require the use of passing in an anonymous type.</span></span> <span data-ttu-id="543d3-157">匿名のレコードは、それらを操作するためのツールです。</span><span class="sxs-lookup"><span data-stu-id="543d3-157">Anonymous records are your tool for working with them.</span></span>

## <a name="limitations"></a><span data-ttu-id="543d3-158">制限事項</span><span class="sxs-lookup"><span data-stu-id="543d3-158">Limitations</span></span>

<span data-ttu-id="543d3-159">匿名のレコードでは、その使用方法にいくつかの制限があります。</span><span class="sxs-lookup"><span data-stu-id="543d3-159">Anonymous records have some restrictions in their usage.</span></span> <span data-ttu-id="543d3-160">設計、本質的なものが、他のユーザーは結果セットのサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="543d3-160">Some are inherent to their design, but others are amenable to change.</span></span>

### <a name="limitations-with-pattern-matching"></a><span data-ttu-id="543d3-161">パターン マッチングの制限事項</span><span class="sxs-lookup"><span data-stu-id="543d3-161">Limitations with pattern matching</span></span>

<span data-ttu-id="543d3-162">匿名のレコードは、名前付きのレコードとは異なり、パターン マッチングをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="543d3-162">Anonymous records do not support pattern matching, unlike named records.</span></span> <span data-ttu-id="543d3-163">次の 3 つの理由があります。</span><span class="sxs-lookup"><span data-stu-id="543d3-163">There are three reasons:</span></span>

1. <span data-ttu-id="543d3-164">パターンは、すべてのフィールドの名前付きのレコードの種類とは異なり、匿名のレコードを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="543d3-164">A pattern would have to account for every field of an anonymous record, unlike named record types.</span></span> <span data-ttu-id="543d3-165">匿名のレコードは構造型のサブタイプをサポートしていません: 標準型があるためにです。</span><span class="sxs-lookup"><span data-stu-id="543d3-165">This is because anonymous records do not support structural subtyping – they are nominal types.</span></span>
2. <span data-ttu-id="543d3-166">ため (1) はありません、パターン一致式でその他のパターンを指定する機能をそれぞれ個別のパターンは匿名の異なるレコードの種類を示すようにします。</span><span class="sxs-lookup"><span data-stu-id="543d3-166">Because of (1), there is no ability to have additional patterns in a pattern match expression, as each distinct pattern would imply a different anonymous record type.</span></span>
3. <span data-ttu-id="543d3-167">(3) のため、匿名のレコード パターンは「ドット」表記の使用よりも詳細になります。</span><span class="sxs-lookup"><span data-stu-id="543d3-167">Because of (3), any anonymous record pattern would be more verbose than the use of “dot” notation.</span></span>

<span data-ttu-id="543d3-168">オープン言語提案がある[コンテキストが限定でパターン マッチングを許可する](https://github.com/fsharp/fslang-suggestions/issues/713)します。</span><span class="sxs-lookup"><span data-stu-id="543d3-168">There is an open language suggestion to [allow pattern matching in limited contexts](https://github.com/fsharp/fslang-suggestions/issues/713).</span></span>

### <a name="limitations-with-mutability"></a><span data-ttu-id="543d3-169">可変性の制約</span><span class="sxs-lookup"><span data-stu-id="543d3-169">Limitations with mutability</span></span>

<span data-ttu-id="543d3-170">現時点で匿名のレコードを定義することは`mutable`データ。</span><span class="sxs-lookup"><span data-stu-id="543d3-170">It is not currently possible to define an anonymous record with `mutable` data.</span></span> <span data-ttu-id="543d3-171">[言語の修正候補を開く](https://github.com/fsharp/fslang-suggestions/issues/732)変更可能なデータを許可します。</span><span class="sxs-lookup"><span data-stu-id="543d3-171">There is an [open language suggestion](https://github.com/fsharp/fslang-suggestions/issues/732) to allow mutable data.</span></span>

### <a name="limitations-with-struct-anonymous-records"></a><span data-ttu-id="543d3-172">構造体の匿名のレコードの制限事項</span><span class="sxs-lookup"><span data-stu-id="543d3-172">Limitations with struct anonymous records</span></span>

<span data-ttu-id="543d3-173">匿名のレコードを構造体を宣言することはできません`IsByRefLike`または`IsReadOnly`します。</span><span class="sxs-lookup"><span data-stu-id="543d3-173">It is not possible to declare struct anonymous records as `IsByRefLike` or `IsReadOnly`.</span></span> <span data-ttu-id="543d3-174">[言語の修正候補を開く](https://github.com/fsharp/fslang-suggestions/issues/712)の`IsByRefLike`と`IsReadOnly`匿名のレコード。</span><span class="sxs-lookup"><span data-stu-id="543d3-174">There is an [open language suggestion](https://github.com/fsharp/fslang-suggestions/issues/712) to for `IsByRefLike` and `IsReadOnly` anonymous records.</span></span>
