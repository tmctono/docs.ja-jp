---
title: DataGridView コントロールでのパフォーマンスチューニング
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], performance tuning
- performance [Windows Forms], DataGridView control
- performance tuning [Windows Forms], data grids
ms.assetid: 6ccbff28-a0ff-41e4-b601-61b31b61851d
ms.openlocfilehash: 77ad86c4cd606bcf074473c97371ec27bcc5605b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744275"
---
# <a name="performance-tuning-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="c0c09-102">Windows フォーム DataGridView コントロールでのパフォーマンス チューニング</span><span class="sxs-lookup"><span data-stu-id="c0c09-102">Performance Tuning in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="c0c09-103">大量のデータを処理する場合、`DataGridView` 制御では、慎重に使用しない限り、オーバーヘッドが大量のメモリを消費する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c0c09-103">When working with large amounts of data, the `DataGridView` control can consume a large amount of memory in overhead, unless you use it carefully.</span></span> <span data-ttu-id="c0c09-104">メモリが制限されているクライアントでは、メモリコストが高い機能を回避することで、このオーバーヘッドの一部を回避できます。</span><span class="sxs-lookup"><span data-stu-id="c0c09-104">On clients with limited memory, you can avoid some of this overhead by avoiding features that have a high memory cost.</span></span> <span data-ttu-id="c0c09-105">また、シナリオのメモリ使用量をカスタマイズするために、仮想モードを使用して、データのメンテナンスと取得のタスクの一部またはすべてを自分で管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="c0c09-105">You can also manage some or all of the data maintenance and retrieval tasks yourself using virtual mode in order to customize the memory usage for your scenario.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c0c09-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c0c09-106">In This Section</span></span>  
 [<span data-ttu-id="c0c09-107">Windows フォーム DataGridView コントロールを拡張するための推奨される手順</span><span class="sxs-lookup"><span data-stu-id="c0c09-107">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="c0c09-108">大量のデータを処理するときに、不要なメモリ使用量とパフォーマンスの低下を回避する方法で `DataGridView` コントロールを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c0c09-108">Describes how to use the `DataGridView` control in a way that avoids unnecessary memory usage and performance penalties when working with large amounts of data.</span></span>  
  
 [<span data-ttu-id="c0c09-109">Windows フォーム DataGridView コントロールでの仮想モード</span><span class="sxs-lookup"><span data-stu-id="c0c09-109">Virtual Mode in the Windows Forms DataGridView Control</span></span>](virtual-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="c0c09-110">仮想モードを使用して標準のデータバインディングメカニズムを補完または置き換える方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c0c09-110">Describes how to use virtual mode to supplement or replace the standard data-binding mechanism.</span></span>  
  
 [<span data-ttu-id="c0c09-111">チュートリアル: Windows フォーム DataGridView コントロールでの仮想モードの実装</span><span class="sxs-lookup"><span data-stu-id="c0c09-111">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-wf-datagridview-control.md)  
 <span data-ttu-id="c0c09-112">いくつかの仮想モードイベントのハンドラーを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c0c09-112">Describes how to implement handlers for several virtual-mode events.</span></span> <span data-ttu-id="c0c09-113">また、行レベルのロールバックを実装し、ユーザーが編集するためにコミットする方法も示します。</span><span class="sxs-lookup"><span data-stu-id="c0c09-113">Also demonstrates how to implement row-level rollback and commit for user edits.</span></span>  
  
 [<span data-ttu-id="c0c09-114">Windows フォーム DataGridView コントロールでの Just-In-Time データ読み込みによる仮想モードの実装</span><span class="sxs-lookup"><span data-stu-id="c0c09-114">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 <span data-ttu-id="c0c09-115">必要に応じてデータを読み込む方法について説明します。これは、使用可能なクライアントメモリが格納できる量よりも多くのデータを表示する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="c0c09-115">Describes how to load data on demand, which is useful when you have more data to display than the available client memory can store.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c0c09-116">リファレンス</span><span class="sxs-lookup"><span data-stu-id="c0c09-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="c0c09-117"><xref:System.Windows.Forms.DataGridView> コントロールのリファレンス ドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="c0c09-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 <span data-ttu-id="c0c09-118"><xref:System.Windows.Forms.DataGridView.VirtualMode%2A> プロパティのリファレンスドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="c0c09-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0c09-119">参照</span><span class="sxs-lookup"><span data-stu-id="c0c09-119">See also</span></span>

- [<span data-ttu-id="c0c09-120">DataGridView コントロール</span><span class="sxs-lookup"><span data-stu-id="c0c09-120">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="c0c09-121">Windows フォーム DataGridView コントロールでのデータ表示モード</span><span class="sxs-lookup"><span data-stu-id="c0c09-121">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)
