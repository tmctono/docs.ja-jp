---
title: 明示的なインターフェイスの実装 - C# プログラミング ガイド
description: C# では、クラスによって、シグネチャが同じメンバーを含むインターフェイスを実装できます。 明示的な実装では、1 つのインターフェイスに固有のクラス メンバーが作成されます。
ms.date: 01/24/2020
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: a6ec328c08d1da84a11431d9400a094df8c72223
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303088"
---
# <a name="explicit-interface-implementation-c-programming-guide"></a><span data-ttu-id="41aec-104">明示的なインターフェイスの実装 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="41aec-104">Explicit Interface Implementation (C# Programming Guide)</span></span>

<span data-ttu-id="41aec-105">シグネチャが同じメンバーが含まれる 2 つのインターフェイスをある[クラス](../../language-reference/keywords/class.md)が実装する場合、そのクラスでそのメンバーを実装することで、実装としてそのメンバーが両方のインターフェイスで使用されます。</span><span class="sxs-lookup"><span data-stu-id="41aec-105">If a [class](../../language-reference/keywords/class.md) implements two interfaces that contain a member with the same signature, then implementing that member on the class will cause both interfaces to use that member as their implementation.</span></span> <span data-ttu-id="41aec-106">次の例では、`Paint` のすべての呼び出しで同じメソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="41aec-106">In the following example, all the calls to `Paint` invoke the same method.</span></span> <span data-ttu-id="41aec-107">この最初のサンプルでは、型が定義されます。</span><span class="sxs-lookup"><span data-stu-id="41aec-107">This first sample defines the types:</span></span>

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefineTypes)]

<span data-ttu-id="41aec-108">次のサンプルでは、メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="41aec-108">The following sample calls the methods:</span></span>

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallMethods)]

<span data-ttu-id="41aec-109">2 つのインターフェイス メンバーで同じ関数を実行しない場合、一方または両方のインターフェイスが正しく実装されません。</span><span class="sxs-lookup"><span data-stu-id="41aec-109">When two interface members don't perform the same function, it leads to an incorrect implementation of one or both of the interfaces.</span></span> <span data-ttu-id="41aec-110">インターフェイス メンバーは明示的に実装できます。そのインターフェイス経由でのみ呼び出され、そのインターフェイスに固有となるクラス メンバーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="41aec-110">It's possible to implement an interface member explicitly—creating a class member that is only called through the interface, and is specific to that interface.</span></span> <span data-ttu-id="41aec-111">インターフェイスの名前とピリオドを利用してクラス メンバーに名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="41aec-111">Name the class member with the name of the interface and a period.</span></span> <span data-ttu-id="41aec-112">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="41aec-112">For example:</span></span>

[!code-csharp[DefineExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#ExplicitImplementation)]

<span data-ttu-id="41aec-113">クラス メンバー `IControl.Paint` は `IControl` インターフェイス経由でのみ利用できます。`ISurface.Paint` は `ISurface` 経由でのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="41aec-113">The class member `IControl.Paint` is only available through the `IControl` interface, and `ISurface.Paint` is only available through `ISurface`.</span></span> <span data-ttu-id="41aec-114">いずれのメソッド実装も個別であり、どちらもクラスで直接利用できません。</span><span class="sxs-lookup"><span data-stu-id="41aec-114">Both method implementations are separate, and neither are available directly on the class.</span></span> <span data-ttu-id="41aec-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="41aec-115">For example:</span></span>

[!code-csharp[CallExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallExplicitImplementation)]

<span data-ttu-id="41aec-116">2 つのインターフェイスで、それぞれが同じ名前の別のメンバー (プロパティやメソッドなど) を宣言するような場合の解決には、明示的な実装も利用されます。</span><span class="sxs-lookup"><span data-stu-id="41aec-116">Explicit implementation is also used to resolve cases where two interfaces each declare different members of the same name such as a property and a method.</span></span> <span data-ttu-id="41aec-117">両方のインターフェイスを実装するには、コンパイラ エラーを回避するために、クラスはプロパティ `P`、メソッド `P`、または両方に明示的な実装を利用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41aec-117">To implement both interfaces, a class has to use explicit implementation either for the property `P`, or the method `P`, or both, to avoid a compiler error.</span></span> <span data-ttu-id="41aec-118">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="41aec-118">For example:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#NameCollision)]

<span data-ttu-id="41aec-119">[C# 8.0](../../whats-new/csharp-8.md#default-interface-methods) 以降では、インターフェイスで宣言されたメンバーの実装を定義できます。</span><span class="sxs-lookup"><span data-stu-id="41aec-119">Beginning with [C# 8.0](../../whats-new/csharp-8.md#default-interface-methods), you can define an implementation for members declared in an interface.</span></span> <span data-ttu-id="41aec-120">クラスでインターフェイスからメソッド実装が継承される場合、そのメソッドにはインターフェイス型の参照を利用する方法でのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="41aec-120">If a class inherits a method implementation from an interface, that method is only accessible through a reference of the interface type.</span></span> <span data-ttu-id="41aec-121">継承したメンバーは、パブリック インターフェイスの一部として表示されません。</span><span class="sxs-lookup"><span data-stu-id="41aec-121">The inherited member doesn't appear as part of the public interface.</span></span> <span data-ttu-id="41aec-122">次のサンプルでは、インターフェイス メソッドの既定の実装が定義されます。</span><span class="sxs-lookup"><span data-stu-id="41aec-122">The following sample defines a default implementation for an interface method:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefaultImplementation)]

<span data-ttu-id="41aec-123">次のサンプルでは、既定の実装が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="41aec-123">The following sample invokes the default implementation:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallDefaultImplementation)]

<span data-ttu-id="41aec-124">`IControl` インターフェイスを実装するあらゆるクラスによって、既定の `Paint` メソッドをパブリック メソッドか明示的なインターフェイス実装としてオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="41aec-124">Any class that implements the `IControl` interface can override the default `Paint` method, either as a public method, or as an explicit interface implementation.</span></span>

## <a name="see-also"></a><span data-ttu-id="41aec-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="41aec-125">See also</span></span>

- [<span data-ttu-id="41aec-126">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="41aec-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="41aec-127">クラスと構造体</span><span class="sxs-lookup"><span data-stu-id="41aec-127">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="41aec-128">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="41aec-128">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="41aec-129">継承</span><span class="sxs-lookup"><span data-stu-id="41aec-129">Inheritance</span></span>](../classes-and-structs/inheritance.md)
