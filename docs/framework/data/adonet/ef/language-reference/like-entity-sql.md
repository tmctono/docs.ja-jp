---
title: LIKE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 8300e6d2-875b-481e-9ef4-e1e7c12d46fa
ms.openlocfilehash: f9e33c78235f637e0aa0622d9d8cc30255722beb
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319681"
---
# <a name="like-entity-sql"></a><span data-ttu-id="9c61d-102">LIKE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="9c61d-102">LIKE (Entity SQL)</span></span>
<span data-ttu-id="9c61d-103">指定された文字列 `String` が指定されたパターンと一致するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="9c61d-103">Determines whether a specific character `String` matches a specified pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c61d-104">構文</span><span class="sxs-lookup"><span data-stu-id="9c61d-104">Syntax</span></span>  
  
```sql  
match [NOT] LIKE pattern [ESCAPE escape]  
```  
  
## <a name="arguments"></a><span data-ttu-id="9c61d-105">引数</span><span class="sxs-lookup"><span data-stu-id="9c61d-105">Arguments</span></span>  
 `match`  
 <span data-ttu-id="9c61d-106">`String` として評価される [!INCLUDE[esql](../../../../../../includes/esql-md.md)] の式。</span><span class="sxs-lookup"><span data-stu-id="9c61d-106">An [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expression that evaluates to a `String`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="9c61d-107">指定された `String` に一致するパターン。</span><span class="sxs-lookup"><span data-stu-id="9c61d-107">A pattern to match to the specified `String`.</span></span>  
  
 `escape`  
 <span data-ttu-id="9c61d-108">エスケープ文字。</span><span class="sxs-lookup"><span data-stu-id="9c61d-108">An escape character.</span></span>  
  
 <span data-ttu-id="9c61d-109">NOT</span><span class="sxs-lookup"><span data-stu-id="9c61d-109">NOT</span></span>  
 <span data-ttu-id="9c61d-110">LIKE の結果を否定することを指定します。</span><span class="sxs-lookup"><span data-stu-id="9c61d-110">Specifies that the result of LIKE be negated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9c61d-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="9c61d-111">Return Value</span></span>  
 <span data-ttu-id="9c61d-112">`true` がパターンに一致する場合は `string`、一致しない場合は `false`。</span><span class="sxs-lookup"><span data-stu-id="9c61d-112">`true` if the `string` matches the pattern; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c61d-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="9c61d-113">Remarks</span></span>  
 <span data-ttu-id="9c61d-114">LIKE 演算子を使用する [!INCLUDE[esql](../../../../../../includes/esql-md.md)] の式は、フィルター条件として等価性を使用する式と同様に評価されます。</span><span class="sxs-lookup"><span data-stu-id="9c61d-114">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] expressions that use the LIKE operator are evaluated in much the same way as expressions that use equality as the filter criteria.</span></span> <span data-ttu-id="9c61d-115">ただし、LIKE 演算子を使用する [!INCLUDE[esql](../../../../../../includes/esql-md.md)] の式には、リテラル文字とワイルドカード文字の両方を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9c61d-115">However, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expressions that use the LIKE operator can include both literals and wildcard characters.</span></span>  
  
 <span data-ttu-id="9c61d-116">次の表では、パターン `string` の構文について説明します。</span><span class="sxs-lookup"><span data-stu-id="9c61d-116">The following table describes the syntax of the pattern `string`.</span></span>  
  
|<span data-ttu-id="9c61d-117">ワイルドカード文字</span><span class="sxs-lookup"><span data-stu-id="9c61d-117">Wildcard Character</span></span>|<span data-ttu-id="9c61d-118">説明</span><span class="sxs-lookup"><span data-stu-id="9c61d-118">Description</span></span>|<span data-ttu-id="9c61d-119">例</span><span class="sxs-lookup"><span data-stu-id="9c61d-119">Example</span></span>|  
|------------------------|-----------------|-------------|  
|%|<span data-ttu-id="9c61d-120">0 個またはそれ以上の文字で構成される任意の `string` です。</span><span class="sxs-lookup"><span data-stu-id="9c61d-120">Any `string` of zero or more characters.</span></span>|<span data-ttu-id="9c61d-121">`title like '%computer%'` と指定すると、タイトルに `"computer"` という単語が含まれるすべてのタイトルが検索されます。</span><span class="sxs-lookup"><span data-stu-id="9c61d-121">`title like '%computer%'` finds all titles with the word `"computer"` anywhere in the title.</span></span>|  
|<span data-ttu-id="9c61d-122">_ (アンダースコア)</span><span class="sxs-lookup"><span data-stu-id="9c61d-122">_ (underscore)</span></span>|<span data-ttu-id="9c61d-123">任意の 1 文字です。</span><span class="sxs-lookup"><span data-stu-id="9c61d-123">Any single character.</span></span>|<span data-ttu-id="9c61d-124">`firstname like '_ean'` と指定すると、`"ean`" で終わる 4 文字の名 (Dean や Sean など) がすべて検索されます。</span><span class="sxs-lookup"><span data-stu-id="9c61d-124">`firstname like '_ean'` finds all four-letter first names that end with `"ean`," such as Dean or Sean.</span></span>|  
|<span data-ttu-id="9c61d-125">[ ]</span><span class="sxs-lookup"><span data-stu-id="9c61d-125">[ ]</span></span>|<span data-ttu-id="9c61d-126">指定した範囲 ([a-f]) またはセット ([abcdef]) にある任意の 1 文字です。</span><span class="sxs-lookup"><span data-stu-id="9c61d-126">Any single character in the specified range ([a-f]) or set ([abcdef]).</span></span>|<span data-ttu-id="9c61d-127">`lastname like '[C-P]arsen'` と指定すると、Carsen や Larsen などのように、C から P の任意の 1 文字で始まり、"arsen" で終わる姓が検索されます。</span><span class="sxs-lookup"><span data-stu-id="9c61d-127">`lastname like '[C-P]arsen'` finds last names ending with "arsen" and beginning with any single character between C and P, such as Carsen or Larsen.</span></span>|  
|<span data-ttu-id="9c61d-128">[^]</span><span class="sxs-lookup"><span data-stu-id="9c61d-128">[^]</span></span>|<span data-ttu-id="9c61d-129">指定した範囲 ([^a-f]) またはセット ([^abcdef]) にない任意の 1 文字です。</span><span class="sxs-lookup"><span data-stu-id="9c61d-129">Any single character not in the specified range ([^a-f]) or set ([^abcdef]).</span></span>|<span data-ttu-id="9c61d-130">`lastname like 'de[^l]%'` と指定すると、"de" で始まり、次の文字が "l" でないすべての姓が検索されます。</span><span class="sxs-lookup"><span data-stu-id="9c61d-130">`lastname like 'de[^l]%'` finds all last names that begin with "de" and do not include "l" as the following letter.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="9c61d-131">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] の LIKE 演算子および ESCAPE 句は、`System.DateTime` または `System.Guid` 値には適用できません。</span><span class="sxs-lookup"><span data-stu-id="9c61d-131">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] LIKE operator and ESCAPE clause cannot be applied to `System.DateTime` or `System.Guid` values.</span></span>  
  
 <span data-ttu-id="9c61d-132">LIKE では、ASCII パターン マッチと Unicode パターン マッチがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9c61d-132">LIKE supports ASCII pattern matching and Unicode pattern matching.</span></span> <span data-ttu-id="9c61d-133">すべてのパラメーターが ASCII 文字の場合は、ASCII パターン マッチが行われます。</span><span class="sxs-lookup"><span data-stu-id="9c61d-133">When all parameters are ASCII characters, ASCII pattern matching is performed.</span></span> <span data-ttu-id="9c61d-134">1 つまたは複数の引数が Unicode の場合は、すべての引数が Unicode に変換され、Unicode パターン マッチが行われます。</span><span class="sxs-lookup"><span data-stu-id="9c61d-134">If one or more of the arguments are Unicode, all arguments are converted to Unicode and Unicode pattern matching is performed.</span></span> <span data-ttu-id="9c61d-135">LIKE で Unicode を使用する場合、後続する空白は意味を持ちます。しかし、Unicode 以外のデータの場合、後続する空白は意味を持ちません。</span><span class="sxs-lookup"><span data-stu-id="9c61d-135">When you use Unicode with LIKE, trailing blanks are significant; however, for non-Unicode, trailing blanks are not significant.</span></span> <span data-ttu-id="9c61d-136">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] のパターン文字列構文は、Transact-SQL のパターン文字列構文と同じです。</span><span class="sxs-lookup"><span data-stu-id="9c61d-136">The pattern string syntax of [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is the same as that of Transact-SQL.</span></span>  
  
 <span data-ttu-id="9c61d-137">パターンは、標準の文字とワイルドカード文字を含むことができます。</span><span class="sxs-lookup"><span data-stu-id="9c61d-137">A pattern can include regular characters and wildcard characters.</span></span> <span data-ttu-id="9c61d-138">パターン マッチ時に、標準の文字は `string` に指定された文字と正確に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c61d-138">During pattern matching, regular characters must exactly match the characters specified in the character `string`.</span></span> <span data-ttu-id="9c61d-139">しかし、ワイルドカード文字は文字列の任意の部分と一致することができます。</span><span class="sxs-lookup"><span data-stu-id="9c61d-139">However, wildcard characters can be matched with arbitrary fragments of the character string.</span></span> <span data-ttu-id="9c61d-140">ワイルドカード文字を使用する場合、LIKE 演算子は = や != などの文字列比較演算子よりも柔軟です。</span><span class="sxs-lookup"><span data-stu-id="9c61d-140">When it is used with wildcard characters, the LIKE operator is more flexible than the = and != string comparison operators.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9c61d-141">特定のプロバイダーを対象とする場合は、プロバイダー固有の拡張機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9c61d-141">You may use provider-specific extensions if you target a specific provider.</span></span> <span data-ttu-id="9c61d-142">ただし、たとえばコンストラクターの扱いは、プロバイダーによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9c61d-142">However, such constructs may be treated differently by other providers, for example.</span></span> <span data-ttu-id="9c61d-143">SqlServer では、[first-last] および [^first-last] のパターンがサポートされています。前者は先頭と末尾の間の 1 文字が完全に一致し、後者は先頭と末尾の間以外の 1 文字が完全に一致します。</span><span class="sxs-lookup"><span data-stu-id="9c61d-143">SqlServer supports [first-last] and [^first-last] patterns where the former matches exactly one character between first and last, and the latter matches exactly one character that is not between first and last.</span></span>  
  
### <a name="escape"></a><span data-ttu-id="9c61d-144">エスケープ特殊文字</span><span class="sxs-lookup"><span data-stu-id="9c61d-144">Escape</span></span>  
 <span data-ttu-id="9c61d-145">前のセクションの表で説明しているように、ESCAPE 句を使用することで、1 文字以上の特殊なワイルドカード文字を含む文字列を検索できます。</span><span class="sxs-lookup"><span data-stu-id="9c61d-145">By using the ESCAPE clause, you can search for character strings that include one or more of the special wildcard characters described in the table in the previous section.</span></span> <span data-ttu-id="9c61d-146">たとえば、複数のドキュメントのタイトルにリテラル "100%" が含まれており、そのドキュメントすべてを検索するとします。</span><span class="sxs-lookup"><span data-stu-id="9c61d-146">For example, assume several documents include the literal "100%" in the title and you want to search for all of those documents.</span></span> <span data-ttu-id="9c61d-147">パーセント (%) 文字はワイルドカード文字であるため、検索を正常に実行するには [!INCLUDE[esql](../../../../../../includes/esql-md.md)] の ESCAPE 句を使用してエスケープする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c61d-147">Because the percent (%) character is a wildcard character, you must escape it using the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ESCAPE clause to successfully execute the search.</span></span> <span data-ttu-id="9c61d-148">このフィルターの例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9c61d-148">The following is an example of this filter.</span></span>  
  
```sql  
"title like '%100!%%' escape '!'"  
```  
  
 <span data-ttu-id="9c61d-149">この検索式では、感嘆符文字 (!) の直後のパーセント ワイルドカード文字 (%) は、ワイルドカード文字としてではなく、リテラルとして処理されます。</span><span class="sxs-lookup"><span data-stu-id="9c61d-149">In this search expression, the percent wildcard character (%) immediately following the exclamation point character (!) is treated as a literal, instead of as a wildcard character.</span></span> <span data-ttu-id="9c61d-150">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] のワイルドカード文字および角かっこ (`[ ]`) 文字を除き、任意の文字をエスケープ文字として使用できます。</span><span class="sxs-lookup"><span data-stu-id="9c61d-150">You can use any character as an escape character except for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] wildcard characters and the square bracket (`[ ]`) characters.</span></span> <span data-ttu-id="9c61d-151">前の例では、感嘆符 (!) 文字はエスケープ文字です。</span><span class="sxs-lookup"><span data-stu-id="9c61d-151">In the previous example, the exclamation point (!) character is the escape character.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c61d-152">例</span><span class="sxs-lookup"><span data-stu-id="9c61d-152">Example</span></span>  
 <span data-ttu-id="9c61d-153">次の 2 つの [!INCLUDE[esql](../../../../../../includes/esql-md.md)] クエリでは、LIKE および ESCAPE 演算子を使用して、指定された文字列が指定されたパターンと一致するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="9c61d-153">The following two [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries use the LIKE and ESCAPE operators to determine whether a specific character string matches a specified pattern.</span></span> <span data-ttu-id="9c61d-154">最初のクエリでは、文字列 `Name` で始まる `Down_` が検索されます。</span><span class="sxs-lookup"><span data-stu-id="9c61d-154">The first query searches for the `Name` that starts with the characters `Down_`.</span></span> <span data-ttu-id="9c61d-155">アンダースコア (`_`) はワイルドカード文字であるため、このクエリは ESCAPE オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="9c61d-155">This query uses the ESCAPE option because the underscore (`_`) is a wildcard character.</span></span> <span data-ttu-id="9c61d-156">ESCAPE オプションを指定しないと、単語 `Down` の後にアンダースコア文字以外の 1 文字で始まる `Name` の値もクエリで検索されます。</span><span class="sxs-lookup"><span data-stu-id="9c61d-156">Without specifying the ESCAPE option, the query would search for any `Name` values that start with the word `Down` followed by any single character other than the underscore character.</span></span> <span data-ttu-id="9c61d-157">このクエリは、AdventureWorks Sales Model が基になっています。</span><span class="sxs-lookup"><span data-stu-id="9c61d-157">The queries are based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="9c61d-158">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9c61d-158">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="9c61d-159">「[方法: PrimitiveType 結果を返すクエリを実行する](../how-to-execute-a-query-that-returns-primitivetype-results.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="9c61d-159">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="9c61d-160">次のクエリを引数として `ExecutePrimitiveTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="9c61d-160">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#LIKE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#like)]  
  
## <a name="see-also"></a><span data-ttu-id="9c61d-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c61d-161">See also</span></span>

- [<span data-ttu-id="9c61d-162">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="9c61d-162">Entity SQL Reference</span></span>](entity-sql-reference.md)
