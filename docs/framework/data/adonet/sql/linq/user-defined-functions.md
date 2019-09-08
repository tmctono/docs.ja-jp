---
title: ユーザー定義関数
ms.date: 03/30/2017
ms.assetid: 3304c9b2-5c7a-4a95-9d45-4f260dcb606e
ms.openlocfilehash: 40697da4fe678668f8f7ecda86abebf40da7b973
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792303"
---
# <a name="user-defined-functions"></a><span data-ttu-id="a25b3-102">ユーザー定義関数</span><span class="sxs-lookup"><span data-stu-id="a25b3-102">User-Defined Functions</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="a25b3-103">では、オブジェクト モデル内のメソッドを使用して、ユーザー定義関数を表します。</span><span class="sxs-lookup"><span data-stu-id="a25b3-103">uses methods in your object model to represent user-defined functions.</span></span> <span data-ttu-id="a25b3-104"><xref:System.Data.Linq.Mapping.FunctionAttribute> 属性、および必要に応じて <xref:System.Data.Linq.Mapping.ParameterAttribute> 属性を適用することによって、メソッドを関数として指定します。</span><span class="sxs-lookup"><span data-stu-id="a25b3-104">You designate methods as functions by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="a25b3-105">詳細については、「 [LINQ to SQL オブジェクトモデル](the-linq-to-sql-object-model.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a25b3-105">For more information, see [The LINQ to SQL Object Model](the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="a25b3-106"><xref:System.InvalidOperationException> を回避するため、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] で作成するユーザー定義関数は次のいずれかの形式にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a25b3-106">To avoid an <xref:System.InvalidOperationException>, user-defined functions in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] must be in one of the following forms:</span></span>  
  
- <span data-ttu-id="a25b3-107">正しいマッピング属性を持つメソッド呼び出しとしてラップされた関数。</span><span class="sxs-lookup"><span data-stu-id="a25b3-107">A function wrapped as a method call having the correct mapping attributes.</span></span> <span data-ttu-id="a25b3-108">詳細については、「[属性ベースのマッピング](attribute-based-mapping.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a25b3-108">For more information, see [Attribute-Based Mapping](attribute-based-mapping.md).</span></span>  
  
- <span data-ttu-id="a25b3-109">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] に固有の静的 SQL メソッド。</span><span class="sxs-lookup"><span data-stu-id="a25b3-109">A static SQL method specific to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
- <span data-ttu-id="a25b3-110">.NET Framework メソッドによってサポートされる関数。</span><span class="sxs-lookup"><span data-stu-id="a25b3-110">A function supported by a .NET Framework method.</span></span>  
  
 <span data-ttu-id="a25b3-111">このセクションのトピックでは、自分でコードを作成する場合に、アプリケーション内でこれらのメソッドを記述および呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a25b3-111">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span> <span data-ttu-id="a25b3-112">Visual Studio を使用する開発者は、通常、オブジェクトリレーショナルデザイナーを使用してユーザー定義関数をマップします。</span><span class="sxs-lookup"><span data-stu-id="a25b3-112">Developers using Visual Studio would typically use the Object Relational Designer to map user-defined functions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a25b3-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a25b3-113">In This Section</span></span>  
 [<span data-ttu-id="a25b3-114">方法: スカラー値のユーザー定義関数を使用する</span><span class="sxs-lookup"><span data-stu-id="a25b3-114">How to: Use Scalar-Valued User-Defined Functions</span></span>](how-to-use-scalar-valued-user-defined-functions.md)  
 <span data-ttu-id="a25b3-115">スカラー値を返す関数を実装する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="a25b3-115">Describes how to implement a function that returns scalar values.</span></span>  
  
 [<span data-ttu-id="a25b3-116">方法: テーブル値ユーザー定義関数を使用する</span><span class="sxs-lookup"><span data-stu-id="a25b3-116">How to: Use Table-Valued User-Defined Functions</span></span>](how-to-use-table-valued-user-defined-functions.md)  
 <span data-ttu-id="a25b3-117">テーブル値を返す関数を実装する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="a25b3-117">Describes how to implement a function that returns table values.</span></span>  
  
 [<span data-ttu-id="a25b3-118">方法: ユーザー定義関数をインラインで呼び出す</span><span class="sxs-lookup"><span data-stu-id="a25b3-118">How to: Call User-Defined Functions Inline</span></span>](how-to-call-user-defined-functions-inline.md)  
 <span data-ttu-id="a25b3-119">関数をインラインで呼び出す方法とインライン呼び出しの実行時の相違点について説明します。</span><span class="sxs-lookup"><span data-stu-id="a25b3-119">Describes how to make inline calls to functions and the differences in execution when the call is made inline.</span></span>
