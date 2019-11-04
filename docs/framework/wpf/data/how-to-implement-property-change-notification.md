---
title: '方法 : プロパティの変更通知を実装する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- notifications of change [WPF]
- data binding [WPF], property change notifications
- change notifications [WPF]
- properties [WPF], change notifications
ms.assetid: 30b59d9e-8c3a-4349-aa82-4be837e841cf
ms.openlocfilehash: 4f9ff49a443577e119b0c1079abbe23bd7ede4c4
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459748"
---
# <a name="how-to-implement-property-change-notification"></a><span data-ttu-id="4d286-102">方法 : プロパティの変更通知を実装する</span><span class="sxs-lookup"><span data-stu-id="4d286-102">How to: Implement Property Change Notification</span></span>
<span data-ttu-id="4d286-103">バインディングターゲットプロパティでバインドソースの動的な変更を自動的に反映できるように <xref:System.Windows.Data.BindingMode.OneWay> または <xref:System.Windows.Data.BindingMode.TwoWay> バインディングをサポートするには (たとえば、ユーザーがフォームを編集したときにプレビューウィンドウが自動的に更新されるようにするため)、クラスは次のようにする必要があります。適切なプロパティ変更通知を提供します。</span><span class="sxs-lookup"><span data-stu-id="4d286-103">To support <xref:System.Windows.Data.BindingMode.OneWay> or <xref:System.Windows.Data.BindingMode.TwoWay> binding to enable your binding target properties to automatically reflect the dynamic changes of the binding source (for example, to have the preview pane updated automatically when the user edits a form), your class needs to provide the proper property changed notifications.</span></span> <span data-ttu-id="4d286-104">この例では、<xref:System.ComponentModel.INotifyPropertyChanged>を実装するクラスを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4d286-104">This example shows how to create a class that implements <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d286-105">例</span><span class="sxs-lookup"><span data-stu-id="4d286-105">Example</span></span>  
 <span data-ttu-id="4d286-106"><xref:System.ComponentModel.INotifyPropertyChanged> を実装するには、<xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> イベントを宣言し、`OnPropertyChanged` メソッドを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d286-106">To implement <xref:System.ComponentModel.INotifyPropertyChanged> you need to declare the <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> event and create the `OnPropertyChanged` method.</span></span> <span data-ttu-id="4d286-107">次に、変更を通知する必要のある各プロパティについて、そのプロパティが更新されるたびに `OnPropertyChanged` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4d286-107">Then for each property you want change notifications for, you call `OnPropertyChanged` whenever the property is updated.</span></span>  
  
 [!code-csharp[SimpleBinding#PersonClass](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 <span data-ttu-id="4d286-108">`Person` クラスを使用して <xref:System.Windows.Data.BindingMode.TwoWay> バインディングをサポートする方法の例については、「 [TextBox テキストでソースを更新するタイミングを制御](how-to-control-when-the-textbox-text-updates-the-source.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d286-108">To see an example of how the `Person` class can be used to support <xref:System.Windows.Data.BindingMode.TwoWay> binding, see [Control When the TextBox Text Updates the Source](how-to-control-when-the-textbox-text-updates-the-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d286-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d286-109">See also</span></span>

- [<span data-ttu-id="4d286-110">バインディング ソースの概要</span><span class="sxs-lookup"><span data-stu-id="4d286-110">Binding Sources Overview</span></span>](binding-sources-overview.md)
- [<span data-ttu-id="4d286-111">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="4d286-111">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="4d286-112">方法トピック</span><span class="sxs-lookup"><span data-stu-id="4d286-112">How-to Topics</span></span>](data-binding-how-to-topics.md)
