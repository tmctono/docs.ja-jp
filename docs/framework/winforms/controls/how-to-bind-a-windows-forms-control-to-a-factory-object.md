---
title: コントロールをファクトリオブジェクトにバインドする
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], binding
- factory objects [Windows Forms], binding to
- BindingSource component [Windows Forms], binding to a factory object
- BindingSource component [Windows Forms], examples
ms.assetid: 7d59af89-ff82-41d8-a48a-f1fbae788b0d
ms.openlocfilehash: 2b4d9aca3345a0cb1e7e995f66a8982dee983ca8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745097"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-factory-object"></a><span data-ttu-id="9fe7b-102">方法 : Windows フォーム コントロールをファクトリ オブジェクトにバインドする</span><span class="sxs-lookup"><span data-stu-id="9fe7b-102">How to: Bind a Windows Forms Control to a Factory Object</span></span>
<span data-ttu-id="9fe7b-103">データをやり取りするコントロールを作成している際に、他のオブジェクトを生成するオブジェクトやメソッドにコントロールをバインドすることが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="9fe7b-103">When you are building controls that interact with data, you will sometimes find it necessary to bind a control to an object or method that generates other objects.</span></span> <span data-ttu-id="9fe7b-104">このようなオブジェクトやメソッドは、ファクトリと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="9fe7b-104">Such an object or method is called a factory.</span></span> <span data-ttu-id="9fe7b-105">たとえば、データ ソースがメモリまたは型内のオブジェクトではなく、メソッドの呼び出しからの戻り値の場合があります。</span><span class="sxs-lookup"><span data-stu-id="9fe7b-105">Your data source might be, for example, the return value from a method call, instead of an object in memory or a type.</span></span> <span data-ttu-id="9fe7b-106">ソースがコレクションを返す限り、コントロールをこの種類のデータ ソースにバインドできます。</span><span class="sxs-lookup"><span data-stu-id="9fe7b-106">You can bind a control to this kind of data source as long as the source returns a collection.</span></span>  
  
 <span data-ttu-id="9fe7b-107"><xref:System.Windows.Forms.BindingSource> コントロールを使用して、コントロールをファクトリ オブジェクトに簡単にバインドすることができます。</span><span class="sxs-lookup"><span data-stu-id="9fe7b-107">You can easily bind a control to a factory object by using the <xref:System.Windows.Forms.BindingSource> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fe7b-108">例</span><span class="sxs-lookup"><span data-stu-id="9fe7b-108">Example</span></span>  
 <span data-ttu-id="9fe7b-109">次の例では、<xref:System.Windows.Forms.DataGridView> コントロールを使用して、<xref:System.Windows.Forms.BindingSource> コントロールをファクトリ メソッドにバインドする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9fe7b-109">The following example demonstrates how to bind a <xref:System.Windows.Forms.DataGridView> control to a factory method by using a <xref:System.Windows.Forms.BindingSource> control.</span></span> <span data-ttu-id="9fe7b-110">ファクトリ メソッドの名前は `GetOrdersByCustomerId` であり、Northwind データベースで、特定の顧客のすべての注文を返します。</span><span class="sxs-lookup"><span data-stu-id="9fe7b-110">The factory method is named `GetOrdersByCustomerId`, and it returns all the orders for a given customer in the Northwind database.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.BindToFactory#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.BindToFactory#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindToFactory#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9fe7b-111">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="9fe7b-111">Compiling the Code</span></span>  
 <span data-ttu-id="9fe7b-112">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9fe7b-112">This example requires:</span></span>  
  
- <span data-ttu-id="9fe7b-113">System、System.Data、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="9fe7b-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fe7b-114">参照</span><span class="sxs-lookup"><span data-stu-id="9fe7b-114">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="9fe7b-115">BindingSource コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9fe7b-115">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="9fe7b-116">方法: Windows フォーム コントロールを型にバインドする</span><span class="sxs-lookup"><span data-stu-id="9fe7b-116">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
