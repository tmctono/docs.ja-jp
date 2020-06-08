---
title: '方法: 並列タスクでバイナリ ツリーを走査する'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to traverse a tree
ms.assetid: 4265d169-6c69-4f36-b10d-b7ae7f72f4df
ms.openlocfilehash: 5ac81a61691ec20daafc9e18978ba5814a150383
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288070"
---
# <a name="how-to-traverse-a-binary-tree-with-parallel-tasks"></a><span data-ttu-id="7987b-102">方法: 並列タスクでバイナリ ツリーを走査する</span><span class="sxs-lookup"><span data-stu-id="7987b-102">How to: Traverse a Binary Tree with Parallel Tasks</span></span>
<span data-ttu-id="7987b-103">次の例では、ツリー データ構造を走査する並列タスクを使用する 2 つの方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7987b-103">The following example shows two ways in which parallel tasks can be used to traverse a tree data structure.</span></span> <span data-ttu-id="7987b-104">ツリー自体の作成は、演習として残しておきます。</span><span class="sxs-lookup"><span data-stu-id="7987b-104">The creation of the tree itself is left as an exercise.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7987b-105">例</span><span class="sxs-lookup"><span data-stu-id="7987b-105">Example</span></span>  
 [!code-csharp[TPL#16](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#16)]
 [!code-vb[TPL#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/treewalk.vb#16)]  
  
 <span data-ttu-id="7987b-106">示した 2 つのメソッドは、機能的に同等です。</span><span class="sxs-lookup"><span data-stu-id="7987b-106">The two methods shown are functionally equivalent.</span></span> <span data-ttu-id="7987b-107">タスクを作成して実行するために、<xref:System.Threading.Tasks.TaskFactory.StartNew%2A> メソッドを使用すると、タスクで待機し、例外を処理するために使用するタスクからハンドルを戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="7987b-107">By using the <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> method to create and run the tasks, you get a handle back from the tasks which can be used to wait on the tasks and handle exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7987b-108">参照</span><span class="sxs-lookup"><span data-stu-id="7987b-108">See also</span></span>

- [<span data-ttu-id="7987b-109">タスク並列ライブラリ (TPL)</span><span class="sxs-lookup"><span data-stu-id="7987b-109">Task Parallel Library (TPL)</span></span>](task-parallel-library-tpl.md)
