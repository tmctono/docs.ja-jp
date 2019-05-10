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
ms.openlocfilehash: 5c95272c672d9b35d61e2fca8cccdbc532ef6776
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211298"
---
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a><span data-ttu-id="69d9c-102">ShouldSerialize メソッドと Reset メソッドによる既定値の定義</span><span class="sxs-lookup"><span data-stu-id="69d9c-102">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>
<span data-ttu-id="69d9c-103">`ShouldSerialize` `Reset`プロパティで指定できる省略可能なメソッドをプロパティでない場合は、単純な既定値を設定します。</span><span class="sxs-lookup"><span data-stu-id="69d9c-103">`ShouldSerialize` and `Reset` are optional methods that you can provide for a property, if the property does not a have simple default value.</span></span> <span data-ttu-id="69d9c-104">プロパティは、単純な既定値を持つ場合は適用して、<xref:System.ComponentModel.DefaultValueAttribute>代わりに、属性クラスのコンス トラクターを既定値を指定します。</span><span class="sxs-lookup"><span data-stu-id="69d9c-104">If the property has a simple default value, you should apply the <xref:System.ComponentModel.DefaultValueAttribute> and supply the default value to the attribute class constructor instead.</span></span> <span data-ttu-id="69d9c-105">これらのメカニズムのいずれかには、デザイナーで、次の機能が有効にします。</span><span class="sxs-lookup"><span data-stu-id="69d9c-105">Either of these mechanisms enables the following features in the designer:</span></span>

- <span data-ttu-id="69d9c-106">プロパティが既定値から変更された場合、プロパティ ブラウザーでビジュアルを示す値を提供します。</span><span class="sxs-lookup"><span data-stu-id="69d9c-106">The property provides visual indication in the property browser if it has been modified from its default value.</span></span>

- <span data-ttu-id="69d9c-107">ユーザーは、プロパティを右クリックし、選択**リセット**プロパティを既定値に復元します。</span><span class="sxs-lookup"><span data-stu-id="69d9c-107">The user can right-click on the property and choose **Reset** to restore the property to its default value.</span></span>

- <span data-ttu-id="69d9c-108">デザイナーより効率的なコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="69d9c-108">The designer generates more efficient code.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="69d9c-109">いずれかが当てはまる、<xref:System.ComponentModel.DefaultValueAttribute>提供または`Reset` *PropertyName*と`ShouldSerialize` *PropertyName*メソッド。</span><span class="sxs-lookup"><span data-stu-id="69d9c-109">Either apply the <xref:System.ComponentModel.DefaultValueAttribute> or provide `Reset`*PropertyName* and `ShouldSerialize`*PropertyName* methods.</span></span> <span data-ttu-id="69d9c-110">どちらも使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="69d9c-110">Do not use both.</span></span>

 <span data-ttu-id="69d9c-111">`Reset` *PropertyName*メソッドは、次のコード フラグメントで示すように、既定値にプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="69d9c-111">The `Reset`*PropertyName* method sets a property to its default value, as shown in the following code fragment.</span></span>

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
>  <span data-ttu-id="69d9c-112">プロパティがない場合、`Reset`メソッドが設定されていない、<xref:System.ComponentModel.DefaultValueAttribute>に、その宣言で指定された既定値がないと、`Reset`オプションのショートカット メニューでそのプロパティが無効になっている、 **プロパティ** Visual Studio での Windows フォーム デザイナーのウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="69d9c-112">If a property does not have a `Reset` method, is not marked with a <xref:System.ComponentModel.DefaultValueAttribute>, and does not have a default value supplied in its declaration, the `Reset` option for that property is disabled in the shortcut menu of the **Properties** window of the Windows Forms Designer in Visual Studio.</span></span>

 <span data-ttu-id="69d9c-113">Visual Studio などのデザイナーを使用して、 `ShouldSerialize` *PropertyName*プロパティが既定値から変更されたかどうかを確認し、プロパティを場合にのみフォームにコードを記述するメソッドが変更されたためより効率的なコードのことができます生成します。</span><span class="sxs-lookup"><span data-stu-id="69d9c-113">Designers such as Visual Studio use the `ShouldSerialize`*PropertyName* method to check whether a property has changed from its default value and write code into the form only if a property is changed, thus allowing for more efficient code generation.</span></span> <span data-ttu-id="69d9c-114">例えば:</span><span class="sxs-lookup"><span data-stu-id="69d9c-114">For example:</span></span>

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

 <span data-ttu-id="69d9c-115">完全なコード例に従います。</span><span class="sxs-lookup"><span data-stu-id="69d9c-115">A complete code example follows.</span></span>

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

 <span data-ttu-id="69d9c-116">この場合、プライベート変数の値にアクセスしている場合でも、`MyFont`プロパティは`null`、プロパティ ブラウザーが表示されない`null`代わりに、が表示されます、<xref:System.Windows.Forms.Control.Font%2A>でない場合は、親のプロパティ`null`、。既定値または<xref:System.Windows.Forms.Control.Font%2A>で定義されている値<xref:System.Windows.Forms.Control>します。</span><span class="sxs-lookup"><span data-stu-id="69d9c-116">In this case, even when the value of the private variable accessed by the `MyFont` property is `null`, the property browser does not display `null`; instead, it displays the <xref:System.Windows.Forms.Control.Font%2A> property of the parent, if it is not `null`, or the default <xref:System.Windows.Forms.Control.Font%2A> value defined in <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="69d9c-117">既定値ため`MyFont`、単に設定することはできません、<xref:System.ComponentModel.DefaultValueAttribute>このプロパティには適用できません。</span><span class="sxs-lookup"><span data-stu-id="69d9c-117">Thus the default value for `MyFont` cannot be simply set, and a <xref:System.ComponentModel.DefaultValueAttribute> cannot be applied to this property.</span></span> <span data-ttu-id="69d9c-118">代わりに、`ShouldSerialize`と`Reset`のメソッドを実装する必要があります、`MyFont`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="69d9c-118">Instead, the `ShouldSerialize` and `Reset` methods must be implemented for the `MyFont` property.</span></span>

## <a name="see-also"></a><span data-ttu-id="69d9c-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="69d9c-119">See also</span></span>

- [<span data-ttu-id="69d9c-120">Windows フォーム コントロールのプロパティ</span><span class="sxs-lookup"><span data-stu-id="69d9c-120">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="69d9c-121">プロパティの定義</span><span class="sxs-lookup"><span data-stu-id="69d9c-121">Defining a Property</span></span>](defining-a-property-in-windows-forms-controls.md)
- [<span data-ttu-id="69d9c-122">プロパティ変更イベント</span><span class="sxs-lookup"><span data-stu-id="69d9c-122">Property-Changed Events</span></span>](property-changed-events.md)
