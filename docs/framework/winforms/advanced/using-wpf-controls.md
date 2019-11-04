---
title: WPF コントロールの使用
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: e9883e9d31fc9e3e2ec3ca06b4fc830bcdc338ae
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460697"
---
# <a name="use-wpf-controls-in-windows-forms-apps"></a><span data-ttu-id="2ef9b-102">Windows フォームアプリで WPF コントロールを使用する</span><span class="sxs-lookup"><span data-stu-id="2ef9b-102">Use WPF controls in Windows Forms apps</span></span>

<span data-ttu-id="2ef9b-103">Windows フォームベースのアプリケーションでは、Windows Presentation Foundation (WPF) コントロールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2ef9b-103">You can use Windows Presentation Foundation (WPF) controls in Windows Forms-based applications.</span></span> <span data-ttu-id="2ef9b-104">これらは2つの異なるビューテクノロジですが、円滑に相互運用されます。</span><span class="sxs-lookup"><span data-stu-id="2ef9b-104">Although these are two different view technologies, they interoperate smoothly.</span></span>

<span data-ttu-id="2ef9b-105">Visual Studio の Windows フォームデザイナーには、Windows Presentation Foundation コントロールをホストするためのビジュアルデザイン環境が用意されています。</span><span class="sxs-lookup"><span data-stu-id="2ef9b-105">The Windows Forms Designer in Visual Studio provides a visual design environment for hosting Windows Presentation Foundation controls.</span></span> <span data-ttu-id="2ef9b-106">WPF コントロールは、<xref:System.Windows.Forms.Integration.ElementHost>という名前の特殊な Windows フォームコントロールによってホストされます。</span><span class="sxs-lookup"><span data-stu-id="2ef9b-106">A WPF control is hosted by a special Windows Forms control that's named <xref:System.Windows.Forms.Integration.ElementHost>.</span></span> <span data-ttu-id="2ef9b-107">このコントロールにより、WPF コントロールはフォームのレイアウトに参加し、キーボードおよびマウスメッセージを受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="2ef9b-107">This control enables the WPF control to participate in the form's layout and to receive keyboard and mouse messages.</span></span> <span data-ttu-id="2ef9b-108">デザイン時には、Windows フォームコントロールの場合と同じように <xref:System.Windows.Forms.Integration.ElementHost> コントロールを配置できます。</span><span class="sxs-lookup"><span data-stu-id="2ef9b-108">At design time, you can arrange the <xref:System.Windows.Forms.Integration.ElementHost> control just as you would any Windows Forms control.</span></span>

<span data-ttu-id="2ef9b-109">WPF ベースのアプリケーションでは、Windows フォームコントロールを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="2ef9b-109">You can also use Windows Forms controls in WPF-based applications.</span></span> <span data-ttu-id="2ef9b-110">詳細については、「 [Visual Studio での XAML のデザイン](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ef9b-110">For more information, see [Design XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).</span></span>

## <a name="see-also"></a><span data-ttu-id="2ef9b-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ef9b-111">See also</span></span>

- [<span data-ttu-id="2ef9b-112">WPF と Windows フォームの相互運用</span><span class="sxs-lookup"><span data-stu-id="2ef9b-112">WPF and Windows Forms interoperation</span></span>](../../wpf/advanced/wpf-and-windows-forms-interoperation.md)
