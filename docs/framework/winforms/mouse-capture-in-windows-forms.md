---
title: マウス キャプチャ
ms.date: 03/30/2017
helpviewer_keywords:
- mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
ms.openlocfilehash: 10583f074831b16dce3c713b4ac9a76c7005c9f5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741023"
---
# <a name="mouse-capture-in-windows-forms"></a><span data-ttu-id="3d02c-102">Windows フォームにおけるマウスのキャプチャ</span><span class="sxs-lookup"><span data-stu-id="3d02c-102">Mouse Capture in Windows Forms</span></span>
<span data-ttu-id="3d02c-103">*マウスキャプチャ*は、コントロールがすべてのマウス入力のコマンドを受け取るときに参照します。</span><span class="sxs-lookup"><span data-stu-id="3d02c-103">*Mouse capture* refers to when a control takes command of all mouse input.</span></span> <span data-ttu-id="3d02c-104">コントロールは、マウスをキャプチャしたときに、ポインターが境界内にあるかどうかにかかわらず、マウス入力を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="3d02c-104">When a control has captured the mouse, it receives mouse input whether or not the pointer is within its borders.</span></span>  
  
## <a name="setting-mouse-capture"></a><span data-ttu-id="3d02c-105">マウスキャプチャの設定</span><span class="sxs-lookup"><span data-stu-id="3d02c-105">Setting Mouse Capture</span></span>  
 <span data-ttu-id="3d02c-106">Windows フォーム、ユーザーがコントロール上でマウスボタンを押したときにコントロールによってマウスがキャプチャされ、ユーザーがマウスボタンを離したときにコントロールによってマウスが解放されます。</span><span class="sxs-lookup"><span data-stu-id="3d02c-106">In Windows Forms the mouse is captured by the control when the user presses a mouse button on a control, and the mouse is released by the control when the user releases the mouse button.</span></span>  
  
 <span data-ttu-id="3d02c-107"><xref:System.Windows.Forms.Control> クラスの <xref:System.Windows.Forms.Control.Capture%2A> プロパティは、コントロールがマウスをキャプチャしたかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="3d02c-107">The <xref:System.Windows.Forms.Control.Capture%2A> property of the <xref:System.Windows.Forms.Control> class specifies whether a control has captured the mouse.</span></span> <span data-ttu-id="3d02c-108">コントロールがマウスキャプチャを失ったタイミングを判断するには、<xref:System.Windows.Forms.Control.MouseCaptureChanged> イベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="3d02c-108">To determine when a control loses mouse capture, handle the <xref:System.Windows.Forms.Control.MouseCaptureChanged> event.</span></span>  
  
 <span data-ttu-id="3d02c-109">前面のウィンドウだけがマウスをキャプチャできます。</span><span class="sxs-lookup"><span data-stu-id="3d02c-109">Only the foreground window can capture the mouse.</span></span> <span data-ttu-id="3d02c-110">バックグラウンドウィンドウがマウスをキャプチャしようとすると、ウィンドウは、マウスポインターがウィンドウの表示部分内にあるときに発生するマウスイベントに対してのみメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="3d02c-110">When a background window attempts to capture the mouse, the window receives messages only for mouse events that occur when the mouse pointer is within the visible portion of the window.</span></span> <span data-ttu-id="3d02c-111">また、前景ウィンドウがマウスをキャプチャした場合でも、ユーザーは別のウィンドウをクリックして、前面に表示することができます。</span><span class="sxs-lookup"><span data-stu-id="3d02c-111">Also, even if the foreground window has captured the mouse, the user can still click another window, bringing it to the foreground.</span></span> <span data-ttu-id="3d02c-112">マウスがキャプチャされると、ショートカットキーは機能しません。</span><span class="sxs-lookup"><span data-stu-id="3d02c-112">When the mouse is captured, shortcut keys do not work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d02c-113">参照</span><span class="sxs-lookup"><span data-stu-id="3d02c-113">See also</span></span>

- [<span data-ttu-id="3d02c-114">Windows フォーム アプリケーションにおけるマウス入力</span><span class="sxs-lookup"><span data-stu-id="3d02c-114">Mouse Input in a Windows Forms Application</span></span>](mouse-input-in-a-windows-forms-application.md)
