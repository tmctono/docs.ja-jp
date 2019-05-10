---
title: <proceduresignature1> オーバー ロードするため、CLS 準拠<proceduresignature2>これが異なる配列パラメーター型の配列または配列パラメーター型のランクのみ
ms.date: 07/20/2015
f1_keywords:
- vbc40035
- bc40035
helpviewer_keywords:
- BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
ms.openlocfilehash: 9006e12838581a98c7e7945278c7d767a3074259
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64661797"
---
# <a name="proceduresignature1-is-not-cls-compliant-because-it-overloads-proceduresignature2-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a><span data-ttu-id="c04a9-102">\<proceduresignature1 > は、オーバー ロードするため、CLS 準拠\<proceduresignature2 > これが異なる配列パラメーター型の配列または配列パラメーター型のランクのみ</span><span class="sxs-lookup"><span data-stu-id="c04a9-102">\<proceduresignature1> is not CLS-compliant because it overloads \<proceduresignature2> which differs from it only by array of array parameter types or by the rank of the array parameter types</span></span>
<span data-ttu-id="c04a9-103">プロシージャまたはプロパティがマーク`<CLSCompliant(True)>`と別のプロシージャまたはプロパティのオーバーライド、パラメーター リストの唯一の違いは、ジャグ配列の入れ子レベルまたは配列のランク。</span><span class="sxs-lookup"><span data-stu-id="c04a9-103">A procedure or property is marked as `<CLSCompliant(True)>` when it overrides another procedure or property and the only difference between their parameter lists is the nesting level of a jagged array or the rank of an array.</span></span>  
  
 <span data-ttu-id="c04a9-104">次の宣言では、2 番目と 3 番目の宣言は、このエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="c04a9-104">In the following declarations, the second and third declarations generate this error.</span></span>  
  
 `Overloads Sub processArray(ByVal arrayParam() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam()() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam(,) As Integer)`  
  
 <span data-ttu-id="c04a9-105">2 番目の宣言元の 1 次元のパラメーターを変更する`arrayParam`配列の配列にします。</span><span class="sxs-lookup"><span data-stu-id="c04a9-105">The second declaration changes the original one-dimensional parameter `arrayParam` to an array of arrays.</span></span> <span data-ttu-id="c04a9-106">3 番目の宣言の変更`arrayParam`2 次元配列 (ランク 2) にします。</span><span class="sxs-lookup"><span data-stu-id="c04a9-106">The third declaration changes `arrayParam` to a two-dimensional array (rank 2).</span></span> <span data-ttu-id="c04a9-107">Visual Basic でこれらの変更のいずれかによってのみ異なるオーバー ロードは、中にこのようなオーバー ロードが準拠していない、 [Language Independence and Language-independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS)。</span><span class="sxs-lookup"><span data-stu-id="c04a9-107">While Visual Basic allows overloads to differ only by one of these changes, such overloading is not compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span>  
  
 <span data-ttu-id="c04a9-108">プログラミング要素に <xref:System.CLSCompliantAttribute> を適用する場合は、準拠または非準拠を示すために、属性の `isCompliant` パラメーターを `True` または `False` のどちらかに設定します。</span><span class="sxs-lookup"><span data-stu-id="c04a9-108">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="c04a9-109">このパラメーターには既定値がありません。値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c04a9-109">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="c04a9-110">要素に <xref:System.CLSCompliantAttribute> を適用しないと、その要素は非準拠と見なされます。</span><span class="sxs-lookup"><span data-stu-id="c04a9-110">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="c04a9-111">既定では、このメッセージは警告です。</span><span class="sxs-lookup"><span data-stu-id="c04a9-111">By default, this message is a warning.</span></span> <span data-ttu-id="c04a9-112">警告を非表示にする方法や、警告をエラーとして扱う方法の詳細については、「[Visual Basic での警告の構成](/visualstudio/ide/configuring-warnings-in-visual-basic)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c04a9-112">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="c04a9-113">**エラー ID:** BC40035</span><span class="sxs-lookup"><span data-stu-id="c04a9-113">**Error ID:** BC40035</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c04a9-114">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="c04a9-114">To correct this error</span></span>  
  
- <span data-ttu-id="c04a9-115">CLS 準拠が必要な場合は、このヘルプ ページに示された変更のみよりも多くの方法で互いに異なる、オーバー ロードを定義します。</span><span class="sxs-lookup"><span data-stu-id="c04a9-115">If you require CLS compliance, define your overloads to differ from each other in more ways than only the changes cited on this Help page.</span></span>  
  
- <span data-ttu-id="c04a9-116">このヘルプで示された変更によってのみページ オーバー ロードとは異なることが必要な場合は、削除、<xref:System.CLSCompliantAttribute>その定義からとしてマークまたは`<CLSCompliant(False)>`します。</span><span class="sxs-lookup"><span data-stu-id="c04a9-116">If you require that the overloads differ only by the changes cited on this Help page, remove the <xref:System.CLSCompliantAttribute> from their definitions or mark them as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c04a9-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="c04a9-117">See also</span></span>

- [<span data-ttu-id="c04a9-118">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="c04a9-118">Procedure Overloading</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="c04a9-119">Overloads</span><span class="sxs-lookup"><span data-stu-id="c04a9-119">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)
