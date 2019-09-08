---
title: '方法: 変更セットを表示する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 126e7245-c5a0-4ebf-800d-cc1fcf9cd0ab
ms.openlocfilehash: 5f49e123e6e980501d330eeecf2719023cdff8e7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781967"
---
# <a name="how-to-display-a-changeset"></a><span data-ttu-id="87a06-102">方法: 変更セットを表示する</span><span class="sxs-lookup"><span data-stu-id="87a06-102">How to: Display a ChangeSet</span></span>
<span data-ttu-id="87a06-103"><xref:System.Data.Linq.DataContext> によって追跡される変更を <xref:System.Data.Linq.DataContext.GetChangeSet%2A> を使って表示することができます。</span><span class="sxs-lookup"><span data-stu-id="87a06-103">You can view changes tracked by a <xref:System.Data.Linq.DataContext> by using <xref:System.Data.Linq.DataContext.GetChangeSet%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87a06-104">例</span><span class="sxs-lookup"><span data-stu-id="87a06-104">Example</span></span>  
 <span data-ttu-id="87a06-105">以下の例では、住所がロンドンの顧客を取得し、これをパリに変更してから変更内容をデータベースに送信しています。</span><span class="sxs-lookup"><span data-stu-id="87a06-105">The following example retrieves customers whose city is London, changes the city to Paris, and submits the changes back to the database.</span></span>  
  
 [!code-csharp[DLinqDebuggingSupport#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#2)]
 [!code-vb[DLinqDebuggingSupport#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#2)]  
  
 <span data-ttu-id="87a06-106">このコードからの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="87a06-106">Output from this code appears similar to the following.</span></span> <span data-ttu-id="87a06-107">最後に概要として、8 か所の変更が示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="87a06-107">Note that the summary at the end shows that eight changes were made.</span></span>  

 ```console
CustomerID: AROUT
   Original value: London
   Updated value: Paris
CustomerID: BSBEV
   Original value: London
   Updated value: Paris
CustomerID: CONSH
   Original value: London
   Updated value: Paris
CustomerID: EASTC
   Original value: London
   Updated value: Paris
CustomerID: NORTS
    Original value: London
    Updated value: Paris
CustomerID: PARIS
    Original value: London
    Updated value: Paris
CustomerID: SEVES
    Original value: London
    Updated value: Paris
CustomerID: SPECD
    Original value: London
    Updated value: Paris
Total changes: {Added: 0, Removed: 0, Modified: 8}
```
  
## <a name="see-also"></a><span data-ttu-id="87a06-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="87a06-108">See also</span></span>

- [<span data-ttu-id="87a06-109">デバッグのサポート</span><span class="sxs-lookup"><span data-stu-id="87a06-109">Debugging Support</span></span>](debugging-support.md)
