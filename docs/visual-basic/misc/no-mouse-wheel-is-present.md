---
title: マウスのホイールが存在しません
ms.date: 07/20/2015
f1_keywords:
- vbrMouse_NoWheelIsPresent
ms.assetid: e924ffba-4af1-4247-9a6f-d19a03738f62
ms.openlocfilehash: a9b468d876945a177f3e326a7dc37e6c8a80285d
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91078841"
---
# <a name="no-mouse-wheel-is-present"></a><span data-ttu-id="76d83-102">マウスのホイールが存在しません</span><span class="sxs-lookup"><span data-stu-id="76d83-102">No mouse wheel is present</span></span>

<span data-ttu-id="76d83-103">`My.Computer.Mouse.WheelScrollLines` プロパティが呼び出されましたが、マウスにスクロール ホイールがありません。</span><span class="sxs-lookup"><span data-stu-id="76d83-103">The `My.Computer.Mouse.WheelScrollLines` property was called, but the mouse has no scroll wheel.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="76d83-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="76d83-104">To correct this error</span></span>  
  
- <span data-ttu-id="76d83-105">`My.Computer.Mouse.WheelExists` プロパティを呼び出す前に `My.Computer.Mouse.WheelScrollLines` プロパティを調べて、マウスにスクロール ホイールがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="76d83-105">Check the `My.Computer.Mouse.WheelExists` property to see if the mouse has a scroll wheel before calling the `My.Computer.Mouse.WheelScrollLines` property.</span></span>  
  
     <span data-ttu-id="76d83-106">- または -</span><span class="sxs-lookup"><span data-stu-id="76d83-106">-or-</span></span>  
  
- <span data-ttu-id="76d83-107">スクロール ホイールのあるマウスをコンピュータにインストールします。</span><span class="sxs-lookup"><span data-stu-id="76d83-107">Install a mouse with a scroll wheel on the computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76d83-108">こちらもご覧ください</span><span class="sxs-lookup"><span data-stu-id="76d83-108">See also</span></span>

- [<span data-ttu-id="76d83-109">マイ. My.computer.mouse.wheelscrolllines</span><span class="sxs-lookup"><span data-stu-id="76d83-109">My.Computer.Mouse.WheelScrollLines</span></span>](xref:Microsoft.VisualBasic.Devices.Mouse.WheelScrollLines)
- [<span data-ttu-id="76d83-110">マイ. My.computer.mouse.wheelexists</span><span class="sxs-lookup"><span data-stu-id="76d83-110">My.Computer.Mouse.WheelExists</span></span>](xref:Microsoft.VisualBasic.Devices.Mouse.WheelExists)
- [<span data-ttu-id="76d83-111">.NET での例外の処理とスロー</span><span class="sxs-lookup"><span data-stu-id="76d83-111">Handling and throwing exceptions in .NET</span></span>](../../standard/exceptions/index.md)
