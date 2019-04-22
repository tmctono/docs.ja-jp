---
title: "'ByRef' パラメーター '<typename1>' の値を、一致する引数に戻してコピーする際の、'<typename2>' から '<parametername>' への暗黙的な変換です。"
ms.date: 07/20/2015
f1_keywords:
- vbc41999
- bc41999
helpviewer_keywords:
- BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
ms.openlocfilehash: 7b02659d96b08c592b25ddf3ef1f99114c3ee269
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58831762"
---
# <a name="implicit-conversion-from-typename1-to-typename2-in-copying-the-value-of-byref-parameter-parametername-back-to-the-matching-argument"></a><span data-ttu-id="29afe-102">暗黙的な変換 '\<typename1 >' を'\<typename2 >' の 'ByRef' パラメーターの値をコピー '\<parametername >'、一致する引数に戻してします。</span><span class="sxs-lookup"><span data-stu-id="29afe-102">Implicit conversion from '\<typename1>' to '\<typename2>' in copying the value of 'ByRef' parameter '\<parametername>' back to the matching argument.</span></span>
<span data-ttu-id="29afe-103">プロシージャが呼び出される、 [ByRef](../../../visual-basic/language-reference/modifiers/byref.md)よりも、対応するパラメーターのさまざまな型の引数。</span><span class="sxs-lookup"><span data-stu-id="29afe-103">A procedure is called with a [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) argument of a different type than that of its corresponding parameter.</span></span>  
  
 <span data-ttu-id="29afe-104">引数を渡す場合`ByRef`、Visual Basic は、ローカル変数の参照を渡す代わりにプロシージャに引数の値をコピーすることがあります。</span><span class="sxs-lookup"><span data-stu-id="29afe-104">If you pass an argument `ByRef`, Visual Basic sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="29afe-105">このような場合は、プロシージャが返されるときに Visual Basic する必要がありますにコピーしてローカル変数の値戻す呼び出し元のコードの引数。</span><span class="sxs-lookup"><span data-stu-id="29afe-105">In such a case, when the procedure returns, Visual Basic must then copy the local variable value back into the argument in the calling code.</span></span>  
  
 <span data-ttu-id="29afe-106">`ByRef` 引数の値がプロシージャにコピーされ、引数とパラメーターが同じ型である場合、変換は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29afe-106">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="29afe-107">種類が異なる場合は、Visual Basic が双方向で変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29afe-107">But if the types are different, Visual Basic must convert in both directions.</span></span> <span data-ttu-id="29afe-108">使用できないため`CType`または暗黙的なプロシージャの引数またはパラメーター、このような変換での他の変換キーワードのいずれかが常にします。</span><span class="sxs-lookup"><span data-stu-id="29afe-108">Because you cannot use `CType` or any of the other conversion keywords on a procedure argument or parameter, such a conversion is always implicit.</span></span>  
  
 <span data-ttu-id="29afe-109">既定では、このメッセージは警告です。</span><span class="sxs-lookup"><span data-stu-id="29afe-109">By default, this message is a warning.</span></span> <span data-ttu-id="29afe-110">警告を非表示にする方法や、警告をエラーとして扱う方法の詳細については、「[Visual Basic での警告の構成](/visualstudio/ide/configuring-warnings-in-visual-basic)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="29afe-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="29afe-111">**エラー ID:** BC41999</span><span class="sxs-lookup"><span data-stu-id="29afe-111">**Error ID:** BC41999</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="29afe-112">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="29afe-112">To correct this error</span></span>  
  
-   <span data-ttu-id="29afe-113">可能であれば、Visual Basic は、変換を行う必要はありませんので、プロシージャのパラメーターとして、同じ種類の呼び出し元の引数を使用します。</span><span class="sxs-lookup"><span data-stu-id="29afe-113">If possible, use a calling argument of the same type as the procedure parameter, so Visual Basic does not need to do any conversion.</span></span>  
  
-   <span data-ttu-id="29afe-114">パラメーター型とは異なる引数型を使用してプロシージャを呼び出す必要があり、呼び出し元の引数に値を返す必要がない場合は、 [ByRef](../../../visual-basic/language-reference/modifiers/byval.md) ではなく `ByRef`になるようにパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="29afe-114">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) instead of `ByRef`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29afe-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="29afe-115">See also</span></span>

- [<span data-ttu-id="29afe-116">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="29afe-116">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="29afe-117">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="29afe-117">Procedure Parameters and Arguments</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [<span data-ttu-id="29afe-118">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="29afe-118">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="29afe-119">暗黙の型変換と明示的な型変換</span><span class="sxs-lookup"><span data-stu-id="29afe-119">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
