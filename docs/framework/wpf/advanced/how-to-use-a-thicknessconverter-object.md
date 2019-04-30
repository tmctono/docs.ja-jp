---
title: '方法: ThicknessConverter オブジェクトを使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF]
- ThicknessConverter objects [WPF]
ms.assetid: 52682194-d7fd-499c-8005-73fcc84e7b2c
ms.openlocfilehash: ebfb8642a01f6d602f4e5ffa58fde6a8ee0b4e1f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62001482"
---
# <a name="how-to-use-a-thicknessconverter-object"></a><span data-ttu-id="6c0f6-102">方法: ThicknessConverter オブジェクトを使用する</span><span class="sxs-lookup"><span data-stu-id="6c0f6-102">How to: Use a ThicknessConverter Object</span></span>
## <a name="example"></a><span data-ttu-id="6c0f6-103">例</span><span class="sxs-lookup"><span data-stu-id="6c0f6-103">Example</span></span>  
 <span data-ttu-id="6c0f6-104">この例のインスタンスを作成する方法を示しています。<xref:System.Windows.ThicknessConverter>境界線の太さを変更するとします。</span><span class="sxs-lookup"><span data-stu-id="6c0f6-104">This example shows how to create an instance of <xref:System.Windows.ThicknessConverter> and use it to change the thickness of a border.</span></span>  
  
 <span data-ttu-id="6c0f6-105">例では、呼び出されるカスタム メソッドを定義します`changeThickness`; このメソッドは、最初の内容を変換、<xref:System.Windows.Controls.ListBoxItem>個別で定義されている、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]のインスタンスへのファイル<xref:System.Windows.Thickness>、後に、コンテンツに変換します、 <xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="6c0f6-105">The example defines a custom method called `changeThickness`; this method first converts the contents of a <xref:System.Windows.Controls.ListBoxItem>, as defined in a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file, to an instance of <xref:System.Windows.Thickness>, and later converts the content into a <xref:System.String>.</span></span> <span data-ttu-id="6c0f6-106">このメソッドは、<xref:System.Windows.Controls.ListBoxItem>に、<xref:System.Windows.ThicknessConverter>オブジェクトで、変換、<xref:System.Windows.Controls.ContentControl.Content%2A>の<xref:System.Windows.Controls.ListBoxItem>のインスタンスに<xref:System.Windows.Thickness>。</span><span class="sxs-lookup"><span data-stu-id="6c0f6-106">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.ThicknessConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Windows.Thickness>.</span></span> <span data-ttu-id="6c0f6-107">この値の値として戻されますが、<xref:System.Windows.Controls.Border.BorderThickness%2A>のプロパティ、<xref:System.Windows.Controls.Border>します。</span><span class="sxs-lookup"><span data-stu-id="6c0f6-107">This value is then passed back as the value of the <xref:System.Windows.Controls.Border.BorderThickness%2A> property of the <xref:System.Windows.Controls.Border>.</span></span>  
  
 <span data-ttu-id="6c0f6-108">この例は実行できません。</span><span class="sxs-lookup"><span data-stu-id="6c0f6-108">This example does not run.</span></span>  
  
 [!code-csharp[ThicknessConverter#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ThicknessConverter/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ThicknessConverter#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThicknessConverter/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6c0f6-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c0f6-109">See also</span></span>

- <xref:System.Windows.Thickness>
- <xref:System.Windows.ThicknessConverter>
- <xref:System.Windows.Controls.Border>
- <span data-ttu-id="6c0f6-110">[方法: Margin プロパティを変更します。](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms750561(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="6c0f6-110">[How to: Change the Margin Property](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms750561(v=vs.90))</span></span>
- <span data-ttu-id="6c0f6-111">[方法: ListBoxItem を新しいデータ型に変換します。](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms749147(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="6c0f6-111">[How to: Convert a ListBoxItem to a new Data Type](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms749147(v=vs.90))</span></span>
- [<span data-ttu-id="6c0f6-112">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="6c0f6-112">Panels Overview</span></span>](../controls/panels-overview.md)
