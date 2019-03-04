---
title: '方法: ディクショナリを使用してイベント インスタンスを格納する - C# プログラミング ガイド'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: f3b8e313bd0b1bd3973102caebb9bbc9da620ae6
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2019
ms.locfileid: "57203033"
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a><span data-ttu-id="f3d56-102">方法: ディクショナリを使用してイベント インスタンスを格納する (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="f3d56-102">How to: Use a Dictionary to Store Event Instances (C# Programming Guide)</span></span>
<span data-ttu-id="f3d56-103">多数のイベントを公開する場合に `accessor-declarations` を使用すると、各イベントにフィールドを割り当てる代わりにディクショナリを使用してイベント インスタンスを格納できます。</span><span class="sxs-lookup"><span data-stu-id="f3d56-103">One use for `accessor-declarations` is to expose many events without allocating a field for each event, but instead using a Dictionary to store the event instances.</span></span> <span data-ttu-id="f3d56-104">これが便利なのは、多数のイベントがあるものの、それらのほとんどが実装されそうもない場合だけです。</span><span class="sxs-lookup"><span data-stu-id="f3d56-104">This is only useful if you have many events, but you expect most of the events will not be implemented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3d56-105">例</span><span class="sxs-lookup"><span data-stu-id="f3d56-105">Example</span></span>  
 [!code-csharp[csProgGuideEvents#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="f3d56-106">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3d56-106">See also</span></span>

- [<span data-ttu-id="f3d56-107">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="f3d56-107">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="f3d56-108">イベント</span><span class="sxs-lookup"><span data-stu-id="f3d56-108">Events</span></span>](../../../csharp/programming-guide/events/index.md)
- [<span data-ttu-id="f3d56-109">デリゲート</span><span class="sxs-lookup"><span data-stu-id="f3d56-109">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
