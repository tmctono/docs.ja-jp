---
title: ストアド プロシージャのみによる操作のカスタマイズ
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 441e8ef3-998c-4d12-8825-ce66a178f90f
ms.openlocfilehash: a242ecdc774d67721aee640e75847317c1b815d6
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70247547"
---
# <a name="customizing-operations-by-using-stored-procedures-exclusively"></a><span data-ttu-id="8f0d1-102">ストアド プロシージャのみによる操作のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="8f0d1-102">Customizing Operations by Using Stored Procedures Exclusively</span></span>
<span data-ttu-id="8f0d1-103">ストアド プロシージャのみを使用してデータにアクセスすることは、一般的なシナリオです。</span><span class="sxs-lookup"><span data-stu-id="8f0d1-103">Access to data by using only stored procedures is a common scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f0d1-104">例</span><span class="sxs-lookup"><span data-stu-id="8f0d1-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="8f0d1-105">説明</span><span class="sxs-lookup"><span data-stu-id="8f0d1-105">Description</span></span>  
 <span data-ttu-id="8f0d1-106">「[ストアドプロシージャを使用した操作のカスタマイズ](customizing-operations-by-using-stored-procedures.md)」で提供されている例を変更するには、ストアドプロシージャをラップするメソッド呼び出しを使用して、最初のクエリ (動的 SQL 実行の原因となるクエリ) を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="8f0d1-106">You can modify the example provided in [Customizing Operations By Using Stored Procedures](customizing-operations-by-using-stored-procedures.md) by replacing even the first query (which causes dynamic SQL execution) with a method call that wraps a stored procedure.</span></span>  
  
 <span data-ttu-id="8f0d1-107">次の例に示すように、`CustomersByCity` がこのメソッドであることを前提とします。</span><span class="sxs-lookup"><span data-stu-id="8f0d1-107">Assume `CustomersByCity` is the method, as in the following example.</span></span>  
  
### <a name="code"></a><span data-ttu-id="8f0d1-108">コード</span><span class="sxs-lookup"><span data-stu-id="8f0d1-108">Code</span></span>  
 [!code-csharp[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#4)]
 [!code-vb[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#4)]  
  
 <span data-ttu-id="8f0d1-109">次のコードは、動的 SQL を使わずに実行されます。</span><span class="sxs-lookup"><span data-stu-id="8f0d1-109">The following code executes without any dynamic SQL.</span></span>  
  
 [!code-csharp[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#5)]
 [!code-vb[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="8f0d1-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f0d1-110">See also</span></span>

- [<span data-ttu-id="8f0d1-111">既定の動作をオーバーライドするときの開発者の責任</span><span class="sxs-lookup"><span data-stu-id="8f0d1-111">Responsibilities of the Developer In Overriding Default Behavior</span></span>](responsibilities-of-the-developer-in-overriding-default-behavior.md)
