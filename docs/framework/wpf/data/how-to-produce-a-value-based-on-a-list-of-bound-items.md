---
title: '方法 : バインドされた項目の一覧に基づいて値を生成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], MultiBinding
- Multibinding [WPF]
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
ms.openlocfilehash: da183a34eb85de54b1e3f54f8d14c09e25640165
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459693"
---
# <a name="how-to-produce-a-value-based-on-a-list-of-bound-items"></a><span data-ttu-id="1561b-102">方法 : バインドされた項目の一覧に基づいて値を生成する</span><span class="sxs-lookup"><span data-stu-id="1561b-102">How to: Produce a Value Based on a List of Bound Items</span></span>
<span data-ttu-id="1561b-103"><xref:System.Windows.Data.MultiBinding> を使用すると、バインディングターゲットプロパティをソースプロパティのリストにバインドし、指定された入力で値を生成するロジックを適用できます。</span><span class="sxs-lookup"><span data-stu-id="1561b-103"><xref:System.Windows.Data.MultiBinding> allows you to bind a binding target property to a list of source properties and then apply logic to produce a value with the given inputs.</span></span> <span data-ttu-id="1561b-104">この例では、<xref:System.Windows.Data.MultiBinding>を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1561b-104">This example demonstrates how to use <xref:System.Windows.Data.MultiBinding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1561b-105">例</span><span class="sxs-lookup"><span data-stu-id="1561b-105">Example</span></span>  
 <span data-ttu-id="1561b-106">次の例では、`NameListData` は、`PersonName` オブジェクトのコレクションを参照します。このオブジェクトは、`firstName` と `lastName` の 2 つのプロパティを含みます。</span><span class="sxs-lookup"><span data-stu-id="1561b-106">In the following example, `NameListData` refers to a collection of `PersonName` objects, which are objects that contain two properties, `firstName` and `lastName`.</span></span> <span data-ttu-id="1561b-107">次の例では、姓が最初の人の姓と名を示す <xref:System.Windows.Controls.TextBlock> を生成します。</span><span class="sxs-lookup"><span data-stu-id="1561b-107">The following example produces a <xref:System.Windows.Controls.TextBlock> that shows the first and last names of a person with the last name first.</span></span>  
  
 [!code-xaml[MultiBinding#Resources1](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xaml[MultiBinding#Resources2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xaml[MultiBinding#MultiBindingTextBox2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xaml[MultiBinding#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 <span data-ttu-id="1561b-108">姓が先の形式を生成する方法を理解するには、次に示す `NameConverter` の実装をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1561b-108">To understand how the last-name-first format is produced, let's take a look at the implementation of the `NameConverter`:</span></span>  
  
 [!code-csharp[MultiBinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 <span data-ttu-id="1561b-109">`NameConverter` は、<xref:System.Windows.Data.IMultiValueConverter> インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="1561b-109">`NameConverter` implements the <xref:System.Windows.Data.IMultiValueConverter> interface.</span></span> <span data-ttu-id="1561b-110">`NameConverter` は、個々のバインディングから値を受け取り、それらを値のオブジェクト配列に格納します。</span><span class="sxs-lookup"><span data-stu-id="1561b-110">`NameConverter` takes the values from the individual bindings and stores them in the values object array.</span></span> <span data-ttu-id="1561b-111"><xref:System.Windows.Data.Binding> 要素が <xref:System.Windows.Data.MultiBinding> 要素の下に表示される順序は、これらの値が配列に格納される順序です。</span><span class="sxs-lookup"><span data-stu-id="1561b-111">The order in which the <xref:System.Windows.Data.Binding> elements appear under the <xref:System.Windows.Data.MultiBinding> element is the order in which those values are stored in the array.</span></span> <span data-ttu-id="1561b-112"><xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> 属性の値は、<xref:System.Windows.Data.MultiBinding.Converter%2A> メソッドのパラメーター引数によって参照されます。このメソッドは、パラメーターに対してスイッチを実行し、名前の書式設定方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="1561b-112">The value of the <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> attribute is referenced by the parameter argument of the <xref:System.Windows.Data.MultiBinding.Converter%2A> method, which performs a switch on the parameter to determine how to format the name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1561b-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="1561b-113">See also</span></span>

- [<span data-ttu-id="1561b-114">バインドされたデータを変換する</span><span class="sxs-lookup"><span data-stu-id="1561b-114">Convert Bound Data</span></span>](how-to-convert-bound-data.md)
- [<span data-ttu-id="1561b-115">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="1561b-115">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="1561b-116">方法トピック</span><span class="sxs-lookup"><span data-stu-id="1561b-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
