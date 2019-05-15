---
title: クラス内の let 束縛
description: クラス定義で 'let' のバインドを使用して、プライベート フィールドと F# クラスのプライベート関数を定義する方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: 29f843e3e065837a53fd5eb26c79088bc0778c76
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645183"
---
# <a name="let-bindings-in-classes"></a><span data-ttu-id="5d629-103">クラス内の let バインド</span><span class="sxs-lookup"><span data-stu-id="5d629-103">let Bindings in Classes</span></span>

<span data-ttu-id="5d629-104">使用して、プライベート フィールドと F# クラスのプライベート関数を定義することができます`let`クラス定義にバインドします。</span><span class="sxs-lookup"><span data-stu-id="5d629-104">You can define private fields and private functions for F# classes by using `let` bindings in the class definition.</span></span>

## <a name="syntax"></a><span data-ttu-id="5d629-105">構文</span><span class="sxs-lookup"><span data-stu-id="5d629-105">Syntax</span></span>

```fsharp
// Field.
[static] let [ mutable ] binding1 [ and ... binding-n ]

// Function.
[static] let [ rec ] binding1 [ and ... binding-n ]
```

## <a name="remarks"></a><span data-ttu-id="5d629-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="5d629-106">Remarks</span></span>

<span data-ttu-id="5d629-107">クラスの見出しと継承宣言後、メンバーの定義の前に、前の構文が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d629-107">The previous syntax appears after the class heading and inheritance declarations but before any member definitions.</span></span> <span data-ttu-id="5d629-108">ような構文は、`let`クラスがクラスで定義した名前の外部でバインドがクラスに限定されているスコープを設定します。</span><span class="sxs-lookup"><span data-stu-id="5d629-108">The syntax is like that of `let` bindings outside of classes, but the names defined in a class have a scope that is limited to the class.</span></span> <span data-ttu-id="5d629-109">A`let`バインディングは、プライベート フィールドまたはデータを公開する関数を作成します。 または、関数で公開されている、プロパティまたはメンバー メソッドを宣言します。</span><span class="sxs-lookup"><span data-stu-id="5d629-109">A `let` binding creates a private field or function; to expose data or functions publicly, declare a property or a member method.</span></span>

<span data-ttu-id="5d629-110">A`let`バインドがない静的なインスタンスと呼びます`let`バインドします。</span><span class="sxs-lookup"><span data-stu-id="5d629-110">A `let` binding that is not static is called an instance `let` binding.</span></span> <span data-ttu-id="5d629-111">インスタンス`let`バインド オブジェクトが作成されたときに実行します。</span><span class="sxs-lookup"><span data-stu-id="5d629-111">Instance `let` bindings execute when objects are created.</span></span> <span data-ttu-id="5d629-112">静的`let`バインド型が最初に使用される前に実行することが保証されると、クラスの静的初期化子の一部であります。</span><span class="sxs-lookup"><span data-stu-id="5d629-112">Static `let` bindings are part of the static initializer for the class, which is guaranteed to execute before the type is first used.</span></span>

<span data-ttu-id="5d629-113">インスタンス内のコード`let`バインドは、プライマリ コンス トラクターのパラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5d629-113">The code within instance `let` bindings can use the primary constructor's parameters.</span></span>

<span data-ttu-id="5d629-114">属性およびアクセシビリティ修飾子がで許可されていません`let`クラスにバインドします。</span><span class="sxs-lookup"><span data-stu-id="5d629-114">Attributes and accessibility modifiers are not permitted on `let` bindings in classes.</span></span>

<span data-ttu-id="5d629-115">次のコード例は、いくつかの種類を示しています`let`クラスにバインドします。</span><span class="sxs-lookup"><span data-stu-id="5d629-115">The following code examples illustrate several types of `let` bindings in classes.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

<span data-ttu-id="5d629-116">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5d629-116">The output is as follows.</span></span>

```
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a><span data-ttu-id="5d629-117">フィールドを作成する別の方法</span><span class="sxs-lookup"><span data-stu-id="5d629-117">Alternative Ways to Create Fields</span></span>

<span data-ttu-id="5d629-118">使用することも、`val`プライベート フィールドを作成するキーワード。</span><span class="sxs-lookup"><span data-stu-id="5d629-118">You can also use the `val` keyword to create a private field.</span></span> <span data-ttu-id="5d629-119">使用する場合、`val`キーワードが与えられていない値と、オブジェクトが作成されますが、代わりに、既定値で初期化されます。</span><span class="sxs-lookup"><span data-stu-id="5d629-119">When using the `val` keyword, the field is not given a value when the object is created, but instead is initialized with a default value.</span></span> <span data-ttu-id="5d629-120">詳細については、次を参照してください。[明示的なフィールド:Val キーワード](explicit-fields-the-val-keyword.md)します。</span><span class="sxs-lookup"><span data-stu-id="5d629-120">For more information, see [Explicit Fields: The val Keyword](explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="5d629-121">メンバーの定義を使用して、キーワードを追加して、クラスでプライベート フィールドを定義することもできます`private`を定義します。</span><span class="sxs-lookup"><span data-stu-id="5d629-121">You can also define private fields in a class by using a member definition and adding the keyword `private` to the definition.</span></span> <span data-ttu-id="5d629-122">コードを書き直すことがなく、メンバーのアクセシビリティを変更する場合に便利なことができます。</span><span class="sxs-lookup"><span data-stu-id="5d629-122">This can be useful if you expect to change the accessibility of a member without rewriting your code.</span></span> <span data-ttu-id="5d629-123">詳細については、「[Access Control](../access-control.md)」(アクセス制御) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d629-123">For more information, see [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5d629-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d629-124">See also</span></span>

- [<span data-ttu-id="5d629-125">メンバー</span><span class="sxs-lookup"><span data-stu-id="5d629-125">Members</span></span>](index.md)
- [<span data-ttu-id="5d629-126">クラス内の `do` バインド</span><span class="sxs-lookup"><span data-stu-id="5d629-126">`do` Bindings in Classes</span></span>](do-bindings-in-classes.md)
- [<span data-ttu-id="5d629-127">`let` バインド</span><span class="sxs-lookup"><span data-stu-id="5d629-127">`let` Bindings</span></span>](../functions/let-bindings.md)
