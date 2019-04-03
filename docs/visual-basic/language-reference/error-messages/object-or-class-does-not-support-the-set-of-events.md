---
title: オブジェクトまたはクラスがこのイベント セットをサポートしていません。
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: 2e00bdd624b54e19f19b6dabf6681bbf89709e60
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822584"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a><span data-ttu-id="a6611-102">オブジェクトまたはクラスがこのイベント セットをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="a6611-102">Object or class does not support the set of events</span></span>
<span data-ttu-id="a6611-103">使用して、`WithEvents`変数でコンポーネントを指定した一連のイベントのイベント ソースとして使用できません。</span><span class="sxs-lookup"><span data-stu-id="a6611-103">You tried to use a `WithEvents` variable with a component that cannot work as an event source for the specified set of events.</span></span> <span data-ttu-id="a6611-104">オブジェクトのイベントをシンク、別のオブジェクトを作成したいなど`Implements`最初のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a6611-104">For example, you wanted to sink the events of an object, then create another object that `Implements` the first object.</span></span> <span data-ttu-id="a6611-105">実装されたオブジェクトからイベントをシンクする想像がこれとは限りません場合です。</span><span class="sxs-lookup"><span data-stu-id="a6611-105">Although you might think you could sink the events from the implemented object, this is not always the case.</span></span> <span data-ttu-id="a6611-106">`Implements` メソッドとプロパティのインターフェイスを実装するだけです。</span><span class="sxs-lookup"><span data-stu-id="a6611-106">`Implements` only implements an interface for methods and properties.</span></span> <span data-ttu-id="a6611-107">`WithEvents` プライベートはサポートされていません`UserControls`させる型情報が必要なため、`ObjectEvent`実行時に使用できません。</span><span class="sxs-lookup"><span data-stu-id="a6611-107">`WithEvents` is not supported for private `UserControls`, because the type info needed to raise the `ObjectEvent` is not available at run time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a6611-108">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="a6611-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="a6611-109">ソース イベントではないコンポーネントのイベントをシンクすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a6611-109">You cannot sink events for a component that does not source events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6611-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6611-110">See also</span></span>

- [<span data-ttu-id="a6611-111">WithEvents</span><span class="sxs-lookup"><span data-stu-id="a6611-111">WithEvents</span></span>](../../../visual-basic/language-reference/modifiers/withevents.md)
- [<span data-ttu-id="a6611-112">Implements ステートメント</span><span class="sxs-lookup"><span data-stu-id="a6611-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
