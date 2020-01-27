---
title: <proceduresignature1> は、配列パラメーター型の配列または配列パラメーター型のランクのみが異なる <proceduresignature2> をオーバーロードするため、CLS に準拠していません。
ms.date: 07/20/2015
f1_keywords:
- vbc40035
- bc40035
helpviewer_keywords:
- BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
ms.openlocfilehash: 6143ebfbe7f131b0e196e531ed4282c8333be4ea
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250180"
---
# <a name="proceduresignature1-is-not-cls-compliant-because-it-overloads-proceduresignature2-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a><span data-ttu-id="2fb33-102">\<proceduresignature1> は、配列パラメーター型の配列または配列パラメーター型のランクのみが異なる \<proceduresignature2> をオーバーロードするため、CLS に準拠していません</span><span class="sxs-lookup"><span data-stu-id="2fb33-102">\<proceduresignature1> is not CLS-compliant because it overloads \<proceduresignature2> which differs from it only by array of array parameter types or by the rank of the array parameter types</span></span>

<span data-ttu-id="2fb33-103">プロシージャまたはプロパティが別のプロシージャまたはプロパティをオーバーライドするときに `<CLSCompliant(True)>` としてマークされます。パラメーターリスト間の唯一の違いは、ジャグ配列または配列のランクの入れ子レベルです。</span><span class="sxs-lookup"><span data-stu-id="2fb33-103">A procedure or property is marked as `<CLSCompliant(True)>` when it overrides another procedure or property and the only difference between their parameter lists is the nesting level of a jagged array or the rank of an array.</span></span>
  
 <span data-ttu-id="2fb33-104">次の宣言では、2番目と3番目の宣言によってこのエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="2fb33-104">In the following declarations, the second and third declarations generate this error:</span></span>
  
 `Overloads Sub ProcessArray(arrayParam() As Integer)`  
  
 `Overloads Sub ProcessArray(arrayParam()() As Integer)`  
  
 `Overloads Sub ProcessArray(arrayParam(,) As Integer)`  
  
 <span data-ttu-id="2fb33-105">2 番目の宣言では、元の1次元パラメーター `arrayParam` を配列の配列に変更します。</span><span class="sxs-lookup"><span data-stu-id="2fb33-105">The second declaration changes the original one-dimensional parameter `arrayParam` to an array of arrays.</span></span> <span data-ttu-id="2fb33-106">3番目の宣言は、`arrayParam` を2次元配列(ランク 2)に変更します。</span><span class="sxs-lookup"><span data-stu-id="2fb33-106">The third declaration changes `arrayParam` to a two-dimensional array (rank 2).</span></span> <span data-ttu-id="2fb33-107">Visual Basic では、これらの変更のいずれかによってのみオーバーロードが異なることが許可されますが、このようなオーバーロードは、[言語への非依存性、および言語非依存コンポーネント](../../../standard/language-independence-and-language-independent-components.md)(CLS)に準拠していません。</span><span class="sxs-lookup"><span data-stu-id="2fb33-107">While Visual Basic allows overloads to differ only by one of these changes, such overloading is not compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span>  
  
 <span data-ttu-id="2fb33-108">プログラミング要素に <xref:System.CLSCompliantAttribute> を適用する場合は、属性の `isCompliant` パラメーターを `True` または `False` のどちらかに設定して、準拠または非準拠を示します。</span><span class="sxs-lookup"><span data-stu-id="2fb33-108">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="2fb33-109">このパラメーターには既定値がありません。値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fb33-109">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="2fb33-110">要素に <xref:System.CLSCompliantAttribute> を適用しないと、その要素は非準拠と見なされます。</span><span class="sxs-lookup"><span data-stu-id="2fb33-110">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="2fb33-111">既定では、このメッセージは警告です。</span><span class="sxs-lookup"><span data-stu-id="2fb33-111">By default, this message is a warning.</span></span> <span data-ttu-id="2fb33-112">警告を非表示にする方法や、警告をエラーとして扱う方法の詳細については、「[Visual Basic での警告の構成](/visualstudio/ide/configuring-warnings-in-visual-basic)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2fb33-112">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="2fb33-113">**エラー ID:** BC40035</span><span class="sxs-lookup"><span data-stu-id="2fb33-113">**Error ID:** BC40035</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2fb33-114">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="2fb33-114">To correct this error</span></span>  
  
- <span data-ttu-id="2fb33-115">CLS 準拠が必要な場合は、このヘルプページで言及されている変更のみよりも多くの方法でオーバーロードを定義します。</span><span class="sxs-lookup"><span data-stu-id="2fb33-115">If you require CLS compliance, define your overloads to differ from each other in more ways than only the changes cited on this Help page.</span></span>
- <span data-ttu-id="2fb33-116">このヘルプページで説明されている変更によってのみオーバーロードが異なる必要がある場合は、定義から <xref:System.CLSCompliantAttribute> を削除するか `<CLSCompliant(False)>` としてマークします。</span><span class="sxs-lookup"><span data-stu-id="2fb33-116">If you require that the overloads differ only by the changes cited on this Help page, remove the <xref:System.CLSCompliantAttribute> from their definitions or mark them as `<CLSCompliant(False)>`.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2fb33-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="2fb33-117">See also</span></span>

- [<span data-ttu-id="2fb33-118">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="2fb33-118">Procedure Overloading</span></span>](../../programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="2fb33-119">Overloads</span><span class="sxs-lookup"><span data-stu-id="2fb33-119">Overloads</span></span>](../modifiers/overloads.md)
