---
title: AddHandler ステートメント
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: 79dbe174209e91f13f5b43e8cdeb0b42edc4d163
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866706"
---
# <a name="addhandler-statement"></a><span data-ttu-id="8e829-102">AddHandler ステートメント</span><span class="sxs-lookup"><span data-stu-id="8e829-102">AddHandler Statement</span></span>

<span data-ttu-id="8e829-103">実行時にイベントをイベント ハンドラーに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="8e829-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e829-104">構文</span><span class="sxs-lookup"><span data-stu-id="8e829-104">Syntax</span></span>  
  
```vb  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="8e829-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="8e829-105">Parts</span></span>  

|||
|---|---|
|<span data-ttu-id="8e829-106">event</span><span class="sxs-lookup"><span data-stu-id="8e829-106">event</span></span>|<span data-ttu-id="8e829-107">処理するイベントの名前。</span><span class="sxs-lookup"><span data-stu-id="8e829-107">The name of the event to handle.</span></span>|  
|`eventhandler`|<span data-ttu-id="8e829-108">イベントを処理するプロシージャの名前。</span><span class="sxs-lookup"><span data-stu-id="8e829-108">The name of a procedure that handles the event.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="8e829-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="8e829-109">Remarks</span></span>  

 <span data-ttu-id="8e829-110">`AddHandler` および `RemoveHandler` ステートメントを使用すると、プログラムの実行中にいつでもイベント処理を開始および停止できます。</span><span class="sxs-lookup"><span data-stu-id="8e829-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="8e829-111">`eventhandler` プロシージャのシグネチャは、イベント `event` のシグネチャと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e829-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="8e829-112">`Handles` キーワードと `AddHandler` ステートメントはどちらも特定のプロシージャで特定のイベントを処理するように指定できますが、両者には違いがあります。</span><span class="sxs-lookup"><span data-stu-id="8e829-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="8e829-113">`AddHandler` ステートメントは、実行時にプロシージャをイベントに接続します。</span><span class="sxs-lookup"><span data-stu-id="8e829-113">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="8e829-114">`Handles` キーワードは、プロシージャの定義時に特定のイベントを処理するよう指定する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="8e829-114">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="8e829-115">詳細については、「[Handles](handles-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e829-115">For more information, see [Handles](handles-clause.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8e829-116">カスタム イベントの場合は、`AddHandler` ステートメントによってイベントの `AddHandler` アクセサーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="8e829-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="8e829-117">カスタム イベントの詳細については、「[Event ステートメント](event-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e829-117">For more information on custom events, see [Event Statement](event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e829-118">例</span><span class="sxs-lookup"><span data-stu-id="8e829-118">Example</span></span>  

 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="8e829-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e829-119">See also</span></span>

- [<span data-ttu-id="8e829-120">RemoveHandler ステートメント</span><span class="sxs-lookup"><span data-stu-id="8e829-120">RemoveHandler Statement</span></span>](removehandler-statement.md)
- [<span data-ttu-id="8e829-121">Handles</span><span class="sxs-lookup"><span data-stu-id="8e829-121">Handles</span></span>](handles-clause.md)
- [<span data-ttu-id="8e829-122">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="8e829-122">Event Statement</span></span>](event-statement.md)
- [<span data-ttu-id="8e829-123">イベント</span><span class="sxs-lookup"><span data-stu-id="8e829-123">Events</span></span>](../../programming-guide/language-features/events/index.md)
