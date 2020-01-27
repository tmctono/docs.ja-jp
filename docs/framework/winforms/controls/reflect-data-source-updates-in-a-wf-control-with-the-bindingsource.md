---
title: BindingSource を使用したコントロールでのデータソースの更新の反映
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data binding [Windows Forms], updating
- BindingSource component [Windows Forms], updating data binding
- examples [Windows Forms], BindingSource component
- data sources [Windows Forms], updating
- BindingSource component [Windows Forms], examples
ms.assetid: bd8bd9b2-af8a-4f11-a3d5-54eecbe2400b
ms.openlocfilehash: f98296b477dbb674cdbdbd8d03e291dd6ca0c8a3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742437"
---
# <a name="how-to-reflect-data-source-updates-in-a-windows-forms-control-with-the-bindingsource"></a><span data-ttu-id="d5b8d-102">方法 : BindingSource を使用して Windows フォーム コントロール内にデータ ソースの更新を反映させる</span><span class="sxs-lookup"><span data-stu-id="d5b8d-102">How to: Reflect Data Source Updates in a Windows Forms Control with the BindingSource</span></span>
<span data-ttu-id="d5b8d-103">データ バインド コントロールを使用する場合、データ ソースがリスト変更イベントを発生させないことがあります。そのようなケースで、データ ソース内の変更に応答する必要が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="d5b8d-103">When you use data-bound controls, you sometimes have to respond to changes in the data source when the data source does not raise list-changed events.</span></span> <span data-ttu-id="d5b8d-104"><xref:System.Windows.Forms.BindingSource> コンポーネントを使用してデータ ソースを Windows フォーム コントロールにバインドすれば、データ ソースが変更されたことを <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> メソッドを呼び出すことによってコントロールに通知できます。</span><span class="sxs-lookup"><span data-stu-id="d5b8d-104">When you use the <xref:System.Windows.Forms.BindingSource> component to bind your data source to a Windows Forms control, you can notify the control that your data source has changed by calling the <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5b8d-105">使用例</span><span class="sxs-lookup"><span data-stu-id="d5b8d-105">Example</span></span>  
 <span data-ttu-id="d5b8d-106">次のコード例では、バインドされたコントロールにデータ ソース内の更新について <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> メソッドを使用して通知する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d5b8d-106">The following code example demonstrates using the <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> method to notify a bound control about an update in the data source.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d5b8d-107">コードのコンパイル方法</span><span class="sxs-lookup"><span data-stu-id="d5b8d-107">Compiling the Code</span></span>  
 <span data-ttu-id="d5b8d-108">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d5b8d-108">This example requires:</span></span>  
  
- <span data-ttu-id="d5b8d-109">System、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="d5b8d-109">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5b8d-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5b8d-110">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="d5b8d-111">BindingSource コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d5b8d-111">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="d5b8d-112">方法 : Windows フォーム コントロールを型にバインドする</span><span class="sxs-lookup"><span data-stu-id="d5b8d-112">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
