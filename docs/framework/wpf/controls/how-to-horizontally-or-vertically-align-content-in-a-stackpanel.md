---
title: '方法: StackPanel にコンテンツを水平方向または垂直方向に配置する'
description: Windows Presentation Foundation の StackPanel でコンテンツの向き、および子コンテンツの HorizontalAlignment と VerticalAlignment を調整する方法について学習します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StackPanel control [WPF], content alignment [WPF]
- content alignment [WPF]
- aligning [WPF], content
ms.assetid: c1e8f962-72c8-4e7a-8670-7a2d7e021791
ms.openlocfilehash: d3c7215d8193d1d8a72597c44cf265f5bd400ea1
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167631"
---
# <a name="how-to-horizontally-or-vertically-align-content-in-a-stackpanel"></a>方法: StackPanel にコンテンツを水平方向または垂直方向に配置する
この例では、<xref:System.Windows.Controls.StackPanel> 要素内のコンテンツの <xref:System.Windows.Controls.StackPanel.Orientation%2A> を調整する方法、および子コンテンツの <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> と <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> を調整する方法を示します。  
  
## <a name="example"></a>例  
 次の例では、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] で 3 つの <xref:System.Windows.Controls.ListBox> 要素を作成します。 各 <xref:System.Windows.Controls.ListBox> は、<xref:System.Windows.Controls.StackPanel> の <xref:System.Windows.Controls.StackPanel.Orientation%2A>、<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>、<xref:System.Windows.FrameworkElement.VerticalAlignment%2A> プロパティの使用可能な値を表します。 ユーザーが <xref:System.Windows.Controls.ListBox> 要素のいずれかの値を選択すると、<xref:System.Windows.Controls.StackPanel> の関連付けられたプロパティとその子要素の <xref:System.Windows.Controls.Button> が変更されます。  
  
 [!code-xaml[StackPanelIntroSamp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml#1)]  
  
 次の分離コード ファイルによって、<xref:System.Windows.Controls.ListBox> 選択の変更に関連付けられているイベントへの変更が定義されます。 <xref:System.Windows.Controls.StackPanel> は <xref:System.Windows.FrameworkElement.Name%2A> `sp1` によって識別されます。  
  
 [!code-csharp[StackPanelIntroSamp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[StackPanelIntroSamp#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelIntroSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>
- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>
- [パネルの概要](panels-overview.md)
