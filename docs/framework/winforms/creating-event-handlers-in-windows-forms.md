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
ms.openlocfilehash: 329060e0c53178a9320be9a7cdff492d69917782
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211250"
---
# <a name="creating-event-handlers-in-windows-forms"></a><span data-ttu-id="ee5f3-102">Windows フォーム内でのイベント ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="ee5f3-102">Creating Event Handlers in Windows Forms</span></span>

<span data-ttu-id="ee5f3-103">イベント ハンドラーは、ユーザーがボタンをクリックする、またはメッセージ キューがメッセージを受信するなどのイベントが発生したときに実行するアクションを決定する、コード内の手順です。</span><span class="sxs-lookup"><span data-stu-id="ee5f3-103">An event handler is a procedure in your code that determines what actions are performed when an event occurs, such as when the user clicks a button or a message queue receives a message.</span></span> <span data-ttu-id="ee5f3-104">イベントが発生すると、そのイベントを受信した一つまたは複数のイベント ハンドラーが実行されます。</span><span class="sxs-lookup"><span data-stu-id="ee5f3-104">When an event is raised, the event handler or handlers that receive the event are executed.</span></span> <span data-ttu-id="ee5f3-105">イベントは複数のハンドラーに割り当てられ、特定のイベントを処理するメソッドは動的に変更できます。</span><span class="sxs-lookup"><span data-stu-id="ee5f3-105">Events can be assigned to multiple handlers, and the methods that handle particular events can be changed dynamically.</span></span> <span data-ttu-id="ee5f3-106">イベント ハンドラーを作成するのに Visual Studio で、Windows フォーム デザイナーを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="ee5f3-106">You can also use the Windows Forms Designer in Visual Studio to create event handlers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="ee5f3-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ee5f3-107">In This Section</span></span>

 <span data-ttu-id="ee5f3-108">[イベントの概要](events-overview-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="ee5f3-108">[Events Overview](events-overview-windows-forms.md)\\</span></span>
 <span data-ttu-id="ee5f3-109">イベント モデルおよびデリゲートの役割を説明します。</span><span class="sxs-lookup"><span data-stu-id="ee5f3-109">Explains the event model and the role of delegates.</span></span>

 <span data-ttu-id="ee5f3-110">[イベント ハンドラーの概要](event-handlers-overview-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="ee5f3-110">[Event Handlers Overview](event-handlers-overview-windows-forms.md)\\</span></span>
 <span data-ttu-id="ee5f3-111">イベントを処理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ee5f3-111">Describes how to handle events.</span></span>

 <span data-ttu-id="ee5f3-112">[方法: Windows フォームの実行時にイベント ハンドラーを作成します。](how-to-create-event-handlers-at-run-time-for-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="ee5f3-112">[How to: Create Event Handlers at Run Time for Windows Forms](how-to-create-event-handlers-at-run-time-for-windows-forms.md)\\</span></span>
 <span data-ttu-id="ee5f3-113">システム イベントおよびユーザー イベントへの動的な応答の手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="ee5f3-113">Gives directions for responding to system or user events dynamically.</span></span>

 <span data-ttu-id="ee5f3-114">[方法: Windows フォームで 1 つのイベント ハンドラーに複数のイベントを接続します。](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="ee5f3-114">[How to: Connect Multiple Events to a Single Event Handler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)\\</span></span>
 <span data-ttu-id="ee5f3-115">イベントを通じて、複数のコントロールに同じ機能を割り当てる手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="ee5f3-115">Gives directions for assigning the same functionality to multiple controls through events.</span></span>

 <span data-ttu-id="ee5f3-116">[Windows フォームのイベントの順序](order-of-events-in-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="ee5f3-116">[Order of Events in Windows Forms](order-of-events-in-windows-forms.md)\\</span></span>
 <span data-ttu-id="ee5f3-117">Windows フォーム コントロールで発生するイベントの順序について説明します。</span><span class="sxs-lookup"><span data-stu-id="ee5f3-117">Describes the order in which events are raised in Windows Forms controls.</span></span>

 <span data-ttu-id="ee5f3-118">[方法: デザイナーを使用してイベント ハンドラーを作成](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100))Windows フォーム デザイナーを使用して、イベント ハンドラーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ee5f3-118">[How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) Describes how to use the Windows Forms Designer to create event handlers.</span></span>

## <a name="related-sections"></a><span data-ttu-id="ee5f3-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="ee5f3-119">Related Sections</span></span>

 <span data-ttu-id="ee5f3-120">[イベント](../../standard/events/index.md)\\</span><span class="sxs-lookup"><span data-stu-id="ee5f3-120">[Events](../../standard/events/index.md)\\</span></span>
 <span data-ttu-id="ee5f3-121">処理およびを使用してイベントの発生に関するトピックへのリンクを提供します、 [!INCLUDE [dnprdnshort](../../../includes/dnprdnshort-md.md)\]。</span><span class="sxs-lookup"><span data-stu-id="ee5f3-121">Provides links to topics on handling and raising events using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)\].</span></span>

 <span data-ttu-id="ee5f3-122">[Visual Basic での継承されたイベント ハンドラーのトラブルシューティング](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)\\</span><span class="sxs-lookup"><span data-stu-id="ee5f3-122">[Troubleshooting Inherited Event Handlers in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)\\</span></span>
 <span data-ttu-id="ee5f3-123">継承されたコンポーネントでイベント ハンドラーに生じる一般的な問題を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="ee5f3-123">Lists common issues that occur with event handlers in inherited components.</span></span>
