---
title: '方法: Windows フォームの LinkLabel コントロールから Web ページを表示する (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- LinkLabel1_LinkClicked
helpviewer_keywords:
- examples [Windows Forms], LinkLabel control
- Web pages [Windows Forms], displaying
- linking [Windows Forms], to Web pages from forms
- Windows Forms, linking to Web pages
- LinkLabel control [Windows Forms], examples
ms.assetid: 477a7398-5971-4de3-b24c-f49f32bdb28a
ms.openlocfilehash: 1be9ff06e749d14b46946e899c6ffb6c3a950d65
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972168"
---
# <a name="how-to-display-a-web-page-from-a-windows-forms-linklabel-control-visual-basic"></a><span data-ttu-id="f65b4-102">方法: Windows フォームの LinkLabel コントロールから Web ページを表示する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f65b4-102">How to: Display a Web Page from a Windows Forms LinkLabel Control (Visual Basic)</span></span>
<span data-ttu-id="f65b4-103">この例では、ユーザーが Windows フォームをクリックすると、既定のブラウザーで Web ページを表示<xref:System.Windows.Forms.LinkLabel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="f65b4-103">This example displays a Web page in the default browser when a user clicks a Windows Forms <xref:System.Windows.Forms.LinkLabel> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f65b4-104">例</span><span class="sxs-lookup"><span data-stu-id="f65b4-104">Example</span></span>  
  
```vb  
Private Sub Form1_Load(ByVal sender As System.Object, ByVal e _  
As System.EventArgs) Handles MyBase.Load  
    LinkLabel1.Text = "Click here to get more info."  
    LinkLabel1.Links.Add(6, 4, "www.microsoft.com")  
End Sub  
Private Sub LinkLabel1_LinkClicked(ByVal sender As System.Object, ByVal _  
e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) Handles _  
LinkLabel1.LinkClicked  
    System.Diagnostics.Process.Start(e.Link.LinkData.ToString())  
End Sub  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f65b4-105">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="f65b4-105">Compiling the Code</span></span>  
 <span data-ttu-id="f65b4-106">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f65b4-106">This example requires:</span></span>  
  
- <span data-ttu-id="f65b4-107">という名前の Windows フォーム`Form1`します。</span><span class="sxs-lookup"><span data-stu-id="f65b4-107">A Windows Form named `Form1`.</span></span>  
  
- <span data-ttu-id="f65b4-108">`LinkLabel1` という名前の <xref:System.Windows.Forms.LinkLabel> コントロール。</span><span class="sxs-lookup"><span data-stu-id="f65b4-108">A <xref:System.Windows.Forms.LinkLabel> control named `LinkLabel1`.</span></span>  
  
- <span data-ttu-id="f65b4-109">インターネットに接続します。</span><span class="sxs-lookup"><span data-stu-id="f65b4-109">An active Internet connection.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="f65b4-110">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="f65b4-110">.NET Framework Security</span></span>  
 <span data-ttu-id="f65b4-111">呼び出し、<xref:System.Diagnostics.Process.Start%2A>メソッドには、完全な信頼が必要です。</span><span class="sxs-lookup"><span data-stu-id="f65b4-111">The call to the <xref:System.Diagnostics.Process.Start%2A> method requires full trust.</span></span> <span data-ttu-id="f65b4-112">詳細については、「 <xref:System.Security.SecurityException> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f65b4-112">For more information, see <xref:System.Security.SecurityException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f65b4-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="f65b4-113">See also</span></span>

- <xref:System.Windows.Forms.LinkLabel>
- [<span data-ttu-id="f65b4-114">LinkLabel コントロール</span><span class="sxs-lookup"><span data-stu-id="f65b4-114">LinkLabel Control</span></span>](linklabel-control-windows-forms.md)
