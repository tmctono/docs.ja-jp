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
ms.openlocfilehash: fd2ef1c25233cc1eaad6bcde68923688393b471d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345108"
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a><span data-ttu-id="f3a20-102">Visual Basic での継承されたイベント ハンドラーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f3a20-102">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>
<span data-ttu-id="f3a20-103">このトピックでは、継承されたコンポーネントのイベントハンドラーで発生する一般的な問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="f3a20-103">This topic lists common issues that arise with event handlers in inherited components.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="f3a20-104">手順</span><span class="sxs-lookup"><span data-stu-id="f3a20-104">Procedures</span></span>  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a><span data-ttu-id="f3a20-105">イベントハンドラーのコードは、すべての呼び出しに対して2回実行されます。</span><span class="sxs-lookup"><span data-stu-id="f3a20-105">Code in Event Handler Executes Twice for Every Call</span></span>  
  
- <span data-ttu-id="f3a20-106">継承されたイベントハンドラーに[Handles](../../../../visual-basic/language-reference/statements/handles-clause.md)句を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="f3a20-106">An inherited event handler must not include a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span> <span data-ttu-id="f3a20-107">基底クラスのメソッドは既にイベントに関連付けられており、それに応じて起動されます。</span><span class="sxs-lookup"><span data-stu-id="f3a20-107">The method in the base class is already associated with the event and will fire accordingly.</span></span> <span data-ttu-id="f3a20-108">継承されたメソッドから `Handles` 句を削除します。</span><span class="sxs-lookup"><span data-stu-id="f3a20-108">Remove the `Handles` clause from the inherited method.</span></span>  
  
     [!code-vb[VbVbalrEvents#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#32)]  
  
- <span data-ttu-id="f3a20-109">継承されたメソッドに `Handles` キーワードがない場合は、コードに追加の[AddHandler ステートメント](../../../../visual-basic/language-reference/statements/addhandler-statement.md)、または同じイベントを処理する追加のメソッドが含まれていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f3a20-109">If the inherited method does not have a `Handles` keyword, verify that your code does not contain an extra [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) or any additional methods that handle the same event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3a20-110">参照</span><span class="sxs-lookup"><span data-stu-id="f3a20-110">See also</span></span>

- [<span data-ttu-id="f3a20-111">イベント</span><span class="sxs-lookup"><span data-stu-id="f3a20-111">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
