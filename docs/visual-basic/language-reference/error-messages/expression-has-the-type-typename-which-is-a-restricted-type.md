---
title: 式は制限がある型 '<typename>' を含んでいるため、'Object' または 'ValueType' から継承されたメンバーにアクセスするのに使用できません。
ms.date: 07/20/2015
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
ms.openlocfilehash: 017a2458562068727674bd3fd9cda8c33d989e8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803169"
---
# <a name="expression-has-the-type-typename-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-object-or-valuetype"></a><span data-ttu-id="a0ba7-102">式の型 '\<typename >' は制限付きの型と 'Object' または 'ValueType' から継承されたメンバーのアクセスに使用することはできません</span><span class="sxs-lookup"><span data-stu-id="a0ba7-102">Expression has the type '\<typename>' which is a restricted type and cannot be used to access members inherited from 'Object' or 'ValueType'</span></span>
<span data-ttu-id="a0ba7-103">式では、共通言語ランタイム (CLR) でボックス化できない型に評価が、ボックス化を必要とするメンバーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="a0ba7-103">An expression evaluates to a type that cannot be boxed by the common language runtime (CLR) but accesses a member that requires boxing.</span></span>  
  
 <span data-ttu-id="a0ba7-104">*ボックス化* とは、型を `Object` (場合によっては <xref:System.ValueType>) に変換するために不可欠な処理です。</span><span class="sxs-lookup"><span data-stu-id="a0ba7-104">*Boxing* refers to the processing necessary to convert a type to `Object` or, on occasion, to <xref:System.ValueType>.</span></span> <span data-ttu-id="a0ba7-105">共通言語ランタイムでは、特定の構造体の型をたとえばボックスことはできません<xref:System.ArgIterator>、 <xref:System.RuntimeArgumentHandle>、および<xref:System.TypedReference>します。</span><span class="sxs-lookup"><span data-stu-id="a0ba7-105">The common language runtime cannot box certain structure types, for example <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, and <xref:System.TypedReference>.</span></span>  
  
 <span data-ttu-id="a0ba7-106">この式から継承されたメソッドの呼び出しに制限付きの型を使用しようとしました。<xref:System.Object>または<xref:System.ValueType>、など<xref:System.Object.GetHashCode%2A>または<xref:System.Object.ToString%2A>します。</span><span class="sxs-lookup"><span data-stu-id="a0ba7-106">This expression attempts to use the restricted type to call a method inherited from <xref:System.Object> or <xref:System.ValueType>, such as <xref:System.Object.GetHashCode%2A> or <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="a0ba7-107">このメソッドにアクセスするには、Visual Basic はこのエラーが発生する暗黙的なボックス化変換をしようとしました。</span><span class="sxs-lookup"><span data-stu-id="a0ba7-107">To access this method, Visual Basic has attempted an implicit boxing conversion that causes this error.</span></span>  
  
 <span data-ttu-id="a0ba7-108">**エラー ID:** BC31393</span><span class="sxs-lookup"><span data-stu-id="a0ba7-108">**Error ID:** BC31393</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a0ba7-109">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="a0ba7-109">To correct this error</span></span>  
  
1. <span data-ttu-id="a0ba7-110">問題の型に評価される式を探します。</span><span class="sxs-lookup"><span data-stu-id="a0ba7-110">Locate the expression that evaluates to the cited type.</span></span>  
  
2. <span data-ttu-id="a0ba7-111">継承されたメソッドを呼び出そうとすると、ステートメントの部分を探します<xref:System.Object>または<xref:System.ValueType>します。</span><span class="sxs-lookup"><span data-stu-id="a0ba7-111">Locate the part of your statement that attempts to call the method inherited from <xref:System.Object> or <xref:System.ValueType>.</span></span>  
  
3. <span data-ttu-id="a0ba7-112">メソッドの呼び出しを回避するために、ステートメントを書き直してください。</span><span class="sxs-lookup"><span data-stu-id="a0ba7-112">Rewrite the statement to avoid the method call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0ba7-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0ba7-113">See also</span></span>

- [<span data-ttu-id="a0ba7-114">暗黙の型変換と明示的な型変換</span><span class="sxs-lookup"><span data-stu-id="a0ba7-114">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
