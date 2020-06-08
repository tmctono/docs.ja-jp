---
title: 範囲変数 <variable> により、それを囲むブロック内の変数、以前に定義された範囲変数、またはクエリ式内で暗黙的に宣言された変数が非表示になります
ms.date: 07/20/2015
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords:
- BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
ms.openlocfilehash: 290ca81dea500558ed73956c91bdf7bfec312014
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400397"
---
# <a name="range-variable-variable-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a><span data-ttu-id="47c21-102">範囲変数 \<variable> により、それを囲むブロック内の変数、以前に定義された範囲変数、またはクエリ式内で暗黙的に宣言された変数が非表示になります</span><span class="sxs-lookup"><span data-stu-id="47c21-102">Range variable \<variable> hides a variable in an enclosing block, a previously defined range variable, or an implicitly declared variable in a query expression</span></span>
<span data-ttu-id="47c21-103">`Select`、`From`、`Aggregate`、または `Let` 句で指定された範囲変数名が、クエリで既に指定されている範囲変数の名前、またはクエリによって暗黙的に宣言された変数の名前 (フィールド名や集計関数の名前など) と重複しています。</span><span class="sxs-lookup"><span data-stu-id="47c21-103">A range variable name specified in a `Select`, `From`, `Aggregate`, or `Let` clause duplicates the name of a range variable already specified previously in the query, or the name of a variable that is implicitly declared by the query, such as a field name or the name of an aggregate function.</span></span>  
  
 <span data-ttu-id="47c21-104">**エラー ID:** BC36633</span><span class="sxs-lookup"><span data-stu-id="47c21-104">**Error ID:** BC36633</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="47c21-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="47c21-105">To correct this error</span></span>  
  
- <span data-ttu-id="47c21-106">特定のクエリ スコープ内のすべての範囲変数の名前が一意であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="47c21-106">Ensure that all range variables in a particular query scope have unique names.</span></span> <span data-ttu-id="47c21-107">入れ子になったクエリのスコープが一意になるように、クエリをかっこで囲むことができます。</span><span class="sxs-lookup"><span data-stu-id="47c21-107">You can enclose a query in parentheses to ensure that nested queries have a unique scope.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47c21-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="47c21-108">See also</span></span>

- [<span data-ttu-id="47c21-109">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="47c21-109">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="47c21-110">From 句</span><span class="sxs-lookup"><span data-stu-id="47c21-110">From Clause</span></span>](../queries/from-clause.md)
- [<span data-ttu-id="47c21-111">Let 句</span><span class="sxs-lookup"><span data-stu-id="47c21-111">Let Clause</span></span>](../queries/let-clause.md)
- [<span data-ttu-id="47c21-112">Aggregate 句</span><span class="sxs-lookup"><span data-stu-id="47c21-112">Aggregate Clause</span></span>](../queries/aggregate-clause.md)
- [<span data-ttu-id="47c21-113">Select 句</span><span class="sxs-lookup"><span data-stu-id="47c21-113">Select Clause</span></span>](../queries/select-clause.md)
