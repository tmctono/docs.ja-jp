---
title: 明示的なインターフェイスの実装 - C# プログラミング ガイド
ms.date: 01/24/2020
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: c6f1f849e0d4e831802b4c9b8b4bc3887363a34c
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628151"
---
# <a name="explicit-interface-implementation-c-programming-guide"></a><span data-ttu-id="322d4-102">明示的なインターフェイスの実装 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="322d4-102">Explicit Interface Implementation (C# Programming Guide)</span></span>

<span data-ttu-id="322d4-103">シグネチャが同じメンバーが含まれる 2 つのインターフェイスをある[クラス](../../language-reference/keywords/class.md)が実装する場合、そのクラスでそのメンバーを実装することで、実装としてそのメンバーが両方のインターフェイスで使用されます。</span><span class="sxs-lookup"><span data-stu-id="322d4-103">If a [class](../../language-reference/keywords/class.md) implements two interfaces that contain a member with the same signature, then implementing that member on the class will cause both interfaces to use that member as their implementation.</span></span> <span data-ttu-id="322d4-104">次の例では、`Paint` のすべての呼び出しで同じメソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="322d4-104">In the following example, all the calls to `Paint` invoke the same method.</span></span> <span data-ttu-id="322d4-105">この最初のサンプルでは、型が定義されます。</span><span class="sxs-lookup"><span data-stu-id="322d4-105">This first sample defines the types:</span></span>

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefineTypes)]

<span data-ttu-id="322d4-106">次のサンプルでは、メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="322d4-106">The following sample calls the methods:</span></span>

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallMethods)]

<span data-ttu-id="322d4-107">2 つのインターフェイス メンバーで同じ関数を実行しない場合、一方または両方のインターフェイスが正しく実装されません。</span><span class="sxs-lookup"><span data-stu-id="322d4-107">When two interface members don't perform the same function, it leads to an incorrect implementation of one or both of the interfaces.</span></span> <span data-ttu-id="322d4-108">インターフェイス メンバーは明示的に実装できます。そのインターフェイス経由でのみ呼び出され、そのインターフェイスに固有となるクラス メンバーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="322d4-108">It's possible to implement an interface member explicitly—creating a class member that is only called through the interface, and is specific to that interface.</span></span> <span data-ttu-id="322d4-109">インターフェイスの名前とピリオドを利用してクラス メンバーに名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="322d4-109">Name the class member with the name of the interface and a period.</span></span> <span data-ttu-id="322d4-110">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="322d4-110">For example:</span></span>

[!code-csharp[DefineExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#ExplicitImplementation)]

<span data-ttu-id="322d4-111">クラス メンバー `IControl.Paint` は `IControl` インターフェイス経由でのみ利用できます。`ISurface.Paint` は `ISurface` 経由でのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="322d4-111">The class member `IControl.Paint` is only available through the `IControl` interface, and `ISurface.Paint` is only available through `ISurface`.</span></span> <span data-ttu-id="322d4-112">いずれのメソッド実装も個別であり、どちらもクラスで直接利用できません。</span><span class="sxs-lookup"><span data-stu-id="322d4-112">Both method implementations are separate, and neither are available directly on the class.</span></span> <span data-ttu-id="322d4-113">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="322d4-113">For example:</span></span>

[!code-csharp[CallExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallExplicitImplementation)]

<span data-ttu-id="322d4-114">2 つのインターフェイスで、それぞれが同じ名前の別のメンバー (プロパティやメソッドなど) を宣言するような場合の解決には、明示的な実装も利用されます。</span><span class="sxs-lookup"><span data-stu-id="322d4-114">Explicit implementation is also used to resolve cases where two interfaces each declare different members of the same name such as a property and a method.</span></span> <span data-ttu-id="322d4-115">両方のインターフェイスを実装するには、コンパイラ エラーを回避するために、クラスはプロパティ `P`、メソッド `P`、または両方に明示的な実装を利用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="322d4-115">To implement both interfaces, a class has to use explicit implementation either for the property `P`, or the method `P`, or both, to avoid a compiler error.</span></span> <span data-ttu-id="322d4-116">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="322d4-116">For example:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#NameCollision)]

<span data-ttu-id="322d4-117">クラスでインターフェイスからメソッド実装が継承される場合、そのメソッドにはインターフェイス型の参照を利用する方法でのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="322d4-117">If a class inherits a method implementation from an interface, that method is only accessible through a reference of the interface type.</span></span> <span data-ttu-id="322d4-118">継承したメンバーは、パブリック インターフェイスの一部として表示されません。</span><span class="sxs-lookup"><span data-stu-id="322d4-118">The inherited member doesn't appear as part of the public interface.</span></span> <span data-ttu-id="322d4-119">次のサンプルでは、インターフェイス メソッドの既定の実装が定義されます。</span><span class="sxs-lookup"><span data-stu-id="322d4-119">The following sample defines a default implementation for an interface method:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefaultImplementation)]

<span data-ttu-id="322d4-120">次のサンプルでは、既定の実装が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="322d4-120">The following sample invokes the default implementation:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallDefaultImplementation)]

<span data-ttu-id="322d4-121">`IControl` インターフェイスを実装するあらゆるクラスによって、既定の `Paint` メソッドをパブリック メソッドか明示的なインターフェイス実装としてオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="322d4-121">Any class that implements the `IControl` interface can override the default `Paint` method, either as a public method, or as an explicit interface implementation.</span></span>

## <a name="see-also"></a><span data-ttu-id="322d4-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="322d4-122">See also</span></span>

- [<span data-ttu-id="322d4-123">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="322d4-123">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="322d4-124">クラスと構造体</span><span class="sxs-lookup"><span data-stu-id="322d4-124">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="322d4-125">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="322d4-125">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="322d4-126">継承</span><span class="sxs-lookup"><span data-stu-id="322d4-126">Inheritance</span></span>](../classes-and-structs/inheritance.md)
