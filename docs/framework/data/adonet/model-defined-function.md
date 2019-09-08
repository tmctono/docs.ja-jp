---
title: モデル定義関数
ms.date: 03/30/2017
ms.assetid: 8bb2edc8-e8e7-44c2-adc7-f44e11bda4f0
ms.openlocfilehash: 1418eccecea647204620455969696c6390bd4a18
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783624"
---
# <a name="model-defined-function"></a><span data-ttu-id="32539-102">モデル定義関数</span><span class="sxs-lookup"><span data-stu-id="32539-102">model-defined function</span></span>
<span data-ttu-id="32539-103">*モデル定義関数*は、概念モデルで定義されている関数です。</span><span class="sxs-lookup"><span data-stu-id="32539-103">A *model-defined function* is a function that is defined in a conceptual model.</span></span> <span data-ttu-id="32539-104">モデル定義関数の本体は[Entity SQL](./ef/language-reference/entity-sql-language.md)で表現されます。これにより、関数は、データソースでサポートされているルールまたは言語とは別に表現できます。</span><span class="sxs-lookup"><span data-stu-id="32539-104">The body of a model-defined function is expressed in [Entity SQL](./ef/language-reference/entity-sql-language.md), which allows for the function to be expressed independently of rules or languages supported in the data source.</span></span>  
  
 <span data-ttu-id="32539-105">モデル定義関数の定義には、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="32539-105">A definition for a model-defined function contains the following information:</span></span>  
  
- <span data-ttu-id="32539-106">関数名。</span><span class="sxs-lookup"><span data-stu-id="32539-106">A function name.</span></span> <span data-ttu-id="32539-107">(必須)</span><span class="sxs-lookup"><span data-stu-id="32539-107">(Required)</span></span>  
  
- <span data-ttu-id="32539-108">戻り値の型。</span><span class="sxs-lookup"><span data-stu-id="32539-108">The type of the return value.</span></span> <span data-ttu-id="32539-109">(オプション)</span><span class="sxs-lookup"><span data-stu-id="32539-109">(Optional)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="32539-110">戻り値の型が指定されていない場合、戻り値は void になります。</span><span class="sxs-lookup"><span data-stu-id="32539-110">If no return type is specified, the return value is void.</span></span>  
  
- <span data-ttu-id="32539-111">パラメーター情報。</span><span class="sxs-lookup"><span data-stu-id="32539-111">Parameter information.</span></span> <span data-ttu-id="32539-112">(オプション)</span><span class="sxs-lookup"><span data-stu-id="32539-112">(Optional)</span></span>  
  
- <span data-ttu-id="32539-113">関数の本体を定義する[Entity SQL](./ef/language-reference/entity-sql-language.md)式。</span><span class="sxs-lookup"><span data-stu-id="32539-113">An [Entity SQL](./ef/language-reference/entity-sql-language.md) expression that defines the body of the function.</span></span>  
  
 <span data-ttu-id="32539-114">モデル定義関数では、出力パラメーターがサポートされません。</span><span class="sxs-lookup"><span data-stu-id="32539-114">Note that model-defined functions do not support output parameters.</span></span> <span data-ttu-id="32539-115">この制約は、モデル定義関数を構成できるようにするためにあります。</span><span class="sxs-lookup"><span data-stu-id="32539-115">This restriction is in place so that model-defined functions can be composed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32539-116">例</span><span class="sxs-lookup"><span data-stu-id="32539-116">Example</span></span>  
 <span data-ttu-id="32539-117">下のダイアグラムは、`Book`、`Publisher`、および `Author` という 3 つのエンティティ型の概念モデルを示しています。</span><span class="sxs-lookup"><span data-stu-id="32539-117">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  
  
 ![公開日を含むモデルを示すスクリーンショット。](./media/model-defined-function/model-published-date-three-entity-types.gif)  
  
 <span data-ttu-id="32539-119">[ADO.NET Entity Framework](./ef/index.md)は、概念スキーマ定義言語 ([CSDL](./ef/language-reference/csdl-specification.md)) と呼ばれるドメイン固有言語 (DSL) を使用して概念モデルを定義します。</span><span class="sxs-lookup"><span data-stu-id="32539-119">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](./ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="32539-120">次の CSDL は、`Book` (上のダイアグラムの) の出版以降の年数を返す概念モデルの関数を定義しています。</span><span class="sxs-lookup"><span data-stu-id="32539-120">The following CSDL defines a function in the conceptual model that returns the numbers of years since an instance of a `Book` (in the diagram above) was published.</span></span>  
  
 [!code-xml[EDM_Example_Model#ModelDefinedFunction](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#modeldefinedfunction)]  
  
## <a name="see-also"></a><span data-ttu-id="32539-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="32539-121">See also</span></span>

- [<span data-ttu-id="32539-122">Entity Data Model キーの概念</span><span class="sxs-lookup"><span data-stu-id="32539-122">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="32539-123">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="32539-123">Entity Data Model</span></span>](entity-data-model.md)
- [<span data-ttu-id="32539-124">Entity Data Model:プリミティブデータ型</span><span class="sxs-lookup"><span data-stu-id="32539-124">Entity Data Model: Primitive Data Types</span></span>](entity-data-model-primitive-data-types.md)
