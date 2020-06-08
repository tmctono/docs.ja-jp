---
title: 式は制限がある型 '<typename>' を含んでいるため、'Object' または 'ValueType' から継承されたメンバーにアクセスするのに使用できません。
ms.date: 07/20/2015
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
ms.openlocfilehash: 0eb30488312cc7519f39a6b819aea15489f2f70a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409521"
---
# <a name="expression-has-the-type-typename-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-object-or-valuetype"></a><span data-ttu-id="ed4ae-102">式は制限がある型 '\<typename>' を含んでいるため、'Object' または 'ValueType' から継承されたメンバーにアクセスするのに使用できません。</span><span class="sxs-lookup"><span data-stu-id="ed4ae-102">Expression has the type '\<typename>' which is a restricted type and cannot be used to access members inherited from 'Object' or 'ValueType'</span></span>
<span data-ttu-id="ed4ae-103">式が共通言語ランタイム (CLR) でボックス化できない型に評価されますが、ボックス化が必要なメンバーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ed4ae-103">An expression evaluates to a type that cannot be boxed by the common language runtime (CLR) but accesses a member that requires boxing.</span></span>  
  
 <span data-ttu-id="ed4ae-104">*ボックス化* とは、型を `Object` (場合によっては <xref:System.ValueType>) に変換するために不可欠な処理です。</span><span class="sxs-lookup"><span data-stu-id="ed4ae-104">*Boxing* refers to the processing necessary to convert a type to `Object` or, on occasion, to <xref:System.ValueType>.</span></span> <span data-ttu-id="ed4ae-105">共通言語ランタイムは、<xref:System.ArgIterator>、<xref:System.RuntimeArgumentHandle>、<xref:System.TypedReference> などの特定の構造体型をボックス化できません。</span><span class="sxs-lookup"><span data-stu-id="ed4ae-105">The common language runtime cannot box certain structure types, for example <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, and <xref:System.TypedReference>.</span></span>  
  
 <span data-ttu-id="ed4ae-106">この式は、制限がある型を使用して、<xref:System.Object> または <xref:System.ValueType> から継承されたメソッド (<xref:System.Object.GetHashCode%2A> や <xref:System.Object.ToString%2A> など) の呼び出しを試みます。</span><span class="sxs-lookup"><span data-stu-id="ed4ae-106">This expression attempts to use the restricted type to call a method inherited from <xref:System.Object> or <xref:System.ValueType>, such as <xref:System.Object.GetHashCode%2A> or <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="ed4ae-107">このメソッドにアクセスするために、Visual Basic は、このエラーの原因となる暗黙的なボックス化変換を試行しました。</span><span class="sxs-lookup"><span data-stu-id="ed4ae-107">To access this method, Visual Basic has attempted an implicit boxing conversion that causes this error.</span></span>  
  
 <span data-ttu-id="ed4ae-108">**エラー ID:** BC31393</span><span class="sxs-lookup"><span data-stu-id="ed4ae-108">**Error ID:** BC31393</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ed4ae-109">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="ed4ae-109">To correct this error</span></span>  
  
1. <span data-ttu-id="ed4ae-110">問題の型に評価される式を探します。</span><span class="sxs-lookup"><span data-stu-id="ed4ae-110">Locate the expression that evaluates to the cited type.</span></span>  
  
2. <span data-ttu-id="ed4ae-111"><xref:System.Object> または <xref:System.ValueType> から継承されたメソッドの呼び出しを試みるステートメントの部分を探します。</span><span class="sxs-lookup"><span data-stu-id="ed4ae-111">Locate the part of your statement that attempts to call the method inherited from <xref:System.Object> or <xref:System.ValueType>.</span></span>  
  
3. <span data-ttu-id="ed4ae-112">ステートメントを書き直して、メソッド呼び出しが行われないようにします。</span><span class="sxs-lookup"><span data-stu-id="ed4ae-112">Rewrite the statement to avoid the method call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed4ae-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed4ae-113">See also</span></span>

- [<span data-ttu-id="ed4ae-114">暗黙の型変換と明示的な型変換</span><span class="sxs-lookup"><span data-stu-id="ed4ae-114">Implicit and Explicit Conversions</span></span>](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
