---
title: Set RadioButton コントロールをセットとして機能するようにグループ化する
ms.date: 03/30/2017
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
ms.openlocfilehash: c4b37c84bf0f93837b91c743c7681d39fd83a659
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732953"
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a><span data-ttu-id="00ac2-102">方法 : セットとして機能する Windows フォーム RadioButton コントロールをグループ化する</span><span class="sxs-lookup"><span data-stu-id="00ac2-102">How to: Group Windows Forms RadioButton Controls to Function as a Set</span></span>
<span data-ttu-id="00ac2-103">Windows フォーム <xref:System.Windows.Forms.RadioButton> コントロールは、1つのプロシージャまたはオブジェクトに割り当てることができる2つ以上の設定の中からユーザーを選択できるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="00ac2-103">Windows Forms <xref:System.Windows.Forms.RadioButton> controls are designed to give users a choice among two or more settings, of which only one can be assigned to a procedure or object.</span></span> <span data-ttu-id="00ac2-104">たとえば、<xref:System.Windows.Forms.RadioButton> コントロールのグループは、注文に対して選択したパッケージキャリアを表示できますが、使用されるのは1つの配送業者だけです。</span><span class="sxs-lookup"><span data-stu-id="00ac2-104">For example, a group of <xref:System.Windows.Forms.RadioButton> controls may display a choice of package carriers for an order, but only one of the carriers will be used.</span></span> <span data-ttu-id="00ac2-105">したがって、機能グループの一部であっても、一度に1つの <xref:System.Windows.Forms.RadioButton> のみ選択できます。</span><span class="sxs-lookup"><span data-stu-id="00ac2-105">Therefore only one <xref:System.Windows.Forms.RadioButton> at a time can be selected, even if it is a part of a functional group.</span></span>  
  
 <span data-ttu-id="00ac2-106">オプションボタンをグループ化するには、<xref:System.Windows.Forms.Panel> コントロール、<xref:System.Windows.Forms.GroupBox> コントロール、フォームなどのコンテナー内に描画します。</span><span class="sxs-lookup"><span data-stu-id="00ac2-106">You group radio buttons by drawing them inside a container such as a <xref:System.Windows.Forms.Panel> control, a <xref:System.Windows.Forms.GroupBox> control, or a form.</span></span> <span data-ttu-id="00ac2-107">フォームに直接追加されたすべてのラジオボタンは、1つのグループになります。</span><span class="sxs-lookup"><span data-stu-id="00ac2-107">All radio buttons that are added directly to a form become one group.</span></span> <span data-ttu-id="00ac2-108">個別のグループを追加するには、パネルまたはグループボックス内に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00ac2-108">To add separate groups, you must place them inside panels or group boxes.</span></span> <span data-ttu-id="00ac2-109">パネルまたはグループボックスの詳細については、「 [Panel コントロールの概要](panel-control-overview-windows-forms.md)」または「 [GroupBox コントロールの概要](groupbox-control-overview-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00ac2-109">For more information about panels or group boxes, see [Panel Control Overview](panel-control-overview-windows-forms.md) or [GroupBox Control Overview](groupbox-control-overview-windows-forms.md).</span></span>  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a><span data-ttu-id="00ac2-110">RadioButton コントロールを他のセットとは独立して機能するようにグループ化するには</span><span class="sxs-lookup"><span data-stu-id="00ac2-110">To group RadioButton controls as a set to function independently of other sets</span></span>  
  
1. <span data-ttu-id="00ac2-111">**ツールボックス**の **[Windows フォーム]** タブから <xref:System.Windows.Forms.GroupBox> または <xref:System.Windows.Forms.Panel> コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="00ac2-111">Drag a <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab on the **Toolbox** onto the form.</span></span>  
  
2. <span data-ttu-id="00ac2-112"><xref:System.Windows.Forms.GroupBox> コントロールまたは <xref:System.Windows.Forms.Panel> コントロールに <xref:System.Windows.Forms.RadioButton> コントロールを描画します。</span><span class="sxs-lookup"><span data-stu-id="00ac2-112">Draw <xref:System.Windows.Forms.RadioButton> controls on the <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00ac2-113">参照</span><span class="sxs-lookup"><span data-stu-id="00ac2-113">See also</span></span>

- <xref:System.Windows.Forms.RadioButton>
- [<span data-ttu-id="00ac2-114">RadioButton コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="00ac2-114">RadioButton Control Overview</span></span>](radiobutton-control-overview-windows-forms.md)
- [<span data-ttu-id="00ac2-115">Panel コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="00ac2-115">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="00ac2-116">GroupBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="00ac2-116">GroupBox Control Overview</span></span>](groupbox-control-overview-windows-forms.md)
- [<span data-ttu-id="00ac2-117">CheckBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="00ac2-117">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="00ac2-118">RadioButton コントロール</span><span class="sxs-lookup"><span data-stu-id="00ac2-118">RadioButton Control</span></span>](radiobutton-control-windows-forms.md)
