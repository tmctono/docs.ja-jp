---
title: 継承のサポート
ms.date: 03/30/2017
ms.assetid: 19bb2794-b4e7-402e-8307-1d1517381a08
ms.openlocfilehash: 668f4f1dd284550e644ce6b8a4491ca47105575e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59230916"
---
# <a name="inheritance-support"></a><span data-ttu-id="7af2c-102">継承のサポート</span><span class="sxs-lookup"><span data-stu-id="7af2c-102">Inheritance Support</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="7af2c-103">サポート*シングル テーブル マッピング*します。</span><span class="sxs-lookup"><span data-stu-id="7af2c-103">supports *single-table mapping*.</span></span> <span data-ttu-id="7af2c-104">これは、1 つの継承階層全体が単一のデータベース テーブルに保存されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="7af2c-104">In other words, a complete inheritance hierarchy is stored in a single database table.</span></span> <span data-ttu-id="7af2c-105">テーブルには、階層構造内で使用され得るすべてのデータ列の平坦化された共用体が格納されます </span><span class="sxs-lookup"><span data-stu-id="7af2c-105">The table contains the flattened union of all possible data columns for the whole hierarchy.</span></span> <span data-ttu-id="7af2c-106">(2 つのテーブルを 1 つに結合し、元のテーブルのいずれかにあった行が新しいテーブルに含まれるようにした結果、1 つの共用体が形成されます)。行によって表されるインスタンスの型に適合しない列には null が設定されます。</span><span class="sxs-lookup"><span data-stu-id="7af2c-106">(A union is the result of combining two tables into one table that has the rows that were present in either of the original tables.) Each row has nulls in the columns that do not apply to the type of the instance represented by the row.</span></span>  
  
 <span data-ttu-id="7af2c-107">シングル テーブル マッピング形式は、継承を表す最も単純な形式であり、多くのクエリのカテゴリで良好なパフォーマンス特性を示します。</span><span class="sxs-lookup"><span data-stu-id="7af2c-107">The single-table mapping strategy is the simplest representation of inheritance and provides good performance characteristics for many different categories of queries.</span></span>  
  
 <span data-ttu-id="7af2c-108">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] でこのマッピングを実装するには、継承階層のルート クラスで属性および属性プロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7af2c-108">To implement this mapping in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you must specify the attributes and attribute properties on the root class of the inheritance hierarchy.</span></span> <span data-ttu-id="7af2c-109">詳細については、「[方法 :継承階層を割り当てる](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md)します。</span><span class="sxs-lookup"><span data-stu-id="7af2c-109">For more information, see [How to: Map Inheritance Hierarchies](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md).</span></span>  
  
 <span data-ttu-id="7af2c-110">Visual Studio を使用している開発者が使用することも、[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]継承階層をマップします。</span><span class="sxs-lookup"><span data-stu-id="7af2c-110">Developers using Visual Studio can also use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to map inheritance hierarchies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7af2c-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="7af2c-111">See also</span></span>

- [<span data-ttu-id="7af2c-112">背景情報</span><span class="sxs-lookup"><span data-stu-id="7af2c-112">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
