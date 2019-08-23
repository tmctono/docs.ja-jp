---
title: ShouldSerialize メソッドと Reset メソッドによる既定値の定義
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property methods
- ShouldPersist method
ms.assetid: 7b6c5e00-3771-46b4-9142-5a80d5864a5e
ms.openlocfilehash: 609fe4896a2b01b8a69ff8a3d0854c85ddbd6a26
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969092"
---
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a><span data-ttu-id="808bb-102">ShouldSerialize メソッドと Reset メソッドによる既定値の定義</span><span class="sxs-lookup"><span data-stu-id="808bb-102">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>
<span data-ttu-id="808bb-103">`ShouldSerialize`と`Reset`は、プロパティに単純な既定値がない場合に、プロパティに対して指定できる省略可能なメソッドです。</span><span class="sxs-lookup"><span data-stu-id="808bb-103">`ShouldSerialize` and `Reset` are optional methods that you can provide for a property, if the property does not a have simple default value.</span></span> <span data-ttu-id="808bb-104">プロパティに単純な既定値がある場合は、 <xref:System.ComponentModel.DefaultValueAttribute>を適用し、代わりに属性クラスコンストラクターに既定値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="808bb-104">If the property has a simple default value, you should apply the <xref:System.ComponentModel.DefaultValueAttribute> and supply the default value to the attribute class constructor instead.</span></span> <span data-ttu-id="808bb-105">これらのメカニズムのいずれかにより、デザイナーで次の機能が有効になります。</span><span class="sxs-lookup"><span data-stu-id="808bb-105">Either of these mechanisms enables the following features in the designer:</span></span>

- <span data-ttu-id="808bb-106">プロパティは、既定値から変更されている場合、プロパティブラウザーで視覚的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="808bb-106">The property provides visual indication in the property browser if it has been modified from its default value.</span></span>

- <span data-ttu-id="808bb-107">ユーザーはプロパティを右クリックし、 **[リセット]** をクリックして、プロパティを既定値に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="808bb-107">The user can right-click on the property and choose **Reset** to restore the property to its default value.</span></span>

- <span data-ttu-id="808bb-108">デザイナーでは、より効率的なコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="808bb-108">The designer generates more efficient code.</span></span>

    > [!NOTE]
    > <span data-ttu-id="808bb-109">を適用する<xref:System.ComponentModel.DefaultValueAttribute>か、 `Reset` *propertyname*メソッド`ShouldSerialize`と*propertyname*メソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="808bb-109">Either apply the <xref:System.ComponentModel.DefaultValueAttribute> or provide `Reset`*PropertyName* and `ShouldSerialize`*PropertyName* methods.</span></span> <span data-ttu-id="808bb-110">両方を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="808bb-110">Do not use both.</span></span>

 <span data-ttu-id="808bb-111">`Reset` *PropertyName*メソッドは、次のコードに示すように、プロパティを既定値に設定します。</span><span class="sxs-lookup"><span data-stu-id="808bb-111">The `Reset`*PropertyName* method sets a property to its default value, as shown in the following code fragment.</span></span>

```vb
Public Sub ResetMyFont()
   MyFont = Nothing
End Sub
```

```csharp
public void ResetMyFont() {
   MyFont = null;
}
```

> [!NOTE]
> <span data-ttu-id="808bb-112">プロパティに`Reset`メソッドがなく、が<xref:System.ComponentModel.DefaultValueAttribute>でマークされておらず、宣言`Reset`に既定値が指定されていない場合、そのプロパティのオプションは、の **[プロパティ]** ウィンドウのショートカットメニューで無効になります。Visual Studio の Windows フォームデザイナー。</span><span class="sxs-lookup"><span data-stu-id="808bb-112">If a property does not have a `Reset` method, is not marked with a <xref:System.ComponentModel.DefaultValueAttribute>, and does not have a default value supplied in its declaration, the `Reset` option for that property is disabled in the shortcut menu of the **Properties** window of the Windows Forms Designer in Visual Studio.</span></span>

 <span data-ttu-id="808bb-113">Visual Studio などのデザイナーでは`ShouldSerialize`、 *PropertyName*メソッドを使用して、プロパティが既定値から変更されたかどうかを確認し、プロパティが変更された場合にのみコードをフォームに記述します。これにより、コード生成をより効率的に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="808bb-113">Designers such as Visual Studio use the `ShouldSerialize`*PropertyName* method to check whether a property has changed from its default value and write code into the form only if a property is changed, thus allowing for more efficient code generation.</span></span> <span data-ttu-id="808bb-114">例えば:</span><span class="sxs-lookup"><span data-stu-id="808bb-114">For example:</span></span>

```vb
'Returns true if the font has changed; otherwise, returns false.
' The designer writes code to the form only if true is returned.
Public Function ShouldSerializeMyFont() As Boolean
   Return Not (thefont Is Nothing)
End Function
```

```csharp
// Returns true if the font has changed; otherwise, returns false.
// The designer writes code to the form only if true is returned.
public bool ShouldSerializeMyFont() {
   return thefont != null;
}
```

 <span data-ttu-id="808bb-115">完全なコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="808bb-115">A complete code example follows.</span></span>

```vb
Option Explicit
Option Strict

Imports System
Imports System.Windows.Forms
Imports System.Drawing

Public Class MyControl
   Inherits Control

   ' Declare an instance of the Font class
   ' and set its default value to Nothing.
   Private thefont As Font = Nothing

   ' The MyFont property.
   Public Property MyFont() As Font
      ' Note that the Font property never
      ' returns null.
      Get
         If Not (thefont Is Nothing) Then
            Return thefont
         End If
         If Not (Parent Is Nothing) Then
            Return Parent.Font
         End If
         Return Control.DefaultFont
      End Get
      Set
         thefont = value
      End Set
   End Property

   Public Function ShouldSerializeMyFont() As Boolean
      Return Not (thefont Is Nothing)
   End Function

   Public Sub ResetMyFont()
      MyFont = Nothing
   End Sub
End Class
```

```csharp
using System;
using System.Windows.Forms;
using System.Drawing;

public class MyControl : Control {
   // Declare an instance of the Font class
   // and set its default value to null.
   private Font thefont = null;

   // The MyFont property.
   public Font MyFont {
      // Note that the MyFont property never
      // returns null.
      get {
         if (thefont != null) return thefont;
         if (Parent != null) return Parent.Font;
         return Control.DefaultFont;
      }
      set {
         thefont = value;
      }
   }

   public bool ShouldSerializeMyFont() {
      return thefont != null;
   }

   public void ResetMyFont() {
      MyFont = null;
   }
}
```

 <span data-ttu-id="808bb-116">`MyFont`この場合、プロパティによってアクセスされるプライベート変数の値がであっ`null`ても、プロパティブラウザーには`null`表示されず、親<xref:System.Windows.Forms.Control.Font%2A> `null`のプロパティが表示されます。またはで<xref:System.Windows.Forms.Control.Font%2A> <xref:System.Windows.Forms.Control>定義されている既定値。</span><span class="sxs-lookup"><span data-stu-id="808bb-116">In this case, even when the value of the private variable accessed by the `MyFont` property is `null`, the property browser does not display `null`; instead, it displays the <xref:System.Windows.Forms.Control.Font%2A> property of the parent, if it is not `null`, or the default <xref:System.Windows.Forms.Control.Font%2A> value defined in <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="808bb-117">したがって、の`MyFont`既定値を単に設定することはできません。また、を<xref:System.ComponentModel.DefaultValueAttribute>このプロパティに適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="808bb-117">Thus the default value for `MyFont` cannot be simply set, and a <xref:System.ComponentModel.DefaultValueAttribute> cannot be applied to this property.</span></span> <span data-ttu-id="808bb-118">代わりに、 `MyFont`プロパティに`Reset`対してメソッドとメソッドを実装する必要があります。`ShouldSerialize`</span><span class="sxs-lookup"><span data-stu-id="808bb-118">Instead, the `ShouldSerialize` and `Reset` methods must be implemented for the `MyFont` property.</span></span>

## <a name="see-also"></a><span data-ttu-id="808bb-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="808bb-119">See also</span></span>

- [<span data-ttu-id="808bb-120">Windows フォーム コントロールのプロパティ</span><span class="sxs-lookup"><span data-stu-id="808bb-120">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="808bb-121">プロパティの定義</span><span class="sxs-lookup"><span data-stu-id="808bb-121">Defining a Property</span></span>](defining-a-property-in-windows-forms-controls.md)
- [<span data-ttu-id="808bb-122">プロパティ変更イベント</span><span class="sxs-lookup"><span data-stu-id="808bb-122">Property-Changed Events</span></span>](property-changed-events.md)
