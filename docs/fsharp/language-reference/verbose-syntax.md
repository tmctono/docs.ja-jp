---
title: 冗語構文
description: F#プログラミング言語における verbose 構文と簡易構文の違いについて説明します。
ms.date: 05/16/2016
ms.openlocfilehash: d2459da60bba5d88bd23615c8bf09ba64f7c22c4
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71214039"
---
# <a name="verbose-syntax"></a><span data-ttu-id="59a97-103">冗語構文</span><span class="sxs-lookup"><span data-stu-id="59a97-103">Verbose Syntax</span></span>

<span data-ttu-id="59a97-104">言語のさまざまな構成要素で使用できる構文には、 *verbose 構文*と*簡易構文*の2つの形式があります。 F#</span><span class="sxs-lookup"><span data-stu-id="59a97-104">There are two forms of syntax available for many constructs in the F# language: *verbose syntax* and *lightweight syntax*.</span></span> <span data-ttu-id="59a97-105">Verbose 構文は一般的に使用されるものではありませんが、インデントの影響が少なくなるという利点があります。</span><span class="sxs-lookup"><span data-stu-id="59a97-105">The verbose syntax is not as commonly used, but has the advantage of being less sensitive to indentation.</span></span> <span data-ttu-id="59a97-106">軽量の構文は短く、インデントを使用して、、、 `begin` `in`などの追加のキーワード`end`ではなく、コンストラクトの開始と終了を通知します。</span><span class="sxs-lookup"><span data-stu-id="59a97-106">The lightweight syntax is shorter and uses indentation to signal the beginning and end of constructs, rather than additional keywords like `begin`, `end`, `in`, and so on.</span></span> <span data-ttu-id="59a97-107">既定の構文は、簡易構文です。</span><span class="sxs-lookup"><span data-stu-id="59a97-107">The default syntax is the lightweight syntax.</span></span> <span data-ttu-id="59a97-108">このトピックでは、軽量F#構文が有効になっていない場合のコンストラクトの構文について説明します。</span><span class="sxs-lookup"><span data-stu-id="59a97-108">This topic describes the syntax for F# constructs when lightweight syntax is not enabled.</span></span> <span data-ttu-id="59a97-109">Verbose 構文は常に有効になっているため、簡易構文を有効にした場合でも、一部のコンストラクトに対して verbose 構文を使用できます。</span><span class="sxs-lookup"><span data-stu-id="59a97-109">Verbose syntax is always enabled, so even if you enable lightweight syntax, you can still use verbose syntax for some constructs.</span></span> <span data-ttu-id="59a97-110">ライトウェイト構文は、 `#light "off"`ディレクティブを使用して無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="59a97-110">You can disable lightweight syntax by using the `#light "off"` directive.</span></span>

## <a name="table-of-constructs"></a><span data-ttu-id="59a97-111">構造体の表</span><span class="sxs-lookup"><span data-stu-id="59a97-111">Table of Constructs</span></span>

<span data-ttu-id="59a97-112">次の表は、2つの形式のF#間に違いがあるコンテキストでの言語構成要素の簡易構文と詳細な構文を示しています。</span><span class="sxs-lookup"><span data-stu-id="59a97-112">The following table shows the lightweight and verbose syntax for F# language constructs in contexts where there is a difference between the two forms.</span></span> <span data-ttu-id="59a97-113">この表では、山かっこ&lt;(&gt;) は、ユーザーが指定した構文要素を囲みます。</span><span class="sxs-lookup"><span data-stu-id="59a97-113">In this table, angle brackets (&lt;&gt;) enclose user-supplied syntax elements.</span></span> <span data-ttu-id="59a97-114">これらのコンストラクトで使用される構文の詳細については、各言語構成要素のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="59a97-114">Refer to the documentation for each language construct for more detailed information about the syntax used within these constructs.</span></span>

<table>
<tr>
<th><span data-ttu-id="59a97-115">言語構成要素</span><span class="sxs-lookup"><span data-stu-id="59a97-115">Language construct</span></span></th>
<th><span data-ttu-id="59a97-116">簡易構文</span><span class="sxs-lookup"><span data-stu-id="59a97-116">Lightweight syntax</span></span></th>
<th><span data-ttu-id="59a97-117">Verbose 構文</span><span class="sxs-lookup"><span data-stu-id="59a97-117">Verbose syntax</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="59a97-118">複合式</span><span class="sxs-lookup"><span data-stu-id="59a97-118">compound expressions</span></span>
</td>
<td>

```xml
<expression1>
<expression2>
```

</td><td>

```fsharp
<expression1>; <expression2>
```

</td>
</tr>
<tr><td>

<span data-ttu-id="59a97-119">入れ子`let`になったバインディング</span><span class="sxs-lookup"><span data-stu-id="59a97-119">nested `let` bindings</span></span>

</td><td>

```fsharp
let f x =
    let a = 1
    let b = 2
    x + a + b
```

</td><td>

```fsharp
let f x =
    let a = 1 in
    let b = 2 in
    x + a + b
```

</td>
</tr>
<tr><td>
<span data-ttu-id="59a97-120">コードブロック</span><span class="sxs-lookup"><span data-stu-id="59a97-120">code block</span></span>
</td><td>

```fsharp
(
    <expression1>
    <expression2>
)
```

</td><td>

```fsharp
begin
    <expression1>;
    <expression2>;
end
```

</td>
</tr>
<tr><td>
`for...do`
</td><td>

```fsharp
for counter = start to finish do
    ...
```

</td><td>

```fsharp
for counter = start to finish do
    ...
done
```

</td>
</tr>
<tr><td>
`while...do`
</td><td>

```fsharp
while <condition> do
    ...
```

</td><td>

```fsharp
while <condition> do
    ...
done
```

</td>
</tr>
<tr><td>
`for...in`
</td><td>

```fsharp
for var in start .. finish do
    ...
```

</td><td>

```fsharp
for var in start .. finish do
    ...
done
```

</td>
</tr>
<tr><td>
`do`
</td><td>

```fsharp
do
    ...
```

</td><td>

```fsharp
do
    ...
in
```

</td>
</tr>
<tr><td><span data-ttu-id="59a97-121">録音</span><span class="sxs-lookup"><span data-stu-id="59a97-121">record</span></span>
</td><td>

```fsharp
type <record-name> =
    {
        <field-declarations>
    }
    <value-or-member-definitions>
```

</td><td>

```fsharp
type <record-name> =
    {
        <field-declarations>
    }
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="59a97-122">class</span><span class="sxs-lookup"><span data-stu-id="59a97-122">class</span></span>
</td><td>

```fsharp
type <class-name>(<params>) =
    ...
```

</td><td>

```fsharp
type <class-name>(<params>) =
    class
        ...
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="59a97-123">構造体</span><span class="sxs-lookup"><span data-stu-id="59a97-123">structure</span></span></td><td>

```fsharp
[<StructAttribute>]
type <structure-name> =
    ...
```

</td><td>

```fsharp
type <structure-name> =
    struct
        ...
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="59a97-124">判別共用体</span><span class="sxs-lookup"><span data-stu-id="59a97-124">discriminated union</span></span></td><td>

```fsharp
type <union-name> =
    | ...
    | ...
    ...
    <value-or-member definitions>
```

</td><td>

```fsharp
type <union-name> =
    | ...
    | ...
    ...
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="59a97-125">interface</span><span class="sxs-lookup"><span data-stu-id="59a97-125">interface</span></span></td><td>

```fsharp
type <interface-name> =
    ...
```

</td><td>

```fsharp
type <interface-name> =
    interface
        ...
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="59a97-126">オブジェクト式</span><span class="sxs-lookup"><span data-stu-id="59a97-126">object expression</span></span></td><td>

```fsharp
{ new <type-name>
    with
        <value-or-member-definitions>
        <interface-implementations>
}
```

</td><td>

```fsharp
{ new <type-name>
    with
        <value-or-member-definitions>
    end
    <interface-implementations>
}
```

</td>
</tr>
<tr><td><span data-ttu-id="59a97-127">インターフェイスの実装</span><span class="sxs-lookup"><span data-stu-id="59a97-127">interface implementation</span></span></td><td>

```fsharp
interface <interface-name>
    with
        <value-or-member-definitions>
```

</td><td>

```fsharp
interface <interface-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="59a97-128">型拡張</span><span class="sxs-lookup"><span data-stu-id="59a97-128">type extension</span></span></td><td>

```fsharp
type <type-name>
    with
        <value-or-member-definitions>
```

</td><td>

```fsharp
type <type-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="59a97-129">name</span><span class="sxs-lookup"><span data-stu-id="59a97-129">module</span></span></td><td>

```fsharp
module <module-name> =
    ...
```

</td><td>

```fsharp
module <module-name> =
    begin
        ...
    end
```

</td>
</tr>
</table>

## <a name="see-also"></a><span data-ttu-id="59a97-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="59a97-130">See also</span></span>

- [<span data-ttu-id="59a97-131">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="59a97-131">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="59a97-132">コンパイラ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="59a97-132">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="59a97-133">コードのフォーマットに関するガイドライン</span><span class="sxs-lookup"><span data-stu-id="59a97-133">Code Formatting Guidelines</span></span>](code-formatting-guidelines.md)
