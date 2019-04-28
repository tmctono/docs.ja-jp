---
title: '方法: SelectedValue、SelectedValuePath、および SelectedItem を使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], SelectedValue properties
- Control class [WPF], SelectedItem properties
- Control class [WPF], TreeView properties
- Control class [WPF], SelectedValue properties
- TreeView control [WPF], SelectedItem properties
- SelectedValue [WPF], SelectedValuePath properties
- TreeView control [WPF], SelectedValuePath properties
- Control class [WPF], SelectedValuePath properties
- SelectedValue [WPF], SelectedItem properties
ms.assetid: 2fc92ad4-f02c-4f89-bbe9-d4978a7af0db
ms.openlocfilehash: d9f7a8f04f53b7d38a49dfef2c947dfa1c2d263d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699137"
---
# <a name="how-to-use-selectedvalue-selectedvaluepath-and-selecteditem"></a><span data-ttu-id="4b4bb-102">方法: SelectedValue、SelectedValuePath、および SelectedItem を使用する</span><span class="sxs-lookup"><span data-stu-id="4b4bb-102">How to: Use SelectedValue, SelectedValuePath, and SelectedItem</span></span>
<span data-ttu-id="4b4bb-103">この例は、使用する方法を示します、<xref:System.Windows.Controls.TreeView.SelectedValue%2A>と<xref:System.Windows.Controls.TreeView.SelectedValuePath%2A>プロパティの値を指定する、<xref:System.Windows.Controls.TreeView.SelectedItem%2A>の<xref:System.Windows.Controls.TreeView>します。</span><span class="sxs-lookup"><span data-stu-id="4b4bb-103">This example shows how to use the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> and <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> properties to specify a value for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> of a <xref:System.Windows.Controls.TreeView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b4bb-104">例</span><span class="sxs-lookup"><span data-stu-id="4b4bb-104">Example</span></span>  
 <span data-ttu-id="4b4bb-105"><xref:System.Windows.Controls.TreeView.SelectedValuePath%2A>プロパティを指定する方法を提供する、<xref:System.Windows.Controls.TreeView.SelectedValue%2A>の<xref:System.Windows.Controls.TreeView.SelectedItem%2A>で、<xref:System.Windows.Controls.TreeView>します。</span><span class="sxs-lookup"><span data-stu-id="4b4bb-105">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property provides a way to specify a <xref:System.Windows.Controls.TreeView.SelectedValue%2A> for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> in a <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="4b4bb-106"><xref:System.Windows.Controls.TreeView.SelectedItem%2A>内のオブジェクトを表す、<xref:System.Windows.Controls.ItemsControl.Items%2A>コレクションと<xref:System.Windows.Controls.TreeView>選択された項目の 1 つのプロパティの値を表示します。</span><span class="sxs-lookup"><span data-stu-id="4b4bb-106">The <xref:System.Windows.Controls.TreeView.SelectedItem%2A> represents an object in the <xref:System.Windows.Controls.ItemsControl.Items%2A> collection and the <xref:System.Windows.Controls.TreeView> displays the value of a single property of the selected item.</span></span> <span data-ttu-id="4b4bb-107"><xref:System.Windows.Controls.TreeView.SelectedValuePath%2A>プロパティの値を決定するために使用されるプロパティへのパスを指定します、<xref:System.Windows.Controls.TreeView.SelectedValue%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="4b4bb-107">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property specifies the path to the property that is used to determine the value of the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property.</span></span> <span data-ttu-id="4b4bb-108">このトピックの例では、この概念を示します。</span><span class="sxs-lookup"><span data-stu-id="4b4bb-108">The examples in this topic illustrate this concept.</span></span>  
  
 <span data-ttu-id="4b4bb-109">次の例は、<xref:System.Windows.Data.XmlDataProvider>従業員情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="4b4bb-109">The following example shows an <xref:System.Windows.Data.XmlDataProvider> that contains employee information.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#XMLDataProvider](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 <span data-ttu-id="4b4bb-110">次の例では、定義、<xref:System.Windows.HierarchicalDataTemplate>を表示する、`EmployeeName`と`EmployeeWorkDay`の`Employee`します。</span><span class="sxs-lookup"><span data-stu-id="4b4bb-110">The following example defines a <xref:System.Windows.HierarchicalDataTemplate> that displays the `EmployeeName` and `EmployeeWorkDay` of the `Employee`.</span></span> <span data-ttu-id="4b4bb-111">なお、<xref:System.Windows.HierarchicalDataTemplate>で指定されていない、`EmployeeNumber`テンプレートの一部として。</span><span class="sxs-lookup"><span data-stu-id="4b4bb-111">Note that the <xref:System.Windows.HierarchicalDataTemplate> does not specify the `EmployeeNumber` as part of the template.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#HierarchicalDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 <span data-ttu-id="4b4bb-112">次の例は、<xref:System.Windows.Controls.TreeView>を使用して、以前に定義された<xref:System.Windows.HierarchicalDataTemplate>設定して、<xref:System.Windows.Controls.TreeView.SelectedValue%2A>プロパティを`EmployeeNumber`します。</span><span class="sxs-lookup"><span data-stu-id="4b4bb-112">The following example shows a <xref:System.Windows.Controls.TreeView> that uses the previously defined <xref:System.Windows.HierarchicalDataTemplate> and that sets the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property to the `EmployeeNumber`.</span></span> <span data-ttu-id="4b4bb-113">選択すると、`EmployeeName`で、 <xref:System.Windows.Controls.TreeView>、<xref:System.Windows.Controls.TreeView.SelectedItem%2A>プロパティが返す、`EmployeeInfo`に、選択した対応するデータ項目`EmployeeName`します。</span><span class="sxs-lookup"><span data-stu-id="4b4bb-113">When you select an `EmployeeName` in the <xref:System.Windows.Controls.TreeView>, the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> property returns the `EmployeeInfo` data item that corresponds to the selected `EmployeeName`.</span></span> <span data-ttu-id="4b4bb-114">ただし、ため、<xref:System.Windows.Controls.TreeView.SelectedValuePath%2A>この<xref:System.Windows.Controls.TreeView>に設定されている`EmployeeNumber`、<xref:System.Windows.Controls.TreeView.SelectedValue%2A>に設定されている、`EmployeeNumber`します。</span><span class="sxs-lookup"><span data-stu-id="4b4bb-114">However, because the <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> of this <xref:System.Windows.Controls.TreeView> is set to `EmployeeNumber`, the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> is set to the `EmployeeNumber`.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#SelectedValuePath](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## <a name="see-also"></a><span data-ttu-id="4b4bb-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b4bb-115">See also</span></span>

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [<span data-ttu-id="4b4bb-116">TreeView の概要</span><span class="sxs-lookup"><span data-stu-id="4b4bb-116">TreeView Overview</span></span>](treeview-overview.md)
- [<span data-ttu-id="4b4bb-117">方法トピック</span><span class="sxs-lookup"><span data-stu-id="4b4bb-117">How-to Topics</span></span>](treeview-how-to-topics.md)
