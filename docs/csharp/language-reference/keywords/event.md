---
description: event - C# リファレンス
title: event - C# リファレンス
ms.date: 07/20/2015
f1_keywords:
- event
- remove
- event_CSharpKeyword
- add
helpviewer_keywords:
- event keyword [C#]
ms.assetid: 7858fd85-153b-4259-85d0-6aa13c35f174
ms.openlocfilehash: 5e75fec12390cb694126c5bec684c40caa378915
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139100"
---
# <a name="event-c-reference"></a><span data-ttu-id="b5528-103">event (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="b5528-103">event (C# reference)</span></span>

<span data-ttu-id="b5528-104">`event` キーワードを使用し、パブリッシャー クラス内にイベントを宣言します。</span><span class="sxs-lookup"><span data-stu-id="b5528-104">The `event` keyword is used to declare an event in a publisher class.</span></span>

## <a name="example"></a><span data-ttu-id="b5528-105">例</span><span class="sxs-lookup"><span data-stu-id="b5528-105">Example</span></span>

<span data-ttu-id="b5528-106">次の例では、基になるデリゲート型として <xref:System.EventHandler> を使用するイベントを宣言し、発生させる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b5528-106">The following example shows how to declare and raise an event that uses <xref:System.EventHandler> as the underlying delegate type.</span></span> <span data-ttu-id="b5528-107">完全なコード例については、「[.NET Framework ガイドラインに準拠したイベントを発行する方法](../../programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)」を参照してください。完全なコード例では、ジェネリック <xref:System.EventHandler%601> デリゲート型の使用方法と、イベントをサブスクライブして、イベント ハンドラー メソッドを作成する方法も確認できます。</span><span class="sxs-lookup"><span data-stu-id="b5528-107">For the complete code example that also shows how to use the generic <xref:System.EventHandler%601> delegate type and how to subscribe to an event and create an event handler method, see [How to publish events that conform to .NET Framework Guidelines](../../programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md).</span></span>

[!code-csharp[csrefKeywordsModifiers#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#7)]

<span data-ttu-id="b5528-108">イベントは、宣言元 (パブリッシャー クラス) のクラスまたは構造体内でしか呼び出せない特殊なマルチキャスト デリゲートです。</span><span class="sxs-lookup"><span data-stu-id="b5528-108">Events are a special kind of multicast delegate that can only be invoked from within the class or struct where they are declared (the publisher class).</span></span> <span data-ttu-id="b5528-109">他のクラスまたは構造体がイベントを受信登録した場合、パブリッシャー クラスがイベントを発生させると、他のクラスまたは構造体のイベント ハンドラー メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b5528-109">If other classes or structs subscribe to the event, their event handler methods will be called when the publisher class raises the event.</span></span> <span data-ttu-id="b5528-110">詳細およびコード例については、「[イベント](../../programming-guide/events/index.md)」および「[デリゲート](../../programming-guide/delegates/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5528-110">For more information and code examples, see [Events](../../programming-guide/events/index.md) and [Delegates](../../programming-guide/delegates/index.md).</span></span>

<span data-ttu-id="b5528-111">イベントは、[public](./public.md)、[private](./private.md)、[protected](./protected.md)、[internal](./internal.md)、[protected internal](./protected-internal.md)、または [private protected](./private-protected.md) としてマークできます。</span><span class="sxs-lookup"><span data-stu-id="b5528-111">Events can be marked as [public](./public.md), [private](./private.md), [protected](./protected.md), [internal](./internal.md), [protected internal](./protected-internal.md), or [private protected](./private-protected.md).</span></span> <span data-ttu-id="b5528-112">これらのアクセス修飾子により、クラスのユーザーがイベントにアクセスする方法が定義されます。</span><span class="sxs-lookup"><span data-stu-id="b5528-112">These access modifiers define how users of the class can access the event.</span></span> <span data-ttu-id="b5528-113">詳細については、「[アクセス修飾子](../../programming-guide/classes-and-structs/access-modifiers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5528-113">For more information, see [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md).</span></span>

## <a name="keywords-and-events"></a><span data-ttu-id="b5528-114">キーワードとイベント</span><span class="sxs-lookup"><span data-stu-id="b5528-114">Keywords and events</span></span>

<span data-ttu-id="b5528-115">イベントには次のキーワードが適用されます。</span><span class="sxs-lookup"><span data-stu-id="b5528-115">The following keywords apply to events.</span></span>

|<span data-ttu-id="b5528-116">キーワード</span><span class="sxs-lookup"><span data-stu-id="b5528-116">Keyword</span></span>|<span data-ttu-id="b5528-117">説明</span><span class="sxs-lookup"><span data-stu-id="b5528-117">Description</span></span>|<span data-ttu-id="b5528-118">詳細情報</span><span class="sxs-lookup"><span data-stu-id="b5528-118">For more information</span></span>|
|-------------|-----------------|--------------------------|
|[<span data-ttu-id="b5528-119">static</span><span class="sxs-lookup"><span data-stu-id="b5528-119">static</span></span>](./static.md)|<span data-ttu-id="b5528-120">クラスのインスタンスが存在しない場合でも、呼び出し元がいつでもイベントを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b5528-120">Makes the event available to callers at any time, even if no instance of the class exists.</span></span>|[<span data-ttu-id="b5528-121">静的クラスと静的クラス メンバー</span><span class="sxs-lookup"><span data-stu-id="b5528-121">Static Classes and Static Class Members</span></span>](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)|
|[<span data-ttu-id="b5528-122">virtual</span><span class="sxs-lookup"><span data-stu-id="b5528-122">virtual</span></span>](./virtual.md)|<span data-ttu-id="b5528-123">[override](./override.md) キーワードを使用してイベントの動作をオーバーライドすることを派生クラスに許可します。</span><span class="sxs-lookup"><span data-stu-id="b5528-123">Allows derived classes to override the event behavior by using the [override](./override.md) keyword.</span></span>|[<span data-ttu-id="b5528-124">継承</span><span class="sxs-lookup"><span data-stu-id="b5528-124">Inheritance</span></span>](../../programming-guide/classes-and-structs/inheritance.md)|
|[<span data-ttu-id="b5528-125">sealed</span><span class="sxs-lookup"><span data-stu-id="b5528-125">sealed</span></span>](./sealed.md)|<span data-ttu-id="b5528-126">派生クラスでは、それが仮想ではなくなったことを指定します。</span><span class="sxs-lookup"><span data-stu-id="b5528-126">Specifies that for derived classes it is no longer virtual.</span></span>||
|[<span data-ttu-id="b5528-127">abstract</span><span class="sxs-lookup"><span data-stu-id="b5528-127">abstract</span></span>](./abstract.md)|<span data-ttu-id="b5528-128">コンパイラはイベント アクセサー ブロックの `add` と `remove` を生成しません。したがって、派生クラスは固有の実装を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5528-128">The compiler will not generate the `add` and `remove` event accessor blocks and therefore derived classes must provide their own implementation.</span></span>||

<span data-ttu-id="b5528-129">イベントは、[static](./static.md) キーワードを使用して静的イベントとして宣言されることもあります。</span><span class="sxs-lookup"><span data-stu-id="b5528-129">An event may be declared as a static event by using the [static](./static.md) keyword.</span></span> <span data-ttu-id="b5528-130">その場合、クラスのインスタンスが存在しなくても、呼び出し元がいつでもイベントを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b5528-130">This makes the event available to callers at any time, even if no instance of the class exists.</span></span> <span data-ttu-id="b5528-131">詳細については、「[静的クラスと静的クラス メンバー](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5528-131">For more information, see [Static Classes and Static Class Members](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>

<span data-ttu-id="b5528-132">イベントは、[virtual](./virtual.md) キーワードを使用して仮想イベントとしてマークできます。</span><span class="sxs-lookup"><span data-stu-id="b5528-132">An event can be marked as a virtual event by using the [virtual](./virtual.md) keyword.</span></span> <span data-ttu-id="b5528-133">その場合、派生クラスでは、[override](./override.md) キーワードを使用してイベントの動作をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="b5528-133">This enables derived classes to override the event behavior by using the [override](./override.md) keyword.</span></span> <span data-ttu-id="b5528-134">詳細については、「[継承](../../programming-guide/classes-and-structs/inheritance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5528-134">For more information, see [Inheritance](../../programming-guide/classes-and-structs/inheritance.md).</span></span> <span data-ttu-id="b5528-135">仮想イベントをオーバーライドするイベントは、[sealed](./sealed.md) にすることもできます。その場合、派生クラスでは、イベントが仮想でなくなります。</span><span class="sxs-lookup"><span data-stu-id="b5528-135">An event overriding a virtual event can also be [sealed](./sealed.md), which specifies that for derived classes it is no longer virtual.</span></span> <span data-ttu-id="b5528-136">最後に、イベントは [abstract](./abstract.md) として宣言できます。その場合、コンパイラはイベント アクセサー ブロックの `add` と `remove` を生成しません。</span><span class="sxs-lookup"><span data-stu-id="b5528-136">Lastly, an event can be declared [abstract](./abstract.md), which means that the compiler will not generate the `add` and `remove` event accessor blocks.</span></span> <span data-ttu-id="b5528-137">したがって、派生クラスごとに固有の実装を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5528-137">Therefore derived classes must provide their own implementation.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b5528-138">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="b5528-138">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="b5528-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5528-139">See also</span></span>

- [<span data-ttu-id="b5528-140">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="b5528-140">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b5528-141">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="b5528-141">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b5528-142">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="b5528-142">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="b5528-143">add</span><span class="sxs-lookup"><span data-stu-id="b5528-143">add</span></span>](./add.md)
- [<span data-ttu-id="b5528-144">remove</span><span class="sxs-lookup"><span data-stu-id="b5528-144">remove</span></span>](./remove.md)
- [<span data-ttu-id="b5528-145">修飾子</span><span class="sxs-lookup"><span data-stu-id="b5528-145">Modifiers</span></span>](index.md)
- [<span data-ttu-id="b5528-146">デリゲートを結合する方法 (マルチキャスト デリゲート)</span><span class="sxs-lookup"><span data-stu-id="b5528-146">How to combine delegates (Multicast Delegates)</span></span>](../../programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)
