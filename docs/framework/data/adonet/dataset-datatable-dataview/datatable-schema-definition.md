---
title: DataTable スキーマの定義
ms.date: 03/30/2017
ms.assetid: efbcdda4-f5a9-421d-8be2-4c194c74552f
ms.openlocfilehash: d18af8001fd24f3b21c3e7fd13f9dabb2587b322
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786389"
---
# <a name="datatable-schema-definition"></a><span data-ttu-id="c92b6-102">DataTable スキーマの定義</span><span class="sxs-lookup"><span data-stu-id="c92b6-102">DataTable Schema Definition</span></span>
<span data-ttu-id="c92b6-103">テーブルのスキーマ (構造) は、列と制約で表されます。</span><span class="sxs-lookup"><span data-stu-id="c92b6-103">The schema, or structure, of a table is represented by columns and constraints.</span></span> <span data-ttu-id="c92b6-104"><xref:System.Data.DataTable> のスキーマは、<xref:System.Data.DataColumn>、<xref:System.Data.ForeignKeyConstraint>、<xref:System.Data.UniqueConstraint> の各オブジェクトを使用して定義します。</span><span class="sxs-lookup"><span data-stu-id="c92b6-104">You define the schema of a <xref:System.Data.DataTable> using <xref:System.Data.DataColumn> objects as well as <xref:System.Data.ForeignKeyConstraint> and <xref:System.Data.UniqueConstraint> objects.</span></span> <span data-ttu-id="c92b6-105">テーブルの列は、データ ソースの列に割り当てたり、式で算出された値を格納したり、格納されている値を自動的にインクリメントしたり、主キー値を格納したりできます。</span><span class="sxs-lookup"><span data-stu-id="c92b6-105">The columns in a table can map to columns in a data source, contain calculated values from expressions, automatically increment their values, or contain primary key values.</span></span>  
  
 <span data-ttu-id="c92b6-106">テーブルの列、リレーション、および制約を名前で参照する場合は、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="c92b6-106">References by name to columns, relations, and constraints in a table are case-sensitive.</span></span> <span data-ttu-id="c92b6-107">複数の列、リレーション、または制約の名前が同じであっても、大文字と小文字が異なっていれば、1 つのテーブルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="c92b6-107">Two or more columns, relations, or constraints can therefore exist in a table that have the same name, but that differ in case.</span></span> <span data-ttu-id="c92b6-108">たとえば、 **col1**と**col1**を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c92b6-108">For example, you can have **Col1** and **col1**.</span></span> <span data-ttu-id="c92b6-109">この場合、列を名前で参照するときは、列名の大文字と小文字を正確に指定する必要があります。正確に指定しない場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c92b6-109">In such as case, a reference to one of the columns by name must match the case of the column name exactly; otherwise an exception is thrown.</span></span> <span data-ttu-id="c92b6-110">たとえば、テーブル**mytable**に**col1**列と**col1**列が含まれている場合、 **col1**を名前によって Mytable として参照し**ます。 Columns ["col1"]** , **col1** as **mytable ["col1"]** です。</span><span class="sxs-lookup"><span data-stu-id="c92b6-110">For example, if the table **myTable** contains the columns **Col1** and **col1**, you would reference **Col1** by name as **myTable.Columns["Col1"]**, and **col1** as **myTable.Columns["col1"]**.</span></span> <span data-ttu-id="c92b6-111">列のいずれかを MyTable として参照しようとしてい**ます。列 ["COL1"]** は例外を生成します。</span><span class="sxs-lookup"><span data-stu-id="c92b6-111">Attempting to reference either of the columns as **myTable.Columns["COL1"]** would generate an exception.</span></span>  
  
 <span data-ttu-id="c92b6-112">大文字と小文字の区別の規則は、特定の名前の列、リレーション、または制約が 1 つしかない場合には適用されません。</span><span class="sxs-lookup"><span data-stu-id="c92b6-112">The case-sensitivity rule does not apply if only one column, relation, or constraint  with a particular name exists.</span></span> <span data-ttu-id="c92b6-113">つまり、特定の列、リレーション、または制約オブジェクトと名前が一致する列、リレーション、または制約オブジェクトがテーブルに存在しない場合は、大文字と小文字を区別せずにそのオブジェクトを名前で参照することができます。このとき、例外はスローされません。</span><span class="sxs-lookup"><span data-stu-id="c92b6-113">That is, if no other column, relation, or constraint object in the table matches the name of that particular column, relation, or constraint object, you may reference the object by name using any case, and no exception is thrown.</span></span> <span data-ttu-id="c92b6-114">たとえば、テーブルに**Col1**しかない場合は、my を使用して参照でき**ます。列 ["COL1"]** 。</span><span class="sxs-lookup"><span data-stu-id="c92b6-114">For example, if the table has only **Col1**, you can reference it using **my.Columns["COL1"]**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c92b6-115">DataTable <xref:System.Data.DataTable.CaseSensitive%2A>のプロパティは 、この動作に影響しません。</span><span class="sxs-lookup"><span data-stu-id="c92b6-115">The <xref:System.Data.DataTable.CaseSensitive%2A> property of the **DataTable** does not affect this behavior.</span></span> <span data-ttu-id="c92b6-116">**CaseSensitive**プロパティは、テーブル内のデータに適用され、並べ替え、検索、フィルター処理、制約の適用などに影響しますが、列、リレーション、および制約への参照には影響しません。</span><span class="sxs-lookup"><span data-stu-id="c92b6-116">The **CaseSensitive** property applies to the data in a table and affects sorting, searching, filtering, enforcing constraints, and so on, but not to references to the columns, relations, and constraints.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c92b6-117">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c92b6-117">In This Section</span></span>  
 [<span data-ttu-id="c92b6-118">DataTable への列の追加</span><span class="sxs-lookup"><span data-stu-id="c92b6-118">Adding Columns to a DataTable</span></span>](adding-columns-to-a-datatable.md)  
 <span data-ttu-id="c92b6-119">**DataColumn**オブジェクトを使用してテーブルの列を定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c92b6-119">Describes how to define the columns of a table using **DataColumn** objects.</span></span>  
  
 [<span data-ttu-id="c92b6-120">式列の作成</span><span class="sxs-lookup"><span data-stu-id="c92b6-120">Creating Expression Columns</span></span>](creating-expression-columns.md)  
 <span data-ttu-id="c92b6-121">列の**式**プロパティを使用して、行の他の列の値に基づいて値を計算する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c92b6-121">Explains how the **Expression** property of a column can be used to calculate values based on the values from other columns in the row.</span></span>  
  
 [<span data-ttu-id="c92b6-122">AutoIncrement 列の作成</span><span class="sxs-lookup"><span data-stu-id="c92b6-122">Creating AutoIncrement Columns</span></span>](creating-autoincrement-columns.md)  
 <span data-ttu-id="c92b6-123">数値を自動的にインクリメントして行ごとに一意の列値が割り当てられるように列を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c92b6-123">Describes how a column can be set to automatically increment numerical values to ensure a unique column value per row.</span></span>  
  
 [<span data-ttu-id="c92b6-124">主キーの定義</span><span class="sxs-lookup"><span data-stu-id="c92b6-124">Defining Primary Keys</span></span>](defining-primary-keys.md)  
 <span data-ttu-id="c92b6-125">1つ以上の**DataColumn**オブジェクトからテーブルの主キーを指定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c92b6-125">Describes how to specify the primary key of a table from one or more **DataColumn** objects.</span></span>  
  
 [<span data-ttu-id="c92b6-126">DataTable の制約</span><span class="sxs-lookup"><span data-stu-id="c92b6-126">DataTable Constraints</span></span>](datatable-constraints.md)  
 <span data-ttu-id="c92b6-127">テーブルの列の外部キー制約と UNIQUE 制約を定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c92b6-127">Describes how to define foreign key and unique constraints for columns in a table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c92b6-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="c92b6-128">See also</span></span>

- [<span data-ttu-id="c92b6-129">DataTables</span><span class="sxs-lookup"><span data-stu-id="c92b6-129">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="c92b6-130">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="c92b6-130">ADO.NET Overview</span></span>](../ado-net-overview.md)
