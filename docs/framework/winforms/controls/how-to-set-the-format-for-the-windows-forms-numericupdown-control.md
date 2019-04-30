---
title: '方法: Windows フォームの NumericUpDown コントロールの書式を設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- NumericUpDown control [Windows Forms], formatting values
- up-down controls [Windows Forms], formatting numeric values
ms.assetid: fa7c5557-6bfb-45b2-975d-8887b23b0ba0
ms.openlocfilehash: 5957a44c7b07aa1b8d8df32667f023c0873ec1de
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013193"
---
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a><span data-ttu-id="3d874-102">方法: Windows フォームの NumericUpDown コントロールの書式を設定する</span><span class="sxs-lookup"><span data-stu-id="3d874-102">How to: Set the Format for the Windows Forms NumericUpDown Control</span></span>
<span data-ttu-id="3d874-103">Windows フォームで値を表示する方法を構成する<xref:System.Windows.Forms.NumericUpDown>コントロール。</span><span class="sxs-lookup"><span data-stu-id="3d874-103">You can configure how values are displayed in the Windows Forms <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="3d874-104"><xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A>プロパティは、小数点より後に表示される番号の数を決定します。 既定値は 0。</span><span class="sxs-lookup"><span data-stu-id="3d874-104">The <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property determines how many numbers appear after the decimal point; the default is 0.</span></span> <span data-ttu-id="3d874-105"><xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A>プロパティが 3 桁ごとの間の区切り記号が挿入されるかどうかを決定します。 既定値は`false`します。</span><span class="sxs-lookup"><span data-stu-id="3d874-105">The <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property determines whether a separator will be inserted between every three decimal digits; the default is `false`.</span></span> <span data-ttu-id="3d874-106">コントロールは、場合に、10 進数の形式ではなく 16 進数の値を表示できます、<xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A>プロパティに設定されて`true`; 既定値は`false`します。</span><span class="sxs-lookup"><span data-stu-id="3d874-106">The control can display values in hexadecimal instead of decimal format, if the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property is set to `true`; the default is `false`.</span></span>  
  
### <a name="to-format-the-numeric-value"></a><span data-ttu-id="3d874-107">数値の書式設定</span><span class="sxs-lookup"><span data-stu-id="3d874-107">To format the numeric value</span></span>  
  
- <span data-ttu-id="3d874-108">10 進値を設定して、表示、<xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A>プロパティを整数に設定、<xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A>プロパティを`true`または`false`します。</span><span class="sxs-lookup"><span data-stu-id="3d874-108">Display a decimal value by setting the <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property to an integer and setting the <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property to `true` or `false`.</span></span>  
  
    ```vb  
    NumericUpDown1.DecimalPlaces = 2  
    NumericUpDown1.ThousandsSeparator = True  
    ```  
  
    ```csharp  
    numericUpDown1.DecimalPlaces = 2;  
    numericUpDown1.ThousandsSeparator = true;  
    ```  
  
    ```cpp  
    numericUpDown1->DecimalPlaces = 2;  
    numericUpDown1->ThousandsSeparator = true;  
    ```  
  
     <span data-ttu-id="3d874-109">- または -</span><span class="sxs-lookup"><span data-stu-id="3d874-109">-or-</span></span>  
  
- <span data-ttu-id="3d874-110">16 進数の値を設定して表示、<xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A>プロパティを`true`します。</span><span class="sxs-lookup"><span data-stu-id="3d874-110">Display a hexadecimal value by setting the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property to `true`.</span></span>  
  
    ```vb  
    NumericUpDown1.Hexadecimal = True  
    ```  
  
    ```csharp  
    numericUpDown1.Hexadecimal = true;  
    ```  
  
    ```cpp  
    numericUpDown1->Hexadecimal = true;  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="3d874-111">実行するすべてのテスト値は、16 進数としてフォームに表示されますが、場合でも、<xref:System.Windows.Forms.NumericUpDown.Value%2A>プロパティに、10 進値をテストします。</span><span class="sxs-lookup"><span data-stu-id="3d874-111">Even if the value is displayed on the form as hexadecimal, any tests you perform on the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property will be testing its decimal value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d874-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="3d874-112">See also</span></span>

- <xref:System.Windows.Forms.NumericUpDown>
- [<span data-ttu-id="3d874-113">NumericUpDown コントロール</span><span class="sxs-lookup"><span data-stu-id="3d874-113">NumericUpDown Control</span></span>](numericupdown-control-windows-forms.md)
- [<span data-ttu-id="3d874-114">NumericUpDown コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="3d874-114">NumericUpDown Control Overview</span></span>](numericupdown-control-overview-windows-forms.md)
