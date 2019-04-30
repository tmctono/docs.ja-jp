---
title: Windows フォームとコントロールの国際対応フォント
ms.date: 03/30/2017
helpviewer_keywords:
- fonts [Windows Forms], international
- international applications [Windows Forms], character display
- fonts [Windows Forms], globalization considerations
- localization [Windows Forms], fonts
- Windows Forms controls, labels
- font fallback in Windows Forms
- globalization [Windows Forms], character sets
dev_langs:
- csharp
- vb
ms.assetid: 2c3066df-9bac-479a-82b2-79e484b346a3
ms.openlocfilehash: 1f9afd575e2de04e0b11556ad34436839e13d968
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942897"
---
# <a name="international-fonts-in-windows-forms-and-controls"></a><span data-ttu-id="330e7-102">Windows フォームとコントロールの国際対応フォント</span><span class="sxs-lookup"><span data-stu-id="330e7-102">International fonts in Windows Forms and controls</span></span>

<span data-ttu-id="330e7-103">国際対応のアプリケーションでは、可能な場合は、フォント フォールバックを使用するフォントを選択する勧めします。</span><span class="sxs-lookup"><span data-stu-id="330e7-103">In International applications, the recommended method of selecting fonts is to use font fallback wherever possible.</span></span> <span data-ttu-id="330e7-104">スクリプトの文字をシステムが決定されるフォント フォールバック手段に属しています。</span><span class="sxs-lookup"><span data-stu-id="330e7-104">Font fallback means that the system determines what script the character belongs to.</span></span>

## <a name="using-font-fallback"></a><span data-ttu-id="330e7-105">フォント フォールバックの使用</span><span class="sxs-lookup"><span data-stu-id="330e7-105">Using font fallback</span></span>

<span data-ttu-id="330e7-106">この機能を利用する設定しないでください、<xref:System.Drawing.Font>フォームまたはその他の要素のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="330e7-106">To take advantage of this feature, don't set the <xref:System.Drawing.Font> property for your form or any other element.</span></span> <span data-ttu-id="330e7-107">アプリケーションは、オペレーティング システムの 1 つのローカライズされた言語によって異なるため既定のシステム フォントを自動的に使用します。</span><span class="sxs-lookup"><span data-stu-id="330e7-107">The application will automatically use the default system font, which differs from one localized language of the operating system to another.</span></span> <span data-ttu-id="330e7-108">アプリケーションを実行すると、システムは自動的に提供されているオペレーティング システムで選択されているカルチャの適切なフォントを使用します。</span><span class="sxs-lookup"><span data-stu-id="330e7-108">When the application runs, the system will automatically provide the correct font for the culture selected in the operating system.</span></span>

<span data-ttu-id="330e7-109">設定しないと、フォント スタイルを変更する場合は、フォントのルールに例外があります。</span><span class="sxs-lookup"><span data-stu-id="330e7-109">There's an exception to the rule of not setting the font, which is for changing the font style.</span></span> <span data-ttu-id="330e7-110">ユーザーが表示されるテキスト ボックスにテキストを太字で表示するボタンをクリックしたアプリケーションの重要なことが考えられます。</span><span class="sxs-lookup"><span data-stu-id="330e7-110">This might be important for an application in which the user clicks a button to make text in a text box appear in boldface.</span></span> <span data-ttu-id="330e7-111">そのためには関数を作成するを太字のテキスト ボックスのフォント スタイルを変更する、フォームのフォントにします。</span><span class="sxs-lookup"><span data-stu-id="330e7-111">To do that, you would write a function to change the text box's font style to bold, based on whatever the form's font is.</span></span> <span data-ttu-id="330e7-112">2 つの場所でこの関数を呼び出すことが重要。 ボタンの<xref:System.Windows.Forms.Control.Click>イベント ハンドラーと、<xref:System.Windows.Forms.Control.FontChanged>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="330e7-112">It's important to call this function in two places: in the button's <xref:System.Windows.Forms.Control.Click> event handler and in the <xref:System.Windows.Forms.Control.FontChanged> event handler.</span></span> <span data-ttu-id="330e7-113">のみ、関数が呼び出された場合、<xref:System.Windows.Forms.Control.Click>フォーム全体のフォント ファミリの変更のイベント ハンドラーとコードの他の部分では、によって、テキスト ボックスは、フォームの残りの部分と変わりません。</span><span class="sxs-lookup"><span data-stu-id="330e7-113">If the function is called only in the <xref:System.Windows.Forms.Control.Click> event handler and some other piece of code changes the font family of the entire form, the text box doesn't change with the rest of the form.</span></span>

```vb
Private Sub MakeBold()
   ' Change the TextBox to a bold version of the form font
   TextBox1.Font = New Font(Me.Font, FontStyle.Bold)
End Sub

Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click
   ' Clicking this button makes the TextBox bold
   MakeBold()
End Sub

Private Sub Form1_FontChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles MyBase.FontChanged
   ' If the TextBox is already bold and the form's font changes,
   ' change the TextBox to a bold version of the new form font
   If (TextBox1.Font.Style = FontStyle.Bold) Then
      MakeBold()
   End If
End Sub
```

```csharp
private void button1_Click(object sender, System.EventArgs e)
{
   // Clicking this button makes the TextBox bold
   MakeBold();
}

private void MakeBold()
{
   // Change the TextBox to a bold version of the form's font
   textBox1.Font = new Font(this.Font, FontStyle.Bold);
}

private void Form1_FontChanged(object sender, System.EventArgs e)
{
   // If the TextBox is already bold and the form's font changes,
   // change the TextBox to a bold version of the new form font
   if (textBox1.Font.Style == FontStyle.Bold)
   {
      MakeBold();
   }
}
```

<span data-ttu-id="330e7-114">ただし、アプリケーションをローカライズするときに太字のフォント可能性があります表示が不十分な特定の言語。</span><span class="sxs-lookup"><span data-stu-id="330e7-114">However, when you localize your application, the bold font may display poorly for certain languages.</span></span> <span data-ttu-id="330e7-115">問題になる場合は、ローカライズで、通常のテキストに太字のフォントを切り替えるオプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="330e7-115">If this is a concern, you want the localizers to have the option of switching the font from bold to regular text.</span></span> <span data-ttu-id="330e7-116">ローカライザーは、開発者は通常、ソース コードへのアクセス権がない、ためにのリソースのファイルにのみ、このオプションがリソース ファイルで設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="330e7-116">Since localizers are typically not developers and don't have access to source code, only to resource files, this option needs to be set in the resource files.</span></span> <span data-ttu-id="330e7-117">これを行うには、設定、<xref:System.Drawing.Font.Bold%2A>プロパティを`true`します。</span><span class="sxs-lookup"><span data-stu-id="330e7-117">To do this, you would set the <xref:System.Drawing.Font.Bold%2A> property to `true`.</span></span> <span data-ttu-id="330e7-118">これは、結果、ローカライザーが編集できる、リソース ファイルに書き込まれているフォントを設定します。</span><span class="sxs-lookup"><span data-stu-id="330e7-118">This results in the font setting being written out to the resource files, where localizers can edit it.</span></span> <span data-ttu-id="330e7-119">後のコードを作成し、`InitializeComponent`フォントをリセットする方法、フォームのフォントに基づいていますが、リソース ファイルで指定されたフォント スタイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="330e7-119">You then write code after the `InitializeComponent` method to reset the font based on whatever the form's font is, but using the font style specified in the resource file.</span></span>

```vb
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)
```

```csharp
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);
```
  
## <a name="see-also"></a><span data-ttu-id="330e7-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="330e7-120">See also</span></span>

- [<span data-ttu-id="330e7-121">Windows フォーム アプリケーションのグローバル化</span><span class="sxs-lookup"><span data-stu-id="330e7-121">Globalizing Windows Forms applications</span></span>](globalizing-windows-forms.md)
- [<span data-ttu-id="330e7-122">フォントとテキストの使用</span><span class="sxs-lookup"><span data-stu-id="330e7-122">Using Fonts and Text</span></span>](using-fonts-and-text.md)
