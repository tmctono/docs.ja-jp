---
title: LINQ to Entities クエリ内の関数の呼び出し
ms.date: 03/30/2017
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
ms.openlocfilehash: 267bb393d9e75c66eb18139e8897da34bd86e159
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251261"
---
# <a name="calling-functions-in-linq-to-entities-queries"></a><span data-ttu-id="57a9f-102">LINQ to Entities クエリ内の関数の呼び出し</span><span class="sxs-lookup"><span data-stu-id="57a9f-102">Calling Functions in LINQ to Entities Queries</span></span>
<span data-ttu-id="57a9f-103">このセクションの各トピックでは、LINQ to Entities クエリで関数を呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="57a9f-103">The topics in this section describe how to call functions in LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="57a9f-104"><xref:System.Data.Objects.EntityFunctions> クラスおよび <xref:System.Data.Objects.SqlClient.SqlFunctions> クラスを使用すると、Entity Framework の一部として正規関数およびデータベース関数にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="57a9f-104">The <xref:System.Data.Objects.EntityFunctions> and <xref:System.Data.Objects.SqlClient.SqlFunctions> classes provide access to canonical and database functions as part of the Entity Framework.</span></span> <span data-ttu-id="57a9f-105">詳細については、「[方法 :正規関数](how-to-call-canonical-functions.md)を呼び出し[、次の方法を実行します。データベース関数](how-to-call-database-functions.md)を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="57a9f-105">For more information, see [How to: Call Canonical Functions](how-to-call-canonical-functions.md) and [How to: Call Database Functions](how-to-call-database-functions.md).</span></span>  
  
 <span data-ttu-id="57a9f-106">カスタム関数を呼び出すプロセスには、3 つの基本的な手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="57a9f-106">The process for calling a custom function requires three basic steps:</span></span>  
  
1. <span data-ttu-id="57a9f-107">概念モデルで関数を定義するか、ストレージ モデルで関数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="57a9f-107">Define a function in your conceptual model or declare a function in your storage model.</span></span>  
  
2. <span data-ttu-id="57a9f-108">メソッドをアプリケーションに追加し、<xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> を使用してこれをモデルの関数にマップします。</span><span class="sxs-lookup"><span data-stu-id="57a9f-108">Add a method to your application and map it to the function in the model with an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span>  
  
3. <span data-ttu-id="57a9f-109">LINQ to Entities クエリから関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="57a9f-109">Call the function in a LINQ to Entities query.</span></span>  
  
 <span data-ttu-id="57a9f-110">詳細については、このセクションの各トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="57a9f-110">For more information, see the topics in this section.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="57a9f-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="57a9f-111">In This Section</span></span>  
 [<span data-ttu-id="57a9f-112">方法: 正規関数を呼び出す</span><span class="sxs-lookup"><span data-stu-id="57a9f-112">How to: Call Canonical Functions</span></span>](how-to-call-canonical-functions.md)  
  
 [<span data-ttu-id="57a9f-113">方法: データベース関数の呼び出し</span><span class="sxs-lookup"><span data-stu-id="57a9f-113">How to: Call Database Functions</span></span>](how-to-call-database-functions.md)  
  
 [<span data-ttu-id="57a9f-114">方法: カスタムデータベース関数を呼び出す</span><span class="sxs-lookup"><span data-stu-id="57a9f-114">How to: Call Custom Database Functions</span></span>](how-to-call-custom-database-functions.md)  
  
 [<span data-ttu-id="57a9f-115">方法: クエリでモデル定義関数を呼び出す</span><span class="sxs-lookup"><span data-stu-id="57a9f-115">How to: Call Model-Defined Functions in Queries</span></span>](how-to-call-model-defined-functions-in-queries.md)  
  
 [<span data-ttu-id="57a9f-116">方法: モデル定義関数をオブジェクトメソッドとして呼び出す</span><span class="sxs-lookup"><span data-stu-id="57a9f-116">How to: Call Model-Defined Functions as Object Methods</span></span>](how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a><span data-ttu-id="57a9f-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="57a9f-117">See also</span></span>

- [<span data-ttu-id="57a9f-118">LINQ to Entities でのクエリ</span><span class="sxs-lookup"><span data-stu-id="57a9f-118">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
- [<span data-ttu-id="57a9f-119">正規関数</span><span class="sxs-lookup"><span data-stu-id="57a9f-119">Canonical Functions</span></span>](canonical-functions.md)
- <span data-ttu-id="57a9f-120">[.edmx ファイルの概要](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="57a9f-120">[.edmx File Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- <span data-ttu-id="57a9f-121">[方法: 概念モデルでカスタム関数を定義する](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="57a9f-121">[How to: Define Custom Functions in the Conceptual Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))</span></span>
