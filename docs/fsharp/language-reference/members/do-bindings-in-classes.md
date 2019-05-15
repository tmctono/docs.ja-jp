---
title: クラス内の do バインド
description: 使用する方法について説明します、 F# 'do'、オブジェクトが作成されたとき、または型が初めて使用すると、操作を実行するクラス定義のバインディング。
ms.date: 05/16/2016
ms.openlocfilehash: c924c882974989436d8ea404ebee0a7ef3c54fd3
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641799"
---
# <a name="do-bindings-in-classes"></a><span data-ttu-id="00234-103">クラス内の do バインド</span><span class="sxs-lookup"><span data-stu-id="00234-103">do Bindings in Classes</span></span>

<span data-ttu-id="00234-104">A`do`クラス定義のバインディング オブジェクトが作成されるときに、静的なは、操作を実行します`do`バインド型を使用する場合最初。</span><span class="sxs-lookup"><span data-stu-id="00234-104">A `do` binding in a class definition performs actions when the object is constructed or, for a static `do` binding, when the type is first used.</span></span>

## <a name="syntax"></a><span data-ttu-id="00234-105">構文</span><span class="sxs-lookup"><span data-stu-id="00234-105">Syntax</span></span>

```fsharp
[static] do expression
```

## <a name="remarks"></a><span data-ttu-id="00234-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="00234-106">Remarks</span></span>

<span data-ttu-id="00234-107">A`do`と連携するか後に、バインドが表示されます`let`バインド、メンバーのクラス定義を定義する前にします。</span><span class="sxs-lookup"><span data-stu-id="00234-107">A `do` binding appears together with or after `let` bindings but before member definitions in a class definition.</span></span> <span data-ttu-id="00234-108">ですが、`do`キーワードは省略可能です`do`バインド モジュール レベルでは、これは省略できませんの`do`クラス定義内のバインディング。</span><span class="sxs-lookup"><span data-stu-id="00234-108">Although the `do` keyword is optional for `do` bindings at the module level, it is not optional for `do` bindings in a class definition.</span></span>

<span data-ttu-id="00234-109">いずれかのすべてのオブジェクトの構築、特定の型、静的でない`do`バインドおよび非静的`let`バインドは、クラス定義で出現する順序で実行されます。</span><span class="sxs-lookup"><span data-stu-id="00234-109">For the construction of every object of any given type, non-static `do` bindings and non-static `let` bindings are executed in the order in which they appear in the class definition.</span></span> <span data-ttu-id="00234-110">複数`do`バインドが 1 つの型で発生することができます。</span><span class="sxs-lookup"><span data-stu-id="00234-110">Multiple `do` bindings can occur in one type.</span></span> <span data-ttu-id="00234-111">非静的`let`バインドおよび非静的`do`バインドが、プライマリ コンス トラクターの本体になります。</span><span class="sxs-lookup"><span data-stu-id="00234-111">The non-static `let` bindings and the non-static `do` bindings become the body of the primary constructor.</span></span> <span data-ttu-id="00234-112">非静的コード`do`プライマリ コンス トラクターのパラメーターと値または関数で定義されているバインディング セクションを参照できる、 `let` bindings セクション。</span><span class="sxs-lookup"><span data-stu-id="00234-112">The code in the non-static `do` bindings section can reference the primary constructor parameters and any values or functions that are defined in the `let` bindings section.</span></span>

<span data-ttu-id="00234-113">非静的`do`バインドは、クラスには、自己識別子で定義されている限り、クラスのメンバーにアクセスできる、`as`見出し、およびクラスの自己識別子でこれらのメンバーのすべての使用が限定されている限り、クラス内のキーワード。</span><span class="sxs-lookup"><span data-stu-id="00234-113">Non-static `do` bindings can access members of the class as long as the class has a self identifier that is defined by an `as` keyword in the class heading, and as long as all uses of those members are qualified with the self identifier for the class.</span></span>

<span data-ttu-id="00234-114">`let`バインド、メンバーが正常に動作することを保証するために必要な多くの場合、クラスのプライベート フィールドを初期化する`do`バインドが後に通常記述`let`でコードのバインディング、`do`バインドできます完全に初期化されたオブジェクトで実行されます。</span><span class="sxs-lookup"><span data-stu-id="00234-114">Because `let` bindings initialize the private fields of a class, which is often necessary to guarantee that members behave as expected, `do` bindings are usually put after `let` bindings so that code in the `do` binding can execute with a fully initialized object.</span></span> <span data-ttu-id="00234-115">コードでは、初期化が完了する前に、メンバーを使用しようとして、InvalidOperationException が発生します。</span><span class="sxs-lookup"><span data-stu-id="00234-115">If your code attempts to use a member before the initialization is complete, an InvalidOperationException is raised.</span></span>

<span data-ttu-id="00234-116">静的`do`バインドは、静的メンバーを参照できる、またはフィールドを囲むクラスしますが、ないインスタンス メンバーまたはフィールド。</span><span class="sxs-lookup"><span data-stu-id="00234-116">Static `do` bindings can reference static members or fields of the enclosing class but not instance members or fields.</span></span> <span data-ttu-id="00234-117">静的`do`バインド クラスが最初に使用される前に実行することが保証されると、クラスの静的初期化子の一部になります。</span><span class="sxs-lookup"><span data-stu-id="00234-117">Static `do` bindings become part of the static initializer for the class, which is guaranteed to execute before the class is first used.</span></span>

<span data-ttu-id="00234-118">属性は無視されます`do`型にバインドします。</span><span class="sxs-lookup"><span data-stu-id="00234-118">Attributes are ignored for `do` bindings in types.</span></span> <span data-ttu-id="00234-119">属性で実行するコードに必要なかどうか、 `do` 、バインドする必要がありますに適用される、プライマリ コンス トラクター。</span><span class="sxs-lookup"><span data-stu-id="00234-119">If an attribute is required for code that executes in a `do` binding, it must be applied to the primary constructor.</span></span>

<span data-ttu-id="00234-120">次のコードでクラスに静的な`do`バインドおよび非静的`do`バインドします。</span><span class="sxs-lookup"><span data-stu-id="00234-120">In the following code, a class has a static `do` binding and a non-static `do` binding.</span></span> <span data-ttu-id="00234-121">オブジェクトが 2 つのパラメーターを持つコンス トラクター`a`と`b`で 2 つのプライベート フィールドが定義されていると、`let`クラスにバインドします。</span><span class="sxs-lookup"><span data-stu-id="00234-121">The object has a constructor that has two parameters, `a` and `b`, and two private fields are defined in the `let` bindings for the class.</span></span> <span data-ttu-id="00234-122">2 つのプロパティも定義します。</span><span class="sxs-lookup"><span data-stu-id="00234-122">Two properties are also defined.</span></span> <span data-ttu-id="00234-123">これらすべては、静的でないスコープ`do`バインディング セクションには、それらすべての値を出力します線で示すようにします。</span><span class="sxs-lookup"><span data-stu-id="00234-123">All of these are in scope in the non-static `do` bindings section, as is illustrated by the line that prints all those values.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

<span data-ttu-id="00234-124">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="00234-124">The output is as follows.</span></span>

```console
Initializing MyType.
Initializing object 1 2 2 4 8 16
```

## <a name="see-also"></a><span data-ttu-id="00234-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="00234-125">See also</span></span>

- [<span data-ttu-id="00234-126">メンバー</span><span class="sxs-lookup"><span data-stu-id="00234-126">Members</span></span>](index.md)
- [<span data-ttu-id="00234-127">クラス</span><span class="sxs-lookup"><span data-stu-id="00234-127">Classes</span></span>](../classes.md)
- [<span data-ttu-id="00234-128">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="00234-128">Constructors</span></span>](constructors.md)
- [<span data-ttu-id="00234-129">クラス内の `let` バインド</span><span class="sxs-lookup"><span data-stu-id="00234-129">`let` Bindings in Classes</span></span>](let-bindings-in-classes.md)
- [<span data-ttu-id="00234-130">`do` バインド</span><span class="sxs-lookup"><span data-stu-id="00234-130">`do` Bindings</span></span>](../functions/do-Bindings.md)
