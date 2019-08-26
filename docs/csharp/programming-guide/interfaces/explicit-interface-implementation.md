---
title: 明示的なインターフェイスの実装 - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: 498c45ff1c5837f5dcb0d4a80d0e3bb249abd694
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69589220"
---
# <a name="explicit-interface-implementation-c-programming-guide"></a><span data-ttu-id="8fa7f-102">明示的なインターフェイスの実装 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="8fa7f-102">Explicit Interface Implementation (C# Programming Guide)</span></span>
<span data-ttu-id="8fa7f-103">シグネチャが同じメンバーが含まれる 2 つのインターフェイスをある[クラス](../../language-reference/keywords/class.md)が実装する場合、そのクラスでそのメンバーを実装することで、実装としてそのメンバーが両方のインターフェイスで使用されます。</span><span class="sxs-lookup"><span data-stu-id="8fa7f-103">If a [class](../../language-reference/keywords/class.md) implements two interfaces that contain a member with the same signature, then implementing that member on the class will cause both interfaces to use that member as their implementation.</span></span> <span data-ttu-id="8fa7f-104">次の例では、`Paint` のすべての呼び出しで同じメソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="8fa7f-104">In the following example, all the calls to `Paint` invoke the same method.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#39)]  
  
 <span data-ttu-id="8fa7f-105">ただし、2 つの[インターフェイス](../../language-reference/keywords/interface.md) メンバーが同じ関数を実行しない場合、一方または両方のインターフェイスが間違って実装される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8fa7f-105">If the two [interface](../../language-reference/keywords/interface.md) members do not perform the same function, however, this can lead to an incorrect implementation of one or both of the interfaces.</span></span> <span data-ttu-id="8fa7f-106">インターフェイス メンバーは明示的に実装できます。そのインターフェイス経由でのみ呼び出され、そのインターフェイスに固有となるクラス メンバーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8fa7f-106">It is possible to implement an interface member explicitly—creating a class member that is only called through the interface, and is specific to that interface.</span></span> <span data-ttu-id="8fa7f-107">この実装は、インターフェイスの名前とピリオドを利用してクラス メンバーに名前を付けることで行われます。</span><span class="sxs-lookup"><span data-stu-id="8fa7f-107">This is accomplished by naming the class member with the name of the interface and a period.</span></span> <span data-ttu-id="8fa7f-108">例:</span><span class="sxs-lookup"><span data-stu-id="8fa7f-108">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#40)]  
  
 <span data-ttu-id="8fa7f-109">クラス メンバー `IControl.Paint` は `IControl` インターフェイス経由でのみ利用できます。`ISurface.Paint` は `ISurface` 経由でのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="8fa7f-109">The class member `IControl.Paint` is only available through the `IControl` interface, and `ISurface.Paint` is only available through `ISurface`.</span></span> <span data-ttu-id="8fa7f-110">いずれのメソッド実装も個別であり、クラスで直接利用できません。</span><span class="sxs-lookup"><span data-stu-id="8fa7f-110">Both method implementations are separate, and neither is available directly on the class.</span></span> <span data-ttu-id="8fa7f-111">例:</span><span class="sxs-lookup"><span data-stu-id="8fa7f-111">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#41](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#41)]  
  
 <span data-ttu-id="8fa7f-112">2 つのインターフェイスで、それぞれが同じ名前の別のメンバー (プロパティやメソッドなど) を宣言するような場合の解決には、明示的な実装も利用されます。</span><span class="sxs-lookup"><span data-stu-id="8fa7f-112">Explicit implementation is also used to resolve cases where two interfaces each declare different members of the same name such as a property and a method:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#42](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#42)]  
  
 <span data-ttu-id="8fa7f-113">両方のインターフェイスを実装するには、コンパイラ エラーを回避するために、クラスはプロパティ P、メソッド P、または両方に明示的な実装を利用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fa7f-113">To implement both interfaces, a class has to use explicit implementation either for the property P, or the method P, or both, to avoid a compiler error.</span></span> <span data-ttu-id="8fa7f-114">例:</span><span class="sxs-lookup"><span data-stu-id="8fa7f-114">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#43](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#43)]  
  
## <a name="see-also"></a><span data-ttu-id="8fa7f-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="8fa7f-115">See also</span></span>

- [<span data-ttu-id="8fa7f-116">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="8fa7f-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="8fa7f-117">クラスと構造体</span><span class="sxs-lookup"><span data-stu-id="8fa7f-117">Classes and Structs</span></span>](../classes-and-structs/index.md)
- <span data-ttu-id="8fa7f-118">"[インターフェイス](./index.md)"</span><span class="sxs-lookup"><span data-stu-id="8fa7f-118">[Interfaces](./index.md)</span></span>
- [<span data-ttu-id="8fa7f-119">継承</span><span class="sxs-lookup"><span data-stu-id="8fa7f-119">Inheritance</span></span>](../classes-and-structs/inheritance.md)
