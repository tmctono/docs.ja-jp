---
title: インデックス付きプロパティ
description: のF#インデックス付きプロパティについて説明します。これにより、順序付けられたデータへの配列に似たアクセスが可能になります。
ms.date: 10/17/2018
ms.openlocfilehash: 379417e31b8e178d8c939e5b23dc144bfb17e562
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627560"
---
# <a name="indexed-properties"></a><span data-ttu-id="3bfca-103">インデックス付きプロパティ</span><span class="sxs-lookup"><span data-stu-id="3bfca-103">Indexed Properties</span></span>

<span data-ttu-id="3bfca-104">順序付けされたデータを抽象化するクラスを定義する場合、基になる実装を公開せずに、そのデータへのインデックス付きアクセスを提供すると役立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="3bfca-104">When defining a class that abstracts over ordered data, it can sometimes be helpful to provide indexed access to that data without exposing the underlying implementation.</span></span> <span data-ttu-id="3bfca-105">これは、 `Item`メンバーによって行われます。</span><span class="sxs-lookup"><span data-stu-id="3bfca-105">This is done with the `Item` member.</span></span>

## <a name="syntax"></a><span data-ttu-id="3bfca-106">構文</span><span class="sxs-lookup"><span data-stu-id="3bfca-106">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="3bfca-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="3bfca-107">Remarks</span></span>

<span data-ttu-id="3bfca-108">前の構文の形式`get`では、メソッド`set`とメソッドの両方を持つインデックス付きプロパティを定義する方法`get` 、メソッドを持つもの、 `set`またはメソッドのみを持つインデックス付きプロパティを定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3bfca-108">The forms of the previous syntax show how to define indexed properties that have both a `get` and a `set` method, have a `get` method only, or have a `set` method only.</span></span> <span data-ttu-id="3bfca-109">Get のみに表示される構文と、set のみに表示される構文の両方を組み合わせて、get と set の両方を持つプロパティを生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="3bfca-109">You can also combine both the syntax shown for get only and the syntax shown for set only, and produce a property that has both get and set.</span></span> <span data-ttu-id="3bfca-110">この2番目の形式では、get メソッドと set メソッドに異なるアクセシビリティ修飾子と属性を配置できます。</span><span class="sxs-lookup"><span data-stu-id="3bfca-110">This latter form allows you to put different accessibility modifiers and attributes on the get and set methods.</span></span>

<span data-ttu-id="3bfca-111">名前`Item`を使用すると、コンパイラはプロパティを既定のインデックス付きプロパティとして扱います。</span><span class="sxs-lookup"><span data-stu-id="3bfca-111">By using the name `Item`, the compiler treats the property as a default indexed property.</span></span> <span data-ttu-id="3bfca-112">*既定のインデックス付きプロパティ*は、オブジェクトインスタンスで配列に似た構文を使用してアクセスできるプロパティです。</span><span class="sxs-lookup"><span data-stu-id="3bfca-112">A *default indexed property* is a property that you can access by using array-like syntax on the object instance.</span></span> <span data-ttu-id="3bfca-113">たとえば、が、 `o`このプロパティを定義する型のオブジェクトである場合、構文`o.[index]`を使用してプロパティにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="3bfca-113">For example, if `o` is an object of the type that defines this property, the syntax `o.[index]` is used to access the property.</span></span>

<span data-ttu-id="3bfca-114">既定以外のインデックス付きプロパティにアクセスするための構文では、通常のメンバーと同じように、プロパティの名前とインデックスをかっこで囲んで指定します。</span><span class="sxs-lookup"><span data-stu-id="3bfca-114">The syntax for accessing a non-default indexed property is to provide the name of the property and the index in parentheses, just like a regular member.</span></span> <span data-ttu-id="3bfca-115">たとえば、の`o`プロパティが呼び出さ`Ordinal`れた場合は、それ`o.Ordinal(index)`にアクセスするためにを記述します。</span><span class="sxs-lookup"><span data-stu-id="3bfca-115">For example, if the property on `o` is called `Ordinal`, you write `o.Ordinal(index)` to access it.</span></span>

<span data-ttu-id="3bfca-116">使用するフォームに関係なく、インデックス付きプロパティの set メソッドには、常にカリー化された形式を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3bfca-116">Regardless of which form you use, you should always use the curried form for the set method on an indexed property.</span></span> <span data-ttu-id="3bfca-117">カリー化関数の詳細については、「[関数](../functions/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3bfca-117">For information about curried functions, see [Functions](../functions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="3bfca-118">例</span><span class="sxs-lookup"><span data-stu-id="3bfca-118">Example</span></span>

<span data-ttu-id="3bfca-119">次のコード例は、get メソッドと set メソッドを持つ既定のインデックス付きプロパティと既定以外のインデックス付きプロパティの定義と使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3bfca-119">The following code example illustrates the definition and use of default and non-default indexed properties that have get and set methods.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a><span data-ttu-id="3bfca-120">出力</span><span class="sxs-lookup"><span data-stu-id="3bfca-120">Output</span></span>

```console
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-values"></a><span data-ttu-id="3bfca-121">複数のインデックス値を持つインデックス付きプロパティ</span><span class="sxs-lookup"><span data-stu-id="3bfca-121">Indexed Properties with multiple index values</span></span>

<span data-ttu-id="3bfca-122">インデックス付きプロパティには、複数のインデックス値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3bfca-122">Indexed properties can have more than one index value.</span></span> <span data-ttu-id="3bfca-123">この場合、プロパティが使用されるときに、値はコンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="3bfca-123">In that case, the values are separated by commas when the property is used.</span></span> <span data-ttu-id="3bfca-124">このようなプロパティの set メソッドには、2つのカリー化引数が必要です。最初の引数はキーを含むタプルで、2番目の引数は設定する値です。</span><span class="sxs-lookup"><span data-stu-id="3bfca-124">The set method in such a property must have two curried arguments, the first of which is a tuple containing the keys, and the second of which is the value to set.</span></span>

<span data-ttu-id="3bfca-125">次のコードは、複数のインデックス値を持つインデックス付きプロパティの使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3bfca-125">The following code demonstrates the use of an indexed property with multiple index values.</span></span>

```fsharp
open System.Collections.Generic

/// Basic implementation of a sparse matrix based on a dictionary
type SparseMatrix() =
    let table = new Dictionary<(int * int), float>()
    member __.Item
        // Because the key is comprised of two values, 'get' has two index values
        with get(key1, key2) = table.[(key1, key2)]

        // 'set' has two index values and a new value to place in the key's position
        and set (key1, key2) value = table.[(key1, key2)] <- value

let sm = new SparseMatrix()
for i in 1..1000 do
    sm.[i, i] <- float i * float i
```

## <a name="see-also"></a><span data-ttu-id="3bfca-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="3bfca-126">See also</span></span>

- [<span data-ttu-id="3bfca-127">メンバー</span><span class="sxs-lookup"><span data-stu-id="3bfca-127">Members</span></span>](index.md)
