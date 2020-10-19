---
title: オブジェクトまたはクラスがこのイベント セットをサポートしていません。
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: c5e8b8de3477147fc3174cdbee401c89753004ad
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159951"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a><span data-ttu-id="1e4fe-102">オブジェクトまたはクラスがこのイベント セットをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="1e4fe-102">Object or class does not support the set of events</span></span>

<span data-ttu-id="1e4fe-103">指定されたイベント セットのイベント ソースとして機能しないコンポーネントで、`WithEvents` 変数を使用しようとしました。</span><span class="sxs-lookup"><span data-stu-id="1e4fe-103">You tried to use a `WithEvents` variable with a component that cannot work as an event source for the specified set of events.</span></span> <span data-ttu-id="1e4fe-104">たとえば、オブジェクトのイベントをシンクしてから、最初のオブジェクトを `Implements` する別のオブジェクトを作成するとします。</span><span class="sxs-lookup"><span data-stu-id="1e4fe-104">For example, you wanted to sink the events of an object, then create another object that `Implements` the first object.</span></span> <span data-ttu-id="1e4fe-105">実装されたオブジェクトからイベントをシンクできると思うかもしれませんが、常にそうであるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="1e4fe-105">Although you might think you could sink the events from the implemented object, this is not always the case.</span></span> <span data-ttu-id="1e4fe-106">`Implements` は、メソッドとプロパティのインターフェイスのみを実装します。</span><span class="sxs-lookup"><span data-stu-id="1e4fe-106">`Implements` only implements an interface for methods and properties.</span></span> <span data-ttu-id="1e4fe-107">`WithEvents` は、`ObjectEvent` を発生させるために必要な型情報が実行時に使用できないため、非公開の `UserControls` ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1e4fe-107">`WithEvents` is not supported for private `UserControls`, because the type info needed to raise the `ObjectEvent` is not available at run time.</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="1e4fe-108">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="1e4fe-108">To correct this error</span></span>

- <span data-ttu-id="1e4fe-109">イベントを発生させないコンポーネントのイベントをシンクすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1e4fe-109">You cannot sink events for a component that does not source events.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e4fe-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="1e4fe-110">See also</span></span>

- [<span data-ttu-id="1e4fe-111">WithEvents</span><span class="sxs-lookup"><span data-stu-id="1e4fe-111">WithEvents</span></span>](../modifiers/withevents.md)
- [<span data-ttu-id="1e4fe-112">Implements ステートメント</span><span class="sxs-lookup"><span data-stu-id="1e4fe-112">Implements Statement</span></span>](../statements/implements-statement.md)
