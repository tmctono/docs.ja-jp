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
ms.openlocfilehash: b79337e6ee8057506ff87c696cecd6b038eeebfc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141645"
---
# <a name="how-to-traverse-a-binary-tree-with-parallel-tasks"></a><span data-ttu-id="83499-102">方法: 並列タスクでバイナリ ツリーを走査する</span><span class="sxs-lookup"><span data-stu-id="83499-102">How to: Traverse a Binary Tree with Parallel Tasks</span></span>
<span data-ttu-id="83499-103">次の例では、ツリー データ構造を走査する並列タスクを使用する 2 つの方法を示します。</span><span class="sxs-lookup"><span data-stu-id="83499-103">The following example shows two ways in which parallel tasks can be used to traverse a tree data structure.</span></span> <span data-ttu-id="83499-104">ツリー自体の作成は、演習として残しておきます。</span><span class="sxs-lookup"><span data-stu-id="83499-104">The creation of the tree itself is left as an exercise.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83499-105">例</span><span class="sxs-lookup"><span data-stu-id="83499-105">Example</span></span>  
 [!code-csharp[TPL#16](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#16)]
 [!code-vb[TPL#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/treewalk.vb#16)]  
  
 <span data-ttu-id="83499-106">示した 2 つのメソッドは、機能的に同等です。</span><span class="sxs-lookup"><span data-stu-id="83499-106">The two methods shown are functionally equivalent.</span></span> <span data-ttu-id="83499-107">タスクを作成して実行するために、<xref:System.Threading.Tasks.TaskFactory.StartNew%2A> メソッドを使用すると、タスクで待機し、例外を処理するために使用するタスクからハンドルを戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="83499-107">By using the <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> method to create and run the tasks, you get a handle back from the tasks which can be used to wait on the tasks and handle exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83499-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="83499-108">See also</span></span>

- [<span data-ttu-id="83499-109">タスク並列ライブラリ (TPL)</span><span class="sxs-lookup"><span data-stu-id="83499-109">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
