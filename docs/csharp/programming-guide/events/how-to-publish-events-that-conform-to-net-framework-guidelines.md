---
title: .NET ガイドラインに準拠したイベントを発行する - C# プログラミング ガイド
description: .NET ガイドラインに準拠したイベントを発行する方法について説明します。 .NET クラス ライブラリ内のすべてのイベントは、EventHandler デリゲートに基づいています。
ms.date: 05/26/2020
helpviewer_keywords:
- events [C#], implementation guidelines
ms.assetid: 9310ae16-8627-44a2-b08c-05e5976202b1
ms.openlocfilehash: 8cc8b0a9fdaeeb6ab6290630c5d78044c2696b9a
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2020
ms.locfileid: "89466171"
---
# <a name="how-to-publish-events-that-conform-to-net-guidelines-c-programming-guide"></a><span data-ttu-id="c0df6-104">.NET ガイドラインに準拠したイベントを発行する方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="c0df6-104">How to publish events that conform to .NET Guidelines (C# Programming Guide)</span></span>

<span data-ttu-id="c0df6-105">ここでは、.NET の標準のパターンに従うイベントをクラスおよび構造体に追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c0df6-105">The following procedure demonstrates how to add events that follow the standard .NET pattern to your classes and structs.</span></span> <span data-ttu-id="c0df6-106">.NET クラス ライブラリ内のすべてのイベントは、次のように定義されている <xref:System.EventHandler> デリゲートに基づいています。</span><span class="sxs-lookup"><span data-stu-id="c0df6-106">All events in the .NET class library are based on the <xref:System.EventHandler> delegate, which is defined as follows:</span></span>

```csharp
public delegate void EventHandler(object sender, EventArgs e);
```

> [!NOTE]
> <span data-ttu-id="c0df6-107">.NET Framework 2.0 には、このデリゲートのジェネリック バージョンである <xref:System.EventHandler%601> が導入されています。</span><span class="sxs-lookup"><span data-stu-id="c0df6-107">.NET Framework 2.0 introduces a generic version of this delegate, <xref:System.EventHandler%601>.</span></span> <span data-ttu-id="c0df6-108">次の例は、両方のバージョンの使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c0df6-108">The following examples show how to use both versions.</span></span>

<span data-ttu-id="c0df6-109">ユーザー定義のクラス内のイベントは、値を返すデリゲートを含む、あらゆる有効なデリゲート型に基づいて発行できますが、一般的には、次の例のように <xref:System.EventHandler> を使用して、.NET のパターンに基づいて発行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c0df6-109">Although events in classes that you define can be based on any valid delegate type, even delegates that return a value, it is generally recommended that you base your events on the .NET pattern by using <xref:System.EventHandler>, as shown in the following example.</span></span>

<span data-ttu-id="c0df6-110">名前 `EventHandler` は、実際にはイベントを処理しないため、混乱を招く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c0df6-110">The name `EventHandler` can lead to a bit of confusion as it doesn't actually handle the event.</span></span> <span data-ttu-id="c0df6-111"><xref:System.EventHandler>、およびジェネリックの <xref:System.EventHandler%601> はデリゲート型です。</span><span class="sxs-lookup"><span data-stu-id="c0df6-111">The <xref:System.EventHandler>, and generic <xref:System.EventHandler%601> are delegate types.</span></span> <span data-ttu-id="c0df6-112">シグネチャがデリゲート定義と一致するメソッドまたはラムダ式は、"*イベント ハンドラー*" で、イベントが発生したときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c0df6-112">A method or lambda expression whose signature matches the delegate definition is the *event handler* and will be invoked when the event is raised.</span></span>

## <a name="publish-events-based-on-the-eventhandler-pattern"></a><span data-ttu-id="c0df6-113">EventHandler パターンに基づいてイベントを発行する</span><span class="sxs-lookup"><span data-stu-id="c0df6-113">Publish events based on the EventHandler pattern</span></span>

1. <span data-ttu-id="c0df6-114">(イベントと共にカスタム データを送信する必要がない場合は、この手順を省略して手順 3a. に進んでください。)パブリッシャー クラスとサブスクライバー クラスの両方から参照できるスコープで、カスタム データのクラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="c0df6-114">(Skip this step and go to Step 3a if you do not have to send custom data with your event.) Declare the class for your custom data at a scope that is visible to both your publisher and subscriber classes.</span></span> <span data-ttu-id="c0df6-115">次に、カスタム イベント データを保持する必須メンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="c0df6-115">Then add the required members to hold your custom event data.</span></span> <span data-ttu-id="c0df6-116">この例では、単純な文字列が 1 つ返されます。</span><span class="sxs-lookup"><span data-stu-id="c0df6-116">In this example, a simple string is returned.</span></span>

    ```csharp
    public class CustomEventArgs : EventArgs
    {
        public CustomEventArgs(string message)
        {
            Message = message;
        }

        public string Message { get; set; }
    }
    ```

2. <span data-ttu-id="c0df6-117">(ジェネリック バージョンの <xref:System.EventHandler%601> を使用する場合、この手順は省略します。)パブリッシャー クラスでデリゲートを宣言します。</span><span class="sxs-lookup"><span data-stu-id="c0df6-117">(Skip this step if you are using the generic version of <xref:System.EventHandler%601>.) Declare a delegate in your publishing class.</span></span> <span data-ttu-id="c0df6-118">`EventHandler` で終わる名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c0df6-118">Give it a name that ends with `EventHandler`.</span></span> <span data-ttu-id="c0df6-119">2 番目のパラメーターで、カスタムの `EventArgs` 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="c0df6-119">The second parameter specifies your custom `EventArgs` type.</span></span>

    ```csharp
    public delegate void CustomEventHandler(object sender, CustomEventArgs args);
    ```

3. <span data-ttu-id="c0df6-120">次のいずれかの手順を使用して、パブリッシャー クラスでイベントを宣言します。</span><span class="sxs-lookup"><span data-stu-id="c0df6-120">Declare the event in your publishing class by using one of the following steps.</span></span>

    1. <span data-ttu-id="c0df6-121">カスタムの EventArgs クラスがない場合、Event 型は非ジェネリック バージョンの EventHandler デリゲートになります。</span><span class="sxs-lookup"><span data-stu-id="c0df6-121">If you have no custom EventArgs class, your Event type will be the non-generic EventHandler delegate.</span></span> <span data-ttu-id="c0df6-122">このデリゲートは、C# プロジェクトを作成したときに含まれている <xref:System> 名前空間で既に宣言されているため、ここで宣言する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c0df6-122">You do not have to declare the delegate because it is already declared in the <xref:System> namespace that is included when you create your C# project.</span></span> <span data-ttu-id="c0df6-123">パブリッシャー クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c0df6-123">Add the following code to your publisher class.</span></span>

        ```csharp
        public event EventHandler RaiseCustomEvent;
        ```

    2. <span data-ttu-id="c0df6-124">非ジェネリック バージョンの <xref:System.EventHandler> を使用し、<xref:System.EventArgs> から派生したカスタム クラスがある場合は、パブリッシャー クラス内でイベントを宣言し、手順 2 のデリゲートを型として使用します。</span><span class="sxs-lookup"><span data-stu-id="c0df6-124">If you are using the non-generic version of <xref:System.EventHandler> and you have a custom class derived from <xref:System.EventArgs>, declare your event inside your publishing class and use your delegate from step 2 as the type.</span></span>

        ```csharp
        public event CustomEventHandler RaiseCustomEvent;
        ```

    3. <span data-ttu-id="c0df6-125">ジェネリック バージョンを使用する場合、カスタム デリゲートは不要です。</span><span class="sxs-lookup"><span data-stu-id="c0df6-125">If you are using the generic version, you do not need a custom delegate.</span></span> <span data-ttu-id="c0df6-126">代わりに、パブリッシャー クラスでイベントの種類として `EventHandler<CustomEventArgs>` を指定します。山かっこの部分は、実際のクラス名で置き換えます。</span><span class="sxs-lookup"><span data-stu-id="c0df6-126">Instead, in your publishing class, you specify your event type as `EventHandler<CustomEventArgs>`, substituting the name of your own class between the angle brackets.</span></span>

        ```csharp
        public event EventHandler<CustomEventArgs> RaiseCustomEvent;
        ```

## <a name="example"></a><span data-ttu-id="c0df6-127">例</span><span class="sxs-lookup"><span data-stu-id="c0df6-127">Example</span></span>

<span data-ttu-id="c0df6-128">次の例は、前の手順を具体的に示しています。ここでは、カスタムの EventArgs クラスを使用し、イベントの種類として <xref:System.EventHandler%601> を使用しています。</span><span class="sxs-lookup"><span data-stu-id="c0df6-128">The following example demonstrates the previous steps by using a custom EventArgs class and <xref:System.EventHandler%601> as the event type.</span></span>

[!code-csharp[csProgGuideEvents#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#2)]

## <a name="see-also"></a><span data-ttu-id="c0df6-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0df6-129">See also</span></span>

- <xref:System.Delegate>
- [<span data-ttu-id="c0df6-130">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="c0df6-130">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c0df6-131">イベント</span><span class="sxs-lookup"><span data-stu-id="c0df6-131">Events</span></span>](index.md)
- [<span data-ttu-id="c0df6-132">デリゲート</span><span class="sxs-lookup"><span data-stu-id="c0df6-132">Delegates</span></span>](../delegates/index.md)
