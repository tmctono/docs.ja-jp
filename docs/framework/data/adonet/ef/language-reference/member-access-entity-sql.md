---
title: . (メンバー アクセス) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4733e3b2-3efa-4b96-b591-ac31350e96ad
ms.openlocfilehash: 6ebedd2b381d035d199e151f64632acf7d502ff5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760624"
---
# <a name="-member-access-entity-sql"></a><span data-ttu-id="78c70-103">.</span><span class="sxs-lookup"><span data-stu-id="78c70-103">.</span></span> <span data-ttu-id="78c70-104">(メンバー アクセス) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="78c70-104">(Member Access) (Entity SQL)</span></span>
<span data-ttu-id="78c70-105">ドット演算子 (.) は、[!INCLUDE[esql](../../../../../../includes/esql-md.md)]メンバー アクセス演算子。</span><span class="sxs-lookup"><span data-stu-id="78c70-105">The dot operator (.) is the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] member access operator.</span></span> <span data-ttu-id="78c70-106">メンバー アクセス演算子を使用すると、構造型概念モデル型のインスタンスのプロパティ値またはフィールド値を生成できます。</span><span class="sxs-lookup"><span data-stu-id="78c70-106">You use the member access operator to yield the value of a property or field of an instance of structural conceptual model type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78c70-107">構文</span><span class="sxs-lookup"><span data-stu-id="78c70-107">Syntax</span></span>  
  
```  
expression.identifier  
```  
  
## <a name="arguments"></a><span data-ttu-id="78c70-108">引数</span><span class="sxs-lookup"><span data-stu-id="78c70-108">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="78c70-109">構造型概念モデル型のインスタンス。</span><span class="sxs-lookup"><span data-stu-id="78c70-109">An instance of a structural conceptual model type.</span></span>  
  
 `identifier`  
 <span data-ttu-id="78c70-110">オブジェクト インスタンスに属するプロパティまたはフィールド。</span><span class="sxs-lookup"><span data-stu-id="78c70-110">A property or field that belongs to an object instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78c70-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="78c70-111">Remarks</span></span>  
 <span data-ttu-id="78c70-112">ドット (.) 演算子は、複合型またはエンティティ型のプロパティの抽出と同様に、レコードからフィールドを抽出するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="78c70-112">The dot (.) operator may be used to extract fields from a record, similar to extracting properties of a complex or entity type.</span></span> <span data-ttu-id="78c70-113">たとえば、Name 型の n が Person 型のメンバーであり、p が Person 型のインスタンスである場合、p.n は有効なメンバー アクセス式として Name 型の値を生成します。</span><span class="sxs-lookup"><span data-stu-id="78c70-113">For example, if n of type Name is a member of type Person, and p is an instance of type Person, then p.n is a legal member access expression that yields a value of type Name.</span></span>  
  
 `select p.Name.FirstName from LOB.Person as p`  
  
## <a name="see-also"></a><span data-ttu-id="78c70-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="78c70-114">See also</span></span>

- [<span data-ttu-id="78c70-115">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="78c70-115">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
