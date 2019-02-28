---
title: Visual Basic での継承されたイベント ハンドラーのトラブルシューティング
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting events [Visual Basic]
- inherited events [Visual Basic]
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
ms.openlocfilehash: 91bded2f1249bfcbeeca28419ee9bcec819babf6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965425"
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a><span data-ttu-id="de38c-102">Visual Basic での継承されたイベント ハンドラーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="de38c-102">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>
<span data-ttu-id="de38c-103">このトピックでは、継承されたコンポーネントのイベント ハンドラーで発生する一般的な問題を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="de38c-103">This topic lists common issues that arise with event handlers in inherited components.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="de38c-104">手順</span><span class="sxs-lookup"><span data-stu-id="de38c-104">Procedures</span></span>  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a><span data-ttu-id="de38c-105">イベント ハンドラーのコードは呼び出しごとに 2 回実行します</span><span class="sxs-lookup"><span data-stu-id="de38c-105">Code in Event Handler Executes Twice for Every Call</span></span>  
  
-   <span data-ttu-id="de38c-106">継承されたイベント ハンドラーが含めることはできません、[処理](../../../../visual-basic/language-reference/statements/handles-clause.md)句。</span><span class="sxs-lookup"><span data-stu-id="de38c-106">An inherited event handler must not include a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span> <span data-ttu-id="de38c-107">基本クラスのメソッドは既に、イベントに関連付けられたが発生します。</span><span class="sxs-lookup"><span data-stu-id="de38c-107">The method in the base class is already associated with the event and will fire accordingly.</span></span> <span data-ttu-id="de38c-108">削除、`Handles`句継承されたメソッドから。</span><span class="sxs-lookup"><span data-stu-id="de38c-108">Remove the `Handles` clause from the inherited method.</span></span>  
  
     [!code-vb[VbVbalrEvents#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#32)]  
  
-   <span data-ttu-id="de38c-109">継承されたメソッドがあるない場合、`Handles`キーワード、コードに追加が含まれていないことを確認します[AddHandler ステートメント](../../../../visual-basic/language-reference/statements/addhandler-statement.md)または他のメソッドを同じイベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="de38c-109">If the inherited method does not have a `Handles` keyword, verify that your code does not contain an extra [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) or any additional methods that handle the same event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de38c-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="de38c-110">See also</span></span>
- [<span data-ttu-id="de38c-111">イベント</span><span class="sxs-lookup"><span data-stu-id="de38c-111">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
