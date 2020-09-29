---
title: '方法: コード エディターを使用してエンティティ クラスをカスタマイズする'
ms.date: 03/30/2017
ms.assetid: ec28332f-9f3c-4e0a-baca-60f9141a68c0
ms.openlocfilehash: 5e61acc9de1ef2f00d5e81a3c3080a9dc46f074d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147698"
---
# <a name="how-to-customize-entity-classes-by-using-the-code-editor"></a><span data-ttu-id="294f2-102">方法: コード エディターを使用してエンティティ クラスをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="294f2-102">How to: Customize Entity Classes by Using the Code Editor</span></span>

<span data-ttu-id="294f2-103">Visual Studio を使用する開発者は、オブジェクト リレーショナル デザイナーを使用して、エンティティ クラスを作成またはカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="294f2-103">Developers using Visual Studio can use the Object Relational Designer to create or customize their entity classes.</span></span>  
  
 <span data-ttu-id="294f2-104">Visual Studio のコード エディターを使用して、独自のマッピング コードを記述したり、既に生成されているコードをカスタマイズしたりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="294f2-104">You can also use the Visual Studio code editor to write your own mapping code or to customize code that has already been generated.</span></span> <span data-ttu-id="294f2-105">詳しくは、「[属性ベースの対応付け](attribute-based-mapping.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="294f2-105">For more information, see [Attribute-Based Mapping](attribute-based-mapping.md).</span></span>  
  
 <span data-ttu-id="294f2-106">このセクションのトピックでは、オブジェクト モデルをカスタマイズする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="294f2-106">The topics in this section describe how to customize your object model.</span></span>  
  
 [<span data-ttu-id="294f2-107">方法: データベースの名前を指定する</span><span class="sxs-lookup"><span data-stu-id="294f2-107">How to: Specify Database Names</span></span>](how-to-specify-database-names.md)  
 <span data-ttu-id="294f2-108"><xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="294f2-108">Describes how to use <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span></span>  
  
 [<span data-ttu-id="294f2-109">方法: クラスとしてテーブルを表す</span><span class="sxs-lookup"><span data-stu-id="294f2-109">How to: Represent Tables as Classes</span></span>](how-to-represent-tables-as-classes.md)  
 <span data-ttu-id="294f2-110"><xref:System.Data.Linq.Mapping.TableAttribute> の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="294f2-110">Describes how to use <xref:System.Data.Linq.Mapping.TableAttribute>.</span></span>  
  
 [<span data-ttu-id="294f2-111">方法: クラス メンバーとして列を表す</span><span class="sxs-lookup"><span data-stu-id="294f2-111">How to: Represent Columns as Class Members</span></span>](how-to-represent-columns-as-class-members.md)  
 <span data-ttu-id="294f2-112"><xref:System.Data.Linq.Mapping.ColumnAttribute> の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="294f2-112">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span></span>  
  
 [<span data-ttu-id="294f2-113">方法: 主キーを表す</span><span class="sxs-lookup"><span data-stu-id="294f2-113">How to: Represent Primary Keys</span></span>](how-to-represent-primary-keys.md)  
 <span data-ttu-id="294f2-114"><xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="294f2-114">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
 [<span data-ttu-id="294f2-115">方法: データベース リレーションシップを割り当てる</span><span class="sxs-lookup"><span data-stu-id="294f2-115">How to: Map Database Relationships</span></span>](how-to-map-database-relationships.md)  
 <span data-ttu-id="294f2-116"><xref:System.Data.Linq.Mapping.AssociationAttribute> 属性の使い方の例を示します。</span><span class="sxs-lookup"><span data-stu-id="294f2-116">Provides examples of using the <xref:System.Data.Linq.Mapping.AssociationAttribute> attribute.</span></span>  
  
 [<span data-ttu-id="294f2-117">方法: 列をデータベース生成列として表す</span><span class="sxs-lookup"><span data-stu-id="294f2-117">How to: Represent Columns as Database-Generated</span></span>](how-to-represent-columns-as-database-generated.md)  
 <span data-ttu-id="294f2-118"><xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="294f2-118">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
 [<span data-ttu-id="294f2-119">方法: 列をタイムスタンプ列またはバージョン列として表現する</span><span class="sxs-lookup"><span data-stu-id="294f2-119">How to: Represent Columns as Timestamp or Version Columns</span></span>](how-to-represent-columns-as-timestamp-or-version-columns.md)  
 <span data-ttu-id="294f2-120"><xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="294f2-120">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
 [<span data-ttu-id="294f2-121">方法: データベース データ型を指定する</span><span class="sxs-lookup"><span data-stu-id="294f2-121">How to: Specify Database Data Types</span></span>](how-to-specify-database-data-types.md)  
 <span data-ttu-id="294f2-122"><xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="294f2-122">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span></span>  
  
 [<span data-ttu-id="294f2-123">方法: 計算列を表す</span><span class="sxs-lookup"><span data-stu-id="294f2-123">How to: Represent Computed Columns</span></span>](how-to-represent-computed-columns.md)  
 <span data-ttu-id="294f2-124"><xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="294f2-124">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span></span>  
  
 [<span data-ttu-id="294f2-125">方法: プライベート ストレージ フィールドを指定する</span><span class="sxs-lookup"><span data-stu-id="294f2-125">How to: Specify Private Storage Fields</span></span>](how-to-specify-private-storage-fields.md)  
 <span data-ttu-id="294f2-126"><xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="294f2-126">Describes how to use <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span></span>  
  
 [<span data-ttu-id="294f2-127">方法: null 値を許可する列として列を表す</span><span class="sxs-lookup"><span data-stu-id="294f2-127">How to: Represent Columns as Allowing Null Values</span></span>](how-to-represent-columns-as-allowing-null-values.md)  
 <span data-ttu-id="294f2-128"><xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="294f2-128">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
 [<span data-ttu-id="294f2-129">方法: 継承階層を割り当てる</span><span class="sxs-lookup"><span data-stu-id="294f2-129">How to: Map Inheritance Hierarchies</span></span>](how-to-map-inheritance-hierarchies.md)  
 <span data-ttu-id="294f2-130">継承階層の指定に必要な割り当てについて説明します。</span><span class="sxs-lookup"><span data-stu-id="294f2-130">Describes the mappings required to specify an inheritance hierarchy.</span></span>  
  
 [<span data-ttu-id="294f2-131">方法: コンカレンシーの競合のチェックを指定する</span><span class="sxs-lookup"><span data-stu-id="294f2-131">How to: Specify Concurrency-Conflict Checking</span></span>](how-to-specify-concurrency-conflict-checking.md)  
 <span data-ttu-id="294f2-132"><xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="294f2-132">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="294f2-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="294f2-133">See also</span></span>

- [<span data-ttu-id="294f2-134">SqlMetal.exe (コード生成ツール)</span><span class="sxs-lookup"><span data-stu-id="294f2-134">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../tools/sqlmetal-exe-code-generation-tool.md)
