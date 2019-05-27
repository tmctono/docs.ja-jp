---
title: '方法: FontDialog コンポーネントを使用してフォントの一覧を表示する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- fonts [Windows Forms], showing list
- FontDialog component [Windows Forms]
- fonts [Windows Forms], attributes
- Font property [Windows Forms], setting with FontDialog component
- Font dialog box [Windows Forms], displaying
- fonts [Windows Forms], selecting
ms.assetid: 35692c1b-0937-4b7a-9207-1ae6bdc244a0
ms.openlocfilehash: 05e9b5e1280d0318354b0d47f4d78f7ec1c5f4e7
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2019
ms.locfileid: "66053445"
---
# <a name="how-to-show-a-font-list-with-the-fontdialog-component"></a><span data-ttu-id="2d985-102">方法: FontDialog コンポーネントを使用してフォントの一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="2d985-102">How to: Show a Font List with the FontDialog Component</span></span>
<span data-ttu-id="2d985-103">[FontDialog](fontdialog-component-windows-forms.md)コンポーネントを重みとサイズなど、表示属性を変更できるだけでなく、フォントを選択してユーザーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2d985-103">The [FontDialog](fontdialog-component-windows-forms.md) component allows users to select a font, as well as change its display aspects, such as its weight and size.</span></span>  
  
 <span data-ttu-id="2d985-104">ダイアログ ボックスで選択されているフォントが返されます、<xref:System.Windows.Forms.FontDialog.Font%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="2d985-104">The font selected in the dialog box is returned in the <xref:System.Windows.Forms.FontDialog.Font%2A> property.</span></span> <span data-ttu-id="2d985-105">したがって、ユーザーが選択されているフォントの利用は、プロパティの読み取りと同じくらい簡単です。</span><span class="sxs-lookup"><span data-stu-id="2d985-105">Thus, taking advantage of the font selected by the user is as easy as reading a property.</span></span>  
  
### <a name="to-select-font-properties-using-the-fontdialog-component"></a><span data-ttu-id="2d985-106">FontDialog コンポーネントを使用するフォント プロパティを選択するには</span><span class="sxs-lookup"><span data-stu-id="2d985-106">To select font properties using the FontDialog Component</span></span>  
  
1. <span data-ttu-id="2d985-107">使用して、ダイアログ ボックスを表示、<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="2d985-107">Display the dialog box using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
2. <span data-ttu-id="2d985-108">使用して、 <xref:System.Windows.Forms.DialogResult>  ダイアログ ボックスが閉じられた方法を決定するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="2d985-108">Use the <xref:System.Windows.Forms.DialogResult> property to determine how the dialog box was closed.</span></span>  
  
3. <span data-ttu-id="2d985-109">使用して、<xref:System.Windows.Forms.FontDialog.Font%2A>目的のフォントを設定するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="2d985-109">Use the <xref:System.Windows.Forms.FontDialog.Font%2A> property to set the desired font.</span></span>  
  
     <span data-ttu-id="2d985-110">次の例で、<xref:System.Windows.Forms.Button>コントロールの<xref:System.Windows.Forms.Control.Click>イベント ハンドラーが表示されます、<xref:System.Windows.Forms.FontDialog>コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="2d985-110">In the example below, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens a <xref:System.Windows.Forms.FontDialog> component.</span></span> <span data-ttu-id="2d985-111">フォントが選択されると、ユーザーの場合にクリックする **[ok]**、<xref:System.Windows.Forms.FontDialog.Font%2A>のプロパティを<xref:System.Windows.Forms.TextBox>フォーム上にあるコントロールを選択したフォントを設定します。</span><span class="sxs-lookup"><span data-stu-id="2d985-111">When a font is chosen and the user clicks **OK**, the <xref:System.Windows.Forms.FontDialog.Font%2A> property of a <xref:System.Windows.Forms.TextBox> control that is on the form is set to the chosen font.</span></span> <span data-ttu-id="2d985-112">この例では、フォームに、<xref:System.Windows.Forms.Button>コントロール、<xref:System.Windows.Forms.TextBox>コントロール、および<xref:System.Windows.Forms.FontDialog>コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="2d985-112">The example assumes your form has a <xref:System.Windows.Forms.Button> control, a  <xref:System.Windows.Forms.TextBox> control, and a <xref:System.Windows.Forms.FontDialog> component.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       If FontDialog1.ShowDialog() = DialogResult.OK Then  
          TextBox1.Font = FontDialog1.Font  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(fontDialog1.ShowDialog() == DialogResult.OK)  
       {  
          textBox1.Font = fontDialog1.Font;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if(fontDialog1->ShowDialog() == DialogResult::OK)  
          {  
             textBox1->Font = fontDialog1->Font;  
          }  
       }  
    ```  
  
     <span data-ttu-id="2d985-113">(VisualC#とビジュアルC++)イベント ハンドラーを登録するフォームのコンス トラクターでは、次のコードを配置します。</span><span class="sxs-lookup"><span data-stu-id="2d985-113">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2d985-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d985-114">See also</span></span>

- <xref:System.Windows.Forms.FontDialog>
- [<span data-ttu-id="2d985-115">FontDialog コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2d985-115">FontDialog Component</span></span>](fontdialog-component-windows-forms.md)
