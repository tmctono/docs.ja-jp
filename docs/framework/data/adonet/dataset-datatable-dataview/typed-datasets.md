---
title: 型指定されたデータセット
ms.date: 03/30/2017
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
ms.openlocfilehash: 4648d49b1d7419d61a3a000404f42e0d02d25786
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198446"
---
# <a name="typed-datasets"></a><span data-ttu-id="fed6a-102">型指定されたデータセット</span><span class="sxs-lookup"><span data-stu-id="fed6a-102">Typed DataSets</span></span>

<span data-ttu-id="fed6a-103">厳密に型指定されていない変数を使用した値への遅延バインディング アクセスに加えて、<xref:System.Data.DataSet> には、厳密に型指定された変数を使用したデータへのアクセスも用意されています。</span><span class="sxs-lookup"><span data-stu-id="fed6a-103">Along with late bound access to values through weakly typed variables, the <xref:System.Data.DataSet> provides access to data through a strongly typed metaphor.</span></span> <span data-ttu-id="fed6a-104">**DataSet** の一部であるテーブルと列は、ユーザーが認識しやすい名前と厳密に型指定された変数を使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fed6a-104">Tables and columns that are part of the **DataSet** can be accessed using user-friendly names and strongly typed variables.</span></span>  
  
 <span data-ttu-id="fed6a-105">型指定された **DataSet** とは、**DataSet** から派生するクラスのことです。</span><span class="sxs-lookup"><span data-stu-id="fed6a-105">A typed **DataSet** is a class that derives from a **DataSet**.</span></span> <span data-ttu-id="fed6a-106">したがって、**DataSet** のすべてのメソッド、イベント、プロパティを継承します。</span><span class="sxs-lookup"><span data-stu-id="fed6a-106">As such, it inherits all the methods, events, and properties of a **DataSet**.</span></span> <span data-ttu-id="fed6a-107">さらに、型指定された **DataSet** には、厳密に型指定されたメソッド、イベント、およびプロパティが用意されています。</span><span class="sxs-lookup"><span data-stu-id="fed6a-107">Additionally, a typed **DataSet** provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="fed6a-108">つまり、コレクションベースのメソッドを使用せずに名前でテーブルおよび列にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fed6a-108">This means you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="fed6a-109">コードが読みやすく変更されただけでなく、型指定された **DataSet** を使用して、入力するとおりにラインを Visual Studio .NET コード エディターに自動挿入できます。</span><span class="sxs-lookup"><span data-stu-id="fed6a-109">Aside from the improved readability of the code, a typed **DataSet** also allows the Visual Studio .NET code editor to automatically complete lines as you type.</span></span>  
  
 <span data-ttu-id="fed6a-110">さらに、厳密に型指定された **DataSet** を使用してコンパイル時に正しい型で値にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fed6a-110">Additionally, the strongly typed **DataSet** provides access to values as the correct type at compile time.</span></span> <span data-ttu-id="fed6a-111">厳密に型指定された **DataSet** を使用すると、型の不一致が実行時ではなく、コードのコンパイル時にキャッチされます。</span><span class="sxs-lookup"><span data-stu-id="fed6a-111">With a strongly typed **DataSet**, type mismatch errors are caught when the code is compiled rather than at run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fed6a-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="fed6a-112">In This Section</span></span>  

 [<span data-ttu-id="fed6a-113">厳密に型指定された DataSet の生成</span><span class="sxs-lookup"><span data-stu-id="fed6a-113">Generating Strongly Typed DataSets</span></span>](generating-strongly-typed-datasets.md)  
 <span data-ttu-id="fed6a-114">厳密に型指定された **DataSet** の作成および使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fed6a-114">Describes how to create and use a strongly typed **DataSet**.</span></span>  
  
 [<span data-ttu-id="fed6a-115">型指定された DataSet の注釈</span><span class="sxs-lookup"><span data-stu-id="fed6a-115">Annotating Typed DataSets</span></span>](annotating-typed-datasets.md)  
 <span data-ttu-id="fed6a-116">基になるスキーマを変更せずに **DataSet** の要素にフレンドリ名を付けるために、厳密に型指定された **DataSet** の生成に使用する XML スキーマ定義言語 (XSD) スキーマに注釈を付ける方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fed6a-116">Describes how to annotate the XML Schema definition language (XSD) schema used to generate a strongly typed **DataSet**, to give **DataSet** elements friendly names without altering the underlying schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fed6a-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="fed6a-117">See also</span></span>

- [<span data-ttu-id="fed6a-118">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="fed6a-118">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="fed6a-119">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="fed6a-119">ADO.NET Overview</span></span>](../ado-net-overview.md)
