---
title: LINQ to Objects (C#)
description: C# での LINQ to Objects について学習します。これは、中間 LINQ プロバイダーまたは API を使用せずに、任意の IEnumerable または IEnumerable<T> コレクションと共に LINQ クエリを使用します。
ms.date: 07/20/2015
ms.assetid: c5c2c178-3529-4f6c-b3df-2d5267af7f22
ms.openlocfilehash: 575708f14487670a4371d470dcdcf650b03c3175
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202527"
---
# <a name="linq-to-objects-c"></a><span data-ttu-id="8fbde-103">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="8fbde-103">LINQ to Objects (C#)</span></span>

<span data-ttu-id="8fbde-104">"LINQ to Objects" という用語は、[LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) や [LINQ to XML](../../../../standard/linq/linq-xml-overview.md) などの中間 LINQ プロバイダーまたは API を使用せずに、LINQ クエリを任意の <xref:System.Collections.IEnumerable> コレクションまたは <xref:System.Collections.Generic.IEnumerable%601> コレクションと直接組み合わせて使用することを意味します。</span><span class="sxs-lookup"><span data-stu-id="8fbde-104">The term "LINQ to Objects" refers to the use of LINQ queries with any <xref:System.Collections.IEnumerable> or <xref:System.Collections.Generic.IEnumerable%601> collection directly, without the use of an intermediate LINQ provider or API such as [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) or [LINQ to XML](../../../../standard/linq/linq-xml-overview.md).</span></span> <span data-ttu-id="8fbde-105">LINQ を使用して、<xref:System.Collections.Generic.List%601>、<xref:System.Array>、<xref:System.Collections.Generic.Dictionary%602> などの任意の列挙可能なコレクションを照会できます。</span><span class="sxs-lookup"><span data-stu-id="8fbde-105">You can use LINQ to query any enumerable collections such as <xref:System.Collections.Generic.List%601>, <xref:System.Array>, or <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="8fbde-106">このコレクションは、ユーザー定義のコレクションでも、.NET API から返されたコレクションでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="8fbde-106">The collection may be user-defined or may be returned by a .NET API.</span></span>  
  
 <span data-ttu-id="8fbde-107">本質的に、LINQ to Objects は、コレクションを扱うための新しい方法です。</span><span class="sxs-lookup"><span data-stu-id="8fbde-107">In a basic sense, LINQ to Objects represents a new approach to collections.</span></span> <span data-ttu-id="8fbde-108">従来の方法では、複雑な `foreach` ループを記述して、コレクションからデータを取得する方法を指定する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="8fbde-108">In the old way, you had to write complex `foreach` loops that specified how to retrieve data from a collection.</span></span> <span data-ttu-id="8fbde-109">LINQ を使用する場合は、何を取得するかを表す宣言コードを記述します。</span><span class="sxs-lookup"><span data-stu-id="8fbde-109">In the LINQ approach, you write declarative code that describes what you want to retrieve.</span></span>  
  
 <span data-ttu-id="8fbde-110">また、LINQ クエリには、従来の `foreach` ループと比べて、次の 3 つの重要な利点があります。</span><span class="sxs-lookup"><span data-stu-id="8fbde-110">In addition, LINQ queries offer three main advantages over traditional `foreach` loops:</span></span>  
  
- <span data-ttu-id="8fbde-111">簡潔で読みやすい (特に複数の条件をフィルター処理する場合)。</span><span class="sxs-lookup"><span data-stu-id="8fbde-111">They are more concise and readable, especially when filtering multiple conditions.</span></span>  
  
- <span data-ttu-id="8fbde-112">強力なフィルター処理、並べ替え、およびグループ化機能を最小限のアプリケーション コードで実現できる。</span><span class="sxs-lookup"><span data-stu-id="8fbde-112">They provide powerful filtering, ordering, and grouping capabilities with a minimum of application code.</span></span>  
  
- <span data-ttu-id="8fbde-113">ほとんど、またはまったく変更せずに、他のデータ ソースに移植できる。</span><span class="sxs-lookup"><span data-stu-id="8fbde-113">They can be ported to other data sources with little or no modification.</span></span>  
  
 <span data-ttu-id="8fbde-114">通常、データに対して実行する操作が複雑なほど、従来の反復処理手法の代わりに LINQ を使用する利便性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="8fbde-114">In general, the more complex the operation you want to perform on the data, the more benefit you'll realize by using LINQ instead of traditional iteration techniques.</span></span>  
  
 <span data-ttu-id="8fbde-115">このセクションでは、いくつか例を挙げながら、LINQ を使った方法を具体的に説明します。</span><span class="sxs-lookup"><span data-stu-id="8fbde-115">The purpose of this section is to demonstrate the LINQ approach with some select examples.</span></span> <span data-ttu-id="8fbde-116">すべてを網羅したものではありません。</span><span class="sxs-lookup"><span data-stu-id="8fbde-116">It's not intended to be exhaustive.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8fbde-117">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8fbde-117">In This Section</span></span>  

 [<span data-ttu-id="8fbde-118">LINQ と文字列 (C#)</span><span class="sxs-lookup"><span data-stu-id="8fbde-118">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)  
 <span data-ttu-id="8fbde-119">LINQ を使用して、文字列および文字列のコレクションの照会と変換を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8fbde-119">Explains how LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="8fbde-120">これらの基本原則を具体的に示す記事へのリンクも含まれます。</span><span class="sxs-lookup"><span data-stu-id="8fbde-120">Also includes links to articles that demonstrate these principles.</span></span>  
  
 [<span data-ttu-id="8fbde-121">LINQ とリフレクション (C#)</span><span class="sxs-lookup"><span data-stu-id="8fbde-121">LINQ and Reflection (C#)</span></span>](how-to-query-an-assembly-s-metadata-with-reflection-linq.md)  
 <span data-ttu-id="8fbde-122">LINQ でリフレクションを使用する方法を示すサンプルへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="8fbde-122">Links to a sample that demonstrates how LINQ uses reflection.</span></span>  
  
 [<span data-ttu-id="8fbde-123">LINQ とファイル ディレクトリ (C#)</span><span class="sxs-lookup"><span data-stu-id="8fbde-123">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)  
 <span data-ttu-id="8fbde-124">LINQ を使用して、ファイル システムとやり取りする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8fbde-124">Explains how LINQ can be used to interact with file systems.</span></span> <span data-ttu-id="8fbde-125">これらの概念を具体的に示す記事へのリンクも含まれます。</span><span class="sxs-lookup"><span data-stu-id="8fbde-125">Also includes links to articles that demonstrate these concepts.</span></span>  
  
 [<span data-ttu-id="8fbde-126">LINQ を使用して ArrayList にクエリを実行する方法 (C#)</span><span class="sxs-lookup"><span data-stu-id="8fbde-126">How to query an ArrayList with LINQ (C#)</span></span>](./how-to-query-an-arraylist-with-linq.md)  
 <span data-ttu-id="8fbde-127">C# で ArrayList を照会する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8fbde-127">Demonstrates how to query an ArrayList in C#.</span></span>  
  
 [<span data-ttu-id="8fbde-128">LINQ クエリのカスタム メソッドを追加する方法 (C#)</span><span class="sxs-lookup"><span data-stu-id="8fbde-128">How to add custom methods for LINQ queries (C#)</span></span>](./how-to-add-custom-methods-for-linq-queries.md)  
 <span data-ttu-id="8fbde-129"><xref:System.Collections.Generic.IEnumerable%601> インターフェイスに拡張メソッドを追加して、LINQ クエリに使用できるメソッド セットを拡張する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8fbde-129">Explains how to extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>  
  
 [<span data-ttu-id="8fbde-130">統合言語クエリ (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="8fbde-130">Language-Integrated Query (LINQ) (C#)</span></span>](./index.md)  
 <span data-ttu-id="8fbde-131">LINQ について説明している記事へのリンクと、クエリを実行するコードの例を示します。</span><span class="sxs-lookup"><span data-stu-id="8fbde-131">Provides links to articles that explain LINQ and provide examples of code that perform queries.</span></span>
