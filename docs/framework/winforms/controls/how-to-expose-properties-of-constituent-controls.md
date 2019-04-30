---
title: '方法: 内在コントロールのプロパティを公開する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user controls [Windows Forms], exposing constituent controls
- controls [Windows Forms], constituent
- custom controls [Windows Forms], exposing properties
- constituent controls
ms.assetid: 5c1ec98b-aa48-4823-986e-4712551cfdf1
ms.openlocfilehash: 44b96218e674c754a1985f2f22a36707cd1776b6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941376"
---
# <a name="how-to-expose-properties-of-constituent-controls"></a><span data-ttu-id="e67a2-102">方法: 内在コントロールのプロパティを公開する</span><span class="sxs-lookup"><span data-stu-id="e67a2-102">How to: Expose Properties of Constituent Controls</span></span>
<span data-ttu-id="e67a2-103">複合コントロールを構成するコントロールが呼び出される*内在コントロール*します。</span><span class="sxs-lookup"><span data-stu-id="e67a2-103">The controls that make up a composite control are called *constituent controls*.</span></span> <span data-ttu-id="e67a2-104">これらのコントロールは通常プライベートで宣言されており、そのため、開発者がアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="e67a2-104">These controls are normally declared private, and thus cannot be accessed by the developer.</span></span> <span data-ttu-id="e67a2-105">今後のユーザーにこれらのコントロールのプロパティを使用できるようにする場合は、ユーザーに公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e67a2-105">If you want to make properties of these controls available to future users, you must expose them to the user.</span></span> <span data-ttu-id="e67a2-106">ユーザー コントロールでプロパティを作成して使用内在コントロールのプロパティを公開、`get`と`set`内在コントロールのプライベート プロパティの変更を有効にするためのプロパティのアクセサー。</span><span class="sxs-lookup"><span data-stu-id="e67a2-106">A property of a constituent control is exposed by creating a property in the user control, and using the `get` and `set` accessors of that property to effect the change in the private property of the constituent control.</span></span>  
  
 <span data-ttu-id="e67a2-107">という名前の構成要素であるボタンで仮想的なユーザー コントロールを検討してください`MyButton`します。</span><span class="sxs-lookup"><span data-stu-id="e67a2-107">Consider a hypothetical user control with a constituent button named `MyButton`.</span></span> <span data-ttu-id="e67a2-108">ユーザーが要求したときに、この例では、`ConstituentButtonBackColor`プロパティに格納された値、<xref:System.Windows.Forms.Control.BackColor%2A>プロパティの`MyButton`配信されます。</span><span class="sxs-lookup"><span data-stu-id="e67a2-108">In this example, when the user requests the `ConstituentButtonBackColor` property, the value stored in the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` is delivered.</span></span> <span data-ttu-id="e67a2-109">その値が自動的に渡される、ユーザーは、このプロパティに値を割り当てます、ときに、<xref:System.Windows.Forms.Control.BackColor%2A>プロパティの`MyButton`と`set`の色を変更する、コードが実行されます`MyButton`。</span><span class="sxs-lookup"><span data-stu-id="e67a2-109">When the user assigns a value to this property, that value is automatically passed to the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` and the `set` code will execute, changing the color of `MyButton`.</span></span>  
  
 <span data-ttu-id="e67a2-110">次の例では、公開する方法を示しています、<xref:System.Windows.Forms.Control.BackColor%2A>構成ボタンのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="e67a2-110">The following example shows how to expose the <xref:System.Windows.Forms.Control.BackColor%2A> property of the constituent button:</span></span>  
  
```vb  
Public Property ButtonColor() as System.Drawing.Color  
   Get  
      Return MyButton.BackColor  
   End Get  
   Set(Value as System.Drawing.Color)  
      MyButton.BackColor = Value  
   End Set  
End Property  
```  
  
```csharp  
public Color ButtonColor  
{  
   get  
   {  
      return(myButton.BackColor);  
   }  
   set  
   {  
      myButton.BackColor = value;  
   }  
}  
```  
  
### <a name="to-expose-a-property-of-a-constituent-control"></a><span data-ttu-id="e67a2-111">内在コントロールのプロパティを公開するには</span><span class="sxs-lookup"><span data-stu-id="e67a2-111">To expose a property of a constituent control</span></span>  
  
1. <span data-ttu-id="e67a2-112">ユーザー コントロールのパブリック プロパティを作成します。</span><span class="sxs-lookup"><span data-stu-id="e67a2-112">Create a public property for your user control.</span></span>  
  
2. <span data-ttu-id="e67a2-113">`get`セクションのプロパティを公開するプロパティの値を取得するコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="e67a2-113">In the `get` section of the property, write code that retrieves the value of the property you want to expose.</span></span>  
  
3. <span data-ttu-id="e67a2-114">`set`セクションのプロパティ、プロパティの値を公開されている、内在コントロールのプロパティに渡されるコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="e67a2-114">In the `set` section of the property, write code that passes the value of the property to the exposed property of the constituent control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e67a2-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="e67a2-115">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- [<span data-ttu-id="e67a2-116">Windows フォーム コントロールのプロパティ</span><span class="sxs-lookup"><span data-stu-id="e67a2-116">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="e67a2-117">さまざまなカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="e67a2-117">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
