---
title: マウスのホイールが存在しません
ms.date: 07/20/2015
f1_keywords:
- vbrMouse_NoWheelIsPresent
ms.assetid: e924ffba-4af1-4247-9a6f-d19a03738f62
ms.openlocfilehash: 0273b9838ef77c83818a8af01613a58662f37a93
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64610736"
---
# <a name="no-mouse-wheel-is-present"></a><span data-ttu-id="38263-102">マウスのホイールが存在しません</span><span class="sxs-lookup"><span data-stu-id="38263-102">No mouse wheel is present</span></span>
<span data-ttu-id="38263-103">`My.Computer.Mouse.WheelScrollLines` プロパティが呼び出されましたが、マウスにスクロール ホイールがありません。</span><span class="sxs-lookup"><span data-stu-id="38263-103">The `My.Computer.Mouse.WheelScrollLines` property was called, but the mouse has no scroll wheel.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="38263-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="38263-104">To correct this error</span></span>  
  
- <span data-ttu-id="38263-105">`My.Computer.Mouse.WheelExists` プロパティを呼び出す前に `My.Computer.Mouse.WheelScrollLines` プロパティを調べて、マウスにスクロール ホイールがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="38263-105">Check the `My.Computer.Mouse.WheelExists` property to see if the mouse has a scroll wheel before calling the `My.Computer.Mouse.WheelScrollLines` property.</span></span>  
  
     <span data-ttu-id="38263-106">- または -</span><span class="sxs-lookup"><span data-stu-id="38263-106">-or-</span></span>  
  
- <span data-ttu-id="38263-107">スクロール ホイールのあるマウスをコンピュータにインストールします。</span><span class="sxs-lookup"><span data-stu-id="38263-107">Install a mouse with a scroll wheel on the computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38263-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="38263-108">See also</span></span>

- [<span data-ttu-id="38263-109">My.Computer.Mouse.WheelScrollLines</span><span class="sxs-lookup"><span data-stu-id="38263-109">My.Computer.Mouse.WheelScrollLines</span></span>](xref:Microsoft.VisualBasic.Devices.Mouse.WheelScrollLines)
- [<span data-ttu-id="38263-110">My.Computer.Mouse.WheelExists</span><span class="sxs-lookup"><span data-stu-id="38263-110">My.Computer.Mouse.WheelExists</span></span>](xref:Microsoft.VisualBasic.Devices.Mouse.WheelExists)
- [<span data-ttu-id="38263-111">.NET での例外の処理とスロー</span><span class="sxs-lookup"><span data-stu-id="38263-111">Handling and throwing exceptions in .NET</span></span>](../../standard/exceptions/index.md)
