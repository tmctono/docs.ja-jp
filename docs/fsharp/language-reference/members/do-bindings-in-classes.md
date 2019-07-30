---
title: クラス内の do バインド
description: クラス定義でF# ' do ' バインディングを使用する方法について説明します。これは、オブジェクトが構築されたとき、または型が最初に使用されたときにアクションを実行します。
ms.date: 05/16/2016
ms.openlocfilehash: ced4f1bb17d9e23bf51cc79b5a275cc334cca013
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627580"
---
# <a name="do-bindings-in-classes"></a><span data-ttu-id="0e509-103">クラス内の do バインド</span><span class="sxs-lookup"><span data-stu-id="0e509-103">do Bindings in Classes</span></span>

<span data-ttu-id="0e509-104">クラス定義内の`do` バインディングは、オブジェクトが構築されたとき、または静的バインディングの場合に、型が最初に使用されたときにアクションを実行します。`do`</span><span class="sxs-lookup"><span data-stu-id="0e509-104">A `do` binding in a class definition performs actions when the object is constructed or, for a static `do` binding, when the type is first used.</span></span>

## <a name="syntax"></a><span data-ttu-id="0e509-105">構文</span><span class="sxs-lookup"><span data-stu-id="0e509-105">Syntax</span></span>

```fsharp
[static] do expression
```

## <a name="remarks"></a><span data-ttu-id="0e509-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="0e509-106">Remarks</span></span>

<span data-ttu-id="0e509-107">バインディング`do`は、バインディングと共に`let` 、またはその後、クラス定義のメンバー定義の前に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0e509-107">A `do` binding appears together with or after `let` bindings but before member definitions in a class definition.</span></span> <span data-ttu-id="0e509-108">キーワードは、モジュールレベルで`do`のバインディングに対しては省略可能ですが、 `do`クラス定義のバインディングでは省略可能ではありません。 `do`</span><span class="sxs-lookup"><span data-stu-id="0e509-108">Although the `do` keyword is optional for `do` bindings at the module level, it is not optional for `do` bindings in a class definition.</span></span>

<span data-ttu-id="0e509-109">指定された型のすべてのオブジェクトの構築では、 `do`非静的バインディングと非`let`静的バインディングは、クラス定義に出現する順序で実行されます。</span><span class="sxs-lookup"><span data-stu-id="0e509-109">For the construction of every object of any given type, non-static `do` bindings and non-static `let` bindings are executed in the order in which they appear in the class definition.</span></span> <span data-ttu-id="0e509-110">複数`do`のバインドを1つの型で実行できます。</span><span class="sxs-lookup"><span data-stu-id="0e509-110">Multiple `do` bindings can occur in one type.</span></span> <span data-ttu-id="0e509-111">非静的`let`バインドと非静的`do`バインドは、プライマリコンストラクターの本体になります。</span><span class="sxs-lookup"><span data-stu-id="0e509-111">The non-static `let` bindings and the non-static `do` bindings become the body of the primary constructor.</span></span> <span data-ttu-id="0e509-112">非静的`do`バインドセクションのコードは、プライマリコンストラクターのパラメーターと、 `let`バインドセクションで定義されている任意の値または関数を参照できます。</span><span class="sxs-lookup"><span data-stu-id="0e509-112">The code in the non-static `do` bindings section can reference the primary constructor parameters and any values or functions that are defined in the `let` bindings section.</span></span>

<span data-ttu-id="0e509-113">非静的`do`バインディングは、クラスのメンバーがクラスの見出しで定義`as`されている自己識別子を持ち、そのメンバーのすべての使用がクラスの自己識別子で修飾されている限り、クラスのメンバーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0e509-113">Non-static `do` bindings can access members of the class as long as the class has a self identifier that is defined by an `as` keyword in the class heading, and as long as all uses of those members are qualified with the self identifier for the class.</span></span>

<span data-ttu-id="0e509-114">バインディング`let`は、メンバーが`do`期待どおりに動作することを保証するために必要な、クラスのプライベートフィールドを初期化するため`let` 、通常、バインディングの後`do`のコードはバインドの後に配置されます。完全に初期化されたオブジェクトを使用してを実行します。</span><span class="sxs-lookup"><span data-stu-id="0e509-114">Because `let` bindings initialize the private fields of a class, which is often necessary to guarantee that members behave as expected, `do` bindings are usually put after `let` bindings so that code in the `do` binding can execute with a fully initialized object.</span></span> <span data-ttu-id="0e509-115">初期化が完了する前にコードがメンバーを使用しようとすると、InvalidOperationException が発生します。</span><span class="sxs-lookup"><span data-stu-id="0e509-115">If your code attempts to use a member before the initialization is complete, an InvalidOperationException is raised.</span></span>

<span data-ttu-id="0e509-116">静的`do`バインドは、外側のクラスの静的メンバーまたはフィールドを参照できますが、インスタンスのメンバーやフィールドを参照することはできません。</span><span class="sxs-lookup"><span data-stu-id="0e509-116">Static `do` bindings can reference static members or fields of the enclosing class but not instance members or fields.</span></span> <span data-ttu-id="0e509-117">静的`do`バインディングは、クラスの静的初期化子の一部になります。これは、クラスが最初に使用される前に実行が保証されます。</span><span class="sxs-lookup"><span data-stu-id="0e509-117">Static `do` bindings become part of the static initializer for the class, which is guaranteed to execute before the class is first used.</span></span>

<span data-ttu-id="0e509-118">型の`do`バインディングでは、属性は無視されます。</span><span class="sxs-lookup"><span data-stu-id="0e509-118">Attributes are ignored for `do` bindings in types.</span></span> <span data-ttu-id="0e509-119">`do`バインディングで実行されるコードに属性が必要な場合は、その属性をプライマリコンストラクターに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e509-119">If an attribute is required for code that executes in a `do` binding, it must be applied to the primary constructor.</span></span>

<span data-ttu-id="0e509-120">次のコードでは、クラスに静的`do`バインディングと非静的`do`バインディングがあります。</span><span class="sxs-lookup"><span data-stu-id="0e509-120">In the following code, a class has a static `do` binding and a non-static `do` binding.</span></span> <span data-ttu-id="0e509-121">オブジェクトには、 `a`とと`b`いう2つのパラメーターを持つコンストラクターがあり、2つの`let`プライベートフィールドがクラスのバインドで定義されています。</span><span class="sxs-lookup"><span data-stu-id="0e509-121">The object has a constructor that has two parameters, `a` and `b`, and two private fields are defined in the `let` bindings for the class.</span></span> <span data-ttu-id="0e509-122">2つのプロパティも定義されています。</span><span class="sxs-lookup"><span data-stu-id="0e509-122">Two properties are also defined.</span></span> <span data-ttu-id="0e509-123">これらはすべて、これらの値をすべて出力する`do`行で示されているように、非静的バインドセクションのスコープ内にあります。</span><span class="sxs-lookup"><span data-stu-id="0e509-123">All of these are in scope in the non-static `do` bindings section, as is illustrated by the line that prints all those values.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

<span data-ttu-id="0e509-124">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0e509-124">The output is as follows.</span></span>

```console
Initializing MyType.
Initializing object 1 2 2 4 8 16
```

## <a name="see-also"></a><span data-ttu-id="0e509-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e509-125">See also</span></span>

- [<span data-ttu-id="0e509-126">メンバー</span><span class="sxs-lookup"><span data-stu-id="0e509-126">Members</span></span>](index.md)
- [<span data-ttu-id="0e509-127">クラス</span><span class="sxs-lookup"><span data-stu-id="0e509-127">Classes</span></span>](../classes.md)
- [<span data-ttu-id="0e509-128">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="0e509-128">Constructors</span></span>](constructors.md)
- [<span data-ttu-id="0e509-129">クラス内の `let` バインド</span><span class="sxs-lookup"><span data-stu-id="0e509-129">`let` Bindings in Classes</span></span>](let-bindings-in-classes.md)
- [<span data-ttu-id="0e509-130">`do`現存</span><span class="sxs-lookup"><span data-stu-id="0e509-130">`do` Bindings</span></span>](../functions/do-Bindings.md)
