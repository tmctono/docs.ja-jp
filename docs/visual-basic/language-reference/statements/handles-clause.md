---
title: Handles 句
ms.date: 07/20/2015
f1_keywords:
- Handles
- vb.Handles
helpviewer_keywords:
- Handles keyword [Visual Basic]
ms.assetid: 1b051c0e-f499-42f6-acb5-6f4f27824b40
ms.openlocfilehash: 2fecad919722f3da25c48f133a9c92b5e683d5e4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345910"
---
# <a name="handles-clause-visual-basic"></a><span data-ttu-id="758ef-102">Handles 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="758ef-102">Handles Clause (Visual Basic)</span></span>
<span data-ttu-id="758ef-103">プロシージャが指定されたイベントを処理することを宣言します。</span><span class="sxs-lookup"><span data-stu-id="758ef-103">Declares that a procedure handles a specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="758ef-104">構文</span><span class="sxs-lookup"><span data-stu-id="758ef-104">Syntax</span></span>  
  
```vb  
proceduredeclaration Handles eventlist  
```  
  
## <a name="parts"></a><span data-ttu-id="758ef-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="758ef-105">Parts</span></span>  
 `proceduredeclaration`  
 <span data-ttu-id="758ef-106">イベントを処理するプロシージャの `Sub` プロシージャ宣言。</span><span class="sxs-lookup"><span data-stu-id="758ef-106">The `Sub` procedure declaration for the procedure that will handle the event.</span></span>  
  
 `eventlist`  
 <span data-ttu-id="758ef-107">コンマで区切られた、`proceduredeclaration` が処理するイベントの一覧。</span><span class="sxs-lookup"><span data-stu-id="758ef-107">List of the events for `proceduredeclaration` to handle, separated by commas.</span></span> <span data-ttu-id="758ef-108">イベントは、現在のクラスの基底クラス、または `WithEvents` キーワードを使用して宣言されたオブジェクトによって発生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="758ef-108">The events must be raised by either the base class for the current class, or by an object declared using the `WithEvents` keyword.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="758ef-109">コメント</span><span class="sxs-lookup"><span data-stu-id="758ef-109">Remarks</span></span>  
 <span data-ttu-id="758ef-110">プロシージャ宣言の最後で `Handles` キーワードを使用すると、 `WithEvents` キーワードで宣言されたオブジェクト変数によって発生したイベントが処理されるようになります。</span><span class="sxs-lookup"><span data-stu-id="758ef-110">Use the `Handles` keyword at the end of a procedure declaration to cause it to handle events raised by an object variable declared using the `WithEvents` keyword.</span></span> <span data-ttu-id="758ef-111">また、`Handles` キーワードを派生クラスで使用すると、基底クラスからのイベントを処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="758ef-111">The `Handles` keyword can also be used in a derived class to handle events from a base class.</span></span>  
  
 <span data-ttu-id="758ef-112">`Handles` キーワードと `AddHandler` ステートメントはどちらも特定のプロシージャで特定のイベントを処理するように指定できますが、両者には違いがあります。</span><span class="sxs-lookup"><span data-stu-id="758ef-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="758ef-113">`Handles` キーワードは、プロシージャの定義時に特定のイベントを処理するよう指定する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="758ef-113">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="758ef-114">`AddHandler` ステートメントは、実行時にプロシージャをイベントに接続します。</span><span class="sxs-lookup"><span data-stu-id="758ef-114">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="758ef-115">詳細については、「 [AddHandler ステートメント](../../../visual-basic/language-reference/statements/addhandler-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="758ef-115">For more information, see [AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span>  
  
 <span data-ttu-id="758ef-116">カスタム イベントの場合、アプリケーションは、プロシージャをイベント ハンドラーとして追加するときにイベントの `AddHandler` アクセサーを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="758ef-116">For custom events, the application invokes the event's `AddHandler` accessor when it adds the procedure as an event handler.</span></span> <span data-ttu-id="758ef-117">カスタムイベントの詳細については、「 [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="758ef-117">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="758ef-118">例</span><span class="sxs-lookup"><span data-stu-id="758ef-118">Example</span></span>  
 [!code-vb[VbVbalrEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#2)]  
  
 <span data-ttu-id="758ef-119">派生クラスで `Handles` ステートメントを使用して基底クラスからのイベントを処理する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="758ef-119">The following example demonstrates how a derived class can use the `Handles` statement to handle an event from a base class.</span></span>  
  
 [!code-vb[VbVbalrEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="758ef-120">例</span><span class="sxs-lookup"><span data-stu-id="758ef-120">Example</span></span>  
 <span data-ttu-id="758ef-121">次の例には、 **WPF アプリケーション**プロジェクトの2つのボタンイベントハンドラーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="758ef-121">The following example contains two button event handlers for a **WPF Application** project.</span></span>  
  
 [!code-vb[VbVbalrEvents#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/class3.vb#41)]  
  
## <a name="example"></a><span data-ttu-id="758ef-122">例</span><span class="sxs-lookup"><span data-stu-id="758ef-122">Example</span></span>  
 <span data-ttu-id="758ef-123">次の例は、前の例と同じです。</span><span class="sxs-lookup"><span data-stu-id="758ef-123">The following example is equivalent to the previous example.</span></span> <span data-ttu-id="758ef-124">`eventlist` 句の `Handles` には 2 つのボタンのイベントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="758ef-124">The `eventlist` in the `Handles` clause contains the events for both buttons.</span></span>  
  
 [!code-vb[VbVbalrEvents#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/class3.vb#42)]  
  
## <a name="see-also"></a><span data-ttu-id="758ef-125">参照</span><span class="sxs-lookup"><span data-stu-id="758ef-125">See also</span></span>

- [<span data-ttu-id="758ef-126">WithEvents</span><span class="sxs-lookup"><span data-stu-id="758ef-126">WithEvents</span></span>](../../../visual-basic/language-reference/modifiers/withevents.md)
- [<span data-ttu-id="758ef-127">AddHandler ステートメント</span><span class="sxs-lookup"><span data-stu-id="758ef-127">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [<span data-ttu-id="758ef-128">RemoveHandler ステートメント</span><span class="sxs-lookup"><span data-stu-id="758ef-128">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [<span data-ttu-id="758ef-129">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="758ef-129">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="758ef-130">RaiseEvent ステートメント</span><span class="sxs-lookup"><span data-stu-id="758ef-130">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
- [<span data-ttu-id="758ef-131">イベント</span><span class="sxs-lookup"><span data-stu-id="758ef-131">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
