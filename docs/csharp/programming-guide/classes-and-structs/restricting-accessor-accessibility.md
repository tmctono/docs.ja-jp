---
title: アクセサーのアクセシビリティの制限 - C# プログラミング ガイド
description: C# でのプロパティの get アクセサーと set アクセサーは、それらが属するプロパティと同等の可視性とアクセス レベルを既定で備えています。 アクセスは制限することができます。
ms.date: 07/20/2015
helpviewer_keywords:
- read-only properties [C#]
- read-only indexers [C#]
- accessors [C#]
- properties [C#], read-only
- asymmetric accessor accessibility [C#]
- indexers [C#], read-only
ms.assetid: 6e655798-e112-4301-a680-6310a6e012e1
ms.openlocfilehash: 18fd1d58dc6125b5180118b2e0d3edc885a4b971
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "86863969"
---
# <a name="restricting-accessor-accessibility-c-programming-guide"></a><span data-ttu-id="15a66-104">アクセサーのアクセシビリティの制限 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="15a66-104">Restricting Accessor Accessibility (C# Programming Guide)</span></span>
<span data-ttu-id="15a66-105">プロパティまたはインデクサーの [get](../../language-reference/keywords/get.md) および [set](../../language-reference/keywords/set.md) 部分は、*アクセサー*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="15a66-105">The [get](../../language-reference/keywords/get.md) and [set](../../language-reference/keywords/set.md) portions of a property or indexer are called *accessors*.</span></span> <span data-ttu-id="15a66-106">既定では、これらのアクセサーは、それらが属するプロパティまたはインデクサーと同じ可視性またはアクセス レベルを持っています。</span><span class="sxs-lookup"><span data-stu-id="15a66-106">By default these accessors have the same visibility or access level of the property or indexer to which they belong.</span></span> <span data-ttu-id="15a66-107">詳細については、「[アクセシビリティ レベル](../../language-reference/keywords/accessibility-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15a66-107">For more information, see [accessibility levels](../../language-reference/keywords/accessibility-levels.md).</span></span> <span data-ttu-id="15a66-108">ただし、これらのアクセサーのいずれかにアクセスを制限すると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="15a66-108">However, it is sometimes useful to restrict access to one of these accessors.</span></span> <span data-ttu-id="15a66-109">通常、これには、`set` アクセサーのアクセシビリティを制限しながら、`get` アクセサーのパブリック アクセスを維持する操作が含まれます。</span><span class="sxs-lookup"><span data-stu-id="15a66-109">Typically, this involves restricting the accessibility of the `set` accessor, while keeping the `get` accessor publicly accessible.</span></span> <span data-ttu-id="15a66-110">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="15a66-110">For example:</span></span>  
  
 [!code-csharp[csProgGuideIndexers#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#6)]  
  
 <span data-ttu-id="15a66-111">この例では、`Name` というプロパティが `get` および `set` アクセサーを定義します。</span><span class="sxs-lookup"><span data-stu-id="15a66-111">In this example, a property called `Name` defines a `get` and `set` accessor.</span></span> <span data-ttu-id="15a66-112">`get` アクセサーは、プロパティ自体のアクセシビリティ レベル (この場合は `public`) を受け取り、同時に `set` アクセサーは、[protected](../../language-reference/keywords/protected.md) アクセサー修飾子をアクセサー自体に適用することによって明示的に制限されます。</span><span class="sxs-lookup"><span data-stu-id="15a66-112">The `get` accessor receives the accessibility level of the property itself, `public` in this case, while the `set` accessor is explicitly restricted by applying the [protected](../../language-reference/keywords/protected.md) access modifier to the accessor itself.</span></span>  
  
## <a name="restrictions-on-access-modifiers-on-accessors"></a><span data-ttu-id="15a66-113">アクセサーのアクセス修飾子の制限</span><span class="sxs-lookup"><span data-stu-id="15a66-113">Restrictions on Access Modifiers on Accessors</span></span>  
 <span data-ttu-id="15a66-114">プロパティまたはインデクサーでのアクセサー修飾子の使用は、以下の条件の対象になります。</span><span class="sxs-lookup"><span data-stu-id="15a66-114">Using the accessor modifiers on properties or indexers is subject to these conditions:</span></span>  
  
- <span data-ttu-id="15a66-115">インターフェイスまたは明示的な [interface](../../language-reference/keywords/interface.md) メンバーの実装でアクセサー修飾子を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="15a66-115">You cannot use accessor modifiers on an interface or an explicit [interface](../../language-reference/keywords/interface.md) member implementation.</span></span>  
  
- <span data-ttu-id="15a66-116">アクセサー修飾子は、プロパティまたはインデクサーに `set` と `get` アクセサーの両方がある場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="15a66-116">You can use accessor modifiers only if the property or indexer has both `set` and `get` accessors.</span></span> <span data-ttu-id="15a66-117">この場合、修飾子は、2 つのアクセサーのいずれかでのみ許可されます。</span><span class="sxs-lookup"><span data-stu-id="15a66-117">In this case, the modifier is permitted on only one of the two accessors.</span></span>  
  
- <span data-ttu-id="15a66-118">プロパティまたはインデクサーに [override](../../language-reference/keywords/override.md) 修飾子がある場合は、アクセサー修飾子はオーバーライドされるアクセサーのアクセサー (存在する場合) と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15a66-118">If the property or indexer has an [override](../../language-reference/keywords/override.md) modifier, the accessor modifier must match the accessor of the overridden accessor, if any.</span></span>  
  
- <span data-ttu-id="15a66-119">アクセサーのアクセシビリティ レベルは、プロパティまたはインデクサー自体のアクセシビリティ レベルよりも制限されていなければなりません</span><span class="sxs-lookup"><span data-stu-id="15a66-119">The accessibility level on the accessor must be more restrictive than the accessibility level on the property or indexer itself.</span></span>  
  
## <a name="access-modifiers-on-overriding-accessors"></a><span data-ttu-id="15a66-120">オーバーライドするアクセサーのアクセス修飾子</span><span class="sxs-lookup"><span data-stu-id="15a66-120">Access Modifiers on Overriding Accessors</span></span>  
 <span data-ttu-id="15a66-121">プロパティまたはインデクサーをオーバーライドする場合は、オーバーライドされたアクセサーがオーバーライドするコードにアクセスできなければなりません。</span><span class="sxs-lookup"><span data-stu-id="15a66-121">When you override a property or indexer, the overridden accessors must be accessible to the overriding code.</span></span> <span data-ttu-id="15a66-122">プロパティ/インデクサーとそのアクセサー両方のアクセシビリティが、対応するオーバーライドされるプロパティ/インデクサーおよびアクセサーと一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="15a66-122">Also, the accessibility of both the property/indexer and its accessors must match the corresponding overridden property/indexer and its accessors.</span></span> <span data-ttu-id="15a66-123">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="15a66-123">For example:</span></span>  
  
 [!code-csharp[csProgGuideIndexers#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#7)]  
  
## <a name="implementing-interfaces"></a><span data-ttu-id="15a66-124">インターフェイスの実装</span><span class="sxs-lookup"><span data-stu-id="15a66-124">Implementing Interfaces</span></span>  
 <span data-ttu-id="15a66-125">アクセサーを使用してインターフェイスを実装する場合、アクセサーがアクセス修飾子を持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="15a66-125">When you use an accessor to implement an interface, the accessor may not have an access modifier.</span></span> <span data-ttu-id="15a66-126">ただし、`get` などの 1 つのアクセサーを使用してインターフェイスを実装する場合、他のアクセサーは、次の例のように、アクセス修飾子を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="15a66-126">However, if you implement the interface using one accessor, such as `get`, the other accessor can have an access modifier, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideIndexers#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#8)]  
  
## <a name="accessor-accessibility-domain"></a><span data-ttu-id="15a66-127">アクセサー アクセシビリティ ドメイン</span><span class="sxs-lookup"><span data-stu-id="15a66-127">Accessor Accessibility Domain</span></span>  
 <span data-ttu-id="15a66-128">アクセサーでアクセス修飾子を使用する場合、アクセサーの[アクセシビリティ ドメイン](../../language-reference/keywords/accessibility-domain.md)はこの修飾子によって決まります。</span><span class="sxs-lookup"><span data-stu-id="15a66-128">If you use an access modifier on the accessor, the [accessibility domain](../../language-reference/keywords/accessibility-domain.md) of the accessor is determined by this modifier.</span></span>  
  
 <span data-ttu-id="15a66-129">アクセサーでアクセス修飾子を使用しなかった場合、アクセサーのアクセシビリティ ドメインは、プロパティまたはインデクサーのアクセシビリティ レベルによって決まります。</span><span class="sxs-lookup"><span data-stu-id="15a66-129">If you did not use an access modifier on the accessor, the accessibility domain of the accessor is determined by the accessibility level of the property or indexer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15a66-130">例</span><span class="sxs-lookup"><span data-stu-id="15a66-130">Example</span></span>  
 <span data-ttu-id="15a66-131">次の例は、`BaseClass`、`DerivedClass`、および `MainClass` という 3 つのクラスを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="15a66-131">The following example contains three classes, `BaseClass`, `DerivedClass`, and `MainClass`.</span></span> <span data-ttu-id="15a66-132">すべてのクラスの `BaseClass`、`Name`、`Id` に 2 つのプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="15a66-132">There are two properties on the `BaseClass`, `Name` and `Id` on both classes.</span></span> <span data-ttu-id="15a66-133">この例は、[protected](../../language-reference/keywords/protected.md) や [private](../../language-reference/keywords/private.md) などの制限アクセス修飾子を使用するときに、`BaseClass` のプロパティ `Id` によって `DerivedClass` のプロパティ `Id` を非表示にする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="15a66-133">The example demonstrates how the property `Id` on `DerivedClass` can be hidden by the property `Id` on `BaseClass` when you use a restrictive access modifier such as [protected](../../language-reference/keywords/protected.md) or [private](../../language-reference/keywords/private.md).</span></span> <span data-ttu-id="15a66-134">そのため、このプロパティに値を割り当てるときには、代わりに `BaseClass` クラスのプロパティが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="15a66-134">Therefore, when you assign values to this property, the property on the `BaseClass` class is called instead.</span></span> <span data-ttu-id="15a66-135">[public](../../language-reference/keywords/public.md) によってアクセス修飾子を置き換えると、プロパティがアクセス可能になります。</span><span class="sxs-lookup"><span data-stu-id="15a66-135">Replacing the access modifier by [public](../../language-reference/keywords/public.md) will make the property accessible.</span></span>  
  
 <span data-ttu-id="15a66-136">この例はまた、`DerivedClass` の `Name` プロパティの `set` アクセサー上の `private` や `protected` などの制限されるアクセス修飾子が、アクセサーへのアクセスを防ぎ、アクセサーに割り当てたときにエラーが生成されることも示しています。</span><span class="sxs-lookup"><span data-stu-id="15a66-136">The example also demonstrates that a restrictive access modifier, such as `private` or `protected`, on the `set` accessor of the `Name` property in `DerivedClass` prevents access to the accessor and generates an error when you assign to it.</span></span>  
  
 [!code-csharp[csProgGuideIndexers#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#5)]  
  
## <a name="comments"></a><span data-ttu-id="15a66-137">コメント</span><span class="sxs-lookup"><span data-stu-id="15a66-137">Comments</span></span>  
 <span data-ttu-id="15a66-138">宣言 `new private string Id` を `new public string Id` によって置き換えた場合、次の出力を取得します。</span><span class="sxs-lookup"><span data-stu-id="15a66-138">Notice that if you replace the declaration `new private string Id` by `new public string Id`, you get the output:</span></span>  
  
 `Name and ID in the base class: Name-BaseClass, ID-BaseClass`  
  
 `Name and ID in the derived class: John, John123`  
  
## <a name="see-also"></a><span data-ttu-id="15a66-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="15a66-139">See also</span></span>

- [<span data-ttu-id="15a66-140">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="15a66-140">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="15a66-141">プロパティ</span><span class="sxs-lookup"><span data-stu-id="15a66-141">Properties</span></span>](./properties.md)
- [<span data-ttu-id="15a66-142">インデクサー</span><span class="sxs-lookup"><span data-stu-id="15a66-142">Indexers</span></span>](../indexers/index.md)
- [<span data-ttu-id="15a66-143">アクセス修飾子</span><span class="sxs-lookup"><span data-stu-id="15a66-143">Access Modifiers</span></span>](./access-modifiers.md)
