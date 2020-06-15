---
title: LINQ to Entities クエリ内の関数の呼び出し
description: これらの記事では、EntityFunctions および SqlFunctions クラスにより、Entity Framework の一部として正規関数およびデータベース関数へのアクセスが可能になるしくみについて説明します。
ms.date: 03/30/2017
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
ms.openlocfilehash: faa6406713592f10e5e7371cd73f29bec4b03b7b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286858"
---
# <a name="calling-functions-in-linq-to-entities-queries"></a><span data-ttu-id="67f62-103">LINQ to Entities クエリ内の関数の呼び出し</span><span class="sxs-lookup"><span data-stu-id="67f62-103">Calling Functions in LINQ to Entities Queries</span></span>
<span data-ttu-id="67f62-104">このセクションの各トピックでは、LINQ to Entities クエリで関数を呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="67f62-104">The topics in this section describe how to call functions in LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="67f62-105"><xref:System.Data.Objects.EntityFunctions> クラスおよび <xref:System.Data.Objects.SqlClient.SqlFunctions> クラスを使用すると、Entity Framework の一部として正規関数およびデータベース関数にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="67f62-105">The <xref:System.Data.Objects.EntityFunctions> and <xref:System.Data.Objects.SqlClient.SqlFunctions> classes provide access to canonical and database functions as part of the Entity Framework.</span></span> <span data-ttu-id="67f62-106">詳細については、[Canonical 関数を呼び出す](how-to-call-canonical-functions.md)」および「[方法:データベース関数を呼び出す](how-to-call-database-functions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67f62-106">For more information, see [How to: Call Canonical Functions](how-to-call-canonical-functions.md) and [How to: Call Database Functions](how-to-call-database-functions.md).</span></span>  
  
 <span data-ttu-id="67f62-107">カスタム関数を呼び出すプロセスには、3 つの基本的な手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="67f62-107">The process for calling a custom function requires three basic steps:</span></span>  
  
1. <span data-ttu-id="67f62-108">概念モデルで関数を定義するか、ストレージ モデルで関数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="67f62-108">Define a function in your conceptual model or declare a function in your storage model.</span></span>  
  
2. <span data-ttu-id="67f62-109">メソッドをアプリケーションに追加し、<xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> を使用してこれをモデルの関数にマップします。</span><span class="sxs-lookup"><span data-stu-id="67f62-109">Add a method to your application and map it to the function in the model with an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span>  
  
3. <span data-ttu-id="67f62-110">LINQ to Entities クエリから関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="67f62-110">Call the function in a LINQ to Entities query.</span></span>  
  
 <span data-ttu-id="67f62-111">詳細については、このセクションの各トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="67f62-111">For more information, see the topics in this section.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="67f62-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="67f62-112">In This Section</span></span>  
 [<span data-ttu-id="67f62-113">方法: Canonical 関数を呼び出す</span><span class="sxs-lookup"><span data-stu-id="67f62-113">How to: Call Canonical Functions</span></span>](how-to-call-canonical-functions.md)  
  
 [<span data-ttu-id="67f62-114">方法: データベース関数を呼び出す</span><span class="sxs-lookup"><span data-stu-id="67f62-114">How to: Call Database Functions</span></span>](how-to-call-database-functions.md)  
  
 [<span data-ttu-id="67f62-115">方法: カスタム データベース関数を呼び出す</span><span class="sxs-lookup"><span data-stu-id="67f62-115">How to: Call Custom Database Functions</span></span>](how-to-call-custom-database-functions.md)  
  
 [<span data-ttu-id="67f62-116">方法: クエリを使用してモデル定義関数を呼び出す</span><span class="sxs-lookup"><span data-stu-id="67f62-116">How to: Call Model-Defined Functions in Queries</span></span>](how-to-call-model-defined-functions-in-queries.md)  
  
 [<span data-ttu-id="67f62-117">方法: モデル定義関数をオブジェクト メソッドとして呼び出す</span><span class="sxs-lookup"><span data-stu-id="67f62-117">How to: Call Model-Defined Functions as Object Methods</span></span>](how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a><span data-ttu-id="67f62-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="67f62-118">See also</span></span>

- [<span data-ttu-id="67f62-119">LINQ to Entities でのクエリ</span><span class="sxs-lookup"><span data-stu-id="67f62-119">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
- [<span data-ttu-id="67f62-120">正規関数</span><span class="sxs-lookup"><span data-stu-id="67f62-120">Canonical Functions</span></span>](canonical-functions.md)
- <span data-ttu-id="67f62-121">[.edmx ファイルの概要](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="67f62-121">[.edmx File Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- <span data-ttu-id="67f62-122">[方法: 概念モデルでカスタム関数を定義する](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="67f62-122">[How to: Define Custom Functions in the Conceptual Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))</span></span>
