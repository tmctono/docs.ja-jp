---
title: LINQ とジェネリック型 (C#)
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], generic types
- generic types [LINQ]
- generics [LINQ]
ms.assetid: 660e3799-25ca-462c-8c4a-8bce04fbb031
ms.openlocfilehash: 9a2d1ac72f70e7cd314d349e81ab2bc815a5bf13
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635575"
---
# <a name="linq-and-generic-types-c"></a><span data-ttu-id="d3198-102">LINQ とジェネリック型 (C#)</span><span class="sxs-lookup"><span data-stu-id="d3198-102">LINQ and Generic Types (C#)</span></span>
<span data-ttu-id="d3198-103">LINQ クエリは、.NET Framework のバージョン 2.0 で導入されたジェネリック型に基づいています。</span><span class="sxs-lookup"><span data-stu-id="d3198-103">LINQ queries are based on generic types, which were introduced in version 2.0 of the .NET Framework.</span></span> <span data-ttu-id="d3198-104">クエリを記述するために、ジェネリックについて詳しく知っておく必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d3198-104">You do not need an in-depth knowledge of generics before you can start writing queries.</span></span> <span data-ttu-id="d3198-105">ただし、次の 2 つの基本的な概念を理解しておくと役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d3198-105">However, you may want to understand two basic concepts:</span></span>  
  
1. <span data-ttu-id="d3198-106"><xref:System.Collections.Generic.List%601> などのジェネリック コレクション クラスのインスタンスを作成するときに、リストに保持されるオブジェクトの型で "T" を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="d3198-106">When you create an instance of a generic collection class such as <xref:System.Collections.Generic.List%601>, you replace the "T" with the type of objects that the list will hold.</span></span> <span data-ttu-id="d3198-107">たとえば、文字列のリストは `List<string>` で表され、`Customer`オブジェクトのリストは `List<Customer>` で表されます。</span><span class="sxs-lookup"><span data-stu-id="d3198-107">For example, a list of strings is expressed as `List<string>`, and a list of `Customer` objects is expressed as `List<Customer>`.</span></span> <span data-ttu-id="d3198-108">ジェネリック リストは厳密に型指定されるため、要素を <xref:System.Object> として格納するコレクションと比べて多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="d3198-108">A generic list is strongly typed and provides many benefits over collections that store their elements as <xref:System.Object>.</span></span> <span data-ttu-id="d3198-109">`Customer`を `List<string>` に追加しようとすると、コンパイル時にエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="d3198-109">If you try to add a `Customer` to a `List<string>`, you will get an error at compile time.</span></span> <span data-ttu-id="d3198-110">実行時に型キャストを実行する必要がないため、ジェネリック コレクションを使用するのは簡単です。</span><span class="sxs-lookup"><span data-stu-id="d3198-110">It is easy to use generic collections because you do not have to perform run-time type-casting.</span></span>  
  
2. <span data-ttu-id="d3198-111"><xref:System.Collections.Generic.IEnumerable%601> は、`foreach` ステートメントを使用してジェネリック コレクションのクラスを列挙できるようにするインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="d3198-111"><xref:System.Collections.Generic.IEnumerable%601> is the interface that enables generic collection classes to be enumerated by using the `foreach` statement.</span></span> <span data-ttu-id="d3198-112"><xref:System.Collections.ArrayList> などの非ジェネリック コレクション クラスが <xref:System.Collections.IEnumerable> をサポートするように、ジェネリック コレクション クラスは、<xref:System.Collections.Generic.IEnumerable%601> をサポートします。</span><span class="sxs-lookup"><span data-stu-id="d3198-112">Generic collection classes support <xref:System.Collections.Generic.IEnumerable%601> just as non-generic collection classes such as <xref:System.Collections.ArrayList> support <xref:System.Collections.IEnumerable>.</span></span>  
  
 <span data-ttu-id="d3198-113">ジェネリックの詳細については、「[ジェネリック](../../generics/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3198-113">For more information about generics, see [Generics](../../generics/index.md).</span></span>  
  
## <a name="ienumerablet-variables-in-linq-queries"></a><span data-ttu-id="d3198-114">LINQ クエリの IEnumerable<T\> 変数</span><span class="sxs-lookup"><span data-stu-id="d3198-114">IEnumerable<T\> variables in LINQ Queries</span></span>  
 <span data-ttu-id="d3198-115">LINQ クエリ変数は、<xref:System.Collections.Generic.IEnumerable%601>、または <xref:System.Linq.IQueryable%601> などの派生型として型指定されます。</span><span class="sxs-lookup"><span data-stu-id="d3198-115">LINQ query variables are typed as <xref:System.Collections.Generic.IEnumerable%601> or a derived type such as <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="d3198-116">`IEnumerable<Customer>` として型指定されたクエリ変数が見つかった場合は、クエリが実行されたときに 0 個以上の `Customer` オブジェクトのシーケンスが作成されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="d3198-116">When you see a query variable that is typed as `IEnumerable<Customer>`, it just means that the query, when it is executed, will produce a sequence of zero or more `Customer` objects.</span></span>  
  
 [!code-csharp[csLINQGettingStarted#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#34)]  
  
 <span data-ttu-id="d3198-117">詳細については、「[LINQ クエリ操作での型の関係](./type-relationships-in-linq-query-operations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3198-117">For more information, see [Type Relationships in LINQ Query Operations](./type-relationships-in-linq-query-operations.md).</span></span>  
  
## <a name="letting-the-compiler-handle-generic-type-declarations"></a><span data-ttu-id="d3198-118">コンパイラによるジェネリック型の宣言の処理</span><span class="sxs-lookup"><span data-stu-id="d3198-118">Letting the Compiler Handle Generic Type Declarations</span></span>  
 <span data-ttu-id="d3198-119">必要に応じて、[var](../../../language-reference/keywords/var.md) キーワードを使用することにより、ジェネリックの構文を回避することもできます。</span><span class="sxs-lookup"><span data-stu-id="d3198-119">If you prefer, you can avoid generic syntax by using the [var](../../../language-reference/keywords/var.md) keyword.</span></span> <span data-ttu-id="d3198-120">`var` キーワードは、`from` 句で指定されたデータ ソースを調べてクエリ変数の型を推論するようにコンパイラに指示します。</span><span class="sxs-lookup"><span data-stu-id="d3198-120">The `var` keyword instructs the compiler to infer the type of a query variable by looking at the data source specified in the `from` clause.</span></span> <span data-ttu-id="d3198-121">次の例では、前の例と同じコンパイル済みのコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="d3198-121">The following example produces the same compiled code as the previous example:</span></span>  
  
 [!code-csharp[csLINQGettingStarted#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#35)]  
  
 <span data-ttu-id="d3198-122">`var` キーワードは、変数の型が明らかな場合、または入れ子にされたジェネリック型 (グループ クエリで生成されたものなど) を明示的に指定する必要がない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="d3198-122">The `var` keyword is useful when the type of the variable is obvious or when it is not that important to explicitly specify nested generic types such as those that are produced by group queries.</span></span> <span data-ttu-id="d3198-123">一般に、`var` を使用すると、他の開発者にとってコードが読みにくくなる可能性があることを理解しておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d3198-123">In general, we recommend that if you use `var`, realize that it can make your code more difficult for others to read.</span></span> <span data-ttu-id="d3198-124">詳細については、「[暗黙的に型指定されるローカル変数](../../classes-and-structs/implicitly-typed-local-variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3198-124">For more information, see [Implicitly Typed Local Variables](../../classes-and-structs/implicitly-typed-local-variables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3198-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3198-125">See also</span></span>

- [<span data-ttu-id="d3198-126">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="d3198-126">Generics</span></span>](../../generics/index.md)
