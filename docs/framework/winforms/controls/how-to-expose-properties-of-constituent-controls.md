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
ms.openlocfilehash: f006e42771a5ecc71f6a508fd78d0e2dd8f2d2f2
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015874"
---
# <a name="how-to-expose-properties-of-constituent-controls"></a><span data-ttu-id="3408a-102">方法: 内在コントロールのプロパティを公開する</span><span class="sxs-lookup"><span data-stu-id="3408a-102">How to: Expose Properties of Constituent Controls</span></span>
<span data-ttu-id="3408a-103">複合コントロールを構成するコントロールは、*内在コントロール*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="3408a-103">The controls that make up a composite control are called *constituent controls*.</span></span> <span data-ttu-id="3408a-104">これらのコントロールは通常、プライベートとして宣言されるため、開発者がアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3408a-104">These controls are normally declared private, and thus cannot be accessed by the developer.</span></span> <span data-ttu-id="3408a-105">これらのコントロールのプロパティを今後のユーザーが使用できるようにするには、それらをユーザーに公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3408a-105">If you want to make properties of these controls available to future users, you must expose them to the user.</span></span> <span data-ttu-id="3408a-106">内在コントロールのプロパティは、ユーザーコントロールにプロパティを作成し、そのプロパティのアクセサー `get`と`set`アクセサーを使用して、内在コントロールのプライベートプロパティの変更を反映することによって公開されます。</span><span class="sxs-lookup"><span data-stu-id="3408a-106">A property of a constituent control is exposed by creating a property in the user control, and using the `get` and `set` accessors of that property to effect the change in the private property of the constituent control.</span></span>

 <span data-ttu-id="3408a-107">という名前`MyButton`の構成ボタンを持つ仮想的なユーザーコントロールを考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="3408a-107">Consider a hypothetical user control with a constituent button named `MyButton`.</span></span> <span data-ttu-id="3408a-108">この例では、ユーザーが`ConstituentButtonBackColor`プロパティを要求すると、の<xref:System.Windows.Forms.Control.BackColor%2A> `MyButton`プロパティに格納されている値が配信されます。</span><span class="sxs-lookup"><span data-stu-id="3408a-108">In this example, when the user requests the `ConstituentButtonBackColor` property, the value stored in the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` is delivered.</span></span> <span data-ttu-id="3408a-109">ユーザーがこのプロパティに値を割り当てた場合、 <xref:System.Windows.Forms.Control.BackColor%2A>その値はの`MyButton` `set`プロパティに自動的に渡され、コードが実行され、の`MyButton`色が変更されます。</span><span class="sxs-lookup"><span data-stu-id="3408a-109">When the user assigns a value to this property, that value is automatically passed to the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` and the `set` code will execute, changing the color of `MyButton`.</span></span>

 <span data-ttu-id="3408a-110">次の例は、構成ボタンの<xref:System.Windows.Forms.Control.BackColor%2A>プロパティを公開する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3408a-110">The following example shows how to expose the <xref:System.Windows.Forms.Control.BackColor%2A> property of the constituent button:</span></span>

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

### <a name="to-expose-a-property-of-a-constituent-control"></a><span data-ttu-id="3408a-111">内在コントロールのプロパティを公開するには</span><span class="sxs-lookup"><span data-stu-id="3408a-111">To expose a property of a constituent control</span></span>

1. <span data-ttu-id="3408a-112">ユーザーコントロールのパブリックプロパティを作成します。</span><span class="sxs-lookup"><span data-stu-id="3408a-112">Create a public property for your user control.</span></span>

2. <span data-ttu-id="3408a-113">プロパティの`get`セクションで、公開するプロパティの値を取得するコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="3408a-113">In the `get` section of the property, write code that retrieves the value of the property you want to expose.</span></span>

3. <span data-ttu-id="3408a-114">プロパティの`set`セクションに、プロパティの値を、構成対象のコントロールの公開されたプロパティに渡すコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="3408a-114">In the `set` section of the property, write code that passes the value of the property to the exposed property of the constituent control.</span></span>

## <a name="see-also"></a><span data-ttu-id="3408a-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="3408a-115">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- [<span data-ttu-id="3408a-116">Windows フォーム コントロールのプロパティ</span><span class="sxs-lookup"><span data-stu-id="3408a-116">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="3408a-117">さまざまなカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="3408a-117">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
