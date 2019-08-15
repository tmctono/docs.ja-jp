---
title: '方法: デザイナーを使用して Windows フォーム Panel コントロールでコントロールをグループ化する'
ms.date: 03/30/2017
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
ms.openlocfilehash: cadfa715b140c63b216ec0ca2e6d6a6589ae3458
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040388"
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a><span data-ttu-id="0b426-102">方法: デザイナーを使用して Windows フォーム Panel コントロールでコントロールをグループ化する</span><span class="sxs-lookup"><span data-stu-id="0b426-102">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>
<span data-ttu-id="0b426-103">Windows フォーム<xref:System.Windows.Forms.Panel>コントロールは、他のコントロールをグループ化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0b426-103">Windows Forms <xref:System.Windows.Forms.Panel> controls are used to group other controls.</span></span> <span data-ttu-id="0b426-104">コントロールをグループ化する理由は3つあります。</span><span class="sxs-lookup"><span data-stu-id="0b426-104">There are three reasons to group controls.</span></span> <span data-ttu-id="0b426-105">1つは、明確なユーザーインターフェイスに関連するフォーム要素を視覚的にグループ化することです。また、オプションボタンのプログラムによるグループ化もあります。次に例を示します。最後に、デザイン時にコントロールを1つの単位として移動します。</span><span class="sxs-lookup"><span data-stu-id="0b426-105">One is visual grouping of related form elements for a clear user interface; another is programmatic grouping, of radio buttons for example; the last is for moving the controls as a unit at design time.</span></span>

## <a name="to-create-a-group-of-controls"></a><span data-ttu-id="0b426-106">コントロールのグループを作成するには</span><span class="sxs-lookup"><span data-stu-id="0b426-106">To create a group of controls</span></span>

1. <span data-ttu-id="0b426-107">ツールボックス<xref:System.Windows.Forms.Panel>の **[Windows フォーム]** タブからフォームにコントロールをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="0b426-107">Drag a <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab of the Toolbox onto a form.</span></span>

2. <span data-ttu-id="0b426-108">パネルに他のコントロールを追加し、各コントロールをパネル内に描画します。</span><span class="sxs-lookup"><span data-stu-id="0b426-108">Add other controls to the panel, drawing each inside the panel.</span></span>

     <span data-ttu-id="0b426-109">パネルに表示する既存のコントロールがある場合は、すべてのコントロールを選択し、クリップボードに切り取って、 <xref:System.Windows.Forms.Panel>コントロールを選択して、パネルに貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="0b426-109">If you have existing controls that you want to enclose in a panel, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.Panel> control, and then paste them into the panel.</span></span> <span data-ttu-id="0b426-110">また、パネルにドラッグすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0b426-110">You can also drag them into the panel.</span></span>

3. <span data-ttu-id="0b426-111">Optionalパネルに罫線を追加する場合は、その<xref:System.Windows.Forms.BorderStyle>プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="0b426-111">(Optional) If you want to add a border to a panel, set its <xref:System.Windows.Forms.BorderStyle> property.</span></span> <span data-ttu-id="0b426-112"><xref:System.Windows.Forms.BorderStyle.Fixed3D> 、<xref:System.Windows.Forms.BorderStyle.FixedSingle>、および<xref:System.Windows.Forms.BorderStyle.None>の3つの選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="0b426-112">There are three choices: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, and <xref:System.Windows.Forms.BorderStyle.None>.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b426-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="0b426-113">See also</span></span>

- [<span data-ttu-id="0b426-114">Panel コントロール</span><span class="sxs-lookup"><span data-stu-id="0b426-114">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="0b426-115">Panel コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="0b426-115">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="0b426-116">方法: パネルの背景を設定する</span><span class="sxs-lookup"><span data-stu-id="0b426-116">How to: Set the Background of a Panel</span></span>](how-to-set-the-background-of-a-windows-forms-panel.md)
