---
title: '方法: バインドされた項目の一覧に基づいて値を生成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], MultiBinding
- Multibinding [WPF]
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
ms.openlocfilehash: c2ec5ff26c89649294df266e790445e5aa5d08ae
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200520"
---
# <a name="how-to-produce-a-value-based-on-a-list-of-bound-items"></a><span data-ttu-id="53fdf-102">方法: バインドされた項目の一覧に基づいて値を生成する</span><span class="sxs-lookup"><span data-stu-id="53fdf-102">How to: Produce a Value Based on a List of Bound Items</span></span>
<xref:System.Windows.Data.MultiBinding> <span data-ttu-id="53fdf-103">ソースのプロパティの一覧にバインディング ターゲット プロパティをバインドし、特定の入力で値を生成するためのロジックを適用できます。</span><span class="sxs-lookup"><span data-stu-id="53fdf-103">allows you to bind a binding target property to a list of source properties and then apply logic to produce a value with the given inputs.</span></span> <span data-ttu-id="53fdf-104">この例を使用して、<xref:System.Windows.Data.MultiBinding>します。</span><span class="sxs-lookup"><span data-stu-id="53fdf-104">This example demonstrates how to use <xref:System.Windows.Data.MultiBinding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53fdf-105">例</span><span class="sxs-lookup"><span data-stu-id="53fdf-105">Example</span></span>  
 <span data-ttu-id="53fdf-106">次の例では、`NameListData` は、`PersonName` オブジェクトのコレクションを参照します。このオブジェクトは、`firstName` と `lastName` の 2 つのプロパティを含みます。</span><span class="sxs-lookup"><span data-stu-id="53fdf-106">In the following example, `NameListData` refers to a collection of `PersonName` objects, which are objects that contain two properties, `firstName` and `lastName`.</span></span> <span data-ttu-id="53fdf-107">次の例で、<xref:System.Windows.Controls.TextBlock>最後の名前を持つ人物の姓と名の最初を示します。</span><span class="sxs-lookup"><span data-stu-id="53fdf-107">The following example produces a <xref:System.Windows.Controls.TextBlock> that shows the first and last names of a person with the last name first.</span></span>  
  
 [!code-xaml[MultiBinding#Resources1](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xaml[MultiBinding#Resources2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xaml[MultiBinding#MultiBindingTextBox2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xaml[MultiBinding#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 <span data-ttu-id="53fdf-108">姓が先の形式を生成する方法を理解するには、次に示す `NameConverter` の実装をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="53fdf-108">To understand how the last-name-first format is produced, let's take a look at the implementation of the `NameConverter`:</span></span>  
  
 [!code-csharp[MultiBinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 `NameConverter` <span data-ttu-id="53fdf-109">実装、<xref:System.Windows.Data.IMultiValueConverter>インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="53fdf-109">implements the <xref:System.Windows.Data.IMultiValueConverter> interface.</span></span> `NameConverter` <span data-ttu-id="53fdf-110">個々 のバインディングから値を取得し、値オブジェクトの配列に格納します。</span><span class="sxs-lookup"><span data-stu-id="53fdf-110">takes the values from the individual bindings and stores them in the values object array.</span></span> <span data-ttu-id="53fdf-111">順序、<xref:System.Windows.Data.Binding>要素は、下に表示されます、<xref:System.Windows.Data.MultiBinding>要素は、これらの値が配列に格納されている順序。</span><span class="sxs-lookup"><span data-stu-id="53fdf-111">The order in which the <xref:System.Windows.Data.Binding> elements appear under the <xref:System.Windows.Data.MultiBinding> element is the order in which those values are stored in the array.</span></span> <span data-ttu-id="53fdf-112">値、<xref:System.Windows.Data.MultiBinding.ConverterParameter%2A>のパラメーターの引数によって参照される属性、<xref:System.Windows.Data.MultiBinding.Converter%2A>メソッドで、名前を書式設定する方法を決定するパラメーターの切り替えを実行します。</span><span class="sxs-lookup"><span data-stu-id="53fdf-112">The value of the <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> attribute is referenced by the parameter argument of the <xref:System.Windows.Data.MultiBinding.Converter%2A> method, which performs a switch on the parameter to determine how to format the name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53fdf-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="53fdf-113">See also</span></span>

- [<span data-ttu-id="53fdf-114">バインドされたデータを変換する</span><span class="sxs-lookup"><span data-stu-id="53fdf-114">Convert Bound Data</span></span>](how-to-convert-bound-data.md)
- [<span data-ttu-id="53fdf-115">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="53fdf-115">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="53fdf-116">方法のトピック</span><span class="sxs-lookup"><span data-stu-id="53fdf-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
