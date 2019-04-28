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
ms.openlocfilehash: cabfd9e799288a332a0b2f96140f5f1cc328508b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755429"
---
# <a name="property-changed-events"></a><span data-ttu-id="637de-102">プロパティ変更イベント</span><span class="sxs-lookup"><span data-stu-id="637de-102">Property-Changed Events</span></span>
<span data-ttu-id="637de-103">という名前のプロパティのときに通知を送信する、制御したいかどうか*PropertyName*という名前のイベントの定義の変更、 *PropertyName* `Changed`という名前のメソッドと`On` *PropertyName* `Changed`イベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="637de-103">If you want your control to send notifications when a property named *PropertyName* changes, define an event named *PropertyName*`Changed` and a method named `On`*PropertyName*`Changed` that raises the event.</span></span> <span data-ttu-id="637de-104">Windows フォームでの名前付け規則では、単語を追加*Changed*プロパティの名前にします。</span><span class="sxs-lookup"><span data-stu-id="637de-104">The naming convention in Windows Forms is to append the word *Changed* to the name of the property.</span></span> <span data-ttu-id="637de-105">プロパティ変更イベントに関連付けられているイベントのデリゲート型は<xref:System.EventHandler>、イベントのデータ型は、<xref:System.EventArgs>します。</span><span class="sxs-lookup"><span data-stu-id="637de-105">The associated event delegate type for property-changed events is <xref:System.EventHandler>, and the event data type is <xref:System.EventArgs>.</span></span> <span data-ttu-id="637de-106">基本クラス<xref:System.Windows.Forms.Control>など多くのプロパティ変更イベントを定義<xref:System.Windows.Forms.Control.BackColorChanged>、 <xref:System.Windows.Forms.Control.BackgroundImageChanged>、 <xref:System.Windows.Forms.Control.FontChanged>、 <xref:System.Windows.Forms.Control.LocationChanged>、およびその他。</span><span class="sxs-lookup"><span data-stu-id="637de-106">The base class <xref:System.Windows.Forms.Control> defines many property-changed events, such as <xref:System.Windows.Forms.Control.BackColorChanged>, <xref:System.Windows.Forms.Control.BackgroundImageChanged>, <xref:System.Windows.Forms.Control.FontChanged>, <xref:System.Windows.Forms.Control.LocationChanged>, and others.</span></span> <span data-ttu-id="637de-107">イベントに関する背景情報は、次を参照してください。[イベント](../../../standard/events/index.md)と[Windows フォーム コントロールのイベント](events-in-windows-forms-controls.md)します。</span><span class="sxs-lookup"><span data-stu-id="637de-107">For background information about events, see [Events](../../../standard/events/index.md) and [Events in Windows Forms Controls](events-in-windows-forms-controls.md).</span></span>  
  
 <span data-ttu-id="637de-108">プロパティ変更イベントは、変更に応答するイベント ハンドラーをアタッチするコントロールのコンシューマーができるため便利です。</span><span class="sxs-lookup"><span data-stu-id="637de-108">Property-changed events are useful because they allow consumers of a control to attach event handlers that respond to the change.</span></span> <span data-ttu-id="637de-109">コントロールを生成するプロパティ変更イベントに応答する場合は、オーバーライド、対応する`On` *PropertyName* `Changed`メソッド、イベントにデリゲートをアタッチする代わりにします。</span><span class="sxs-lookup"><span data-stu-id="637de-109">If your control needs to respond to a property-changed event that it raises, override the corresponding `On`*PropertyName*`Changed` method instead of attaching a delegate to the event.</span></span> <span data-ttu-id="637de-110">その他のプロパティを更新するか、その描画サーフェイスの一部またはすべてを再描画、コントロールは通常、プロパティ変更イベントに応答します。</span><span class="sxs-lookup"><span data-stu-id="637de-110">A control typically responds to a property-changed event by updating other properties or by redrawing some or all of its drawing surface.</span></span>  
  
 <span data-ttu-id="637de-111">次の例は、どのように`FlashTrackBar`カスタム コントロールの応答から継承したプロパティ変更イベントの一部<xref:System.Windows.Forms.Control>します。</span><span class="sxs-lookup"><span data-stu-id="637de-111">The following example shows how the `FlashTrackBar` custom control responds to some of the property-changed events that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="637de-112">完全なサンプルでは、「[方法。進行状況を示す Windows フォーム コントロールを作成する](how-to-create-a-windows-forms-control-that-shows-progress.md)します。</span><span class="sxs-lookup"><span data-stu-id="637de-112">For the complete sample, see [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#2)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="637de-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="637de-113">See also</span></span>

- [<span data-ttu-id="637de-114">イベント</span><span class="sxs-lookup"><span data-stu-id="637de-114">Events</span></span>](../../../standard/events/index.md)
- [<span data-ttu-id="637de-115">Windows フォーム コントロールのイベント</span><span class="sxs-lookup"><span data-stu-id="637de-115">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)
- [<span data-ttu-id="637de-116">Windows フォーム コントロールのプロパティ</span><span class="sxs-lookup"><span data-stu-id="637de-116">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
