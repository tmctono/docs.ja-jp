---
title: クラス内の let 束縛
description: クラス定義で ' let ' バインディングを使用しF#て、クラスのプライベートフィールドとプライベート関数を定義する方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: 1366ab8f1f4f606fe5947a8fc4df10de49346b3e
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216533"
---
# <a name="let-bindings-in-classes"></a><span data-ttu-id="c93c0-103">クラス内の let バインド</span><span class="sxs-lookup"><span data-stu-id="c93c0-103">let Bindings in Classes</span></span>

<span data-ttu-id="c93c0-104">クラス定義のバインディングを使用F# `let`して、クラスのプライベートフィールドとプライベート関数を定義できます。</span><span class="sxs-lookup"><span data-stu-id="c93c0-104">You can define private fields and private functions for F# classes by using `let` bindings in the class definition.</span></span>

## <a name="syntax"></a><span data-ttu-id="c93c0-105">構文</span><span class="sxs-lookup"><span data-stu-id="c93c0-105">Syntax</span></span>

```fsharp
// Field.
[static] let [ mutable ] binding1 [ and ... binding-n ]

// Function.
[static] let [ rec ] binding1 [ and ... binding-n ]
```

## <a name="remarks"></a><span data-ttu-id="c93c0-106">コメント</span><span class="sxs-lookup"><span data-stu-id="c93c0-106">Remarks</span></span>

<span data-ttu-id="c93c0-107">前の構文は、クラスの見出しと継承宣言の後、メンバー定義の前に記述されます。</span><span class="sxs-lookup"><span data-stu-id="c93c0-107">The previous syntax appears after the class heading and inheritance declarations but before any member definitions.</span></span> <span data-ttu-id="c93c0-108">構文は、クラスの外部`let`のバインドの場合と似ていますが、クラスで定義されている名前には、クラスに限定されたスコープがあります。</span><span class="sxs-lookup"><span data-stu-id="c93c0-108">The syntax is like that of `let` bindings outside of classes, but the names defined in a class have a scope that is limited to the class.</span></span> <span data-ttu-id="c93c0-109">バインディング`let`は、プライベートフィールドまたは関数を作成します。データまたは関数を公開するには、プロパティまたはメンバーメソッドを宣言します。</span><span class="sxs-lookup"><span data-stu-id="c93c0-109">A `let` binding creates a private field or function; to expose data or functions publicly, declare a property or a member method.</span></span>

<span data-ttu-id="c93c0-110">静的でない`let` `let`バインディングは、インスタンスバインディングと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="c93c0-110">A `let` binding that is not static is called an instance `let` binding.</span></span> <span data-ttu-id="c93c0-111">インスタンス`let`バインドは、オブジェクトの作成時に実行されます。</span><span class="sxs-lookup"><span data-stu-id="c93c0-111">Instance `let` bindings execute when objects are created.</span></span> <span data-ttu-id="c93c0-112">静的`let`バインディングは、クラスの静的初期化子の一部であり、型が最初に使用される前に確実に実行されることが保証されています。</span><span class="sxs-lookup"><span data-stu-id="c93c0-112">Static `let` bindings are part of the static initializer for the class, which is guaranteed to execute before the type is first used.</span></span>

<span data-ttu-id="c93c0-113">インスタンス`let`バインド内のコードでは、プライマリコンストラクターのパラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c93c0-113">The code within instance `let` bindings can use the primary constructor's parameters.</span></span>

<span data-ttu-id="c93c0-114">属性とアクセシビリティ修飾子は、クラスの`let`バインドでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="c93c0-114">Attributes and accessibility modifiers are not permitted on `let` bindings in classes.</span></span>

<span data-ttu-id="c93c0-115">次のコード例は、クラスの`let`いくつかの種類のバインドを示しています。</span><span class="sxs-lookup"><span data-stu-id="c93c0-115">The following code examples illustrate several types of `let` bindings in classes.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

<span data-ttu-id="c93c0-116">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c93c0-116">The output is as follows.</span></span>

```console
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a><span data-ttu-id="c93c0-117">フィールドを作成する別の方法</span><span class="sxs-lookup"><span data-stu-id="c93c0-117">Alternative Ways to Create Fields</span></span>

<span data-ttu-id="c93c0-118">また、キーワードを使用`val`してプライベートフィールドを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="c93c0-118">You can also use the `val` keyword to create a private field.</span></span> <span data-ttu-id="c93c0-119">`val`キーワードを使用する場合、オブジェクトの作成時にフィールドに値は与えられませんが、代わりに既定値を使用して初期化されます。</span><span class="sxs-lookup"><span data-stu-id="c93c0-119">When using the `val` keyword, the field is not given a value when the object is created, but instead is initialized with a default value.</span></span> <span data-ttu-id="c93c0-120">詳細については、次を参照してください。[明示的なフィールド:Val キーワード](explicit-fields-the-val-keyword.md)。</span><span class="sxs-lookup"><span data-stu-id="c93c0-120">For more information, see [Explicit Fields: The val Keyword](explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="c93c0-121">メンバー定義を使用し、キーワード`private`を定義に追加することで、クラスのプライベートフィールドを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="c93c0-121">You can also define private fields in a class by using a member definition and adding the keyword `private` to the definition.</span></span> <span data-ttu-id="c93c0-122">これは、コードを書き直さずにメンバーのアクセシビリティを変更することが予想される場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="c93c0-122">This can be useful if you expect to change the accessibility of a member without rewriting your code.</span></span> <span data-ttu-id="c93c0-123">詳細については、「[Access Control](../access-control.md)」(アクセス制御) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c93c0-123">For more information, see [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c93c0-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="c93c0-124">See also</span></span>

- [<span data-ttu-id="c93c0-125">メンバー</span><span class="sxs-lookup"><span data-stu-id="c93c0-125">Members</span></span>](index.md)
- [<span data-ttu-id="c93c0-126">クラス内の `do` バインド</span><span class="sxs-lookup"><span data-stu-id="c93c0-126">`do` Bindings in Classes</span></span>](do-bindings-in-classes.md)
- [<span data-ttu-id="c93c0-127">`let`現存</span><span class="sxs-lookup"><span data-stu-id="c93c0-127">`let` Bindings</span></span>](../functions/let-bindings.md)
