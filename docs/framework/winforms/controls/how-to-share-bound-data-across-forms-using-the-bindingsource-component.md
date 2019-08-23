---
title: '方法: BindingSource コンポーネントを使用してフォーム間でバインド データを共有する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], BindingSource component
- data binding [Windows Forms], sharing data across forms
- BindingSource component [Windows Forms], examples
- BindingSource [Windows Forms], using with multiple forms
ms.assetid: a1a49630-db9c-4485-b888-1f62a373a4f7
ms.openlocfilehash: aa497194fd4ac65f48773a45175333a1d862b453
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956074"
---
# <a name="how-to-share-bound-data-across-forms-using-the-bindingsource-component"></a><span data-ttu-id="cc97d-102">方法: BindingSource コンポーネントを使用してフォーム間でバインド データを共有する</span><span class="sxs-lookup"><span data-stu-id="cc97d-102">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>
<span data-ttu-id="cc97d-103"><xref:System.Windows.Forms.BindingSource> コンポーネントを使用してフォーム間でデータを簡単に共有できます。</span><span class="sxs-lookup"><span data-stu-id="cc97d-103">You can easily share data across forms using the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="cc97d-104">たとえば、データ ソースのデータを集計する 1 つの読み取り専用のフォームと、データ ソース内の現在選択されているアイテムについての詳細情報を含む別の編集可能なフォームを表示することがあります。</span><span class="sxs-lookup"><span data-stu-id="cc97d-104">For example, you may want to display one read-only form that summarizes the data-source data and another editable form that contains detailed information about the currently selected item in the data source.</span></span> <span data-ttu-id="cc97d-105">この例は、このシナリオを示しています。</span><span class="sxs-lookup"><span data-stu-id="cc97d-105">This example demonstrates this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc97d-106">例</span><span class="sxs-lookup"><span data-stu-id="cc97d-106">Example</span></span>  
 <span data-ttu-id="cc97d-107">次のコード例は、<xref:System.Windows.Forms.BindingSource> およびフォーム間でバインドされたデータを共有する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="cc97d-107">The following code example demonstrates how to share a <xref:System.Windows.Forms.BindingSource> and its bound data across forms.</span></span> <span data-ttu-id="cc97d-108">この例で、共有された <xref:System.Windows.Forms.BindingSource> が子フォームのコンストラクターに渡されます。</span><span class="sxs-lookup"><span data-stu-id="cc97d-108">In this example, the shared <xref:System.Windows.Forms.BindingSource> is passed to the constructor of the child form.</span></span> <span data-ttu-id="cc97d-109">子フォームでは、メイン フォームで現在選択されているアイテムのデータをユーザーが編集することができます。</span><span class="sxs-lookup"><span data-stu-id="cc97d-109">The child form allows the user to edit the data for the currently selected item in the main form.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cc97d-110">例の <xref:System.Windows.Forms.BindingSource> コンポーネントの <xref:System.Windows.Forms.BindingSource.BindingComplete> イベントは、2 つの形式が同期を保つために処理されます。</span><span class="sxs-lookup"><span data-stu-id="cc97d-110">The <xref:System.Windows.Forms.BindingSource.BindingComplete> event for the <xref:System.Windows.Forms.BindingSource> component is handled in the example to ensure that the two forms remain synchronized.</span></span> <span data-ttu-id="cc97d-111">これが実行される理由の詳細につい[ては、「方法:同じデータソースにバインドされている複数の](../multiple-controls-bound-to-data-source-synchronized.md)コントロールが同期されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cc97d-111">For more information about why this is done, see [How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized](../multiple-controls-bound-to-data-source-synchronized.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleForms#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleForms#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cc97d-112">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="cc97d-112">Compiling the Code</span></span>  
 <span data-ttu-id="cc97d-113">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cc97d-113">This example requires:</span></span>  
  
- <span data-ttu-id="cc97d-114">System、System.Windows.Forms、System.Drawing、System.Data、および System.Xml アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="cc97d-114">References to the System, System.Windows.Forms, System.Drawing, System.Data, and System.Xml assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc97d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="cc97d-115">See also</span></span>

- [<span data-ttu-id="cc97d-116">BindingSource コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cc97d-116">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="cc97d-117">Windows フォームでのデータ バインディング</span><span class="sxs-lookup"><span data-stu-id="cc97d-117">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="cc97d-118">方法: データバインドで発生するエラーと例外を処理する</span><span class="sxs-lookup"><span data-stu-id="cc97d-118">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)
