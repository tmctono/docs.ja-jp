---
title: 構造体の使用 - C# プログラミング ガイド
ms.date: 07/20/2015
helpviewer_keywords:
- structs [C#], using
ms.assetid: cea4a459-9eb9-442b-8d08-490e0797ba38
ms.openlocfilehash: 22d63465c534090a8918348ea5f050739c0cf01c
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964743"
---
# <a name="using-structs-c-programming-guide"></a><span data-ttu-id="acb35-102">構造体の使用 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="acb35-102">Using structs (C# Programming Guide)</span></span>

<span data-ttu-id="acb35-103">`struct` 型は、 `Point`、 `Rectangle`、 `Color`などの軽量のオブジェクトを表すのに適しています。</span><span class="sxs-lookup"><span data-stu-id="acb35-103">The `struct` type is suitable for representing lightweight objects such as `Point`, `Rectangle`, and `Color`.</span></span> <span data-ttu-id="acb35-104">点を表すには [自動実装プロパティ](../../language-reference/keywords/class.md) がある [クラス](./auto-implemented-properties.md)を使用するのと同じくらい便利ですが、シナリオによっては [構造体](../../language-reference/keywords/struct.md) を使用する方がより効率的です。</span><span class="sxs-lookup"><span data-stu-id="acb35-104">Although it is just as convenient to represent a point as a [class](../../language-reference/keywords/class.md) with [Auto-Implemented Properties](./auto-implemented-properties.md), a [struct](../../language-reference/keywords/struct.md) might be more efficient in some scenarios.</span></span> <span data-ttu-id="acb35-105">たとえば、1,000 個の `Point` オブジェクトから成る配列を宣言する場合は、各オブジェクトの参照用に追加のメモリを割り当てます。この場合、構造体であれば処理上の負荷を抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="acb35-105">For example, if you declare an array of 1000 `Point` objects, you will allocate additional memory for referencing each object; in this case, a struct would be less expensive.</span></span> <span data-ttu-id="acb35-106">.NET には <xref:System.Drawing.Point> という名前のオブジェクトが既に含まれているため、この例の構造体には代わりに `Coords` という名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="acb35-106">Because .NET already contains an object called <xref:System.Drawing.Point>, the struct in this example is named `Coords` instead.</span></span>

[!code-csharp[csProgGuideObjects#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#1)]

<span data-ttu-id="acb35-107">構造体にパラメーターなしのコンストラクターを定義するとエラーになります。</span><span class="sxs-lookup"><span data-stu-id="acb35-107">It is an error to define a parameterless constructor for a struct.</span></span> <span data-ttu-id="acb35-108">また、構造体の本体のインスタンス フィールドを初期化した場合もエラーになります。</span><span class="sxs-lookup"><span data-stu-id="acb35-108">It is also an error to initialize an instance field in a struct body.</span></span> <span data-ttu-id="acb35-109">外部アクセス可能な構造体メンバーを初期化するには、パラメーター化されたコンストラクター、暗黙的なパラメーターなしのコンストラクター、[オブジェクト初期化子](object-and-collection-initializers.md)を使用するか、構造体を宣言した後で個別にメンバーにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="acb35-109">You can initialize externally accessible struct members only by using a parameterized constructor, the implicit, parameterless constructor, an [object initializer](object-and-collection-initializers.md), or by accessing the members individually after the struct is declared.</span></span> <span data-ttu-id="acb35-110">プライベートかそれ以外の理由でアクセスできないメンバーの場合、コンストラクターを独占的に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="acb35-110">Any private or otherwise inaccessible members require the use of constructors exclusively.</span></span>

<span data-ttu-id="acb35-111">[new](../../language-reference/operators/new-operator.md) 演算子を使用して struct オブジェクトを作成すると、[コンストラクター シグネチャ](constructors.md#constructor-syntax)に基づき、オブジェクトが作成されて適切なコンストラクターが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="acb35-111">When you create a struct object using the [new](../../language-reference/operators/new-operator.md) operator, it gets created and the appropriate constructor is called according to the [constructor's signature](constructors.md#constructor-syntax).</span></span> <span data-ttu-id="acb35-112">クラスとは異なり、構造体は `new` 演算子を使用せずにインスタンス化できます。</span><span class="sxs-lookup"><span data-stu-id="acb35-112">Unlike classes, structs can be instantiated without using the `new` operator.</span></span> <span data-ttu-id="acb35-113">このような場合、コンストラクターの呼び出しが行われないため、割り当てがより効率的になります。</span><span class="sxs-lookup"><span data-stu-id="acb35-113">In such a case, there is no constructor call, which makes the allocation more efficient.</span></span> <span data-ttu-id="acb35-114">ただし、各フィールドは未割り当てのままになり、すべてのフィールドが初期化されるまではオブジェクトを使用できません。</span><span class="sxs-lookup"><span data-stu-id="acb35-114">However, the fields will remain unassigned and the object cannot be used until all of the fields are initialized.</span></span> <span data-ttu-id="acb35-115">たとえば、プロパティから値を取得または設定することができません。</span><span class="sxs-lookup"><span data-stu-id="acb35-115">This includes the inability to get or set values through properties.</span></span>

<span data-ttu-id="acb35-116">パラメーターなしのコンストラクターを使用して構造体オブジェクトを初期化する場合、その[既定値](../../language-reference/builtin-types/default-values.md)に基づいてすべてのメンバーが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="acb35-116">If you instantiate a struct object using the parameterless constructor, all members are assigned according to their [default values](../../language-reference/builtin-types/default-values.md).</span></span>

<span data-ttu-id="acb35-117">構造体のパラメーターを使用してコンストラクターを記述するとき、すべてのメンバーを明示的に初期化する必要があります。それ以外の場合、1 つまたは複数のメンバーが未割り当てのままとなり、構造体を使用できず、コンパイラ エラー [CS0171](../../misc/cs0171.md) が生成されます。</span><span class="sxs-lookup"><span data-stu-id="acb35-117">When writing a constructor with parameters for a struct, you must explicitly initialize all members; otherwise one or more members remain unassigned and the struct cannot be used, producing compiler error [CS0171](../../misc/cs0171.md).</span></span>

<span data-ttu-id="acb35-118">クラスには継承がありますが、構造体には継承がありません。</span><span class="sxs-lookup"><span data-stu-id="acb35-118">There is no inheritance for structs as there is for classes.</span></span> <span data-ttu-id="acb35-119">構造体は、他の構造体やクラスから継承できず、基本クラスになることはできません。</span><span class="sxs-lookup"><span data-stu-id="acb35-119">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="acb35-120">ただし、構造体は、基本クラス <xref:System.Object>から継承します。</span><span class="sxs-lookup"><span data-stu-id="acb35-120">Structs, however, inherit from the base class <xref:System.Object>.</span></span> <span data-ttu-id="acb35-121">構造体は、クラスの場合とまったく同じ方法でインターフェイスを実装できます。</span><span class="sxs-lookup"><span data-stu-id="acb35-121">A struct can implement interfaces, and it does that exactly as classes do.</span></span>

<span data-ttu-id="acb35-122">`struct`キーワードを使用してクラスを宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="acb35-122">You cannot declare a class using the keyword `struct`.</span></span> <span data-ttu-id="acb35-123">C# では、クラスと構造体は、意味が異なります。</span><span class="sxs-lookup"><span data-stu-id="acb35-123">In C#, classes and structs are semantically different.</span></span> <span data-ttu-id="acb35-124">構造体は値型ですが、クラスは参照型です。</span><span class="sxs-lookup"><span data-stu-id="acb35-124">A struct is a value type, while a class is a reference type.</span></span> <span data-ttu-id="acb35-125">詳細については、[値型](../../language-reference/keywords/value-types.md)と[参照型](../../language-reference/keywords/reference-types.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="acb35-125">For more information, see [Value types](../../language-reference/keywords/value-types.md) and [Reference types](../../language-reference/keywords/reference-types.md).</span></span>

<span data-ttu-id="acb35-126">参照型の機能が必要な場合以外は、小さいクラスを構造体として宣言した方が、システムによってより効率的に処理される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="acb35-126">Unless you need reference-type semantics, a small class may be more efficiently handled by the system if you declare it as a struct instead.</span></span>

## <a name="example-1"></a><span data-ttu-id="acb35-127">例 1</span><span class="sxs-lookup"><span data-stu-id="acb35-127">Example 1</span></span>

<span data-ttu-id="acb35-128">この例では、パラメーターなしのコンストラクターとパラメーター化されたコンストラクターの両方を使用して `struct` の初期化を示します。</span><span class="sxs-lookup"><span data-stu-id="acb35-128">This example demonstrates `struct` initialization using both parameterless and parameterized constructors.</span></span>

[!code-csharp[csProgGuideObjects#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#1)]

[!code-csharp[csProgGuideObjects#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#2)]

## <a name="example-2"></a><span data-ttu-id="acb35-129">例 2</span><span class="sxs-lookup"><span data-stu-id="acb35-129">Example 2</span></span>

<span data-ttu-id="acb35-130">構造体に固有の機能を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="acb35-130">This example demonstrates a feature that is unique to structs.</span></span> <span data-ttu-id="acb35-131">この例では、`new` 演算子を使用せずに Coords オブジェクトを作成しています。</span><span class="sxs-lookup"><span data-stu-id="acb35-131">It creates a Coords object without using the `new` operator.</span></span> <span data-ttu-id="acb35-132">`struct` を `class`という単語に置き換えた場合、プログラムはコンパイルされません。</span><span class="sxs-lookup"><span data-stu-id="acb35-132">If you replace the word `struct` with the word `class`, the program will not compile.</span></span>

[!code-csharp[csProgGuideObjects#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#1)]

[!code-csharp[csProgGuideObjects#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#3)]

## <a name="see-also"></a><span data-ttu-id="acb35-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="acb35-133">See also</span></span>

- [<span data-ttu-id="acb35-134">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="acb35-134">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="acb35-135">クラスと構造体</span><span class="sxs-lookup"><span data-stu-id="acb35-135">Classes and Structs</span></span>](index.md)
- [<span data-ttu-id="acb35-136">構造体</span><span class="sxs-lookup"><span data-stu-id="acb35-136">Structs</span></span>](structs.md)
