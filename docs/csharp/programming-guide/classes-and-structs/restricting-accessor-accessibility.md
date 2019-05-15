---
title: アクセサーのアクセシビリティの制限 - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- read-only properties [C#]
- read-only indexers [C#]
- accessors [C#]
- properties [C#], read-only
- asymmetric accessor accessibility [C#]
- indexers [C#], read-only
ms.assetid: 6e655798-e112-4301-a680-6310a6e012e1
ms.openlocfilehash: cde196c2bf0b40443c6b497a6a73863e5f89dd0a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64582989"
---
# <a name="restricting-accessor-accessibility-c-programming-guide"></a><span data-ttu-id="d62b1-102">アクセサーのアクセシビリティの制限 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="d62b1-102">Restricting Accessor Accessibility (C# Programming Guide)</span></span>
<span data-ttu-id="d62b1-103">プロパティまたはインデクサーの [get](../../../csharp/language-reference/keywords/get.md) および [set](../../../csharp/language-reference/keywords/set.md) 部分は、*アクセサー*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="d62b1-103">The [get](../../../csharp/language-reference/keywords/get.md) and [set](../../../csharp/language-reference/keywords/set.md) portions of a property or indexer are called *accessors*.</span></span> <span data-ttu-id="d62b1-104">既定では、これらのアクセサーは、それらが属するプロパティまたはインデクサーと同じ可視性またはアクセス レベルを持っています。</span><span class="sxs-lookup"><span data-stu-id="d62b1-104">By default these accessors have the same visibility or access level of the property or indexer to which they belong.</span></span> <span data-ttu-id="d62b1-105">詳細については、「[アクセシビリティ レベル](../../../csharp/language-reference/keywords/accessibility-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d62b1-105">For more information, see [accessibility levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> <span data-ttu-id="d62b1-106">ただし、これらのアクセサーのいずれかにアクセスを制限すると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="d62b1-106">However, it is sometimes useful to restrict access to one of these accessors.</span></span> <span data-ttu-id="d62b1-107">通常、これには、`set` アクセサーのアクセシビリティを制限しながら、`get` アクセサーのパブリック アクセスを維持する操作が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d62b1-107">Typically, this involves restricting the accessibility of the `set` accessor, while keeping the `get` accessor publicly accessible.</span></span> <span data-ttu-id="d62b1-108">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d62b1-108">For example:</span></span>  
  
 [!code-csharp[csProgGuideIndexers#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#6)]  
  
 <span data-ttu-id="d62b1-109">この例では、`Name` というプロパティが `get` および `set` アクセサーを定義します。</span><span class="sxs-lookup"><span data-stu-id="d62b1-109">In this example, a property called `Name` defines a `get` and `set` accessor.</span></span> <span data-ttu-id="d62b1-110">`get` アクセサーは、プロパティ自体のアクセシビリティ レベル (この場合は `public`) を受け取り、同時に `set` アクセサーは、[protected](../../../csharp/language-reference/keywords/protected.md) アクセサー修飾子をアクセサー自体に適用することによって明示的に制限されます。</span><span class="sxs-lookup"><span data-stu-id="d62b1-110">The `get` accessor receives the accessibility level of the property itself, `public` in this case, while the `set` accessor is explicitly restricted by applying the [protected](../../../csharp/language-reference/keywords/protected.md) access modifier to the accessor itself.</span></span>  
  
## <a name="restrictions-on-access-modifiers-on-accessors"></a><span data-ttu-id="d62b1-111">アクセサーのアクセス修飾子の制限</span><span class="sxs-lookup"><span data-stu-id="d62b1-111">Restrictions on Access Modifiers on Accessors</span></span>  
 <span data-ttu-id="d62b1-112">プロパティまたはインデクサーでのアクセサー修飾子の使用は、以下の条件の対象になります。</span><span class="sxs-lookup"><span data-stu-id="d62b1-112">Using the accessor modifiers on properties or indexers is subject to these conditions:</span></span>  
  
- <span data-ttu-id="d62b1-113">インターフェイスまたは明示的な [interface](../../../csharp/language-reference/keywords/interface.md) メンバーの実装でアクセサー修飾子を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d62b1-113">You cannot use accessor modifiers on an interface or an explicit [interface](../../../csharp/language-reference/keywords/interface.md) member implementation.</span></span>  
  
- <span data-ttu-id="d62b1-114">アクセサー修飾子は、プロパティまたはインデクサーに `set` と `get` アクセサーの両方がある場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d62b1-114">You can use accessor modifiers only if the property or indexer has both `set` and `get` accessors.</span></span> <span data-ttu-id="d62b1-115">この場合、修飾子は、2 つのアクセサーのいずれかでのみ許可されます。</span><span class="sxs-lookup"><span data-stu-id="d62b1-115">In this case, the modifier is permitted on only one of the two accessors.</span></span>  
  
- <span data-ttu-id="d62b1-116">プロパティまたはインデクサーに [override](../../../csharp/language-reference/keywords/override.md) 修飾子がある場合は、アクセサー修飾子はオーバーライドされるアクセサーのアクセサー (存在する場合) と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d62b1-116">If the property or indexer has an [override](../../../csharp/language-reference/keywords/override.md) modifier, the accessor modifier must match the accessor of the overridden accessor, if any.</span></span>  
  
- <span data-ttu-id="d62b1-117">アクセサーのアクセシビリティ レベルは、プロパティまたはインデクサー自体のアクセシビリティ レベルよりも制限されていなければなりません</span><span class="sxs-lookup"><span data-stu-id="d62b1-117">The accessibility level on the accessor must be more restrictive than the accessibility level on the property or indexer itself.</span></span>  
  
## <a name="access-modifiers-on-overriding-accessors"></a><span data-ttu-id="d62b1-118">オーバーライドするアクセサーのアクセス修飾子</span><span class="sxs-lookup"><span data-stu-id="d62b1-118">Access Modifiers on Overriding Accessors</span></span>  
 <span data-ttu-id="d62b1-119">プロパティまたはインデクサーをオーバーライドする場合は、オーバーライドされたアクセサーがオーバーライドするコードにアクセスできなければなりません。</span><span class="sxs-lookup"><span data-stu-id="d62b1-119">When you override a property or indexer, the overridden accessors must be accessible to the overriding code.</span></span> <span data-ttu-id="d62b1-120">プロパティ/インデクサーとそのアクセサー両方のアクセシビリティが、対応するオーバーライドされるプロパティ/インデクサーおよびアクセサーと一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d62b1-120">Also, the accessibility of both the property/indexer and its accessors must match the corresponding overridden property/indexer and its accessors.</span></span> <span data-ttu-id="d62b1-121">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d62b1-121">For example:</span></span>  
  
 [!code-csharp[csProgGuideIndexers#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#7)]  
  
## <a name="implementing-interfaces"></a><span data-ttu-id="d62b1-122">インターフェイスの実装</span><span class="sxs-lookup"><span data-stu-id="d62b1-122">Implementing Interfaces</span></span>  
 <span data-ttu-id="d62b1-123">アクセサーを使用してインターフェイスを実装する場合、アクセサーがアクセス修飾子を持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="d62b1-123">When you use an accessor to implement an interface, the accessor may not have an access modifier.</span></span> <span data-ttu-id="d62b1-124">ただし、`get` などの 1 つのアクセサーを使用してインターフェイスを実装する場合、他のアクセサーは、次の例のように、アクセス修飾子を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="d62b1-124">However, if you implement the interface using one accessor, such as `get`, the other accessor can have an access modifier, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideIndexers#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#8)]  
  
## <a name="accessor-accessibility-domain"></a><span data-ttu-id="d62b1-125">アクセサー アクセシビリティ ドメイン</span><span class="sxs-lookup"><span data-stu-id="d62b1-125">Accessor Accessibility Domain</span></span>  
 <span data-ttu-id="d62b1-126">アクセサーでアクセス修飾子を使用する場合、アクセサーの[アクセシビリティ ドメイン](../../../csharp/language-reference/keywords/accessibility-domain.md)はこの修飾子によって決まります。</span><span class="sxs-lookup"><span data-stu-id="d62b1-126">If you use an access modifier on the accessor, the [accessibility domain](../../../csharp/language-reference/keywords/accessibility-domain.md) of the accessor is determined by this modifier.</span></span>  
  
 <span data-ttu-id="d62b1-127">アクセサーでアクセス修飾子を使用しなかった場合、アクセサーのアクセシビリティ ドメインは、プロパティまたはインデクサーのアクセシビリティ レベルによって決まります。</span><span class="sxs-lookup"><span data-stu-id="d62b1-127">If you did not use an access modifier on the accessor, the accessibility domain of the accessor is determined by the accessibility level of the property or indexer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d62b1-128">例</span><span class="sxs-lookup"><span data-stu-id="d62b1-128">Example</span></span>  
 <span data-ttu-id="d62b1-129">次の例は、`BaseClass`、`DerivedClass`、および `MainClass` という 3 つのクラスを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="d62b1-129">The following example contains three classes, `BaseClass`, `DerivedClass`, and `MainClass`.</span></span> <span data-ttu-id="d62b1-130">すべてのクラスの `BaseClass`、`Name`、`Id` に 2 つのプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="d62b1-130">There are two properties on the `BaseClass`, `Name` and `Id` on both classes.</span></span> <span data-ttu-id="d62b1-131">この例は、[protected](../../../csharp/language-reference/keywords/protected.md) や [private](../../../csharp/language-reference/keywords/private.md) などの制限アクセス修飾子を使用するときに、`BaseClass` のプロパティ `Id` によって `DerivedClass` のプロパティ `Id` を非表示にする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d62b1-131">The example demonstrates how the property `Id` on `DerivedClass` can be hidden by the property `Id` on `BaseClass` when you use a restrictive access modifier such as [protected](../../../csharp/language-reference/keywords/protected.md) or [private](../../../csharp/language-reference/keywords/private.md).</span></span> <span data-ttu-id="d62b1-132">そのため、このプロパティに値を割り当てるときには、代わりに `BaseClass` クラスのプロパティが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d62b1-132">Therefore, when you assign values to this property, the property on the `BaseClass` class is called instead.</span></span> <span data-ttu-id="d62b1-133">[public](../../../csharp/language-reference/keywords/public.md) によってアクセス修飾子を置き換えると、プロパティがアクセス可能になります。</span><span class="sxs-lookup"><span data-stu-id="d62b1-133">Replacing the access modifier by [public](../../../csharp/language-reference/keywords/public.md) will make the property accessible.</span></span>  
  
 <span data-ttu-id="d62b1-134">この例はまた、`DerivedClass` の `Name` プロパティの `set` アクセサー上の `private` や `protected` などの制限されるアクセス修飾子が、アクセサーへのアクセスを防ぎ、アクセサーに割り当てたときにエラーが生成されることも示しています。</span><span class="sxs-lookup"><span data-stu-id="d62b1-134">The example also demonstrates that a restrictive access modifier, such as `private` or `protected`, on the `set` accessor of the `Name` property in `DerivedClass` prevents access to the accessor and generates an error when you assign to it.</span></span>  
  
 [!code-csharp[csProgGuideIndexers#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#5)]  
  
## <a name="comments"></a><span data-ttu-id="d62b1-135">コメント</span><span class="sxs-lookup"><span data-stu-id="d62b1-135">Comments</span></span>  
 <span data-ttu-id="d62b1-136">宣言 `new private string Id` を `new public string Id` によって置き換えた場合、次の出力を取得します。</span><span class="sxs-lookup"><span data-stu-id="d62b1-136">Notice that if you replace the declaration `new private string Id` by `new public string Id`, you get the output:</span></span>  
  
 `Name and ID in the base class: Name-BaseClass, ID-BaseClass`  
  
 `Name and ID in the derived class: John, John123`  
  
## <a name="see-also"></a><span data-ttu-id="d62b1-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="d62b1-137">See also</span></span>

- [<span data-ttu-id="d62b1-138">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="d62b1-138">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="d62b1-139">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d62b1-139">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)
- [<span data-ttu-id="d62b1-140">インデクサー</span><span class="sxs-lookup"><span data-stu-id="d62b1-140">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)
- [<span data-ttu-id="d62b1-141">アクセス修飾子</span><span class="sxs-lookup"><span data-stu-id="d62b1-141">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)
