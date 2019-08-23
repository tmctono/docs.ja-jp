---
title: モデル宣言関数
ms.date: 03/30/2017
ms.assetid: aba87f13-5685-4f6b-ad14-918e8a7d5c2a
ms.openlocfilehash: 73e716f1c42dfbbb91dc6456212de2a331d7c4ef
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943922"
---
# <a name="model-declared-function"></a><span data-ttu-id="f7a3c-102">モデル宣言関数</span><span class="sxs-lookup"><span data-stu-id="f7a3c-102">model-declared function</span></span>
<span data-ttu-id="f7a3c-103">*モデルで宣言*された関数は、概念モデルで宣言されているが、その概念モデルで定義されていない関数です。</span><span class="sxs-lookup"><span data-stu-id="f7a3c-103">A *model-declared function* is a function that is declared in a conceptual model, but is not defined in that conceptual model.</span></span> <span data-ttu-id="f7a3c-104">この関数は、ホスト環境またはストレージ環境で定義します。</span><span class="sxs-lookup"><span data-stu-id="f7a3c-104">The function might be defined in the hosting or storage environment.</span></span> <span data-ttu-id="f7a3c-105">たとえば、モデル宣言関数は、データベースに定義された関数にマップされ、これによって概念モデルにおけるサーバー側の機能が公開される場合があります。</span><span class="sxs-lookup"><span data-stu-id="f7a3c-105">For example, a model-declared function might be mapped to a function that is defined in a database, thus exposing server-side functionality in the conceptual model.</span></span>  
  
 <span data-ttu-id="f7a3c-106">モデル宣言関数の宣言には、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f7a3c-106">The declaration of a model-declared function contains the following information:</span></span>  
  
- <span data-ttu-id="f7a3c-107">関数の名前。</span><span class="sxs-lookup"><span data-stu-id="f7a3c-107">The name of the function.</span></span> <span data-ttu-id="f7a3c-108">(必須)</span><span class="sxs-lookup"><span data-stu-id="f7a3c-108">(Required)</span></span>  
  
- <span data-ttu-id="f7a3c-109">戻り値の型。</span><span class="sxs-lookup"><span data-stu-id="f7a3c-109">The type of the return value.</span></span> <span data-ttu-id="f7a3c-110">(オプション)</span><span class="sxs-lookup"><span data-stu-id="f7a3c-110">(Optional)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="f7a3c-111">戻り値が指定されていない場合、戻り値の型は void になります。</span><span class="sxs-lookup"><span data-stu-id="f7a3c-111">If no return value is specified, the return type is void.</span></span>  
  
- <span data-ttu-id="f7a3c-112">パラメーター名と型を含むパラメーター情報。</span><span class="sxs-lookup"><span data-stu-id="f7a3c-112">Parameter information, including parameter name and type.</span></span> <span data-ttu-id="f7a3c-113">(オプション)</span><span class="sxs-lookup"><span data-stu-id="f7a3c-113">(Optional)</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7a3c-114">例</span><span class="sxs-lookup"><span data-stu-id="f7a3c-114">Example</span></span>  
 <span data-ttu-id="f7a3c-115">[ADO.NET Entity Framework](./ef/index.md)は、概念スキーマ定義言語 ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) と呼ばれるドメイン固有言語 (DSL) を使用して概念モデルを定義します。</span><span class="sxs-lookup"><span data-stu-id="f7a3c-115">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="f7a3c-116">CSDL では、モデルで宣言された関数の1つの実装は、( [FunctionImport 要素](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#functionimport-element-csdl)を使用した) 関数インポートです。</span><span class="sxs-lookup"><span data-stu-id="f7a3c-116">In CSDL, one implementation of a model-declared function is a function import (using the [FunctionImport element](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#functionimport-element-csdl)).</span></span> <span data-ttu-id="f7a3c-117">次の CSDL は、関数インポート定義を含むエンティティ コンテナーを定義しています。</span><span class="sxs-lookup"><span data-stu-id="f7a3c-117">The following CSDL defines an entity container with a function import definition.</span></span> <span data-ttu-id="f7a3c-118">戻り値の型が指定されていないため、関数の戻り値の型は void になります。</span><span class="sxs-lookup"><span data-stu-id="f7a3c-118">Note that the return type for the function is void since no return type is specified.</span></span>  
  
 [!code-xml[EDM_Example_Model#FunctionImport](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#functionimport)]  
  
## <a name="see-also"></a><span data-ttu-id="f7a3c-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7a3c-119">See also</span></span>

- [<span data-ttu-id="f7a3c-120">Entity Data Model キーの概念</span><span class="sxs-lookup"><span data-stu-id="f7a3c-120">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="f7a3c-121">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="f7a3c-121">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
