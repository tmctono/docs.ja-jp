---
title: 範囲変数 <variable> により、それを囲むブロック内の変数、以前に定義された範囲変数、またはクエリ式内で暗黙的に宣言された変数が非表示になります
ms.date: 07/20/2015
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords:
- BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
ms.openlocfilehash: e31f728de228bea743f6c7b5cbfef3cd73367262
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971629"
---
# <a name="range-variable-variable-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a><span data-ttu-id="781f5-102">範囲変数\<変数 >、それを囲むブロック、以前に定義された範囲変数、またはクエリ式で、暗黙的に宣言された変数内の変数を非表示になります</span><span class="sxs-lookup"><span data-stu-id="781f5-102">Range variable \<variable> hides a variable in an enclosing block, a previously defined range variable, or an implicitly declared variable in a query expression</span></span>
<span data-ttu-id="781f5-103">指定された範囲変数の名前、 `Select`、 `From`、 `Aggregate`、または`Let`句、クエリまたはクエリで暗黙的に宣言されている変数の名前で既に指定されて範囲変数の名前に重複など、フィールド名または集計関数の名前。</span><span class="sxs-lookup"><span data-stu-id="781f5-103">A range variable name specified in a `Select`, `From`, `Aggregate`, or `Let` clause duplicates the name of a range variable already specified previously in the query, or the name of a variable that is implicitly declared by the query, such as a field name or the name of an aggregate function.</span></span>  
  
 <span data-ttu-id="781f5-104">**エラー ID:** BC36633</span><span class="sxs-lookup"><span data-stu-id="781f5-104">**Error ID:** BC36633</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="781f5-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="781f5-105">To correct this error</span></span>  
  
- <span data-ttu-id="781f5-106">特定のクエリ スコープ内のすべての範囲変数に一意の名前があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="781f5-106">Ensure that all range variables in a particular query scope have unique names.</span></span> <span data-ttu-id="781f5-107">クエリは、入れ子になったクエリは、一意のスコープでいることを確認するためにかっこで囲むことができます。</span><span class="sxs-lookup"><span data-stu-id="781f5-107">You can enclose a query in parentheses to ensure that nested queries have a unique scope.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="781f5-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="781f5-108">See also</span></span>

- [<span data-ttu-id="781f5-109">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="781f5-109">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="781f5-110">From 句</span><span class="sxs-lookup"><span data-stu-id="781f5-110">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="781f5-111">Let 句</span><span class="sxs-lookup"><span data-stu-id="781f5-111">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)
- [<span data-ttu-id="781f5-112">Aggregate 句</span><span class="sxs-lookup"><span data-stu-id="781f5-112">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="781f5-113">Select 句</span><span class="sxs-lookup"><span data-stu-id="781f5-113">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
