---
title: インデックス付きプロパティ
description: のF#インデックス付きプロパティについて説明します。これにより、順序付けられたデータへの配列に似たアクセスが可能になります。
ms.date: 11/04/2019
ms.openlocfilehash: f6cf3bfa737d2bf458e379594be5884696cee3e1
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976612"
---
# <a name="indexed-properties"></a><span data-ttu-id="8a02d-103">インデックス付きプロパティ</span><span class="sxs-lookup"><span data-stu-id="8a02d-103">Indexed Properties</span></span>

<span data-ttu-id="8a02d-104">順序付けされたデータを抽象化するクラスを定義する場合、基になる実装を公開せずに、そのデータへのインデックス付きアクセスを提供すると役立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="8a02d-104">When defining a class that abstracts over ordered data, it can sometimes be helpful to provide indexed access to that data without exposing the underlying implementation.</span></span> <span data-ttu-id="8a02d-105">これは `Item` メンバーによって行われます。</span><span class="sxs-lookup"><span data-stu-id="8a02d-105">This is done with the `Item` member.</span></span>

## <a name="syntax"></a><span data-ttu-id="8a02d-106">構文</span><span class="sxs-lookup"><span data-stu-id="8a02d-106">Syntax</span></span>

```fsharp
// Indexed property that can be read and written to
member self-identifier.Item
    with get(index-values) =
        get-member-body
    and set index-values values-to-set =
        set-member-body

// Indexed property can only be read
member self-identifier.Item
    with get(index-values) =
        get-member-body

// Indexed property that can only be set
member self-identifier.Item
    with set index-values values-to-set =
        set-member-body
```

## <a name="remarks"></a><span data-ttu-id="8a02d-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="8a02d-107">Remarks</span></span>

<span data-ttu-id="8a02d-108">前の構文の形式は、`get` と `set` メソッドの両方を持つインデックス付きプロパティを定義する方法、`get` メソッドのみを持つもの、または `set` メソッドのみを持つインデックス付きプロパティを定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8a02d-108">The forms of the previous syntax show how to define indexed properties that have both a `get` and a `set` method, have a `get` method only, or have a `set` method only.</span></span> <span data-ttu-id="8a02d-109">Get のみに表示される構文と、set のみに表示される構文の両方を組み合わせて、get と set の両方を持つプロパティを生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="8a02d-109">You can also combine both the syntax shown for get only and the syntax shown for set only, and produce a property that has both get and set.</span></span> <span data-ttu-id="8a02d-110">この2番目の形式では、get メソッドと set メソッドに異なるアクセシビリティ修飾子と属性を配置できます。</span><span class="sxs-lookup"><span data-stu-id="8a02d-110">This latter form allows you to put different accessibility modifiers and attributes on the get and set methods.</span></span>

<span data-ttu-id="8a02d-111">名前 `Item`を使用すると、コンパイラはプロパティを既定のインデックス付きプロパティとして扱います。</span><span class="sxs-lookup"><span data-stu-id="8a02d-111">By using the name `Item`, the compiler treats the property as a default indexed property.</span></span> <span data-ttu-id="8a02d-112">*既定のインデックス付きプロパティ*は、オブジェクトインスタンスで配列に似た構文を使用してアクセスできるプロパティです。</span><span class="sxs-lookup"><span data-stu-id="8a02d-112">A *default indexed property* is a property that you can access by using array-like syntax on the object instance.</span></span> <span data-ttu-id="8a02d-113">たとえば、`o` がこのプロパティを定義する型のオブジェクトである場合、プロパティにアクセスするために `o.[index]` 構文が使用されます。</span><span class="sxs-lookup"><span data-stu-id="8a02d-113">For example, if `o` is an object of the type that defines this property, the syntax `o.[index]` is used to access the property.</span></span>

<span data-ttu-id="8a02d-114">既定以外のインデックス付きプロパティにアクセスするための構文では、通常のメンバーと同じように、プロパティの名前とインデックスをかっこで囲んで指定します。</span><span class="sxs-lookup"><span data-stu-id="8a02d-114">The syntax for accessing a non-default indexed property is to provide the name of the property and the index in parentheses, just like a regular member.</span></span> <span data-ttu-id="8a02d-115">たとえば、`o` のプロパティが `Ordinal`として呼び出された場合は、それにアクセスするための `o.Ordinal(index)` を記述します。</span><span class="sxs-lookup"><span data-stu-id="8a02d-115">For example, if the property on `o` is called `Ordinal`, you write `o.Ordinal(index)` to access it.</span></span>

<span data-ttu-id="8a02d-116">使用するフォームに関係なく、インデックス付きプロパティの set メソッドには、常にカリー化された形式を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a02d-116">Regardless of which form you use, you should always use the curried form for the set method on an indexed property.</span></span> <span data-ttu-id="8a02d-117">カリー化関数の詳細については、「[関数](../functions/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a02d-117">For information about curried functions, see [Functions](../functions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="8a02d-118">例</span><span class="sxs-lookup"><span data-stu-id="8a02d-118">Example</span></span>

<span data-ttu-id="8a02d-119">次のコード例は、get メソッドと set メソッドを持つ既定のインデックス付きプロパティと既定以外のインデックス付きプロパティの定義と使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8a02d-119">The following code example illustrates the definition and use of default and non-default indexed properties that have get and set methods.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a><span data-ttu-id="8a02d-120">出力</span><span class="sxs-lookup"><span data-stu-id="8a02d-120">Output</span></span>

```console
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-values"></a><span data-ttu-id="8a02d-121">複数のインデックス値を持つインデックス付きプロパティ</span><span class="sxs-lookup"><span data-stu-id="8a02d-121">Indexed Properties with multiple index values</span></span>

<span data-ttu-id="8a02d-122">インデックス付きプロパティには、複数のインデックス値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8a02d-122">Indexed properties can have more than one index value.</span></span> <span data-ttu-id="8a02d-123">この場合、プロパティが使用されるときに、値はコンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="8a02d-123">In that case, the values are separated by commas when the property is used.</span></span> <span data-ttu-id="8a02d-124">このようなプロパティの set メソッドには、2つのカリー化引数が必要です。最初の引数はキーを含むタプルで、2番目の引数は設定する値です。</span><span class="sxs-lookup"><span data-stu-id="8a02d-124">The set method in such a property must have two curried arguments, the first of which is a tuple containing the keys, and the second of which is the value to set.</span></span>

<span data-ttu-id="8a02d-125">次のコードは、複数のインデックス値を持つインデックス付きプロパティの使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8a02d-125">The following code demonstrates the use of an indexed property with multiple index values.</span></span>

```fsharp
open System.Collections.Generic

/// Basic implementation of a sparse matrix based on a dictionary
type SparseMatrix() =
    let table = new Dictionary<(int * int), float>()
    member _.Item
        // Because the key is comprised of two values, 'get' has two index values
        with get(key1, key2) = table.[(key1, key2)]

        // 'set' has two index values and a new value to place in the key's position
        and set (key1, key2) value = table.[(key1, key2)] <- value

let sm = new SparseMatrix()
for i in 1..1000 do
    sm.[i, i] <- float i * float i
```

## <a name="see-also"></a><span data-ttu-id="8a02d-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a02d-126">See also</span></span>

- [<span data-ttu-id="8a02d-127">メンバー</span><span class="sxs-lookup"><span data-stu-id="8a02d-127">Members</span></span>](index.md)
