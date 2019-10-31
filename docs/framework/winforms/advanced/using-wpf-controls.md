---
title: WPF コントロールの使用
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 5e05ec7fc503565333a4d05662a4e40d8d1193af
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197468"
---
# <a name="use-wpf-controls-in-windows-forms-apps"></a><span data-ttu-id="049b0-102">Windows フォームアプリで WPF コントロールを使用する</span><span class="sxs-lookup"><span data-stu-id="049b0-102">Use WPF controls in Windows Forms apps</span></span>

<span data-ttu-id="049b0-103">Windows フォームベースのアプリケーションでは、Windows Presentation Foundation (WPF) コントロールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="049b0-103">You can use Windows Presentation Foundation (WPF) controls in Windows Forms-based applications.</span></span> <span data-ttu-id="049b0-104">これらは2つの異なるビューテクノロジですが、円滑に相互運用されます。</span><span class="sxs-lookup"><span data-stu-id="049b0-104">Although these are two different view technologies, they interoperate smoothly.</span></span>

<span data-ttu-id="049b0-105">Visual Studio の Windows フォームデザイナーには、Windows Presentation Foundation コントロールをホストするためのビジュアルデザイン環境が用意されています。</span><span class="sxs-lookup"><span data-stu-id="049b0-105">The Windows Forms Designer in Visual Studio provides a visual design environment for hosting Windows Presentation Foundation controls.</span></span> <span data-ttu-id="049b0-106">WPF コントロールは、<xref:System.Windows.Forms.Integration.ElementHost>という名前の特殊な Windows フォームコントロールによってホストされます。</span><span class="sxs-lookup"><span data-stu-id="049b0-106">A WPF control is hosted by a special Windows Forms control that's named <xref:System.Windows.Forms.Integration.ElementHost>.</span></span> <span data-ttu-id="049b0-107">このコントロールにより、WPF コントロールはフォームのレイアウトに参加し、キーボードおよびマウスメッセージを受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="049b0-107">This control enables the WPF control to participate in the form's layout and to receive keyboard and mouse messages.</span></span> <span data-ttu-id="049b0-108">デザイン時には、Windows フォームコントロールの場合と同じように <xref:System.Windows.Forms.Integration.ElementHost> コントロールを配置できます。</span><span class="sxs-lookup"><span data-stu-id="049b0-108">At design time, you can arrange the <xref:System.Windows.Forms.Integration.ElementHost> control just as you would any Windows Forms control.</span></span>

<span data-ttu-id="049b0-109">WPF ベースのアプリケーションでは、Windows フォームコントロールを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="049b0-109">You can also use Windows Forms controls in WPF-based applications.</span></span> <span data-ttu-id="049b0-110">詳細については、「 [Visual Studio での XAML のデザイン](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="049b0-110">For more information, see [Design XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).</span></span>

## <a name="see-also"></a><span data-ttu-id="049b0-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="049b0-111">See also</span></span>

- [<span data-ttu-id="049b0-112">WPF と Windows フォームの相互運用</span><span class="sxs-lookup"><span data-stu-id="049b0-112">WPF and Windows Forms interoperation</span></span>](../../wpf/advanced/wpf-and-windows-forms-interoperation.md)
