---
title: Windows フォーム内でのイベント ハンドラーの作成
ms.date: 03/30/2017
helpviewer_keywords:
- event handling [Windows Forms]
- Windows Forms controls, event handling
- Windows Forms, event handling
- events [Windows Forms], event handlers
- event handlers [Windows Forms]
ms.assetid: 6514e530-c6b8-489c-a8d2-eda7b7072701
ms.openlocfilehash: 6b1d146dfd9d51641bc9eb5d8be4cd2508c223a1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963479"
---
# <a name="creating-event-handlers-in-windows-forms"></a><span data-ttu-id="a8991-102">Windows フォーム内でのイベント ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="a8991-102">Creating Event Handlers in Windows Forms</span></span>

<span data-ttu-id="a8991-103">イベント ハンドラーは、ユーザーがボタンをクリックする、またはメッセージ キューがメッセージを受信するなどのイベントが発生したときに実行するアクションを決定する、コード内の手順です。</span><span class="sxs-lookup"><span data-stu-id="a8991-103">An event handler is a procedure in your code that determines what actions are performed when an event occurs, such as when the user clicks a button or a message queue receives a message.</span></span> <span data-ttu-id="a8991-104">イベントが発生すると、そのイベントを受信した一つまたは複数のイベント ハンドラーが実行されます。</span><span class="sxs-lookup"><span data-stu-id="a8991-104">When an event is raised, the event handler or handlers that receive the event are executed.</span></span> <span data-ttu-id="a8991-105">イベントは複数のハンドラーに割り当てられ、特定のイベントを処理するメソッドは動的に変更できます。</span><span class="sxs-lookup"><span data-stu-id="a8991-105">Events can be assigned to multiple handlers, and the methods that handle particular events can be changed dynamically.</span></span> <span data-ttu-id="a8991-106">また、Visual Studio の Windows フォームデザイナーを使用して、イベントハンドラーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="a8991-106">You can also use the Windows Forms Designer in Visual Studio to create event handlers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="a8991-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a8991-107">In This Section</span></span>

 <span data-ttu-id="a8991-108">[イベントの概要](events-overview-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="a8991-108">[Events Overview](events-overview-windows-forms.md)</span></span>\
 <span data-ttu-id="a8991-109">イベント モデルおよびデリゲートの役割を説明します。</span><span class="sxs-lookup"><span data-stu-id="a8991-109">Explains the event model and the role of delegates.</span></span>

 <span data-ttu-id="a8991-110">[イベント ハンドラーの概要](event-handlers-overview-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="a8991-110">[Event Handlers Overview](event-handlers-overview-windows-forms.md)</span></span>\
 <span data-ttu-id="a8991-111">イベントを処理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a8991-111">Describes how to handle events.</span></span>

 <span data-ttu-id="a8991-112">[方法: 実行時に Windows フォームのイベントハンドラーを作成する](how-to-create-event-handlers-at-run-time-for-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="a8991-112">[How to: Create Event Handlers at Run Time for Windows Forms](how-to-create-event-handlers-at-run-time-for-windows-forms.md)</span></span>\
 <span data-ttu-id="a8991-113">システム イベントおよびユーザー イベントへの動的な応答の手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="a8991-113">Gives directions for responding to system or user events dynamically.</span></span>

 <span data-ttu-id="a8991-114">[方法: Windows フォームの1つのイベントハンドラーに複数のイベントを接続する](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="a8991-114">[How to: Connect Multiple Events to a Single Event Handler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)</span></span>\
 <span data-ttu-id="a8991-115">イベントを通じて、複数のコントロールに同じ機能を割り当てる手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="a8991-115">Gives directions for assigning the same functionality to multiple controls through events.</span></span>

 <span data-ttu-id="a8991-116">[Windows フォーム内のイベントの順序](order-of-events-in-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="a8991-116">[Order of Events in Windows Forms](order-of-events-in-windows-forms.md)</span></span>\
 <span data-ttu-id="a8991-117">Windows フォーム コントロールで発生するイベントの順序について説明します。</span><span class="sxs-lookup"><span data-stu-id="a8991-117">Describes the order in which events are raised in Windows Forms controls.</span></span>

 <span data-ttu-id="a8991-118">[方法: デザイナー](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100))を使用してイベントハンドラーを作成する Windows フォームデザイナーを使用してイベントハンドラーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a8991-118">[How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) Describes how to use the Windows Forms Designer to create event handlers.</span></span>

## <a name="related-sections"></a><span data-ttu-id="a8991-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8991-119">Related Sections</span></span>

 <span data-ttu-id="a8991-120">[イベント](../../standard/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="a8991-120">[Events](../../standard/events/index.md)</span></span>\
 <span data-ttu-id="a8991-121">.NET Framework を使用したイベントの処理と発生に関するトピックへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="a8991-121">Provides links to topics on handling and raising events using the .NET Framework.</span></span>

 <span data-ttu-id="a8991-122">[Visual Basic での継承されたイベント ハンドラーのトラブルシューティング](../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)</span><span class="sxs-lookup"><span data-stu-id="a8991-122">[Troubleshooting Inherited Event Handlers in Visual Basic](../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)</span></span>\
 <span data-ttu-id="a8991-123">継承されたコンポーネントでイベント ハンドラーに生じる一般的な問題を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="a8991-123">Lists common issues that occur with event handlers in inherited components.</span></span>
