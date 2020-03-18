---
title: インターフェイス イベントを実装する方法 - C# プログラミング ガイド
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], event implementation in classes
- events [C#], in interfaces
ms.assetid: 63527447-9535-4880-8e95-35e2075827df
ms.openlocfilehash: 8c0d221ef1272a43e2682ef2af3fa37d2d12d35e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79167481"
---
# <a name="how-to-implement-interface-events-c-programming-guide"></a><span data-ttu-id="594b5-102">インターフェイス イベントを実装する方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="594b5-102">How to implement interface events (C# Programming Guide)</span></span>
<span data-ttu-id="594b5-103">[インターフェイス](../../language-reference/keywords/interface.md)では[イベント](../../language-reference/keywords/event.md)を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="594b5-103">An [interface](../../language-reference/keywords/interface.md) can declare an [event](../../language-reference/keywords/event.md).</span></span> <span data-ttu-id="594b5-104">次の例では、クラス内にインターフェイス イベントを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="594b5-104">The following example shows how to implement interface events in a class.</span></span> <span data-ttu-id="594b5-105">基本的な原則は、インターフェイスのメソッドやプロパティを実装する場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="594b5-105">Basically the rules are the same as when you implement any interface method or property.</span></span>  
  
## <a name="to-implement-interface-events-in-a-class"></a><span data-ttu-id="594b5-106">クラス内でインターフェイス イベントを実装するには</span><span class="sxs-lookup"><span data-stu-id="594b5-106">To implement interface events in a class</span></span>  
  
<span data-ttu-id="594b5-107">クラス内でイベントを宣言してから、適切な領域でそのイベントを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="594b5-107">Declare the event in your class and then invoke it in the appropriate areas.</span></span>  
  
```csharp
namespace ImplementInterfaceEvents  
{  
    public interface IDrawingObject  
    {  
        event EventHandler ShapeChanged;  
    }  
    public class MyEventArgs : EventArgs
    {  
        // class members  
    }  
    public class Shape : IDrawingObject  
    {  
        public event EventHandler ShapeChanged;  
        void ChangeShape()  
        {  
            // Do something here before the event…  

            OnShapeChanged(new MyEventArgs(/*arguments*/));  

            // or do something here after the event.
        }  
        protected virtual void OnShapeChanged(MyEventArgs e)  
        {  
            ShapeChanged?.Invoke(this, e);  
        }  
    }  

}  
```  
  
## <a name="example"></a><span data-ttu-id="594b5-108">例</span><span class="sxs-lookup"><span data-stu-id="594b5-108">Example</span></span>  
<span data-ttu-id="594b5-109">次の例では、同じ名前のイベント名がある 2 つ以上のインターフェイスからクラスを継承するという、あまり一般的でない状況の対処方法を示します。</span><span class="sxs-lookup"><span data-stu-id="594b5-109">The following example shows how to handle the less-common situation in which your class inherits from two or more interfaces and each interface has an event with the same name.</span></span> <span data-ttu-id="594b5-110">このような場合は、1 つ以上のイベントに対して明示的なインターフェイスの実装を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="594b5-110">In this situation, you must provide an explicit interface implementation for at least one of the events.</span></span> <span data-ttu-id="594b5-111">イベントに対する明示的なインターフェイスの実装を記述する場合、`add` および `remove` の各イベント アクセサーも記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="594b5-111">When you write an explicit interface implementation for an event, you must also write the `add` and `remove` event accessors.</span></span> <span data-ttu-id="594b5-112">通常ではこれらのアクセサーはコンパイラで指定しますが、この例ではコンパイラで指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="594b5-112">Normally these are provided by the compiler, but in this case the compiler cannot provide them.</span></span>  
  
<span data-ttu-id="594b5-113">独自のアクセサーを指定することで、2 つのイベントがクラス内の同一イベントと別々のイベントのどちらによって表されるかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="594b5-113">By providing your own accessors, you can specify whether the two events are represented by the same event in your class, or by different events.</span></span> <span data-ttu-id="594b5-114">たとえば、インターフェイスの仕様上、イベントを複数回発生させる必要がある場合は、各イベントをクラス内の別々の実装に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="594b5-114">For example, if the events should be raised at different times according to the interface specifications, you can associate each event with a separate implementation in your class.</span></span> <span data-ttu-id="594b5-115">次の例では、サブスクライバーで `OnDraw` または `IShape` のいずれかに図形参照をキャストして、どちらの `IDrawingObject` イベントを受信するかを決定しています。</span><span class="sxs-lookup"><span data-stu-id="594b5-115">In the following example, subscribers determine which `OnDraw` event they will receive by casting the shape reference to either an `IShape` or an `IDrawingObject`.</span></span>  
  
 [!code-csharp[csProgGuideEvents#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#10)]
  
## <a name="see-also"></a><span data-ttu-id="594b5-116">参照</span><span class="sxs-lookup"><span data-stu-id="594b5-116">See also</span></span>

- [<span data-ttu-id="594b5-117">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="594b5-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="594b5-118">イベント</span><span class="sxs-lookup"><span data-stu-id="594b5-118">Events</span></span>](./index.md)
- [<span data-ttu-id="594b5-119">デリゲート</span><span class="sxs-lookup"><span data-stu-id="594b5-119">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="594b5-120">明示的なインターフェイスの実装</span><span class="sxs-lookup"><span data-stu-id="594b5-120">Explicit Interface Implementation</span></span>](../interfaces/explicit-interface-implementation.md)
- [<span data-ttu-id="594b5-121">派生クラスから基本クラス イベントを発生させる方法</span><span class="sxs-lookup"><span data-stu-id="594b5-121">How to raise base class events in derived classes</span></span>](./how-to-raise-base-class-events-in-derived-classes.md)
