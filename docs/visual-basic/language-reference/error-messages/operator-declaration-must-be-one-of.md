---
title: '演算子宣言は次のいずれかでなければなりません: +、-、*、\、/、^、&amp;、Like、Mod、And、Or、Xor、Not、<<、>>、=、<>、<、<=、>、>=、CType、IsTrue、または IsFalse'
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: c388b1b0762dd7475ca365a8a62228d0b5d59414
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873610"
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not--"></a><span data-ttu-id="be0e8-102">演算子宣言は次のいずれかでなければなりません: +、-、\*、\,/、^、&amp;、Like、Mod、And、Or、Xor、Not、\<\<, >>...</span><span class="sxs-lookup"><span data-stu-id="be0e8-102">Operator declaration must be one of:  +,-,\*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, \<\<, >>...</span></span>

<span data-ttu-id="be0e8-103">オーバーロードの対象となる演算子のみ宣言できます。</span><span class="sxs-lookup"><span data-stu-id="be0e8-103">You can declare only an operator that is eligible for overloading.</span></span> <span data-ttu-id="be0e8-104">次の表に宣言可能な演算子を示します。</span><span class="sxs-lookup"><span data-stu-id="be0e8-104">The following table lists the operators you can declare.</span></span>  
  
|<span data-ttu-id="be0e8-105">種類</span><span class="sxs-lookup"><span data-stu-id="be0e8-105">Type</span></span>|<span data-ttu-id="be0e8-106">演算子</span><span class="sxs-lookup"><span data-stu-id="be0e8-106">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="be0e8-107">単項</span><span class="sxs-lookup"><span data-stu-id="be0e8-107">Unary</span></span>|<span data-ttu-id="be0e8-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="be0e8-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="be0e8-109">2 項</span><span class="sxs-lookup"><span data-stu-id="be0e8-109">Binary</span></span>|<span data-ttu-id="be0e8-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="be0e8-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="be0e8-111">変換 (単項)</span><span class="sxs-lookup"><span data-stu-id="be0e8-111">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="be0e8-112">2 項の一覧に示した `=` 演算子は比較演算子であり、代入演算子ではありません。</span><span class="sxs-lookup"><span data-stu-id="be0e8-112">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="be0e8-113">**エラー ID:** BC33000</span><span class="sxs-lookup"><span data-stu-id="be0e8-113">**Error ID:** BC33000</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="be0e8-114">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="be0e8-114">To correct this error</span></span>  
  
1. <span data-ttu-id="be0e8-115">演算子をオーバーロード可能な演算子の中から選択します。</span><span class="sxs-lookup"><span data-stu-id="be0e8-115">Select an operator from the set of overloadable operators.</span></span>  
  
2. <span data-ttu-id="be0e8-116">直接オーバーロードできない演算子をオーバーロードする機能が必要な場合は、適切なパラメーターを受け取り適切な値を返す `Function` プロシージャを作成します。</span><span class="sxs-lookup"><span data-stu-id="be0e8-116">If you need the functionality of overloading an operator that you cannot overload directly, create a `Function` procedure that takes the appropriate parameters and returns the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be0e8-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="be0e8-117">See also</span></span>

- [<span data-ttu-id="be0e8-118">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="be0e8-118">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="be0e8-119">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="be0e8-119">Operator Procedures</span></span>](../../programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="be0e8-120">方法: 演算子を定義する</span><span class="sxs-lookup"><span data-stu-id="be0e8-120">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="be0e8-121">方法: 変換演算子を定義する</span><span class="sxs-lookup"><span data-stu-id="be0e8-121">How to: Define a Conversion Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="be0e8-122">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="be0e8-122">Function Statement</span></span>](../statements/function-statement.md)
