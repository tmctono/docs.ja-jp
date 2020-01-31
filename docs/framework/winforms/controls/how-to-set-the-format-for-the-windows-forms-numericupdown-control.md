---
title: NumericUpDown コントロールの形式を設定する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- NumericUpDown control [Windows Forms], formatting values
- up-down controls [Windows Forms], formatting numeric values
ms.assetid: fa7c5557-6bfb-45b2-975d-8887b23b0ba0
ms.openlocfilehash: 5ef1c801e96bef7b92e7e69dc36491144c456eeb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742178"
---
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a><span data-ttu-id="10859-102">方法 : Windows フォームの NumericUpDown コントロールの書式を設定する</span><span class="sxs-lookup"><span data-stu-id="10859-102">How to: Set the Format for the Windows Forms NumericUpDown Control</span></span>
<span data-ttu-id="10859-103">Windows フォーム <xref:System.Windows.Forms.NumericUpDown> コントロールでの値の表示方法を構成できます。</span><span class="sxs-lookup"><span data-stu-id="10859-103">You can configure how values are displayed in the Windows Forms <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="10859-104"><xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> プロパティは、小数点の後に表示する数字の数を決定します。既定値は0です。</span><span class="sxs-lookup"><span data-stu-id="10859-104">The <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property determines how many numbers appear after the decimal point; the default is 0.</span></span> <span data-ttu-id="10859-105"><xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> プロパティは、3桁の10進数の間に区切り記号を挿入するかどうかを決定します。既定値は `false`です。</span><span class="sxs-lookup"><span data-stu-id="10859-105">The <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property determines whether a separator will be inserted between every three decimal digits; the default is `false`.</span></span> <span data-ttu-id="10859-106"><xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> プロパティが `true`に設定されている場合、コントロールでは、10進数形式ではなく16進数で値を表示できます。既定値は `false`です。</span><span class="sxs-lookup"><span data-stu-id="10859-106">The control can display values in hexadecimal instead of decimal format, if the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property is set to `true`; the default is `false`.</span></span>  
  
### <a name="to-format-the-numeric-value"></a><span data-ttu-id="10859-107">数値の書式を設定するには</span><span class="sxs-lookup"><span data-stu-id="10859-107">To format the numeric value</span></span>  
  
- <span data-ttu-id="10859-108">Decimal 値を表示するには、<xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> プロパティを整数に設定し、<xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> プロパティを `true` または `false`に設定します。</span><span class="sxs-lookup"><span data-stu-id="10859-108">Display a decimal value by setting the <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property to an integer and setting the <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property to `true` or `false`.</span></span>  
  
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
  
     <span data-ttu-id="10859-109">-または-</span><span class="sxs-lookup"><span data-stu-id="10859-109">-or-</span></span>  
  
- <span data-ttu-id="10859-110"><xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> プロパティを `true`に設定して、16進数の値を表示します。</span><span class="sxs-lookup"><span data-stu-id="10859-110">Display a hexadecimal value by setting the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property to `true`.</span></span>  
  
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
    > <span data-ttu-id="10859-111">値が16進数としてフォームに表示されている場合でも、<xref:System.Windows.Forms.NumericUpDown.Value%2A> プロパティで実行するテストでは、その10進値がテストされます。</span><span class="sxs-lookup"><span data-stu-id="10859-111">Even if the value is displayed on the form as hexadecimal, any tests you perform on the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property will be testing its decimal value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10859-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="10859-112">See also</span></span>

- <xref:System.Windows.Forms.NumericUpDown>
- [<span data-ttu-id="10859-113">NumericUpDown コントロール</span><span class="sxs-lookup"><span data-stu-id="10859-113">NumericUpDown Control</span></span>](numericupdown-control-windows-forms.md)
- [<span data-ttu-id="10859-114">NumericUpDown コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="10859-114">NumericUpDown Control Overview</span></span>](numericupdown-control-overview-windows-forms.md)
