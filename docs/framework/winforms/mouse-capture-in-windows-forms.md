---
title: Windows フォームにおけるマウスのキャプチャ
ms.date: 03/30/2017
helpviewer_keywords:
- mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
ms.openlocfilehash: afb58df99ea30f5e7e6ab5b9156af195d273c44d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57712709"
---
# <a name="mouse-capture-in-windows-forms"></a><span data-ttu-id="4a227-102">Windows フォームにおけるマウスのキャプチャ</span><span class="sxs-lookup"><span data-stu-id="4a227-102">Mouse Capture in Windows Forms</span></span>
<span data-ttu-id="4a227-103">*マウスのキャプチャ*コントロールのすべてのマウス入力コマンドの実行時を参照します。</span><span class="sxs-lookup"><span data-stu-id="4a227-103">*Mouse capture* refers to when a control takes command of all mouse input.</span></span> <span data-ttu-id="4a227-104">コントロールは、マウスをキャプチャしたら、マウス ポインターが境界内にあるかどうかを示すマウス入力を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="4a227-104">When a control has captured the mouse, it receives mouse input whether or not the pointer is within its borders.</span></span>  
  
## <a name="setting-mouse-capture"></a><span data-ttu-id="4a227-105">マウスのキャプチャの設定</span><span class="sxs-lookup"><span data-stu-id="4a227-105">Setting Mouse Capture</span></span>  
 <span data-ttu-id="4a227-106">Windows フォームで、ユーザーがコントロールのマウス ボタンを押すし、ユーザーがマウス ボタンを離したときに、マウスがコントロールによってリリースされたときに、マウスはコントロールによってキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="4a227-106">In Windows Forms the mouse is captured by the control when the user presses a mouse button on a control, and the mouse is released by the control when the user releases the mouse button.</span></span>  
  
 <span data-ttu-id="4a227-107"><xref:System.Windows.Forms.Control.Capture%2A>のプロパティ、<xref:System.Windows.Forms.Control>クラスは、コントロールがマウスをキャプチャしたかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a227-107">The <xref:System.Windows.Forms.Control.Capture%2A> property of the <xref:System.Windows.Forms.Control> class specifies whether a control has captured the mouse.</span></span> <span data-ttu-id="4a227-108">コントロールがマウス キャプチャを失ったときにするには、処理、<xref:System.Windows.Forms.Control.MouseCaptureChanged>イベント。</span><span class="sxs-lookup"><span data-stu-id="4a227-108">To determine when a control loses mouse capture, handle the <xref:System.Windows.Forms.Control.MouseCaptureChanged> event.</span></span>  
  
 <span data-ttu-id="4a227-109">前面のウィンドウには、マウスをキャプチャできます。</span><span class="sxs-lookup"><span data-stu-id="4a227-109">Only the foreground window can capture the mouse.</span></span> <span data-ttu-id="4a227-110">背景ウィンドウがマウスをキャプチャしようとすると、ウィンドウは、ウィンドウの表示部分内にマウス ポインターがときに発生するマウス イベントにのみメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="4a227-110">When a background window attempts to capture the mouse, the window receives messages only for mouse events that occur when the mouse pointer is within the visible portion of the window.</span></span> <span data-ttu-id="4a227-111">また、前面のウィンドウがマウスをキャプチャした場合でも、ユーザー クリックできます別のウィンドウへの前景色。</span><span class="sxs-lookup"><span data-stu-id="4a227-111">Also, even if the foreground window has captured the mouse, the user can still click another window, bringing it to the foreground.</span></span> <span data-ttu-id="4a227-112">マウスをキャプチャしたら、ショートカット キーは機能しません。</span><span class="sxs-lookup"><span data-stu-id="4a227-112">When the mouse is captured, shortcut keys do not work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a227-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a227-113">See also</span></span>
- [<span data-ttu-id="4a227-114">Windows フォーム アプリケーションにおけるマウス入力</span><span class="sxs-lookup"><span data-stu-id="4a227-114">Mouse Input in a Windows Forms Application</span></span>](mouse-input-in-a-windows-forms-application.md)
