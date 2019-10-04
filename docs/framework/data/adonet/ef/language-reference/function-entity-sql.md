---
title: FUNCTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 0bb88992-37ed-4991-ace5-55be612a2c4d
ms.openlocfilehash: bacc773351812a5db60f493f3025c8e4b07dbaa2
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833798"
---
# <a name="function-entity-sql"></a><span data-ttu-id="9bdb1-102">FUNCTION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="9bdb1-102">FUNCTION (Entity SQL)</span></span>
<span data-ttu-id="9bdb1-103">Entity SQL クエリ コマンドのスコープに関数を定義します。</span><span class="sxs-lookup"><span data-stu-id="9bdb1-103">Defines a function in the scope of an Entity SQL query command.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bdb1-104">構文</span><span class="sxs-lookup"><span data-stu-id="9bdb1-104">Syntax</span></span>  
  
```sql  
FUNCTION function-name  
( [ { parameter_name <type_definition>   
        [ ,...n ]  
  ]  
) AS ( function_expression )   
  
<type_definition>::=  
    { data_type | COLLECTION ( <type_definition> )   
                | REF ( data_type )   
                | ROW ( row_expression )   
        }   
```  
  
## <a name="arguments"></a><span data-ttu-id="9bdb1-105">引数</span><span class="sxs-lookup"><span data-stu-id="9bdb1-105">Arguments</span></span>  
 `function-name`  
 <span data-ttu-id="9bdb1-106">関数名。</span><span class="sxs-lookup"><span data-stu-id="9bdb1-106">Name of the function.</span></span>  
  
 `parameter-name`  
 <span data-ttu-id="9bdb1-107">関数のパラメーター名。</span><span class="sxs-lookup"><span data-stu-id="9bdb1-107">Name of a parameter in the function.</span></span>  
  
 `function_expression`  
 <span data-ttu-id="9bdb1-108">関数である有効な Entity SQL 式。</span><span class="sxs-lookup"><span data-stu-id="9bdb1-108">A valid Entity SQL expression that is the function.</span></span> <span data-ttu-id="9bdb1-109">関数内のコマンドは、関数に渡される `parameter_name` パラメーターに基づいて実行されます。</span><span class="sxs-lookup"><span data-stu-id="9bdb1-109">The command in the function can act on `parameter_name` parameters passed to the function.</span></span>  
  
 `data_type`  
 <span data-ttu-id="9bdb1-110">サポートされる型の名前。</span><span class="sxs-lookup"><span data-stu-id="9bdb1-110">Name of a supported type.</span></span>  
  
 <span data-ttu-id="9bdb1-111">COLLECTION (< type_definition @ no__t-0)</span><span class="sxs-lookup"><span data-stu-id="9bdb1-111">COLLECTION ( <type_definition`>` )</span></span>  
 <span data-ttu-id="9bdb1-112">サポートされる型、行、または参照のコレクションを返す式。</span><span class="sxs-lookup"><span data-stu-id="9bdb1-112">An expression that returns a collection of supported types, rows, or references.</span></span>  
  
 <span data-ttu-id="9bdb1-113">REF **(** `data_type` **)**</span><span class="sxs-lookup"><span data-stu-id="9bdb1-113">REF **(**`data_type`**)**</span></span>  
 <span data-ttu-id="9bdb1-114">エンティティ型への参照を返す式。</span><span class="sxs-lookup"><span data-stu-id="9bdb1-114">An expression that returns a reference to an entity type.</span></span>  
  
 <span data-ttu-id="9bdb1-115">ROW **(** `row_expression` **)**</span><span class="sxs-lookup"><span data-stu-id="9bdb1-115">ROW **(**`row_expression`**)**</span></span>  
 <span data-ttu-id="9bdb1-116">1 つまたは複数の値から構造的に型指定された匿名レコードを返す式。</span><span class="sxs-lookup"><span data-stu-id="9bdb1-116">An expression that returns anonymous, structurally typed records from one or more values.</span></span> <span data-ttu-id="9bdb1-117">詳細については、「 [ROW](row-entity-sql.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9bdb1-117">For more information, see [ROW](row-entity-sql.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9bdb1-118">コメント</span><span class="sxs-lookup"><span data-stu-id="9bdb1-118">Remarks</span></span>  
 <span data-ttu-id="9bdb1-119">関数のシグネチャが異なっていれば、名前が同じ複数の関数をインラインで宣言することは可能です。</span><span class="sxs-lookup"><span data-stu-id="9bdb1-119">Multiple functions with the same name can be declared inline, as long as the function signatures are different.</span></span> <span data-ttu-id="9bdb1-120">詳細については、「 [Function Overload Resolution](function-overload-resolution-entity-sql.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9bdb1-120">For more information, see [Function Overload Resolution](function-overload-resolution-entity-sql.md).</span></span>  
  
 <span data-ttu-id="9bdb1-121">関数がインラインである場合、Entity SQL コマンドに呼び出せるのは、そのコマンド内で定義された後のみです。</span><span class="sxs-lookup"><span data-stu-id="9bdb1-121">An inline function can be called in an Entity SQL command only after it has been defined in that command.</span></span> <span data-ttu-id="9bdb1-122">ただし、インライン関数を別のインライン関数内で呼び出す場合には、呼び出される関数が定義される前でも後でもかまいません。</span><span class="sxs-lookup"><span data-stu-id="9bdb1-122">However, an inline function can be called inside another inline function either before or after the called function has been defined.</span></span> <span data-ttu-id="9bdb1-123">次の例では、関数 B が定義される前に、関数 A が関数 B を呼び出しています。</span><span class="sxs-lookup"><span data-stu-id="9bdb1-123">In the following example, function A calls function B before function B is defined:</span></span>  
  
 `Function A() as ('A calls B. ' + B())`  
  
 `Function B() as ('B was called.')`  
  
 `A()`  
  
 <span data-ttu-id="9bdb1-124">詳細については、「[方法 :ユーザー定義関数 @ no__t を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9bdb1-124">For more information, see [How to: Call a User-Defined Function](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100)).</span></span>  
  
 <span data-ttu-id="9bdb1-125">関数をモデル自体で宣言することもできます。</span><span class="sxs-lookup"><span data-stu-id="9bdb1-125">Functions can also be declared in the model itself.</span></span> <span data-ttu-id="9bdb1-126">モデルで宣言された関数は、コマンドでインラインで宣言された関数と同じように実行されます。</span><span class="sxs-lookup"><span data-stu-id="9bdb1-126">Functions declared in the model are executed in the same way as functions declared inline in the command.</span></span> <span data-ttu-id="9bdb1-127">詳細については、「[ユーザー定義関数](user-defined-functions-entity-sql.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9bdb1-127">For more information, see [User-Defined Functions](user-defined-functions-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9bdb1-128">例</span><span class="sxs-lookup"><span data-stu-id="9bdb1-128">Example</span></span>  
 <span data-ttu-id="9bdb1-129">次の Entity SQL コマンドは、関数 `Products` を定義します。この関数は、整数値を受け取って、返された製品をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="9bdb1-129">The following Entity SQL command defines a function `Products` that takes an integer value to filter the returned products.</span></span>  
  
 [!code-sql[DP EntityServices Concepts#FUNCTION1](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#function1)]  
  
## <a name="example"></a><span data-ttu-id="9bdb1-130">例</span><span class="sxs-lookup"><span data-stu-id="9bdb1-130">Example</span></span>  
 <span data-ttu-id="9bdb1-131">次の Entity SQL コマンドは、関数 `StringReturnsCollection` を定義します。この関数は、文字列のコレクションを受け取って、返された連絡先をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="9bdb1-131">The following Entity SQL command defines a function `StringReturnsCollection` that takes a collection of strings to filter the returned contacts.</span></span>  
  
 [!code-sql[DP EntityServices Concepts#FUNCTION2](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#function2)]  
  
## <a name="see-also"></a><span data-ttu-id="9bdb1-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="9bdb1-132">See also</span></span>

- [<span data-ttu-id="9bdb1-133">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="9bdb1-133">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="9bdb1-134">Entity SQL 言語</span><span class="sxs-lookup"><span data-stu-id="9bdb1-134">Entity SQL Language</span></span>](entity-sql-language.md)
