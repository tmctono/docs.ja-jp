---
title: '方法: XAML を使用してテーブルを定義する'
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], defining tables
- documents [WPF], defining tables with XAML
- tables [WPF], defining with XAML
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
ms.openlocfilehash: 011f612527f0c9e89ec05643edbb95b2d908488c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776582"
---
# <a name="how-to-define-a-table-with-xaml"></a><span data-ttu-id="efa18-102">方法: XAML を使用してテーブルを定義する</span><span class="sxs-lookup"><span data-stu-id="efa18-102">How to: Define a Table with XAML</span></span>
<span data-ttu-id="efa18-103">次の例では、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] を使用して、<xref:System.Windows.Documents.Table> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="efa18-103">The following example demonstrates how to define a <xref:System.Windows.Documents.Table> using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  <span data-ttu-id="efa18-104">このテーブル例には、(<xref:System.Windows.Documents.TableColumn> によって表される) 4 つの列と (<xref:System.Windows.Documents.TableRow> によって表される) いくつかの行があります。それらには、データの他にタイトル、ヘッダー、およびフッター情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="efa18-104">The example table has four columns (represented by <xref:System.Windows.Documents.TableColumn> elements) and several rows (represented by <xref:System.Windows.Documents.TableRow> elements) containing data as well as title, header, and footer information.</span></span>  <span data-ttu-id="efa18-105">行は <xref:System.Windows.Documents.TableRowGroup> 要素に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="efa18-105">Rows must be contained in a <xref:System.Windows.Documents.TableRowGroup> element.</span></span>  <span data-ttu-id="efa18-106">テーブルの各行は、(<xref:System.Windows.Documents.TableCell> 要素によって表される) 1 つ以上のセルで構成されています。</span><span class="sxs-lookup"><span data-stu-id="efa18-106">Each row in the table is comprised of one or more cells (represented by <xref:System.Windows.Documents.TableCell> elements).</span></span>  <span data-ttu-id="efa18-107">テーブルのセルのコンテンツは、この場合は <xref:System.Windows.Documents.Paragraph> 要素である <xref:System.Windows.Documents.Block> 要素に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="efa18-107">Content in a table cell must be contained in a <xref:System.Windows.Documents.Block> element; in this case <xref:System.Windows.Documents.Paragraph> elements are used.</span></span>  <span data-ttu-id="efa18-108">このテーブルには、(<xref:System.Windows.Documents.Hyperlink> 要素によって表される) ハイパーリンクもフッター行にあります。</span><span class="sxs-lookup"><span data-stu-id="efa18-108">The table also hosts a hyperlink (represented by the <xref:System.Windows.Documents.Hyperlink> element) in the footer row.</span></span>  
  
## <a name="example"></a><span data-ttu-id="efa18-109">例</span><span class="sxs-lookup"><span data-stu-id="efa18-109">Example</span></span>  
 [!code-xaml[TableSnippetsXAML#_TableXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 <span data-ttu-id="efa18-110">この例で定義したテーブルのレンダリング結果は、次の図のとおりです。</span><span class="sxs-lookup"><span data-stu-id="efa18-110">The following figure shows how the table defined in this example renders:</span></span>  
  
 ![XAML で定義したテーブルのスクリーンショット。](./media/how-to-define-a-table-with-xaml/planetary-information-xaml-table.png)
