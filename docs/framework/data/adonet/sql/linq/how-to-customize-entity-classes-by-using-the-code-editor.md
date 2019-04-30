---
title: '方法: コード エディターを使用してエンティティ クラスをカスタマイズする'
ms.date: 03/30/2017
ms.assetid: ec28332f-9f3c-4e0a-baca-60f9141a68c0
ms.openlocfilehash: 05a523f8b98c7b64350b67c217baba07dca14de3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62037831"
---
# <a name="how-to-customize-entity-classes-by-using-the-code-editor"></a><span data-ttu-id="d56fd-102">方法: コード エディターを使用してエンティティ クラスをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="d56fd-102">How to: Customize Entity Classes by Using the Code Editor</span></span>
<span data-ttu-id="d56fd-103">Visual Studio を使用して開発者が使用できる、[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]を作成したり、エンティティ クラスをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="d56fd-103">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to create or customize their entity classes.</span></span>  
  
 <span data-ttu-id="d56fd-104">マッピング コードを記述するか、既に生成されているコードをカスタマイズする、Visual Studio コード エディターを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d56fd-104">You can also use the Visual Studio code editor to write your own mapping code or to customize code that has already been generated.</span></span> <span data-ttu-id="d56fd-105">詳細については、次を参照してください。[属性ベースの対応付け](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)します。</span><span class="sxs-lookup"><span data-stu-id="d56fd-105">For more information, see [Attribute-Based Mapping](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span></span>  
  
 <span data-ttu-id="d56fd-106">このセクションのトピックでは、オブジェクト モデルをカスタマイズする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d56fd-106">The topics in this section describe how to customize your object model.</span></span>  
  
 [<span data-ttu-id="d56fd-107">方法: データベース名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d56fd-107">How to: Specify Database Names</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-database-names.md)  
 <span data-ttu-id="d56fd-108"><xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d56fd-108">Describes how to use <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span></span>  
  
 [<span data-ttu-id="d56fd-109">方法: クラスとしてテーブルを表す</span><span class="sxs-lookup"><span data-stu-id="d56fd-109">How to: Represent Tables as Classes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-tables-as-classes.md)  
 <span data-ttu-id="d56fd-110"><xref:System.Data.Linq.Mapping.TableAttribute> の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d56fd-110">Describes how to use <xref:System.Data.Linq.Mapping.TableAttribute>.</span></span>  
  
 [<span data-ttu-id="d56fd-111">方法: クラス メンバーとして列を表す</span><span class="sxs-lookup"><span data-stu-id="d56fd-111">How to: Represent Columns as Class Members</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-class-members.md)  
 <span data-ttu-id="d56fd-112"><xref:System.Data.Linq.Mapping.ColumnAttribute> の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d56fd-112">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span></span>  
  
 [<span data-ttu-id="d56fd-113">方法: 主キーを表す</span><span class="sxs-lookup"><span data-stu-id="d56fd-113">How to: Represent Primary Keys</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-primary-keys.md)  
 <span data-ttu-id="d56fd-114"><xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d56fd-114">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
 [<span data-ttu-id="d56fd-115">方法: データベース リレーションシップを割り当てる</span><span class="sxs-lookup"><span data-stu-id="d56fd-115">How to: Map Database Relationships</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-database-relationships.md)  
 <span data-ttu-id="d56fd-116"><xref:System.Data.Linq.Mapping.AssociationAttribute> 属性の使い方の例を示します。</span><span class="sxs-lookup"><span data-stu-id="d56fd-116">Provides examples of using the <xref:System.Data.Linq.Mapping.AssociationAttribute> attribute.</span></span>  
  
 [<span data-ttu-id="d56fd-117">方法: データベース生成として列を表す</span><span class="sxs-lookup"><span data-stu-id="d56fd-117">How to: Represent Columns as Database-Generated</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-database-generated.md)  
 <span data-ttu-id="d56fd-118"><xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d56fd-118">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
 [<span data-ttu-id="d56fd-119">方法: タイムスタンプ列またはバージョン列を表す</span><span class="sxs-lookup"><span data-stu-id="d56fd-119">How to: Represent Columns as Timestamp or Version Columns</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-timestamp-or-version-columns.md)  
 <span data-ttu-id="d56fd-120"><xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d56fd-120">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
 [<span data-ttu-id="d56fd-121">方法: データベースのデータ型を指定します。</span><span class="sxs-lookup"><span data-stu-id="d56fd-121">How to: Specify Database Data Types</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-database-data-types.md)  
 <span data-ttu-id="d56fd-122"><xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d56fd-122">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span></span>  
  
 [<span data-ttu-id="d56fd-123">方法: 計算列を表す</span><span class="sxs-lookup"><span data-stu-id="d56fd-123">How to: Represent Computed Columns</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-computed-columns.md)  
 <span data-ttu-id="d56fd-124"><xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d56fd-124">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span></span>  
  
 [<span data-ttu-id="d56fd-125">方法: プライベート ストレージ フィールドを指定します。</span><span class="sxs-lookup"><span data-stu-id="d56fd-125">How to: Specify Private Storage Fields</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-private-storage-fields.md)  
 <span data-ttu-id="d56fd-126"><xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d56fd-126">Describes how to use <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span></span>  
  
 [<span data-ttu-id="d56fd-127">方法: Null 値を許容するよう列を表す</span><span class="sxs-lookup"><span data-stu-id="d56fd-127">How to: Represent Columns as Allowing Null Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-allowing-null-values.md)  
 <span data-ttu-id="d56fd-128"><xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d56fd-128">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
 [<span data-ttu-id="d56fd-129">方法: 継承階層を割り当てる</span><span class="sxs-lookup"><span data-stu-id="d56fd-129">How to: Map Inheritance Hierarchies</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md)  
 <span data-ttu-id="d56fd-130">継承階層の指定に必要な割り当てについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d56fd-130">Describes the mappings required to specify an inheritance hierarchy.</span></span>  
  
 [<span data-ttu-id="d56fd-131">方法: 同時実行の競合のチェックを指定します。</span><span class="sxs-lookup"><span data-stu-id="d56fd-131">How to: Specify Concurrency-Conflict Checking</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-concurrency-conflict-checking.md)  
 <span data-ttu-id="d56fd-132"><xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d56fd-132">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d56fd-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="d56fd-133">See also</span></span>

- [<span data-ttu-id="d56fd-134">SqlMetal.exe (コード生成ツール)</span><span class="sxs-lookup"><span data-stu-id="d56fd-134">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)
