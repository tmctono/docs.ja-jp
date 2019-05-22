---
title: '方法: 派生クラスから基本クラス イベントを発生させる - C# プログラミング ガイド'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], in derived classes
ms.assetid: 2d20556a-0aad-46fc-845e-f85d86ea617a
ms.openlocfilehash: 2f200ff00534bde1fa0d016d64099e3ca28535a8
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65585848"
---
# <a name="how-to-raise-base-class-events-in-derived-classes-c-programming-guide"></a><span data-ttu-id="11fae-102">方法: 派生クラスから基本クラス イベントを発生させる (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="11fae-102">How to: Raise Base Class Events in Derived Classes (C# Programming Guide)</span></span>
<span data-ttu-id="11fae-103">ここでは単純な例を使用し、派生クラスからも発生させることができるように基底クラスでイベントを宣言する標準的な方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="11fae-103">The following simple example shows the standard way to declare events in a base class so that they can also be raised from derived classes.</span></span> <span data-ttu-id="11fae-104">このパターンは、.NET Framework クラス ライブラリの Windows フォーム クラスで広く使用されています。</span><span class="sxs-lookup"><span data-stu-id="11fae-104">This pattern is used extensively in Windows Forms classes in the .NET Framework class library.</span></span>  
  
 <span data-ttu-id="11fae-105">他のクラスの基底クラスとして使用できるクラスを作成するときは、イベントは宣言元のクラス内からしか呼び出せない特別な種類のデリゲートであることを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11fae-105">When you create a class that can be used as a base class for other classes, you should consider the fact that events are a special type of delegate that can only be invoked from within the class that declared them.</span></span> <span data-ttu-id="11fae-106">派生クラスは、基底クラスの中で宣言されたイベントを直接呼び出せません。</span><span class="sxs-lookup"><span data-stu-id="11fae-106">Derived classes cannot directly invoke events that are declared within the base class.</span></span> <span data-ttu-id="11fae-107">常に基底クラスからイベントを発生させるようにすると便利な場合もありますが、ほとんどの場合、派生クラスで基底クラス イベントを呼び出せるようにするべきです。</span><span class="sxs-lookup"><span data-stu-id="11fae-107">Although sometimes you may want an event that can only be raised by the base class, most of the time, you should enable the derived class to invoke base class events.</span></span> <span data-ttu-id="11fae-108">そのために、イベントをラップする基底クラスで、保護された呼び出しメソッドを作成できます。</span><span class="sxs-lookup"><span data-stu-id="11fae-108">To do this, you can create a protected invoking method in the base class that wraps the event.</span></span> <span data-ttu-id="11fae-109">この呼び出しメソッドを呼び出すかオーバーライドすることによって、派生クラスから間接的にイベントを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="11fae-109">By calling or overriding this invoking method, derived classes can invoke the event indirectly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11fae-110">基底クラスで仮想イベントを宣言したり、派生クラスでそれらをオーバーライドしたりしないでください。</span><span class="sxs-lookup"><span data-stu-id="11fae-110">Do not declare virtual events in a base class and override them in a derived class.</span></span> <span data-ttu-id="11fae-111">C# コンパイラはこれらを正しく処理できず、派生イベントに対するサブスクライバーが基底クラスのイベントを実際に受信登録するかどうかは予測できません。</span><span class="sxs-lookup"><span data-stu-id="11fae-111">The C# compiler does not handle these correctly and it is unpredictable whether a subscriber to the derived event will actually be subscribing to the base class event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11fae-112">例</span><span class="sxs-lookup"><span data-stu-id="11fae-112">Example</span></span>  
 [!code-csharp[csProgGuideEvents#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="11fae-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="11fae-113">See also</span></span>

- [<span data-ttu-id="11fae-114">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="11fae-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="11fae-115">イベント</span><span class="sxs-lookup"><span data-stu-id="11fae-115">Events</span></span>](../../../csharp/programming-guide/events/index.md)
- [<span data-ttu-id="11fae-116">デリゲート</span><span class="sxs-lookup"><span data-stu-id="11fae-116">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
- [<span data-ttu-id="11fae-117">アクセス修飾子</span><span class="sxs-lookup"><span data-stu-id="11fae-117">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="11fae-118">Windows フォーム内でのイベント ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="11fae-118">Creating Event Handlers in Windows Forms</span></span>](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)
