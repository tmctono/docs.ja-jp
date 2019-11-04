---
title: event - C# リファレンス
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- event
- remove
- event_CSharpKeyword
- add
helpviewer_keywords:
- event keyword [C#]
ms.assetid: 7858fd85-153b-4259-85d0-6aa13c35f174
ms.openlocfilehash: a6a62881f7205891bafe039a42da44eb8f8d03c0
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422828"
---
# <a name="event-c-reference"></a><span data-ttu-id="1a02d-102">event (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="1a02d-102">event (C# Reference)</span></span>
<span data-ttu-id="1a02d-103">`event` キーワードを使用し、パブリッシャー クラス内にイベントを宣言します。</span><span class="sxs-lookup"><span data-stu-id="1a02d-103">The `event` keyword is used to declare an event in a publisher class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a02d-104">例</span><span class="sxs-lookup"><span data-stu-id="1a02d-104">Example</span></span>  
 <span data-ttu-id="1a02d-105">次の例では、基になるデリゲート型として <xref:System.EventHandler> を使用するイベントを宣言し、発生させる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1a02d-105">The following example shows how to declare and raise an event that uses <xref:System.EventHandler> as the underlying delegate type.</span></span> <span data-ttu-id="1a02d-106">ジェネリック <xref:System.EventHandler%601> デリゲート型を使う方法、およびイベントをサブスクライブしてイベント ハンドラー メソッドを作成する方法も示す完全なコード例については、「[方法: .NET Framework ガイドラインに準拠したイベントを発行する](../../programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1a02d-106">For the complete code example that also shows how to use the generic <xref:System.EventHandler%601> delegate type and how to subscribe to an event and create an event handler method, see [How to: Publish Events that Conform to .NET Framework Guidelines](../../programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md).</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#7)]
  
 <span data-ttu-id="1a02d-107">イベントは、宣言元 (パブリッシャー クラス) のクラスまたは構造体内でしか呼び出せない特殊なマルチキャスト デリゲートです。</span><span class="sxs-lookup"><span data-stu-id="1a02d-107">Events are a special kind of multicast delegate that can only be invoked from within the class or struct where they are declared (the publisher class).</span></span> <span data-ttu-id="1a02d-108">他のクラスまたは構造体がイベントを受信登録した場合、パブリッシャー クラスがイベントを発生させると、他のクラスまたは構造体のイベント ハンドラー メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1a02d-108">If other classes or structs subscribe to the event, their event handler methods will be called when the publisher class raises the event.</span></span> <span data-ttu-id="1a02d-109">詳細およびコード例については、「[イベント](../../programming-guide/events/index.md)」および「[デリゲート](../../programming-guide/delegates/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a02d-109">For more information and code examples, see [Events](../../programming-guide/events/index.md) and [Delegates](../../programming-guide/delegates/index.md).</span></span>  
  
 <span data-ttu-id="1a02d-110">イベントは、[public](./public.md)、[private](./private.md)、[protected](./protected.md)、[internal](./internal.md)、[protected internal](./protected-internal.md) または [private protected](./private-protected.md) としてマークできます。</span><span class="sxs-lookup"><span data-stu-id="1a02d-110">Events can be marked as [public](./public.md), [private](./private.md), [protected](./protected.md), [internal](./internal.md), [protected internal](./protected-internal.md) or [private protected](./private-protected.md).</span></span> <span data-ttu-id="1a02d-111">これらのアクセス修飾子により、クラスのユーザーがイベントにアクセスする方法が定義されます。</span><span class="sxs-lookup"><span data-stu-id="1a02d-111">These access modifiers define how users of the class can access the event.</span></span> <span data-ttu-id="1a02d-112">詳細については、「[アクセス修飾子](../../programming-guide/classes-and-structs/access-modifiers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a02d-112">For more information, see [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
## <a name="keywords-and-events"></a><span data-ttu-id="1a02d-113">キーワードとイベント</span><span class="sxs-lookup"><span data-stu-id="1a02d-113">Keywords and Events</span></span>  
 <span data-ttu-id="1a02d-114">イベントには次のキーワードが適用されます。</span><span class="sxs-lookup"><span data-stu-id="1a02d-114">The following keywords apply to events.</span></span>  
  
|<span data-ttu-id="1a02d-115">キーワード</span><span class="sxs-lookup"><span data-stu-id="1a02d-115">Keyword</span></span>|<span data-ttu-id="1a02d-116">説明</span><span class="sxs-lookup"><span data-stu-id="1a02d-116">Description</span></span>|<span data-ttu-id="1a02d-117">詳細情報</span><span class="sxs-lookup"><span data-stu-id="1a02d-117">For more information</span></span>|  
|-------------|-----------------|--------------------------|  
|[<span data-ttu-id="1a02d-118">static</span><span class="sxs-lookup"><span data-stu-id="1a02d-118">static</span></span>](./static.md)|<span data-ttu-id="1a02d-119">クラスのインスタンスが存在しない場合でも、呼び出し元がいつでもイベントを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1a02d-119">Makes the event available to callers at any time, even if no instance of the class exists.</span></span>|[<span data-ttu-id="1a02d-120">静的クラスと静的クラス メンバー</span><span class="sxs-lookup"><span data-stu-id="1a02d-120">Static Classes and Static Class Members</span></span>](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)|  
|[<span data-ttu-id="1a02d-121">virtual</span><span class="sxs-lookup"><span data-stu-id="1a02d-121">virtual</span></span>](./virtual.md)|<span data-ttu-id="1a02d-122">[override](./override.md) キーワードを使用してイベントの動作をオーバーライドすることを派生クラスに許可します。</span><span class="sxs-lookup"><span data-stu-id="1a02d-122">Allows derived classes to override the event behavior by using the [override](./override.md) keyword.</span></span>|[<span data-ttu-id="1a02d-123">継承</span><span class="sxs-lookup"><span data-stu-id="1a02d-123">Inheritance</span></span>](../../programming-guide/classes-and-structs/inheritance.md)|  
|[<span data-ttu-id="1a02d-124">sealed</span><span class="sxs-lookup"><span data-stu-id="1a02d-124">sealed</span></span>](./sealed.md)|<span data-ttu-id="1a02d-125">派生クラスでは、それが仮想ではなくなったことを指定します。</span><span class="sxs-lookup"><span data-stu-id="1a02d-125">Specifies that for derived classes it is no longer virtual.</span></span>||  
|[<span data-ttu-id="1a02d-126">abstract</span><span class="sxs-lookup"><span data-stu-id="1a02d-126">abstract</span></span>](./abstract.md)|<span data-ttu-id="1a02d-127">コンパイラはイベント アクセサー ブロックの `add` と `remove` を生成しません。したがって、派生クラスは固有の実装を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a02d-127">The compiler will not generate the `add` and `remove` event accessor blocks and therefore derived classes must provide their own implementation.</span></span>||  
  
 <span data-ttu-id="1a02d-128">イベントは、[static](./static.md) キーワードを使用して静的イベントとして宣言されることもあります。</span><span class="sxs-lookup"><span data-stu-id="1a02d-128">An event may be declared as a static event by using the [static](./static.md) keyword.</span></span> <span data-ttu-id="1a02d-129">その場合、クラスのインスタンスが存在しなくても、呼び出し元がいつでもイベントを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1a02d-129">This makes the event available to callers at any time, even if no instance of the class exists.</span></span> <span data-ttu-id="1a02d-130">詳細については、「[静的クラスと静的クラス メンバー](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a02d-130">For more information, see [Static Classes and Static Class Members](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
 <span data-ttu-id="1a02d-131">イベントは、[virtual](./virtual.md) キーワードを使用して仮想イベントとしてマークできます。</span><span class="sxs-lookup"><span data-stu-id="1a02d-131">An event can be marked as a virtual event by using the [virtual](./virtual.md) keyword.</span></span> <span data-ttu-id="1a02d-132">その場合、派生クラスでは、[override](./override.md) キーワードを使用してイベントの動作をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="1a02d-132">This enables derived classes to override the event behavior by using the [override](./override.md) keyword.</span></span> <span data-ttu-id="1a02d-133">詳細については、「[継承](../../programming-guide/classes-and-structs/inheritance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a02d-133">For more information, see [Inheritance](../../programming-guide/classes-and-structs/inheritance.md).</span></span> <span data-ttu-id="1a02d-134">仮想イベントをオーバーライドするイベントは、[sealed](./sealed.md) にすることもできます。その場合、派生クラスでは、イベントが仮想でなくなります。</span><span class="sxs-lookup"><span data-stu-id="1a02d-134">An event overriding a virtual event can also be [sealed](./sealed.md), which specifies that for derived classes it is no longer virtual.</span></span> <span data-ttu-id="1a02d-135">最後に、イベントは [abstract](./abstract.md) として宣言できます。その場合、コンパイラはイベント アクセサー ブロックの `add` と `remove` を生成しません。</span><span class="sxs-lookup"><span data-stu-id="1a02d-135">Lastly, an event can be declared [abstract](./abstract.md), which means that the compiler will not generate the `add` and `remove` event accessor blocks.</span></span> <span data-ttu-id="1a02d-136">したがって、派生クラスごとに固有の実装を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a02d-136">Therefore derived classes must provide their own implementation.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="1a02d-137">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="1a02d-137">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1a02d-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a02d-138">See also</span></span>

- [<span data-ttu-id="1a02d-139">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="1a02d-139">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1a02d-140">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="1a02d-140">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1a02d-141">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="1a02d-141">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="1a02d-142">add</span><span class="sxs-lookup"><span data-stu-id="1a02d-142">add</span></span>](./add.md)
- [<span data-ttu-id="1a02d-143">remove</span><span class="sxs-lookup"><span data-stu-id="1a02d-143">remove</span></span>](./remove.md)
- [<span data-ttu-id="1a02d-144">修飾子</span><span class="sxs-lookup"><span data-stu-id="1a02d-144">Modifiers</span></span>](index.md)
- [<span data-ttu-id="1a02d-145">方法: デリゲートを結合する (マルチキャスト デリゲート)</span><span class="sxs-lookup"><span data-stu-id="1a02d-145">How to: Combine Delegates (Multicast Delegates)</span></span>](../../programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)
