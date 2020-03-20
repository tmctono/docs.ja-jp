---
title: 明示的なインターフェイスの実装 - C# プログラミング ガイド
ms.date: 01/24/2020
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: ea32a279b7c464174a7fada5ef93ccf62ef39884
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79167674"
---
# <a name="explicit-interface-implementation-c-programming-guide"></a><span data-ttu-id="3d2c6-102">明示的なインターフェイスの実装 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="3d2c6-102">Explicit Interface Implementation (C# Programming Guide)</span></span>

<span data-ttu-id="3d2c6-103">シグネチャが同じメンバーが含まれる 2 つのインターフェイスをある[クラス](../../language-reference/keywords/class.md)が実装する場合、そのクラスでそのメンバーを実装することで、実装としてそのメンバーが両方のインターフェイスで使用されます。</span><span class="sxs-lookup"><span data-stu-id="3d2c6-103">If a [class](../../language-reference/keywords/class.md) implements two interfaces that contain a member with the same signature, then implementing that member on the class will cause both interfaces to use that member as their implementation.</span></span> <span data-ttu-id="3d2c6-104">次の例では、`Paint` のすべての呼び出しで同じメソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3d2c6-104">In the following example, all the calls to `Paint` invoke the same method.</span></span> <span data-ttu-id="3d2c6-105">この最初のサンプルでは、型が定義されます。</span><span class="sxs-lookup"><span data-stu-id="3d2c6-105">This first sample defines the types:</span></span>

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefineTypes)]

<span data-ttu-id="3d2c6-106">次のサンプルでは、メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3d2c6-106">The following sample calls the methods:</span></span>

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallMethods)]

<span data-ttu-id="3d2c6-107">2 つのインターフェイス メンバーで同じ関数を実行しない場合、一方または両方のインターフェイスが正しく実装されません。</span><span class="sxs-lookup"><span data-stu-id="3d2c6-107">When two interface members don't perform the same function, it leads to an incorrect implementation of one or both of the interfaces.</span></span> <span data-ttu-id="3d2c6-108">インターフェイス メンバーは明示的に実装できます。そのインターフェイス経由でのみ呼び出され、そのインターフェイスに固有となるクラス メンバーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="3d2c6-108">It's possible to implement an interface member explicitly—creating a class member that is only called through the interface, and is specific to that interface.</span></span> <span data-ttu-id="3d2c6-109">インターフェイスの名前とピリオドを利用してクラス メンバーに名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="3d2c6-109">Name the class member with the name of the interface and a period.</span></span> <span data-ttu-id="3d2c6-110">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3d2c6-110">For example:</span></span>

[!code-csharp[DefineExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#ExplicitImplementation)]

<span data-ttu-id="3d2c6-111">クラス メンバー `IControl.Paint` は `IControl` インターフェイス経由でのみ利用できます。`ISurface.Paint` は `ISurface` 経由でのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="3d2c6-111">The class member `IControl.Paint` is only available through the `IControl` interface, and `ISurface.Paint` is only available through `ISurface`.</span></span> <span data-ttu-id="3d2c6-112">いずれのメソッド実装も個別であり、どちらもクラスで直接利用できません。</span><span class="sxs-lookup"><span data-stu-id="3d2c6-112">Both method implementations are separate, and neither are available directly on the class.</span></span> <span data-ttu-id="3d2c6-113">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3d2c6-113">For example:</span></span>

[!code-csharp[CallExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallExplicitImplementation)]

<span data-ttu-id="3d2c6-114">2 つのインターフェイスで、それぞれが同じ名前の別のメンバー (プロパティやメソッドなど) を宣言するような場合の解決には、明示的な実装も利用されます。</span><span class="sxs-lookup"><span data-stu-id="3d2c6-114">Explicit implementation is also used to resolve cases where two interfaces each declare different members of the same name such as a property and a method.</span></span> <span data-ttu-id="3d2c6-115">両方のインターフェイスを実装するには、コンパイラ エラーを回避するために、クラスはプロパティ `P`、メソッド `P`、または両方に明示的な実装を利用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d2c6-115">To implement both interfaces, a class has to use explicit implementation either for the property `P`, or the method `P`, or both, to avoid a compiler error.</span></span> <span data-ttu-id="3d2c6-116">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3d2c6-116">For example:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#NameCollision)]

<span data-ttu-id="3d2c6-117">[C# 8.0](../../whats-new/csharp-8.md#default-interface-methods) 以降では、インターフェイスで宣言されたメンバーの実装を定義できます。</span><span class="sxs-lookup"><span data-stu-id="3d2c6-117">Beginning with [C# 8.0](../../whats-new/csharp-8.md#default-interface-methods), you can define an implementation for members declared in an interface.</span></span> <span data-ttu-id="3d2c6-118">クラスでインターフェイスからメソッド実装が継承される場合、そのメソッドにはインターフェイス型の参照を利用する方法でのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3d2c6-118">If a class inherits a method implementation from an interface, that method is only accessible through a reference of the interface type.</span></span> <span data-ttu-id="3d2c6-119">継承したメンバーは、パブリック インターフェイスの一部として表示されません。</span><span class="sxs-lookup"><span data-stu-id="3d2c6-119">The inherited member doesn't appear as part of the public interface.</span></span> <span data-ttu-id="3d2c6-120">次のサンプルでは、インターフェイス メソッドの既定の実装が定義されます。</span><span class="sxs-lookup"><span data-stu-id="3d2c6-120">The following sample defines a default implementation for an interface method:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefaultImplementation)]

<span data-ttu-id="3d2c6-121">次のサンプルでは、既定の実装が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3d2c6-121">The following sample invokes the default implementation:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallDefaultImplementation)]

<span data-ttu-id="3d2c6-122">`IControl` インターフェイスを実装するあらゆるクラスによって、既定の `Paint` メソッドをパブリック メソッドか明示的なインターフェイス実装としてオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="3d2c6-122">Any class that implements the `IControl` interface can override the default `Paint` method, either as a public method, or as an explicit interface implementation.</span></span>

## <a name="see-also"></a><span data-ttu-id="3d2c6-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="3d2c6-123">See also</span></span>

- [<span data-ttu-id="3d2c6-124">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="3d2c6-124">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="3d2c6-125">クラスと構造体</span><span class="sxs-lookup"><span data-stu-id="3d2c6-125">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="3d2c6-126">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3d2c6-126">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="3d2c6-127">継承</span><span class="sxs-lookup"><span data-stu-id="3d2c6-127">Inheritance</span></span>](../classes-and-structs/inheritance.md)
