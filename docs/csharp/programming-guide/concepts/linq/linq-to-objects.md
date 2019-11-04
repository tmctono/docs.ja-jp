---
title: LINQ to Objects (C#)
ms.date: 07/20/2015
ms.assetid: c5c2c178-3529-4f6c-b3df-2d5267af7f22
ms.openlocfilehash: 8c0eb71fffdd29d9599d74c789a66ec7caf1faeb
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "73418179"
---
# <a name="linq-to-objects-c"></a><span data-ttu-id="98cd1-102">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="98cd1-102">LINQ to Objects (C#)</span></span>
<span data-ttu-id="98cd1-103">"LINQ to Objects" という用語は、[LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) や [LINQ to XML](./linq-to-xml-overview.md) などの中間 LINQ プロバイダーまたは API を使用せずに、LINQ クエリを任意の <xref:System.Collections.IEnumerable> コレクションまたは <xref:System.Collections.Generic.IEnumerable%601> コレクションと直接組み合わせて使用することを意味します。</span><span class="sxs-lookup"><span data-stu-id="98cd1-103">The term "LINQ to Objects" refers to the use of LINQ queries with any <xref:System.Collections.IEnumerable> or <xref:System.Collections.Generic.IEnumerable%601> collection directly, without the use of an intermediate LINQ provider or API such as [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) or [LINQ to XML](./linq-to-xml-overview.md).</span></span> <span data-ttu-id="98cd1-104">LINQ を使用して、<xref:System.Collections.Generic.List%601>、<xref:System.Array>、<xref:System.Collections.Generic.Dictionary%602> などの任意の列挙可能なコレクションを照会できます。</span><span class="sxs-lookup"><span data-stu-id="98cd1-104">You can use LINQ to query any enumerable collections such as <xref:System.Collections.Generic.List%601>, <xref:System.Array>, or <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="98cd1-105">このコレクションは、ユーザー定義のコレクションでも、.NET Framework API から返されたコレクションでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="98cd1-105">The collection may be user-defined or may be returned by a .NET Framework API.</span></span>  
  
 <span data-ttu-id="98cd1-106">本質的に、LINQ to Objects は、コレクションを扱うための新しい方法です。</span><span class="sxs-lookup"><span data-stu-id="98cd1-106">In a basic sense, LINQ to Objects represents a new approach to collections.</span></span> <span data-ttu-id="98cd1-107">従来の方法では、複雑な `foreach` ループを記述して、コレクションからデータを取得する方法を指定する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="98cd1-107">In the old way, you had to write complex `foreach` loops that specified how to retrieve data from a collection.</span></span> <span data-ttu-id="98cd1-108">LINQ を使用する場合は、何を取得するかを表す宣言コードを記述します。</span><span class="sxs-lookup"><span data-stu-id="98cd1-108">In the LINQ approach, you write declarative code that describes what you want to retrieve.</span></span>  
  
 <span data-ttu-id="98cd1-109">また、LINQ クエリには、従来の `foreach` ループと比べて、次の 3 つの重要な利点があります。</span><span class="sxs-lookup"><span data-stu-id="98cd1-109">In addition, LINQ queries offer three main advantages over traditional `foreach` loops:</span></span>  
  
1. <span data-ttu-id="98cd1-110">簡潔で読みやすい (特に複数の条件をフィルター処理する場合)。</span><span class="sxs-lookup"><span data-stu-id="98cd1-110">They are more concise and readable, especially when filtering multiple conditions.</span></span>  
  
2. <span data-ttu-id="98cd1-111">強力なフィルター処理、並べ替え、およびグループ化機能を最小限のアプリケーション コードで実現できる。</span><span class="sxs-lookup"><span data-stu-id="98cd1-111">They provide powerful filtering, ordering, and grouping capabilities with a minimum of application code.</span></span>  
  
3. <span data-ttu-id="98cd1-112">ほとんど、またはまったく変更せずに、他のデータ ソースに移植できる。</span><span class="sxs-lookup"><span data-stu-id="98cd1-112">They can be ported to other data sources with little or no modification.</span></span>  
  
 <span data-ttu-id="98cd1-113">通常、データに対して実行する操作が複雑なほど、従来の反復処理手法の代わりに LINQ を使用する利便性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="98cd1-113">In general, the more complex the operation you want to perform on the data, the more benefit you will realize by using LINQ instead of traditional iteration techniques.</span></span>  
  
 <span data-ttu-id="98cd1-114">このセクションでは、いくつか例を挙げながら、LINQ を使った方法を具体的に説明します。</span><span class="sxs-lookup"><span data-stu-id="98cd1-114">The purpose of this section is to demonstrate the LINQ approach with some select examples.</span></span> <span data-ttu-id="98cd1-115">ただし、すべてを網羅したものではありません。</span><span class="sxs-lookup"><span data-stu-id="98cd1-115">It is not intended to be exhaustive.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="98cd1-116">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="98cd1-116">In This Section</span></span>  
 [<span data-ttu-id="98cd1-117">LINQ と文字列 (C#)</span><span class="sxs-lookup"><span data-stu-id="98cd1-117">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)  
 <span data-ttu-id="98cd1-118">LINQ を使用して、文字列および文字列のコレクションの照会と変換を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="98cd1-118">Explains how LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="98cd1-119">これらの基本原則を具体的に示すトピックへのリンクも含まれます。</span><span class="sxs-lookup"><span data-stu-id="98cd1-119">Also includes links to topics that demonstrate these principles.</span></span>  
  
 [<span data-ttu-id="98cd1-120">LINQ とリフレクション (C#)</span><span class="sxs-lookup"><span data-stu-id="98cd1-120">LINQ and Reflection (C#)</span></span>](how-to-query-an-assembly-s-metadata-with-reflection-linq.md)  
 <span data-ttu-id="98cd1-121">LINQ でリフレクションを使用する方法を示すサンプルへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="98cd1-121">Links to a sample that demonstrates how LINQ uses reflection.</span></span>  
  
 [<span data-ttu-id="98cd1-122">LINQ とファイル ディレクトリ (C#)</span><span class="sxs-lookup"><span data-stu-id="98cd1-122">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)  
 <span data-ttu-id="98cd1-123">LINQ を使用して、ファイル システムとやり取りする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="98cd1-123">Explains how LINQ can be used to interact with file systems.</span></span> <span data-ttu-id="98cd1-124">これらの概念を具体的に示すトピックへのリンクも含まれます。</span><span class="sxs-lookup"><span data-stu-id="98cd1-124">Also includes links to topics that demonstrate these concepts.</span></span>  
  
 [<span data-ttu-id="98cd1-125">方法: LINQ を使用して ArrayList を照会する (C#)</span><span class="sxs-lookup"><span data-stu-id="98cd1-125">How to: Query an ArrayList with LINQ (C#)</span></span>](./how-to-query-an-arraylist-with-linq.md)  
 <span data-ttu-id="98cd1-126">C# で ArrayList を照会する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="98cd1-126">Demonstrates how to query an ArrayList in C#.</span></span>  
  
 [<span data-ttu-id="98cd1-127">方法: LINQ クエリのカスタム メソッドを追加する (C#)</span><span class="sxs-lookup"><span data-stu-id="98cd1-127">How to: Add Custom Methods for LINQ Queries (C#)</span></span>](./how-to-add-custom-methods-for-linq-queries.md)  
 <span data-ttu-id="98cd1-128"><xref:System.Collections.Generic.IEnumerable%601> インターフェイスに拡張メソッドを追加して、LINQ クエリに使用できるメソッド セットを拡張する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="98cd1-128">Explains how to extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>  
  
 [<span data-ttu-id="98cd1-129">統合言語クエリ (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="98cd1-129">Language-Integrated Query (LINQ) (C#)</span></span>](./index.md)  
 <span data-ttu-id="98cd1-130">LINQ について説明しているトピックへのリンクと、クエリを実行するコードの例を示します。</span><span class="sxs-lookup"><span data-stu-id="98cd1-130">Provides links to topics that explain LINQ and provide examples of code that perform queries.</span></span>
