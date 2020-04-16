---
title: 冗語構文
description: F# プログラミング言語での詳細構文と軽量構文の違いについて説明します。
ms.date: 05/16/2016
ms.openlocfilehash: 722807695c56beb0d681b95a78ed8cb8c1df3ddf
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463904"
---
# <a name="verbose-syntax"></a><span data-ttu-id="e0fad-103">冗語構文</span><span class="sxs-lookup"><span data-stu-id="e0fad-103">Verbose Syntax</span></span>

<span data-ttu-id="e0fad-104">F# 言語の多くの構文には、*詳細な構文*と*簡易構文*の 2 種類の構文が用意されています。</span><span class="sxs-lookup"><span data-stu-id="e0fad-104">There are two forms of syntax available for many constructs in the F# language: *verbose syntax* and *lightweight syntax*.</span></span> <span data-ttu-id="e0fad-105">詳細な構文は、一般的には使用されませんが、インデントに対する感度が低いという利点があります。</span><span class="sxs-lookup"><span data-stu-id="e0fad-105">The verbose syntax is not as commonly used, but has the advantage of being less sensitive to indentation.</span></span> <span data-ttu-id="e0fad-106">軽量構文は短く、インデントを使用して、 `begin`、`end`などの`in`追加のキーワードではなく、コンストラクトの先頭と末尾を通知します。</span><span class="sxs-lookup"><span data-stu-id="e0fad-106">The lightweight syntax is shorter and uses indentation to signal the beginning and end of constructs, rather than additional keywords like `begin`, `end`, `in`, and so on.</span></span> <span data-ttu-id="e0fad-107">既定の構文は、簡易構文です。</span><span class="sxs-lookup"><span data-stu-id="e0fad-107">The default syntax is the lightweight syntax.</span></span> <span data-ttu-id="e0fad-108">このトピックでは、簡易構文が有効でない場合の F# コンストラクトの構文について説明します。</span><span class="sxs-lookup"><span data-stu-id="e0fad-108">This topic describes the syntax for F# constructs when lightweight syntax is not enabled.</span></span> <span data-ttu-id="e0fad-109">詳細構文は常に有効であるため、簡易構文を有効にしても、一部の構文では詳細構文を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e0fad-109">Verbose syntax is always enabled, so even if you enable lightweight syntax, you can still use verbose syntax for some constructs.</span></span> <span data-ttu-id="e0fad-110">ディレクティブを使用して、簡易構文を`#light "off"`無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e0fad-110">You can disable lightweight syntax by using the `#light "off"` directive.</span></span>

## <a name="table-of-constructs"></a><span data-ttu-id="e0fad-111">コンストラクトの表</span><span class="sxs-lookup"><span data-stu-id="e0fad-111">Table of Constructs</span></span>

<span data-ttu-id="e0fad-112">次の表は、2 つの形式の間に違いがあるコンテキストでの F# 言語構成要素の軽量構文と詳細構文を示しています。</span><span class="sxs-lookup"><span data-stu-id="e0fad-112">The following table shows the lightweight and verbose syntax for F# language constructs in contexts where there is a difference between the two forms.</span></span> <span data-ttu-id="e0fad-113">この表では、山かっこ (&lt;&gt;) でユーザーが指定した構文要素を囲みます。</span><span class="sxs-lookup"><span data-stu-id="e0fad-113">In this table, angle brackets (&lt;&gt;) enclose user-supplied syntax elements.</span></span> <span data-ttu-id="e0fad-114">これらの構文で使用される構文の詳細については、各言語構成要素のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0fad-114">Refer to the documentation for each language construct for more detailed information about the syntax used within these constructs.</span></span>

<table>
<tr>
<th><span data-ttu-id="e0fad-115">言語構成</span><span class="sxs-lookup"><span data-stu-id="e0fad-115">Language construct</span></span></th>
<th><span data-ttu-id="e0fad-116">軽量構文</span><span class="sxs-lookup"><span data-stu-id="e0fad-116">Lightweight syntax</span></span></th>
<th><span data-ttu-id="e0fad-117">詳細構文</span><span class="sxs-lookup"><span data-stu-id="e0fad-117">Verbose syntax</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="e0fad-118">複合式</span><span class="sxs-lookup"><span data-stu-id="e0fad-118">compound expressions</span></span>
</td>
<td>

```xml
<expression1 />
<expression2 />
```

</td><td>

```fsharp
<expression1>; <expression2>
```

</td>
</tr>
<tr><td>

<span data-ttu-id="e0fad-119">ネストされた`let`バインディング</span><span class="sxs-lookup"><span data-stu-id="e0fad-119">nested `let` bindings</span></span>

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
<span data-ttu-id="e0fad-120">コード ブロック</span><span class="sxs-lookup"><span data-stu-id="e0fad-120">code block</span></span>
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
<tr><td><span data-ttu-id="e0fad-121">レコード (record)</span><span class="sxs-lookup"><span data-stu-id="e0fad-121">record</span></span>
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
<tr><td><span data-ttu-id="e0fad-122">class</span><span class="sxs-lookup"><span data-stu-id="e0fad-122">class</span></span>
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
<tr><td><span data-ttu-id="e0fad-123">structure</span><span class="sxs-lookup"><span data-stu-id="e0fad-123">structure</span></span></td><td>

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
<tr><td><span data-ttu-id="e0fad-124">差別化組合</span><span class="sxs-lookup"><span data-stu-id="e0fad-124">discriminated union</span></span></td><td>

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
<tr><td><span data-ttu-id="e0fad-125">interface</span><span class="sxs-lookup"><span data-stu-id="e0fad-125">interface</span></span></td><td>

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
<tr><td><span data-ttu-id="e0fad-126">オブジェクト式</span><span class="sxs-lookup"><span data-stu-id="e0fad-126">object expression</span></span></td><td>

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
<tr><td><span data-ttu-id="e0fad-127">インターフェイスの実装</span><span class="sxs-lookup"><span data-stu-id="e0fad-127">interface implementation</span></span></td><td>

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
<tr><td><span data-ttu-id="e0fad-128">型拡張子</span><span class="sxs-lookup"><span data-stu-id="e0fad-128">type extension</span></span></td><td>

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
<tr><td><span data-ttu-id="e0fad-129">name</span><span class="sxs-lookup"><span data-stu-id="e0fad-129">module</span></span></td><td>

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

## <a name="see-also"></a><span data-ttu-id="e0fad-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0fad-130">See also</span></span>

- [<span data-ttu-id="e0fad-131">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="e0fad-131">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="e0fad-132">コンパイラ ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="e0fad-132">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="e0fad-133">コードのフォーマットに関するガイドライン</span><span class="sxs-lookup"><span data-stu-id="e0fad-133">Code Formatting Guidelines</span></span>](../style-guide/formatting.md)
