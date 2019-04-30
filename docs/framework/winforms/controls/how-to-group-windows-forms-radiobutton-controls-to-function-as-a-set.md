---
title: '方法: セットとして機能する Windows フォーム RadioButton コントロールをグループ化する'
ms.date: 03/30/2017
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
ms.openlocfilehash: 857e61bc89e072aebcf34793d7e8504ece3318c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941311"
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a><span data-ttu-id="91f00-102">方法: セットとして機能する Windows フォーム RadioButton コントロールをグループ化する</span><span class="sxs-lookup"><span data-stu-id="91f00-102">How to: Group Windows Forms RadioButton Controls to Function as a Set</span></span>
<span data-ttu-id="91f00-103">Windows フォーム<xref:System.Windows.Forms.RadioButton>間うち 1 つだけをプロシージャまたはオブジェクトに割り当てることが、2 つ以上の設定の選択をユーザーに付与するコントロールが設計されています。</span><span class="sxs-lookup"><span data-stu-id="91f00-103">Windows Forms <xref:System.Windows.Forms.RadioButton> controls are designed to give users a choice among two or more settings, of which only one can be assigned to a procedure or object.</span></span> <span data-ttu-id="91f00-104">たとえばのグループ<xref:System.Windows.Forms.RadioButton>コントロールは、注文の配送業者をパッケージの選択を表示可能性がありますが、通信事業者の 1 つだけ使用されます。</span><span class="sxs-lookup"><span data-stu-id="91f00-104">For example, a group of <xref:System.Windows.Forms.RadioButton> controls may display a choice of package carriers for an order, but only one of the carriers will be used.</span></span> <span data-ttu-id="91f00-105">そのため 1 つだけ<xref:System.Windows.Forms.RadioButton>一度に選択できる場合でも、機能グループの一部であります。</span><span class="sxs-lookup"><span data-stu-id="91f00-105">Therefore only one <xref:System.Windows.Forms.RadioButton> at a time can be selected, even if it is a part of a functional group.</span></span>  
  
 <span data-ttu-id="91f00-106">ラジオ ボタンをグループ化など、コンテナー内でそれらを描画することで、<xref:System.Windows.Forms.Panel>コントロール、<xref:System.Windows.Forms.GroupBox>コントロール、またはフォーム。</span><span class="sxs-lookup"><span data-stu-id="91f00-106">You group radio buttons by drawing them inside a container such as a <xref:System.Windows.Forms.Panel> control, a <xref:System.Windows.Forms.GroupBox> control, or a form.</span></span> <span data-ttu-id="91f00-107">フォームになる 1 つのグループに直接追加されるすべてのラジオ ボタン。</span><span class="sxs-lookup"><span data-stu-id="91f00-107">All radio buttons that are added directly to a form become one group.</span></span> <span data-ttu-id="91f00-108">個別のグループを追加するにはパネルまたはグループ ボックス内を配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91f00-108">To add separate groups, you must place them inside panels or group boxes.</span></span> <span data-ttu-id="91f00-109">パネルまたはグループ ボックスの詳細については、次を参照してください。 [Panel コントロールの概要](panel-control-overview-windows-forms.md)または[GroupBox コントロールの概要](groupbox-control-overview-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="91f00-109">For more information about panels or group boxes, see [Panel Control Overview](panel-control-overview-windows-forms.md) or [GroupBox Control Overview](groupbox-control-overview-windows-forms.md).</span></span>  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a><span data-ttu-id="91f00-110">その他のセットとは無関係に関数をセットとして RadioButton コントロールをグループ化</span><span class="sxs-lookup"><span data-stu-id="91f00-110">To group RadioButton controls as a set to function independently of other sets</span></span>  
  
1. <span data-ttu-id="91f00-111">ドラッグ、<xref:System.Windows.Forms.GroupBox>または<xref:System.Windows.Forms.Panel>コントロールから、 **Windows フォーム** タブで、**ツールボックス**フォーム上にします。</span><span class="sxs-lookup"><span data-stu-id="91f00-111">Drag a <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab on the **Toolbox** onto the form.</span></span>  
  
2. <span data-ttu-id="91f00-112">描画<xref:System.Windows.Forms.RadioButton>のコントロールに対して、<xref:System.Windows.Forms.GroupBox>または<xref:System.Windows.Forms.Panel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="91f00-112">Draw <xref:System.Windows.Forms.RadioButton> controls on the <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91f00-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="91f00-113">See also</span></span>

- <xref:System.Windows.Forms.RadioButton>
- [<span data-ttu-id="91f00-114">RadioButton コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="91f00-114">RadioButton Control Overview</span></span>](radiobutton-control-overview-windows-forms.md)
- [<span data-ttu-id="91f00-115">Panel コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="91f00-115">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="91f00-116">GroupBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="91f00-116">GroupBox Control Overview</span></span>](groupbox-control-overview-windows-forms.md)
- [<span data-ttu-id="91f00-117">CheckBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="91f00-117">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="91f00-118">RadioButton コントロール</span><span class="sxs-lookup"><span data-stu-id="91f00-118">RadioButton Control</span></span>](radiobutton-control-windows-forms.md)
