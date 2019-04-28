---
title: null セマンティクス
ms.date: 03/30/2017
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
ms.openlocfilehash: eb1e96ba44c5d64e8366a654c2d06d89c9b46c9a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61767541"
---
# <a name="null-semantics"></a><span data-ttu-id="bdb6b-102">null セマンティクス</span><span class="sxs-lookup"><span data-stu-id="bdb6b-102">Null Semantics</span></span>
<span data-ttu-id="bdb6b-103">次の表のさまざまな部分へのリンク、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]ドキュメント、 `null` (`Nothing` Visual Basic で) について説明しています。</span><span class="sxs-lookup"><span data-stu-id="bdb6b-103">The following table provides links to various parts of the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation where `null` (`Nothing` in Visual Basic) issues are discussed.</span></span>  
  
|<span data-ttu-id="bdb6b-104">トピック</span><span class="sxs-lookup"><span data-stu-id="bdb6b-104">Topic</span></span>|<span data-ttu-id="bdb6b-105">説明</span><span class="sxs-lookup"><span data-stu-id="bdb6b-105">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="bdb6b-106">SQL と CLR の型の不一致</span><span class="sxs-lookup"><span data-stu-id="bdb6b-106">SQL-CLR Type Mismatches</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mismatches.md)|<span data-ttu-id="bdb6b-107">このトピックの「Null セマンティクス」セクションには、2 つの状態共通言語ランタイム (CLR) と 3 つの状態 SQL ブール ディスカッションが含まれています。 <xref:System.Boolean>、リテラル`Nothing`(Visual Basic) と`null`(C#)、およびその他の類似問題です。</span><span class="sxs-lookup"><span data-stu-id="bdb6b-107">The "Null Semantics" section of this topic includes discussion of the three-state SQL Boolean versus the two-state common language runtime (CLR) <xref:System.Boolean>, the literal `Nothing` (Visual Basic) and `null` (C#), and other similar issues.</span></span>|  
|[<span data-ttu-id="bdb6b-108">標準クエリ演算子の変換</span><span class="sxs-lookup"><span data-stu-id="bdb6b-108">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)|<span data-ttu-id="bdb6b-109">このトピックの「null セマンティクス」セクションでは、 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]での null の比較のセマンティクスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bdb6b-109">The "Null Semantics" section of this topic describes null comparison semantics in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|  
|[<span data-ttu-id="bdb6b-110">System.String メソッド</span><span class="sxs-lookup"><span data-stu-id="bdb6b-110">System.String Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/system-string-methods.md)|<span data-ttu-id="bdb6b-111">このトピックの「.NET との相違」セクションでは、 <xref:System.String.LastIndexOf%2A> の戻り値が 0 の場合に、文字列が null の場合と、見つかった位置が 0 の場合の両方があることについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bdb6b-111">The "Differences from .NET" section of this topic describes how a return of 0 from <xref:System.String.LastIndexOf%2A> might mean either that the string is null or that the found position is 0.</span></span>|  
|[<span data-ttu-id="bdb6b-112">数値のシーケンスの合計の計算</span><span class="sxs-lookup"><span data-stu-id="bdb6b-112">Compute the Sum of Values in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)|<span data-ttu-id="bdb6b-113">について説明しますが、どのように<xref:System.Linq.Enumerable.Sum%2A>に演算子が評価される`null`(`Nothing` Visual Basic で) null のみを含むシーケンス、または空のシーケンス 0 ではなく。</span><span class="sxs-lookup"><span data-stu-id="bdb6b-113">Describes how the <xref:System.Linq.Enumerable.Sum%2A> operator evaluates to `null` (`Nothing` in Visual Basic) instead of 0 for a sequence that contains only nulls or for an empty sequence.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bdb6b-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="bdb6b-114">See also</span></span>

- [<span data-ttu-id="bdb6b-115">データ型と関数</span><span class="sxs-lookup"><span data-stu-id="bdb6b-115">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
