---
title: '方法: StackPanel を作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- StackPanel control [WPF], creating
ms.assetid: e7ce65cb-720a-4bb6-95b6-286b74488a58
ms.openlocfilehash: bcf6decff2fbc012b5f8b62794f0d7b2cd9f29fc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051002"
---
# <a name="how-to-create-a-stackpanel"></a><span data-ttu-id="f3f86-102">方法: StackPanel を作成する</span><span class="sxs-lookup"><span data-stu-id="f3f86-102">How to: Create a StackPanel</span></span>
<span data-ttu-id="f3f86-103">この例は、作成する方法を示します、<xref:System.Windows.Controls.StackPanel>します。</span><span class="sxs-lookup"><span data-stu-id="f3f86-103">This example shows how to create a <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3f86-104">例</span><span class="sxs-lookup"><span data-stu-id="f3f86-104">Example</span></span>  
 <span data-ttu-id="f3f86-105">A<xref:System.Windows.Controls.StackPanel>すると、指定した方向に要素を積み重ねることができます。</span><span class="sxs-lookup"><span data-stu-id="f3f86-105">A <xref:System.Windows.Controls.StackPanel> allows you to stack elements in a specified direction.</span></span> <span data-ttu-id="f3f86-106">定義されているプロパティを使用して<xref:System.Windows.Controls.StackPanel>、コンテンツ流し込むことができます垂直方向に、これは、既定の設定、または水平方向にします。</span><span class="sxs-lookup"><span data-stu-id="f3f86-106">By using properties that are defined on <xref:System.Windows.Controls.StackPanel>, content can flow both vertically, which is the default setting, or horizontally.</span></span>  
  
 <span data-ttu-id="f3f86-107">次の例を垂直に積み重ねます 5<xref:System.Windows.Controls.TextBlock>制御する場合に、それぞれ異なる<xref:System.Windows.Controls.Border>と<xref:System.Windows.Controls.Border.Background%2A>を使用して<xref:System.Windows.Controls.StackPanel>します。</span><span class="sxs-lookup"><span data-stu-id="f3f86-107">The following example vertically stacks five <xref:System.Windows.Controls.TextBlock> controls, each with a different <xref:System.Windows.Controls.Border> and <xref:System.Windows.Controls.Border.Background%2A>, by using <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="f3f86-108">子要素を持つ指定されていない<xref:System.Windows.FrameworkElement.Width%2A>に親ウィンドウに合わせて伸縮。 ただし、子要素がある、指定した<xref:System.Windows.FrameworkElement.Width%2A>、ウィンドウ内で中央揃えされます。</span><span class="sxs-lookup"><span data-stu-id="f3f86-108">The child elements that have no specified <xref:System.Windows.FrameworkElement.Width%2A> stretch to fill the parent window; however, the child elements that have a specified <xref:System.Windows.FrameworkElement.Width%2A>, are centered within the window.</span></span>  
  
 <span data-ttu-id="f3f86-109">既定のスタック方向、<xref:System.Windows.Controls.StackPanel>が垂直方向。</span><span class="sxs-lookup"><span data-stu-id="f3f86-109">The default stack direction in a <xref:System.Windows.Controls.StackPanel> is vertical.</span></span> <span data-ttu-id="f3f86-110">コンテンツの流れを制御する、<xref:System.Windows.Controls.StackPanel>を使用して、<xref:System.Windows.Controls.StackPanel.Orientation%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="f3f86-110">To control content flow in a <xref:System.Windows.Controls.StackPanel>, use the <xref:System.Windows.Controls.StackPanel.Orientation%2A> property.</span></span> <span data-ttu-id="f3f86-111">使用して水平方向の配置を制御することができます、<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="f3f86-111">You can control horizontal alignment by using the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property.</span></span>  
  
```xaml  
<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" WindowTitle="StackPanel Sample">  
  <StackPanel>  
    <Border Background="SkyBlue" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="12">Stacked Item #1</TextBlock>  
    </Border>  
    <Border Width="400" Background="CadetBlue" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="14">Stacked Item #2</TextBlock>  
    </Border>  
    <Border Background="LightGoldenRodYellow" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="16">Stacked Item #3</TextBlock>  
    </Border>  
    <Border Width="200" Background="PaleGreen" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="18">Stacked Item #4</TextBlock>  
    </Border>  
    <Border Background="White" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="20">Stacked Item #5</TextBlock>  
    </Border>  
  </StackPanel>  
</Page>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f3f86-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3f86-112">See also</span></span>

- <xref:System.Windows.Controls.StackPanel>
- [<span data-ttu-id="f3f86-113">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="f3f86-113">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="f3f86-114">方法トピック</span><span class="sxs-lookup"><span data-stu-id="f3f86-114">How-to Topics</span></span>](stackpanel-how-to-topics.md)
