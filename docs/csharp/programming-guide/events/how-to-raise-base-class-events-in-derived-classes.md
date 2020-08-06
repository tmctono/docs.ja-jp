---
title: 派生クラスから基底クラス イベントを発生させる方法 - C# プログラミング ガイド
description: 派生クラスから基底クラスのイベントを発生させる方法について説明します。 コード例を参照し、使用可能なその他のリソースを確認します。
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], in derived classes
ms.assetid: 2d20556a-0aad-46fc-845e-f85d86ea617a
ms.openlocfilehash: b0b0a16a1fd165e437fc79ccacb20d406f5cff63
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302101"
---
# <a name="how-to-raise-base-class-events-in-derived-classes-c-programming-guide"></a><span data-ttu-id="fdfbc-104">派生クラスから基底クラス イベントを発生させる方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="fdfbc-104">How to raise base class events in derived classes (C# Programming Guide)</span></span>
<span data-ttu-id="fdfbc-105">ここでは単純な例を使用し、派生クラスからも発生させることができるように基底クラスでイベントを宣言する標準的な方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fdfbc-105">The following simple example shows the standard way to declare events in a base class so that they can also be raised from derived classes.</span></span> <span data-ttu-id="fdfbc-106">このパターンは、.NET クラス ライブラリの Windows フォーム クラスで広く使用されています。</span><span class="sxs-lookup"><span data-stu-id="fdfbc-106">This pattern is used extensively in Windows Forms classes in the .NET class libraries.</span></span>  
  
 <span data-ttu-id="fdfbc-107">他のクラスの基底クラスとして使用できるクラスを作成するときは、イベントは宣言元のクラス内からしか呼び出せない特別な種類のデリゲートであることを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fdfbc-107">When you create a class that can be used as a base class for other classes, you should consider the fact that events are a special type of delegate that can only be invoked from within the class that declared them.</span></span> <span data-ttu-id="fdfbc-108">派生クラスは、基底クラスの中で宣言されたイベントを直接呼び出せません。</span><span class="sxs-lookup"><span data-stu-id="fdfbc-108">Derived classes cannot directly invoke events that are declared within the base class.</span></span> <span data-ttu-id="fdfbc-109">常に基底クラスからイベントを発生させるようにすると便利な場合もありますが、ほとんどの場合、派生クラスで基底クラス イベントを呼び出せるようにするべきです。</span><span class="sxs-lookup"><span data-stu-id="fdfbc-109">Although sometimes you may want an event that can only be raised by the base class, most of the time, you should enable the derived class to invoke base class events.</span></span> <span data-ttu-id="fdfbc-110">そのために、イベントをラップする基底クラスで、保護された呼び出しメソッドを作成できます。</span><span class="sxs-lookup"><span data-stu-id="fdfbc-110">To do this, you can create a protected invoking method in the base class that wraps the event.</span></span> <span data-ttu-id="fdfbc-111">この呼び出しメソッドを呼び出すかオーバーライドすることによって、派生クラスから間接的にイベントを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="fdfbc-111">By calling or overriding this invoking method, derived classes can invoke the event indirectly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fdfbc-112">基底クラスで仮想イベントを宣言したり、派生クラスでそれらをオーバーライドしたりしないでください。</span><span class="sxs-lookup"><span data-stu-id="fdfbc-112">Do not declare virtual events in a base class and override them in a derived class.</span></span> <span data-ttu-id="fdfbc-113">C# コンパイラはこれらを正しく処理できず、派生イベントに対するサブスクライバーが基底クラスのイベントを実際に受信登録するかどうかは予測できません。</span><span class="sxs-lookup"><span data-stu-id="fdfbc-113">The C# compiler does not handle these correctly and it is unpredictable whether a subscriber to the derived event will actually be subscribing to the base class event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fdfbc-114">例</span><span class="sxs-lookup"><span data-stu-id="fdfbc-114">Example</span></span>  
 [!code-csharp[csProgGuideEvents#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="fdfbc-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="fdfbc-115">See also</span></span>

- [<span data-ttu-id="fdfbc-116">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="fdfbc-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="fdfbc-117">イベント</span><span class="sxs-lookup"><span data-stu-id="fdfbc-117">Events</span></span>](./index.md)
- [<span data-ttu-id="fdfbc-118">デリゲート</span><span class="sxs-lookup"><span data-stu-id="fdfbc-118">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="fdfbc-119">アクセス修飾子</span><span class="sxs-lookup"><span data-stu-id="fdfbc-119">Access Modifiers</span></span>](../classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="fdfbc-120">Windows フォーム内でのイベント ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="fdfbc-120">Creating Event Handlers in Windows Forms</span></span>](../../../framework/winforms/creating-event-handlers-in-windows-forms.md)
