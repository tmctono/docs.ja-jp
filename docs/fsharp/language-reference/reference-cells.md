---
title: 参照セル
description: F#参照セルは、参照セマンティクスを使用して変更可能な値を作成できるストレージの場所です。
ms.date: 05/16/2016
ms.openlocfilehash: faaa4a6b54ff0366163b6821edff7fa4cb2f5a88
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627252"
---
# <a name="reference-cells"></a><span data-ttu-id="da5bd-103">参照セル</span><span class="sxs-lookup"><span data-stu-id="da5bd-103">Reference Cells</span></span>

<span data-ttu-id="da5bd-104">*参照セル*は、参照セマンティクスを使用して変更可能な値を作成できるストレージの場所です。</span><span class="sxs-lookup"><span data-stu-id="da5bd-104">*Reference cells* are storage locations that enable you to create mutable values with reference semantics.</span></span>

## <a name="syntax"></a><span data-ttu-id="da5bd-105">構文</span><span class="sxs-lookup"><span data-stu-id="da5bd-105">Syntax</span></span>

```fsharp
ref expression
```

## <a name="remarks"></a><span data-ttu-id="da5bd-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="da5bd-106">Remarks</span></span>

<span data-ttu-id="da5bd-107">値をカプセル化する新しい参照セルを作成するには、値の前に `ref` 演算子を指定します。</span><span class="sxs-lookup"><span data-stu-id="da5bd-107">You use the `ref` operator before a value to create a new reference cell that encapsulates the value.</span></span> <span data-ttu-id="da5bd-108">基になる値は変更可能なので、後で変更できます。</span><span class="sxs-lookup"><span data-stu-id="da5bd-108">You can then change the underlying value because it is mutable.</span></span>

<span data-ttu-id="da5bd-109">参照セルは、単なるアドレスではなく、実際の値を保持します。</span><span class="sxs-lookup"><span data-stu-id="da5bd-109">A reference cell holds an actual value; it is not just an address.</span></span> <span data-ttu-id="da5bd-110">`ref` 演算子を使用して参照セルを作成すると、基の値のコピーが、カプセル化された変更可能な値として作成されます。</span><span class="sxs-lookup"><span data-stu-id="da5bd-110">When you create a reference cell by using the `ref` operator, you create a copy of the underlying value as an encapsulated mutable value.</span></span>

<span data-ttu-id="da5bd-111">参照セルを逆参照するには、`!` (感嘆符) 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="da5bd-111">You can dereference a reference cell by using the `!` (bang) operator.</span></span>

<span data-ttu-id="da5bd-112">次のコード例は、参照セルの宣言と使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="da5bd-112">The following code example illustrates the declaration and use of reference cells.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2201.fs)]

<span data-ttu-id="da5bd-113">出力は `50`になります。</span><span class="sxs-lookup"><span data-stu-id="da5bd-113">The output is `50`.</span></span>

<span data-ttu-id="da5bd-114">参照セルは、次のように宣言される `Ref` ジェネリック レコード型のインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="da5bd-114">Reference cells are instances of the `Ref` generic record type, which is declared as follows.</span></span>

```fsharp
type Ref<'a> =
{ mutable contents: 'a }
```

<span data-ttu-id="da5bd-115">`'a ref` 型は、`Ref<'a>` のシノニムです。</span><span class="sxs-lookup"><span data-stu-id="da5bd-115">The type `'a ref` is a synonym for `Ref<'a>`.</span></span> <span data-ttu-id="da5bd-116">コンパイラと IDE の IntelliSense では、この型について前者が表示されますが、基になる定義は後者です。</span><span class="sxs-lookup"><span data-stu-id="da5bd-116">The compiler and IntelliSense in the IDE display the former for this type, but the underlying definition is the latter.</span></span>

<span data-ttu-id="da5bd-117">`ref` 演算子は、新しい参照セルを作成します。</span><span class="sxs-lookup"><span data-stu-id="da5bd-117">The `ref` operator creates a new reference cell.</span></span> <span data-ttu-id="da5bd-118">次のコードは、`ref` 演算子の宣言です。</span><span class="sxs-lookup"><span data-stu-id="da5bd-118">The following code is the declaration of the `ref` operator.</span></span>

```fsharp
let ref x = { contents = x }
```

<span data-ttu-id="da5bd-119">次の表に、参照セルで使用できる機能を示します。</span><span class="sxs-lookup"><span data-stu-id="da5bd-119">The following table shows the features that are available on the reference cell.</span></span>

|<span data-ttu-id="da5bd-120">演算子、メンバー、またはフィールド</span><span class="sxs-lookup"><span data-stu-id="da5bd-120">Operator, member, or field</span></span>|<span data-ttu-id="da5bd-121">説明</span><span class="sxs-lookup"><span data-stu-id="da5bd-121">Description</span></span>|<span data-ttu-id="da5bd-122">型</span><span class="sxs-lookup"><span data-stu-id="da5bd-122">Type</span></span>|<span data-ttu-id="da5bd-123">定義</span><span class="sxs-lookup"><span data-stu-id="da5bd-123">Definition</span></span>|
|--------------------------|-----------|----|----------|
|<span data-ttu-id="da5bd-124">`!` (逆参照演算子)</span><span class="sxs-lookup"><span data-stu-id="da5bd-124">`!` (dereference operator)</span></span>|<span data-ttu-id="da5bd-125">基になる値を返します。</span><span class="sxs-lookup"><span data-stu-id="da5bd-125">Returns the underlying value.</span></span>|`'a ref -> 'a`|`let (!) r = r.contents`|
|<span data-ttu-id="da5bd-126">`:=` (代入演算子)</span><span class="sxs-lookup"><span data-stu-id="da5bd-126">`:=` (assignment operator)</span></span>|<span data-ttu-id="da5bd-127">基になる値を変更します。</span><span class="sxs-lookup"><span data-stu-id="da5bd-127">Changes the underlying value.</span></span>|`'a ref -> 'a -> unit`|`let (:=) r x = r.contents <- x`|
|<span data-ttu-id="da5bd-128">`ref` (演算子)</span><span class="sxs-lookup"><span data-stu-id="da5bd-128">`ref` (operator)</span></span>|<span data-ttu-id="da5bd-129">新しい参照セルに値をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="da5bd-129">Encapsulates a value into a new reference cell.</span></span>|`'a -> 'a ref`|`let ref x = { contents = x }`|
|<span data-ttu-id="da5bd-130">`Value` (プロパティ)</span><span class="sxs-lookup"><span data-stu-id="da5bd-130">`Value` (property)</span></span>|<span data-ttu-id="da5bd-131">基になる値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="da5bd-131">Gets or sets the underlying value.</span></span>|`unit -> 'a`|`member x.Value = x.contents`|
|<span data-ttu-id="da5bd-132">`contents` (レコード フィールド)</span><span class="sxs-lookup"><span data-stu-id="da5bd-132">`contents` (record field)</span></span>|<span data-ttu-id="da5bd-133">基になる値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="da5bd-133">Gets or sets the underlying value.</span></span>|`'a`|`let ref x = { contents = x }`|

<span data-ttu-id="da5bd-134">基になる値にアクセスする方法はいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="da5bd-134">There are several ways to access the underlying value.</span></span> <span data-ttu-id="da5bd-135">逆参照演算子 (`!`) によって返される値は、代入可能な値ではありません。</span><span class="sxs-lookup"><span data-stu-id="da5bd-135">The value returned by the dereference operator (`!`) is not an assignable value.</span></span> <span data-ttu-id="da5bd-136">したがって、基になる値を変更する場合は、代わりに代入演算子 (`:=`) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da5bd-136">Therefore, if you are modifying the underlying value, you must use the assignment operator (`:=`) instead.</span></span>

<span data-ttu-id="da5bd-137">`Value` プロパティと `contents` フィールドは、いずれも代入可能な値です。</span><span class="sxs-lookup"><span data-stu-id="da5bd-137">Both the `Value` property and the `contents` field are assignable values.</span></span> <span data-ttu-id="da5bd-138">したがって、次のコードに示すように、これらを使用して基になる値にアクセスしたり、基になる値を変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="da5bd-138">Therefore, you can use these to either access or change the underlying value, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2203.fs)]

<span data-ttu-id="da5bd-139">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="da5bd-139">The output is as follows.</span></span>

```
10
10
11
12
```

<span data-ttu-id="da5bd-140">`contents` フィールドは、他のバージョンの ML との互換性のために用意されており、コンパイル中に警告を生成します。</span><span class="sxs-lookup"><span data-stu-id="da5bd-140">The field `contents` is provided for compatibility with other versions of ML and will produce a warning during compilation.</span></span> <span data-ttu-id="da5bd-141">この警告を無効にするには、`--mlcompatibility` コンパイラ オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="da5bd-141">To disable the warning, use the `--mlcompatibility` compiler option.</span></span> <span data-ttu-id="da5bd-142">詳細については、「[コンパイラ オプション](compiler-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da5bd-142">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="da5bd-143">C# プログラマことを知っている`ref`と同じものでない (C#) `ref` F# でします。</span><span class="sxs-lookup"><span data-stu-id="da5bd-143">C# programmers should know that `ref` in C# is not the same thing as `ref` in F#.</span></span> <span data-ttu-id="da5bd-144">の同等の構成F#体は、参照セルとは異なる概念である[byref](byrefs.md)です。</span><span class="sxs-lookup"><span data-stu-id="da5bd-144">The equivalent constructs in F# are [byrefs](byrefs.md), which are a different concept from reference cells.</span></span>

<span data-ttu-id="da5bd-145">として`mutable`マーク[された](./values/index.md)値`'a ref`は、クロージャによってキャプチャされた場合に自動的にに昇格される場合があります。</span><span class="sxs-lookup"><span data-stu-id="da5bd-145">Values marked as `mutable`may be automatically promoted to `'a ref` if captured by a closure; see [Values](./values/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="da5bd-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="da5bd-146">See also</span></span>

- [<span data-ttu-id="da5bd-147">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="da5bd-147">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="da5bd-148">パラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="da5bd-148">Parameters and Arguments</span></span>](parameters-and-arguments.md)
- [<span data-ttu-id="da5bd-149">シンボルと演算子のリファレンス</span><span class="sxs-lookup"><span data-stu-id="da5bd-149">Symbol and Operator Reference</span></span>](./symbol-and-operator-reference/index.md)
- [<span data-ttu-id="da5bd-150">値</span><span class="sxs-lookup"><span data-stu-id="da5bd-150">Values</span></span>](./values/index.md)
