---
title: プロパティ変更イベント
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- properties [Windows Forms], changes
ms.assetid: 268039ec-5aaa-4d76-b902-acccb036c850
ms.openlocfilehash: 0ff5b3874d9de169f4a9f1040d601173af352c06
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703232"
---
# <a name="property-changed-events"></a><span data-ttu-id="f906e-102">プロパティ変更イベント</span><span class="sxs-lookup"><span data-stu-id="f906e-102">Property-Changed Events</span></span>
<span data-ttu-id="f906e-103">という名前のプロパティのときに通知を送信する、制御したいかどうか*PropertyName*という名前のイベントの定義の変更、 *PropertyName* `Changed`という名前のメソッドと`On` *PropertyName* `Changed`イベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="f906e-103">If you want your control to send notifications when a property named *PropertyName* changes, define an event named *PropertyName*`Changed` and a method named `On`*PropertyName*`Changed` that raises the event.</span></span> <span data-ttu-id="f906e-104">Windows フォームでの名前付け規則では、単語を追加*Changed*プロパティの名前にします。</span><span class="sxs-lookup"><span data-stu-id="f906e-104">The naming convention in Windows Forms is to append the word *Changed* to the name of the property.</span></span> <span data-ttu-id="f906e-105">プロパティ変更イベントに関連付けられているイベントのデリゲート型は<xref:System.EventHandler>、イベントのデータ型は、<xref:System.EventArgs>します。</span><span class="sxs-lookup"><span data-stu-id="f906e-105">The associated event delegate type for property-changed events is <xref:System.EventHandler>, and the event data type is <xref:System.EventArgs>.</span></span> <span data-ttu-id="f906e-106">基本クラス<xref:System.Windows.Forms.Control>など多くのプロパティ変更イベントを定義<xref:System.Windows.Forms.Control.BackColorChanged>、 <xref:System.Windows.Forms.Control.BackgroundImageChanged>、 <xref:System.Windows.Forms.Control.FontChanged>、 <xref:System.Windows.Forms.Control.LocationChanged>、およびその他。</span><span class="sxs-lookup"><span data-stu-id="f906e-106">The base class <xref:System.Windows.Forms.Control> defines many property-changed events, such as <xref:System.Windows.Forms.Control.BackColorChanged>, <xref:System.Windows.Forms.Control.BackgroundImageChanged>, <xref:System.Windows.Forms.Control.FontChanged>, <xref:System.Windows.Forms.Control.LocationChanged>, and others.</span></span> <span data-ttu-id="f906e-107">イベントに関する背景情報は、次を参照してください。[イベント](../../../standard/events/index.md)と[Windows フォーム コントロールのイベント](events-in-windows-forms-controls.md)します。</span><span class="sxs-lookup"><span data-stu-id="f906e-107">For background information about events, see [Events](../../../standard/events/index.md) and [Events in Windows Forms Controls](events-in-windows-forms-controls.md).</span></span>  
  
 <span data-ttu-id="f906e-108">プロパティ変更イベントは、変更に応答するイベント ハンドラーをアタッチするコントロールのコンシューマーができるため便利です。</span><span class="sxs-lookup"><span data-stu-id="f906e-108">Property-changed events are useful because they allow consumers of a control to attach event handlers that respond to the change.</span></span> <span data-ttu-id="f906e-109">コントロールを生成するプロパティ変更イベントに応答する場合は、オーバーライド、対応する`On` *PropertyName* `Changed`メソッド、イベントにデリゲートをアタッチする代わりにします。</span><span class="sxs-lookup"><span data-stu-id="f906e-109">If your control needs to respond to a property-changed event that it raises, override the corresponding `On`*PropertyName*`Changed` method instead of attaching a delegate to the event.</span></span> <span data-ttu-id="f906e-110">その他のプロパティを更新するか、その描画サーフェイスの一部またはすべてを再描画、コントロールは通常、プロパティ変更イベントに応答します。</span><span class="sxs-lookup"><span data-stu-id="f906e-110">A control typically responds to a property-changed event by updating other properties or by redrawing some or all of its drawing surface.</span></span>  
  
 <span data-ttu-id="f906e-111">次の例は、どのように`FlashTrackBar`カスタム コントロールの応答から継承したプロパティ変更イベントの一部<xref:System.Windows.Forms.Control>します。</span><span class="sxs-lookup"><span data-stu-id="f906e-111">The following example shows how the `FlashTrackBar` custom control responds to some of the property-changed events that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="f906e-112">完全なサンプルでは、「[方法。進行状況を示す Windows フォーム コントロールを作成する](how-to-create-a-windows-forms-control-that-shows-progress.md)します。</span><span class="sxs-lookup"><span data-stu-id="f906e-112">For the complete sample, see [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#2)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="f906e-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="f906e-113">See also</span></span>
- [<span data-ttu-id="f906e-114">イベント</span><span class="sxs-lookup"><span data-stu-id="f906e-114">Events</span></span>](../../../standard/events/index.md)
- [<span data-ttu-id="f906e-115">Windows フォーム コントロールのイベント</span><span class="sxs-lookup"><span data-stu-id="f906e-115">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)
- [<span data-ttu-id="f906e-116">Windows フォーム コントロールのプロパティ</span><span class="sxs-lookup"><span data-stu-id="f906e-116">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
