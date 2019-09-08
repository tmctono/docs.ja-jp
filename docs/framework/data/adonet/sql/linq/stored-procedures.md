---
title: ストアド プロシージャ
ms.date: 03/30/2017
ms.assetid: 4d23dd7a-a85f-44ff-a717-af7d0950c0fc
ms.openlocfilehash: 80ea105eef33ebb2a0e52d91a631258400ea3dff
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792479"
---
# <a name="stored-procedures"></a><span data-ttu-id="7a238-102">ストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="7a238-102">Stored Procedures</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="7a238-103">では、オブジェクトモデルのメソッドを使用して、データベース内のストアドプロシージャを表します。</span><span class="sxs-lookup"><span data-stu-id="7a238-103">uses methods in your object model to represent stored procedures in the database.</span></span> <span data-ttu-id="7a238-104"><xref:System.Data.Linq.Mapping.FunctionAttribute> 属性、および必要に応じて <xref:System.Data.Linq.Mapping.ParameterAttribute> 属性を適用することによって、メソッドをストアド プロシージャとして指定します。</span><span class="sxs-lookup"><span data-stu-id="7a238-104">You designate methods as stored procedures by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="7a238-105">詳細については、「 [LINQ to SQL オブジェクトモデル](the-linq-to-sql-object-model.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a238-105">For more information, see [The LINQ to SQL Object Model](the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="7a238-106">Visual Studio を使用する開発者は、通常、オブジェクトリレーショナルデザイナーを使用してストアドプロシージャをマップします。</span><span class="sxs-lookup"><span data-stu-id="7a238-106">Developers using Visual Studio would typically use the Object Relational Designer to map stored procedures.</span></span> <span data-ttu-id="7a238-107">このセクションのトピックでは、自分でコードを作成する場合に、アプリケーション内でこれらのメソッドを記述および呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7a238-107">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7a238-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7a238-108">In This Section</span></span>  
 [<span data-ttu-id="7a238-109">方法: 行セットを返す</span><span class="sxs-lookup"><span data-stu-id="7a238-109">How to: Return Rowsets</span></span>](how-to-return-rowsets.md)  
 <span data-ttu-id="7a238-110">データ行を返す方法および入力パラメーターの使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7a238-110">Describes how to return rows of data and shows how to use an input parameter.</span></span>  
  
 [<span data-ttu-id="7a238-111">方法: パラメーターを受け取るストアドプロシージャを使用する</span><span class="sxs-lookup"><span data-stu-id="7a238-111">How to: Use Stored Procedures that Take Parameters</span></span>](how-to-use-stored-procedures-that-take-parameters.md)  
 <span data-ttu-id="7a238-112">入力パラメーターおよび出力パラメーターの使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7a238-112">Describes how to use input and output parameters.</span></span>  
  
 [<span data-ttu-id="7a238-113">方法: 複数の結果形状にマップされたストアドプロシージャを使用する</span><span class="sxs-lookup"><span data-stu-id="7a238-113">How to: Use Stored Procedures Mapped for Multiple Result Shapes</span></span>](how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md)  
 <span data-ttu-id="7a238-114">同じストアド プロシージャで複数の形状の結果を返す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7a238-114">Describes how to provide for returns of multiple shapes in the same stored procedure.</span></span>  
  
 [<span data-ttu-id="7a238-115">方法: シーケンシャルな結果図形にマップされたストアドプロシージャを使用する</span><span class="sxs-lookup"><span data-stu-id="7a238-115">How to: Use Stored Procedures Mapped for Sequential Result Shapes</span></span>](how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md)  
 <span data-ttu-id="7a238-116">リターン シーケンスが既知の場合に複数の形状を返す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7a238-116">Describes how to provide for multiple shapes where the return sequence is known.</span></span>  
  
 [<span data-ttu-id="7a238-117">ストアド プロシージャによる操作のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="7a238-117">Customizing Operations By Using Stored Procedures</span></span>](customizing-operations-by-using-stored-procedures.md)  
 <span data-ttu-id="7a238-118">ストアド プロシージャを使用して挿入、更新、および削除の操作を実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7a238-118">Describes how to use stored procedures to implement insert, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="7a238-119">ストアド プロシージャのみによる操作のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="7a238-119">Customizing Operations by Using Stored Procedures Exclusively</span></span>](customizing-operations-by-using-stored-procedures-exclusively.md)  
 <span data-ttu-id="7a238-120">ストアド プロシージャのみを使用して挿入、更新、および削除の操作を実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7a238-120">Describes how to use nothing but stored procedures to implement insert, update, and delete operations.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7a238-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a238-121">Related Sections</span></span>  
 [<span data-ttu-id="7a238-122">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="7a238-122">Programming Guide</span></span>](programming-guide.md)  
 <span data-ttu-id="7a238-123">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] オブジェクト モデルを作成および使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7a238-123">Provides information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="7a238-124">チュートリアル: ストアドプロシージャのみを使用する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7a238-124">Walkthrough: Using Only Stored Procedures (Visual Basic)</span></span>](walkthrough-using-only-stored-procedures-visual-basic.md)  
 <span data-ttu-id="7a238-125">Visual Basic でストアド プロシージャを使用する手順を示します。</span><span class="sxs-lookup"><span data-stu-id="7a238-125">Includes procedures that illustrate how to use stored procedures in Visual Basic.</span></span>  
  
 [<span data-ttu-id="7a238-126">チュートリアル: ストアドプロシージャのみを使用C#する ()</span><span class="sxs-lookup"><span data-stu-id="7a238-126">Walkthrough: Using Only Stored Procedures (C#)</span></span>](walkthrough-using-only-stored-procedures-csharp.md)  
 <span data-ttu-id="7a238-127">C# でストアド プロシージャを使用する手順を示します。</span><span class="sxs-lookup"><span data-stu-id="7a238-127">Includes procedures that illustrate how to use stored procedures in C#.</span></span>
