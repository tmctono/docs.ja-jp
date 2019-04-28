---
title: プロパティ
description: オブジェクトに関連付けられている値を表すメンバーである F# プロパティ、について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: bf605ee1135bd3b3561bde9a8ae66353497931b0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666366"
---
# <a name="properties"></a><span data-ttu-id="bfbc9-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="bfbc9-103">Properties</span></span>

<span data-ttu-id="bfbc9-104">*プロパティ*オブジェクトに関連付けられている値を表すメンバーします。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-104">*Properties* are members that represent values associated with an object.</span></span>

## <a name="syntax"></a><span data-ttu-id="bfbc9-105">構文</span><span class="sxs-lookup"><span data-stu-id="bfbc9-105">Syntax</span></span>

```fsharp
// Property that has both get and set defined.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with [accessibility-modifier] get() =
    get-function-body
and [accessibility-modifier] set parameter =
    set-function-body

// Alternative syntax for a property that has get and set.
[ attributes-for-get ]
[ static ] member [accessibility-modifier-for-get] [self-identifier.]PropertyName =
    get-function-body
[ attributes-for-set ]
[ static ] member [accessibility-modifier-for-set] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName =
    get-function-body

// Alternative syntax for property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with get() =
    get-function-body

// Property that has set only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Automatically implemented properties.
[ attributes ]
[ static ] member val [accessibility-modifier] PropertyName = initialization-expression [ with get, set ]
```

## <a name="remarks"></a><span data-ttu-id="bfbc9-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="bfbc9-106">Remarks</span></span>

<span data-ttu-id="bfbc9-107">プロパティは、"が、"オブジェクト指向プログラミング、オブジェクト インスタンスにして、または型の静的プロパティに関連付けられているデータを表すリレーションシップ。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-107">Properties represent the "has a" relationship in object-oriented programming, representing data that is associated with object instances or, for static properties, with the type.</span></span>

<span data-ttu-id="bfbc9-108">プロパティに、(バッキング ストアとも呼ばれます) の基になる値を明示的に指定するかどうか、またはのバッキング ストアを自動的に生成するコンパイラを許可したいかどうかに応じて、2 つの方法でプロパティを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-108">You can declare properties in two ways, depending on whether you want to explicitly specify the underlying value (also called the backing store) for the property, or if you want to allow the compiler to automatically generate the backing store for you.</span></span> <span data-ttu-id="bfbc9-109">通常、プロパティが値または変数の単純なラッパーにすぎませんプロパティに、自明でない実装がある場合より明確な方法、および自動の方法を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-109">Generally, you should use the more explicit way if the property has a non-trivial implementation and the automatic way when the property is just a simple wrapper for a value or variable.</span></span> <span data-ttu-id="bfbc9-110">プロパティを明示的に宣言するには、使用、`member`キーワード。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-110">To declare a property explicitly, use the `member` keyword.</span></span> <span data-ttu-id="bfbc9-111">この宣言型構文を指定する構文の後に、`get`と`set`もという名前のメソッド*アクセサー*します。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-111">This declarative syntax is followed by the syntax that specifies the `get` and `set` methods, also named *accessors*.</span></span> <span data-ttu-id="bfbc9-112">読み取り/書き込み、書き込み専用、読み取り専用プロパティでは、さまざまな形式で「構文」セクションに示すように、明示的な構文が使用されます。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-112">The various forms of the explicit syntax shown in the syntax section are used for read/write, read-only, and write-only properties.</span></span> <span data-ttu-id="bfbc9-113">読み取り専用のプロパティを定義するのみ、`get`メソッドです。 書き込み専用のプロパティの定義のみ、`set`メソッド。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-113">For read-only properties, you define only a `get` method; for write-only properties, define only a `set` method.</span></span> <span data-ttu-id="bfbc9-114">プロパティは、両方を持つ場合は注意`get`と`set`アクセサー、別の構文を使用する属性とは、次のコードのように、アクセサーごとに異なるアクセシビリティ修飾子を指定します。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-114">Note that when a property has both `get` and `set` accessors, the alternative syntax enables you to specify attributes and accessibility modifiers that are different for each accessor, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3201.fs)]

<span data-ttu-id="bfbc9-115">読み取り/書き込みプロパティは、両方があるため、`get`と`set`メソッドの順序`get`と`set`元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-115">For read/write properties, which have both a `get` and `set` method, the order of `get` and `set` can be reversed.</span></span> <span data-ttu-id="bfbc9-116">構文を指定する代わりに、`get`のみの構文と`set`結合構文を使用する代わりにのみです。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-116">Alternatively, you can provide the syntax shown for `get` only and the syntax shown for `set` only instead of using the combined syntax.</span></span> <span data-ttu-id="bfbc9-117">これを行う簡単にコメント アウト個人`get`または`set`メソッドでは、これは行う必要がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-117">Doing this makes it easier to comment out the individual `get` or `set` method, if that is something you might need to do.</span></span> <span data-ttu-id="bfbc9-118">結合の構文を使用するには、この方法は、次のコードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-118">This alternative to using the combined syntax is shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3203.fs)]

<span data-ttu-id="bfbc9-119">プライベート値のプロパティのデータと呼びます保留が*バッキング ストア*します。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-119">Private values that hold the data for properties are called *backing stores*.</span></span> <span data-ttu-id="bfbc9-120">コンパイラでバッキング ストアを自動的に作成するには、キーワードを使用して`member val`、自己の識別子を省略し、プロパティを初期化する式を指定します。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-120">To have the compiler create the backing store automatically, use the keywords `member val`, omit the self-identifier, then provide an expression to initialize the property.</span></span> <span data-ttu-id="bfbc9-121">プロパティを変更可能である場合は、含める`with get, set`します。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-121">If the property is to be mutable, include `with get, set`.</span></span> <span data-ttu-id="bfbc9-122">たとえば、次のクラス型には、自動的に実装された 2 つのプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-122">For example, the following class type includes two automatically implemented properties.</span></span> <span data-ttu-id="bfbc9-123">`Property1` 読み取り専用であり、プライマリ コンス トラクターに渡される引数に初期化されますと`Property2`は空の文字列に初期化され設定可能なプロパティです。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-123">`Property1` is read-only and is initialized to the argument provided to the primary constructor, and `Property2` is a settable property initialized to an empty string:</span></span>

```fsharp
type MyClass(property1 : int) =
member val Property1 = property1
member val Property2 = "" with get, set
```

<span data-ttu-id="bfbc9-124">自動実装プロパティにと同じように他のメンバー定義の前に含める必要があるために、型の初期化の一環`let`バインドと`do`型定義内のバインディング。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-124">Automatically implemented properties are part of the initialization of a type, so they must be included before any other member definitions, just like `let` bindings and `do` bindings in a type definition.</span></span> <span data-ttu-id="bfbc9-125">初期化時に、プロパティがアクセスされるたびにしないと、自動的に実装されたプロパティを初期化する式がのみ評価されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-125">Note that the expression that initializes an automatically implemented property is only evaluated upon initialization, and not every time the property is accessed.</span></span> <span data-ttu-id="bfbc9-126">この動作では、明示的に実装されたプロパティの動作とは対照的です。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-126">This behavior is in contrast to the behavior of an explicitly implemented property.</span></span> <span data-ttu-id="bfbc9-127">この実質的に意味はこれらのプロパティを初期化するコードは、クラスのコンス トラクターに追加されます。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-127">What this effectively means is that the code to initialize these properties is added to the constructor of a class.</span></span> <span data-ttu-id="bfbc9-128">この違いを示しています。 次のコードを検討してください。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-128">Consider the following code that shows this difference:</span></span>

```fsharp
type MyClass() =
    let random  = new System.Random()
    member val AutoProperty = random.Next() with get, set
    member this.ExplicitProperty = random.Next()

let class1 = new MyClass()

printfn "class1.AutoProperty = %d" class1.AutoProperty
printfn "class1.AutoProperty = %d" class1.AutoProperty
printfn "class1.ExplicitProperty = %d" class1.ExplicitProperty
printfn "class1.ExplicitProperty = %d" class1.ExplicitProperty
```

<span data-ttu-id="bfbc9-129">**出力**</span><span class="sxs-lookup"><span data-stu-id="bfbc9-129">**Output**</span></span>

```
class1.AutoProperty = 1853799794
class1.AutoProperty = 1853799794
class1.ExplicitProperty = 978922705
class1.ExplicitProperty = 1131210765
```

<span data-ttu-id="bfbc9-130">AutoProperty の値変更されていないことと、繰り返し呼び出したときに、ExplicitProperty 変更のたびに呼び出されますが、上記のコードの出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-130">The output of the preceding code shows that the value of AutoProperty is unchanged when called repeatedly, whereas the ExplicitProperty changes each time it is called.</span></span> <span data-ttu-id="bfbc9-131">これを示します、自動的に実装されたプロパティの式では、毎回は評価されませんは明示的なプロパティの getter メソッドです。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-131">This demonstrates that the expression for an automatically implemented property is not evaluated each time, as is the getter method for the explicit property.</span></span>

>[!WARNING]
><span data-ttu-id="bfbc9-132">Entity Framework などのいくつかのライブラリがあります (`System.Data.Entity`) 自動的に実装されたプロパティの初期化とうまく連携する基本クラス コンス トラクターでカスタム操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-132">There are some libraries, such as the Entity Framework (`System.Data.Entity`) that perform custom operations in base class constructors that don't work well with the initialization of automatically implemented properties.</span></span> <span data-ttu-id="bfbc9-133">その場合、明示的なプロパティを使用してみてください。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-133">In those cases, try using explicit properties.</span></span>

<span data-ttu-id="bfbc9-134">プロパティは、クラス、構造体、判別共用体、レコード、インターフェイス、および拡張機能の型のメンバーであることができ、オブジェクトの式で定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-134">Properties can be members of classes, structures, discriminated unions, records, interfaces, and type extensions and can also be defined in object expressions.</span></span>

<span data-ttu-id="bfbc9-135">属性は、プロパティに適用できます。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-135">Attributes can be applied to properties.</span></span> <span data-ttu-id="bfbc9-136">プロパティに属性を適用するには、プロパティの前に別の行に属性を記述します。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-136">To apply an attribute to a property, write the attribute on a separate line before the property.</span></span> <span data-ttu-id="bfbc9-137">詳細については、「[属性](../attributes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-137">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="bfbc9-138">既定では、プロパティはパブリックです。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-138">By default, properties are public.</span></span> <span data-ttu-id="bfbc9-139">アクセシビリティ修飾子は、プロパティにも適用できます。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-139">Accessibility modifiers can also be applied to properties.</span></span> <span data-ttu-id="bfbc9-140">アクセシビリティ修飾子を適用する場合は追加、プロパティの名前の直前に両方に適用するものです、`get`と`set`メソッドです追加する前に、`get`と`set`異なるアクセシビリティがある場合、キーワード。各アクセサーが必要です。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-140">To apply an accessibility modifier, add it immediately before the name of the property if it is meant to apply to both the `get` and `set` methods; add it before the `get` and `set` keywords if different accessibility is required for each accessor.</span></span> <span data-ttu-id="bfbc9-141">*アクセシビリティ修飾子*、次のいずれかを指定できます: `public`、 `private`、`internal`します。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-141">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="bfbc9-142">詳細については、「[Access Control](../access-control.md)」(アクセス制御) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-142">For more information, see [Access Control](../access-control.md).</span></span>

<span data-ttu-id="bfbc9-143">プロパティの実装は、プロパティがアクセスされるたびに実行されます。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-143">Property implementations are executed each time a property is accessed.</span></span>

## <a name="static-and-instance-properties"></a><span data-ttu-id="bfbc9-144">静的およびインスタンスのプロパティ</span><span class="sxs-lookup"><span data-stu-id="bfbc9-144">Static and Instance Properties</span></span>

<span data-ttu-id="bfbc9-145">プロパティは、静的またはインスタンスのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-145">Properties can be static or instance properties.</span></span> <span data-ttu-id="bfbc9-146">静的なプロパティは、インスタンスを指定しないで呼び出すことができ、個々 のオブジェクトではなく、種類に関連付けられた値に使用されます。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-146">Static properties can be invoked without an instance and are used for values associated with the type, not with individual objects.</span></span> <span data-ttu-id="bfbc9-147">静的プロパティは、自己識別子を省略します。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-147">For static properties, omit the self-identifier.</span></span> <span data-ttu-id="bfbc9-148">自己識別子は、インスタンスのプロパティに必要です。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-148">The self-identifier is required for instance properties.</span></span>

<span data-ttu-id="bfbc9-149">次の静的プロパティの定義は静的フィールドがあるシナリオに基づいて`myStaticValue`プロパティのバッキング ストアは。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-149">The following static property definition is based on a scenario in which you have a static field `myStaticValue` that is the backing store for the property.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3204.fs)]

<span data-ttu-id="bfbc9-150">プロパティもできる配列に似た、呼び出された場合*インデックス付きプロパティ*します。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-150">Properties can also be array-like, in which case they are called *indexed properties*.</span></span> <span data-ttu-id="bfbc9-151">詳細については、次を参照してください。[インデックス付きプロパティ](indexed-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-151">For more information, see [Indexed Properties](indexed-properties.md).</span></span>

## <a name="type-annotation-for-properties"></a><span data-ttu-id="bfbc9-152">プロパティの型の注釈</span><span class="sxs-lookup"><span data-stu-id="bfbc9-152">Type Annotation for Properties</span></span>

<span data-ttu-id="bfbc9-153">多くの場合、コンパイラは、バッキング ストアの種類のプロパティの型を推論するのに十分な情報が、型の注釈を追加することで、型を明示的に設定することができます。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-153">In many cases, the compiler has enough information to infer the type of a property from the type of the backing store, but you can set the type explicitly by adding a type annotation.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3205.fs)]

## <a name="using-property-set-accessors"></a><span data-ttu-id="bfbc9-154">Set アクセサーのプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-154">Using Property set Accessors</span></span>

<span data-ttu-id="bfbc9-155">提供するプロパティを設定する`set`アクセサーを使用して、`<-`演算子。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-155">You can set properties that provide `set` accessors by using the `<-` operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3206.fs)]

<span data-ttu-id="bfbc9-156">出力は**20**します。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-156">The output is **20**.</span></span>

## <a name="abstract-properties"></a><span data-ttu-id="bfbc9-157">抽象プロパティ</span><span class="sxs-lookup"><span data-stu-id="bfbc9-157">Abstract Properties</span></span>

<span data-ttu-id="bfbc9-158">プロパティは、抽象にすることができます。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-158">Properties can be abstract.</span></span> <span data-ttu-id="bfbc9-159">メソッドと同様`abstract`プロパティに関連付けられた仮想ディスパッチがあることを意味します。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-159">As with methods, `abstract` just means that there is a virtual dispatch associated with the property.</span></span> <span data-ttu-id="bfbc9-160">抽象プロパティは、同じクラスの定義のないは、本当に抽象することができます。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-160">Abstract properties can be truly abstract, that is, without a definition in the same class.</span></span> <span data-ttu-id="bfbc9-161">このようなプロパティを含むクラスは、抽象クラスではそのためです。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-161">The class that contains such a property is therefore an abstract class.</span></span> <span data-ttu-id="bfbc9-162">代わりに、抽象はだけことを意味は仮想関数、プロパティをその場合は、定義が同じクラス内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-162">Alternatively, abstract can just mean that a property is virtual, and in that case, a definition must be present in the same class.</span></span> <span data-ttu-id="bfbc9-163">抽象プロパティをプライベートにすることはできませんし、1 つのアクセサーが抽象の場合は、他の必要がありますも抽象にすることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-163">Note that abstract properties must not be private, and if one accessor is abstract, the other must also be abstract.</span></span> <span data-ttu-id="bfbc9-164">抽象クラスの詳細については、次を参照してください。[抽象クラス](../abstract-classes.md)します。</span><span class="sxs-lookup"><span data-stu-id="bfbc9-164">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3207.fs)]

## <a name="see-also"></a><span data-ttu-id="bfbc9-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="bfbc9-165">See also</span></span>

- [<span data-ttu-id="bfbc9-166">メンバー</span><span class="sxs-lookup"><span data-stu-id="bfbc9-166">Members</span></span>](index.md)
- [<span data-ttu-id="bfbc9-167">メソッド</span><span class="sxs-lookup"><span data-stu-id="bfbc9-167">Methods</span></span>](methods.md)
