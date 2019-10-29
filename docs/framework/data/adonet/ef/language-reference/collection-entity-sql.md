---
title: COLLECTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 03228bfa-be3a-4ccc-82f8-eee429f85cf1
ms.openlocfilehash: 5a1af1aab8a084b19e48fbdbb159d7ddd8a8dd7c
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039905"
---
# <a name="collection-entity-sql"></a><span data-ttu-id="4c956-102">COLLECTION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="4c956-102">COLLECTION (Entity SQL)</span></span>
<span data-ttu-id="4c956-103">COLLECTION キーワードは、インライン関数を定義する場合にのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="4c956-103">The COLLECTION keyword is only used in the definition of an inline function.</span></span> <span data-ttu-id="4c956-104">コレクション関数は、値のコレクションを操作してスカラー出力を生成する関数です。</span><span class="sxs-lookup"><span data-stu-id="4c956-104">Collection functions are functions that operate on a collection of values and produce a scalar output.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c956-105">構文</span><span class="sxs-lookup"><span data-stu-id="4c956-105">Syntax</span></span>  
  
```csharp  
COLLECTION(type_definition)
```  
  
## <a name="arguments"></a><span data-ttu-id="4c956-106">引数</span><span class="sxs-lookup"><span data-stu-id="4c956-106">Arguments</span></span>  
 `type_definition`  
 <span data-ttu-id="4c956-107">サポートされる型、行、または参照のコレクションを返す式。</span><span class="sxs-lookup"><span data-stu-id="4c956-107">An expression that returns a collection of supported types, rows, or references.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c956-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="4c956-108">Remarks</span></span>  
 <span data-ttu-id="4c956-109">COLLECTION キーワードについて詳しくは、「 [Type Definitions](type-definitions-entity-sql.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4c956-109">For more information about the COLLECTION keyword, see [Type Definitions](type-definitions-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c956-110">例</span><span class="sxs-lookup"><span data-stu-id="4c956-110">Example</span></span>  
 <span data-ttu-id="4c956-111">次の例は、COLLECTION キーワードを使用して 10 進数のコレクションをインライン クエリ関数の引数として宣言する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4c956-111">The following sample shows how to use the COLLECTION keyword to declare a collection of decimals as an argument for an inline query function.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]  
  
## <a name="see-also"></a><span data-ttu-id="4c956-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c956-112">See also</span></span>

- [<span data-ttu-id="4c956-113">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="4c956-113">Entity SQL Reference</span></span>](entity-sql-reference.md)
