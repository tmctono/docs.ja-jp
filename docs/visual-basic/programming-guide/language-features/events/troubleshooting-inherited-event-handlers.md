---
title: 継承されたイベント ハンドラーのトラブルシューティング
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting events [Visual Basic]
- inherited events [Visual Basic]
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
ms.openlocfilehash: 4e7bedd1de5197fcf8b69091f4cc878f41b01cd5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405107"
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a><span data-ttu-id="4dee1-102">Visual Basic での継承されたイベント ハンドラーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="4dee1-102">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>
<span data-ttu-id="4dee1-103">このトピックでは、継承されたコンポーネントのイベント ハンドラーで生じる一般的な問題を示します。</span><span class="sxs-lookup"><span data-stu-id="4dee1-103">This topic lists common issues that arise with event handlers in inherited components.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="4dee1-104">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="4dee1-104">Procedures</span></span>  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a><span data-ttu-id="4dee1-105">呼び出しのたびにイベント ハンドラーのコードが 2 回実行される</span><span class="sxs-lookup"><span data-stu-id="4dee1-105">Code in Event Handler Executes Twice for Every Call</span></span>  
  
- <span data-ttu-id="4dee1-106">継承イベント ハンドラーには、[Handles](../../../language-reference/statements/handles-clause.md) 句を含めないでください。</span><span class="sxs-lookup"><span data-stu-id="4dee1-106">An inherited event handler must not include a [Handles](../../../language-reference/statements/handles-clause.md) clause.</span></span> <span data-ttu-id="4dee1-107">基底クラスのメソッドは既にイベントに関連付けられており、適切に実行されます。</span><span class="sxs-lookup"><span data-stu-id="4dee1-107">The method in the base class is already associated with the event and will fire accordingly.</span></span> <span data-ttu-id="4dee1-108">継承メソッドの `Handles` 句を削除してください。</span><span class="sxs-lookup"><span data-stu-id="4dee1-108">Remove the `Handles` clause from the inherited method.</span></span>  
  
     [!code-vb[VbVbalrEvents#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#32)]  
  
- <span data-ttu-id="4dee1-109">継承メソッドに `Handles` キーワードを含めていない場合は、余計な [AddHandler ステートメント](../../../language-reference/statements/addhandler-statement.md)、または同じイベントを処理する別のメソッドが含まれていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4dee1-109">If the inherited method does not have a `Handles` keyword, verify that your code does not contain an extra [AddHandler Statement](../../../language-reference/statements/addhandler-statement.md) or any additional methods that handle the same event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dee1-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="4dee1-110">See also</span></span>

- [<span data-ttu-id="4dee1-111">イベント</span><span class="sxs-lookup"><span data-stu-id="4dee1-111">Events</span></span>](index.md)
