---
title: NumericUpDown コントロールを使用して数値を設定して返す
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- numeric values [Windows Forms], Windows Forms
- Windows Forms, numeric values
- Windows Forms controls, NumericUpDown
- NumericUpDown control [Windows Forms], setting and returning values
ms.assetid: 5bd8f8cd-4c12-49ea-9cc3-2a647d064689
ms.openlocfilehash: a0b264fec9619b467c293bcb96278c4517775ac3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743019"
---
# <a name="how-to-set-and-return-numeric-values-with-the-windows-forms-numericupdown-control"></a><span data-ttu-id="97bd5-102">方法 : Windows フォームの NumericUpDown コントロールを使用して数値を設定および取得する</span><span class="sxs-lookup"><span data-stu-id="97bd5-102">How to: Set and Return Numeric Values with the Windows Forms NumericUpDown Control</span></span>
<span data-ttu-id="97bd5-103"><xref:System.Windows.Forms.NumericUpDown> コントロール Windows フォームの数値は <xref:System.Windows.Forms.NumericUpDown.Value%2A> プロパティによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="97bd5-103">The numeric value of the Windows Forms <xref:System.Windows.Forms.NumericUpDown> control is determined by its <xref:System.Windows.Forms.NumericUpDown.Value%2A> property.</span></span> <span data-ttu-id="97bd5-104">他のプロパティと同様に、コントロールの値の条件付きテストを記述できます。</span><span class="sxs-lookup"><span data-stu-id="97bd5-104">You can write conditional tests for the control's value just as with any other property.</span></span> <span data-ttu-id="97bd5-105"><xref:System.Windows.Forms.NumericUpDown.Value%2A> プロパティが設定されたら、それに対して操作を実行するコードを記述して直接調整できます。または、<xref:System.Windows.Forms.NumericUpDown.UpButton%2A> メソッドと <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> メソッドを呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="97bd5-105">Once the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property is set, you can adjust it directly by writing code to perform operations on it, or you can call the <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> and <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> methods.</span></span>  
  
### <a name="to-set-the-numeric-value"></a><span data-ttu-id="97bd5-106">数値を設定するには</span><span class="sxs-lookup"><span data-stu-id="97bd5-106">To set the numeric value</span></span>  
  
1. <span data-ttu-id="97bd5-107">コードまたはプロパティウィンドウの <xref:System.Windows.Forms.NumericUpDown.Value%2A> プロパティに値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="97bd5-107">Assign a value to the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property in code or in the Properties window.</span></span>  
  
    ```vb  
    NumericUpDown1.Value = 55  
    ```  
  
    ```csharp  
    numericUpDown1.Value = 55;  
    ```  
  
    ```cpp  
    numericUpDown1->Value = 55;  
    ```  
  
     <span data-ttu-id="97bd5-108">-または-</span><span class="sxs-lookup"><span data-stu-id="97bd5-108">-or-</span></span>  
  
2. <span data-ttu-id="97bd5-109"><xref:System.Windows.Forms.NumericUpDown.UpButton%2A> または <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> メソッドを呼び出して、<xref:System.Windows.Forms.NumericUpDown.Increment%2A> プロパティで指定した量だけ値を増減させます。</span><span class="sxs-lookup"><span data-stu-id="97bd5-109">Call the <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> or <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> method to increase or decrease the value by the amount specified in the <xref:System.Windows.Forms.NumericUpDown.Increment%2A> property.</span></span>  
  
    ```vb  
    NumericUpDown1.UpButton()  
    ```  
  
    ```csharp  
    numericUpDown1.UpButton();  
    ```  
  
    ```cpp  
    numericUpDown1->UpButton();  
    ```  
  
### <a name="to-return-the-numeric-value"></a><span data-ttu-id="97bd5-110">数値を取得するには</span><span class="sxs-lookup"><span data-stu-id="97bd5-110">To return the numeric value</span></span>  
  
- <span data-ttu-id="97bd5-111">コード内の <xref:System.Windows.Forms.NumericUpDown.Value%2A> プロパティにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="97bd5-111">Access the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property in code.</span></span>  
  
    ```vb  
    If NumericUpDown1.Value >= 65 Then  
       MessageBox.Show("Age is: " & NumericUpDown1.Value.ToString)  
    Else  
       MessageBox.Show("The customer is ineligible for a senior citizen discount.")  
    End If  
    ```  
  
    ```csharp  
    if(numericUpDown1.Value >= 65)  
    {  
       MessageBox.Show("Age is: " + numericUpDown1.Value.ToString());  
    }  
    else  
    {  
       MessageBox.Show("The customer is ineligible for a senior citizen discount.");  
    }  
    ```  
  
    ```cpp  
    if(numericUpDown1->Value >= 65)  
    {  
       MessageBox::Show(String::Concat("Age is: ",  
          numericUpDown1->Value.ToString()));  
    }  
    else  
    {  
       MessageBox::Show  
          ("The customer is ineligible for a senior citizen discount.");  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="97bd5-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="97bd5-112">See also</span></span>

- <xref:System.Windows.Forms.NumericUpDown>
- <xref:System.Windows.Forms.NumericUpDown.Value%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.Increment%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.UpButton%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.DownButton%2A?displayProperty=nameWithType>
- [<span data-ttu-id="97bd5-113">NumericUpDown コントロール</span><span class="sxs-lookup"><span data-stu-id="97bd5-113">NumericUpDown Control</span></span>](numericupdown-control-windows-forms.md)
- [<span data-ttu-id="97bd5-114">NumericUpDown コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="97bd5-114">NumericUpDown Control Overview</span></span>](numericupdown-control-overview-windows-forms.md)
