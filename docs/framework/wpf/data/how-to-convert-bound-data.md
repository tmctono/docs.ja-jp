---
title: '方法 : バインドされたデータを変換する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- converting [WPF], bound data
- data binding [WPF], converting bound data
- binding data [WPF], converting bound data
ms.assetid: b00aaa19-c6df-4c3b-a9fd-88a0b488df2b
ms.openlocfilehash: f9ad390626092d481bf47f017f643a29302c1b29
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458858"
---
# <a name="how-to-convert-bound-data"></a><span data-ttu-id="15206-102">方法 : バインドされたデータを変換する</span><span class="sxs-lookup"><span data-stu-id="15206-102">How to: Convert Bound Data</span></span>
<span data-ttu-id="15206-103">この例では、バインディングで使用されるデータへの変換を適用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="15206-103">This example shows how to apply conversion to data that is used in bindings.</span></span>  
  
 <span data-ttu-id="15206-104">バインド時にデータを変換するには、<xref:System.Windows.Data.IValueConverter> インターフェイスを実装するクラスを作成する必要があります。これには、<xref:System.Windows.Data.IValueConverter.Convert%2A> メソッドと <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> メソッドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="15206-104">To convert data during binding, you must create a class that implements the <xref:System.Windows.Data.IValueConverter> interface, which includes the <xref:System.Windows.Data.IValueConverter.Convert%2A> and <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15206-105">例</span><span class="sxs-lookup"><span data-stu-id="15206-105">Example</span></span>  
 <span data-ttu-id="15206-106">次の例は、年、月、および日のみが表示されるように、渡された日付値を変換する日付コンバーターの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="15206-106">The following example shows the implementation of a date converter that converts the date value passed in so that it only shows the year, the month, and the day.</span></span> <span data-ttu-id="15206-107"><xref:System.Windows.Data.IValueConverter> インターフェイスを実装する場合は、次の例のように、実装を <xref:System.Windows.Data.ValueConversionAttribute> 属性で装飾して、変換に関係するデータ型を開発ツールに示すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="15206-107">When implementing the <xref:System.Windows.Data.IValueConverter> interface, it is a good practice to decorate the implementation with a <xref:System.Windows.Data.ValueConversionAttribute> attribute to indicate to development tools the data types involved in the conversion, as in the following example:</span></span>  
  
 [!code-csharp[DataBindingLab#18](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 <span data-ttu-id="15206-108">コンバーターを作成したら、それをリソースとして [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] ファイルに追加できます。</span><span class="sxs-lookup"><span data-stu-id="15206-108">Once you have created a converter, you can add it as a resource in your [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="15206-109">次の例では、 *src*は*DateConverter*が定義されている名前空間にマップされます。</span><span class="sxs-lookup"><span data-stu-id="15206-109">In the following example, *src* maps to the namespace in which *DateConverter* is defined.</span></span>  
  
 [!code-xaml[DataBindingLab#15](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 <span data-ttu-id="15206-110">最後に、次の構文を使用して、バインドでコンバーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="15206-110">Finally, you can use the converter in your binding using the following syntax.</span></span> <span data-ttu-id="15206-111">次の例では、<xref:System.Windows.Controls.TextBlock> のテキストコンテンツが、外部データソースのプロパティである*StartDate*にバインドされています。</span><span class="sxs-lookup"><span data-stu-id="15206-111">In the following example, the text content of the <xref:System.Windows.Controls.TextBlock> is bound to *StartDate*, which is a property of an external data source.</span></span>  
  
 [!code-xaml[DataBindingLab#17](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 <span data-ttu-id="15206-112">上の例で参照されているスタイルリソースは、このトピックに記載されていないリソースセクションで定義されています。</span><span class="sxs-lookup"><span data-stu-id="15206-112">The style resources referenced in the above example are defined in a resource section not shown in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15206-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="15206-113">See also</span></span>

- [<span data-ttu-id="15206-114">バインディングの検証の実装</span><span class="sxs-lookup"><span data-stu-id="15206-114">Implement Binding Validation</span></span>](how-to-implement-binding-validation.md)
- [<span data-ttu-id="15206-115">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="15206-115">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="15206-116">方法トピック</span><span class="sxs-lookup"><span data-stu-id="15206-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
