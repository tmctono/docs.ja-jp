---
title: '方法: コントロールに透明な背景を指定する'
ms.date: 03/30/2017
helpviewer_keywords:
- transparent backgrounds [Windows Forms], custom controls
- custom controls [Windows Forms], transparent background
- transparency [Windows Forms], Windows Forms custom controls
ms.assetid: 32433e63-f4e9-4305-9857-6de3edeb944a
ms.openlocfilehash: a82807ea3873b2217d1f05f6c720c599ea79abdd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966639"
---
# <a name="how-to-give-your-control-a-transparent-background"></a><span data-ttu-id="5df7d-102">方法: コントロールに透明な背景を指定する</span><span class="sxs-lookup"><span data-stu-id="5df7d-102">How to: Give Your Control a Transparent Background</span></span>
<span data-ttu-id="5df7d-103">.NET Framework の従来のバージョンでは、あらかじめフォームのコンストラクターに <xref:System.Windows.Forms.Control.SetStyle%2A> メソッドを設定しておかないと、透明な背景色を設定できませんでした。</span><span class="sxs-lookup"><span data-stu-id="5df7d-103">In earlier versions of the .NET Framework, controls didn't support setting transparent backcolors without first setting the <xref:System.Windows.Forms.Control.SetStyle%2A> method in the forms's constructor.</span></span> <span data-ttu-id="5df7d-104">フレームワークの現在のバージョンでは、ほとんどのコントロールの背景色を、設計時に <xref:System.Drawing.Color.Transparent%2A> [プロパティ] **ウィンドウで、またはフォームのコンストラクターのコードで、** に設定できます。</span><span class="sxs-lookup"><span data-stu-id="5df7d-104">In the current framework version, the backcolor for most controls can be set to <xref:System.Drawing.Color.Transparent%2A> in the **Properties** window at design time, or in code in the form's constructor.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5df7d-105">Windows フォーム コントロールは、完全な透過性はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="5df7d-105">Windows Forms controls do not support true transparency.</span></span> <span data-ttu-id="5df7d-106">透明な Windows フォーム コントロールの背景は、その親によって描画されます。</span><span class="sxs-lookup"><span data-stu-id="5df7d-106">The background of a transparent Windows Forms control is painted by its parent.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5df7d-107"><xref:System.Windows.Controls.Button> プロパティが <xref:System.Windows.Forms.ButtonBase.BackColor%2A> に設定されている場合でも、 <xref:System.Drawing.Color.Transparent%2A>コントロールは透明な背景をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="5df7d-107">The <xref:System.Windows.Controls.Button> control doesn't support a transparent backcolor even when the <xref:System.Windows.Forms.ButtonBase.BackColor%2A> property is set to <xref:System.Drawing.Color.Transparent%2A>.</span></span>  
  
### <a name="to-give-your-control-a-transparent-backcolor"></a><span data-ttu-id="5df7d-108">コントロールに透明な背景を設定するには</span><span class="sxs-lookup"><span data-stu-id="5df7d-108">To give your control a transparent backcolor</span></span>  
  
- <span data-ttu-id="5df7d-109">[プロパティ] ウィンドウで <xref:System.Windows.Forms.ButtonBase.BackColor%2A> プロパティを選択し、 <xref:System.Drawing.Color.Transparent%2A>に設定します。</span><span class="sxs-lookup"><span data-stu-id="5df7d-109">In the Properties window, choose the <xref:System.Windows.Forms.ButtonBase.BackColor%2A> property and set it to <xref:System.Drawing.Color.Transparent%2A></span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5df7d-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="5df7d-110">See also</span></span>

- <xref:System.Drawing.Color.FromArgb%2A>
- [<span data-ttu-id="5df7d-111">.NET Framework を使用したカスタム Windows フォーム コントロールの開発</span><span class="sxs-lookup"><span data-stu-id="5df7d-111">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="5df7d-112">マネージド グラフィックス クラスの使用</span><span class="sxs-lookup"><span data-stu-id="5df7d-112">Using Managed Graphics Classes</span></span>](../advanced/using-managed-graphics-classes.md)
- [<span data-ttu-id="5df7d-113">方法: 不透明な直線と半透明な線を描画する</span><span class="sxs-lookup"><span data-stu-id="5df7d-113">How to: Draw Opaque and Semitransparent Lines</span></span>](../advanced/how-to-draw-opaque-and-semitransparent-lines.md)
