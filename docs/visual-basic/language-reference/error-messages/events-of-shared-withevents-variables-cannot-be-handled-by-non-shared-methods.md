---
title: 共有 WithEvents 変数のイベントを、非共有メソッドで処理できません。
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: 2b32043898986b3e3e68fab18c5f907843d7691c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803268"
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a><span data-ttu-id="37c77-102">共有 WithEvents 変数のイベントを、非共有メソッドで処理できません。</span><span class="sxs-lookup"><span data-stu-id="37c77-102">Events of shared WithEvents variables cannot be handled by non-shared methods</span></span>
<span data-ttu-id="37c77-103">宣言された変数、`Shared`修飾子は、共有変数。</span><span class="sxs-lookup"><span data-stu-id="37c77-103">A variable declared with the `Shared` modifier is a shared variable.</span></span> <span data-ttu-id="37c77-104">共有変数は、1 つだけの記憶域の場所を識別します。</span><span class="sxs-lookup"><span data-stu-id="37c77-104">A shared variable identifies exactly one storage location.</span></span> <span data-ttu-id="37c77-105">宣言された変数、`WithEvents`修飾子は、変数が属する型が変数で発生させるイベントのセットを処理することをアサートします。</span><span class="sxs-lookup"><span data-stu-id="37c77-105">A variable declared with the `WithEvents` modifier asserts that the type to which the variable belongs handles the set of events the variable raises.</span></span> <span data-ttu-id="37c77-106">プロパティがによって作成された変数に値が割り当てられると、`WithEvents`宣言は、既存のイベント ハンドラーでアンフックし、を使用して、新しいイベント ハンドラーをフック、`Add`メソッド。</span><span class="sxs-lookup"><span data-stu-id="37c77-106">When a value is assigned to the variable, the property created by the `WithEvents` declaration unhooks any existing event handler and hooks up the new event handler via the `Add` method.</span></span>  
  
 <span data-ttu-id="37c77-107">**エラー ID:** BC30594</span><span class="sxs-lookup"><span data-stu-id="37c77-107">**Error ID:** BC30594</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="37c77-108">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="37c77-108">To correct this error</span></span>  
  
-   <span data-ttu-id="37c77-109">イベント ハンドラーを宣言`Shared`します。</span><span class="sxs-lookup"><span data-stu-id="37c77-109">Declare your event handler `Shared`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37c77-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="37c77-110">See also</span></span>

- [<span data-ttu-id="37c77-111">Shared</span><span class="sxs-lookup"><span data-stu-id="37c77-111">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="37c77-112">WithEvents</span><span class="sxs-lookup"><span data-stu-id="37c77-112">WithEvents</span></span>](../../../visual-basic/language-reference/modifiers/withevents.md)
