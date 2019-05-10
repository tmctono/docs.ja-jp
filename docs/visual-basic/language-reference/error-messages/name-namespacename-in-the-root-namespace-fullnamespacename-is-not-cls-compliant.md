---
title: ルート名前空間 <namespacename> にある名前 <fullnamespacename> は CLS に準拠していません。
ms.date: 07/20/2015
f1_keywords:
- vbc40039
- bc40039
helpviewer_keywords:
- BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
ms.openlocfilehash: faed46eaf21513945ef4eb0c76d36780e960d380
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592026"
---
# <a name="name-namespacename-in-the-root-namespace-fullnamespacename-is-not-cls-compliant"></a><span data-ttu-id="98ae7-102">名前\<namespacename > ルート名前空間で\<fullnamespacename > CLS 準拠ではありません</span><span class="sxs-lookup"><span data-stu-id="98ae7-102">Name \<namespacename> in the root namespace \<fullnamespacename> is not CLS-compliant</span></span>
<span data-ttu-id="98ae7-103">アセンブリをマーク`<CLSCompliant(True)>`、ルート名前空間の名前の要素は、アンダー スコアで始まるが、(`_`)。</span><span class="sxs-lookup"><span data-stu-id="98ae7-103">An assembly is marked as `<CLSCompliant(True)>`, but an element of the root namespace name begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="98ae7-104">プログラミング要素ですが準拠するため、1 つまたは複数アンダー スコアを含めることができます、 [Language Independence and Language-independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS) にする必要がありますされませんアンダー スコアで始まりです。</span><span class="sxs-lookup"><span data-stu-id="98ae7-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="98ae7-105">「 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98ae7-105">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="98ae7-106">プログラミング要素に <xref:System.CLSCompliantAttribute> を適用する場合は、準拠または非準拠を示すために、属性の `isCompliant` パラメーターを `True` または `False` のどちらかに設定します。</span><span class="sxs-lookup"><span data-stu-id="98ae7-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="98ae7-107">このパラメーターには既定値がありません。値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98ae7-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="98ae7-108">要素に <xref:System.CLSCompliantAttribute> を適用しないと、その要素は非準拠と見なされます。</span><span class="sxs-lookup"><span data-stu-id="98ae7-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="98ae7-109">既定では、このメッセージは警告です。</span><span class="sxs-lookup"><span data-stu-id="98ae7-109">By default, this message is a warning.</span></span> <span data-ttu-id="98ae7-110">警告を非表示にする方法や、警告をエラーとして扱う方法の詳細については、「[Visual Basic での警告の構成](/visualstudio/ide/configuring-warnings-in-visual-basic)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="98ae7-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="98ae7-111">**エラー ID:** BC40039</span><span class="sxs-lookup"><span data-stu-id="98ae7-111">**Error ID:** BC40039</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="98ae7-112">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="98ae7-112">To correct this error</span></span>  
  
- <span data-ttu-id="98ae7-113">CLS 準拠が必要な場合は、ルート名前空間の名前を変更してから、アンダー スコアで始まる要素がないようにします。</span><span class="sxs-lookup"><span data-stu-id="98ae7-113">If you require CLS compliance, change the root namespace name so that none of its elements begins with an underscore.</span></span>  
  
- <span data-ttu-id="98ae7-114">削除し、名前空間の名前を変更できないことが必要な場合、<xref:System.CLSCompliantAttribute>アセンブリからとしてマークまたは`<CLSCompliant(False)>`します。</span><span class="sxs-lookup"><span data-stu-id="98ae7-114">If you require that the namespace name remain unchanged, then remove the <xref:System.CLSCompliantAttribute> from the assembly or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98ae7-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="98ae7-115">See also</span></span>

- [<span data-ttu-id="98ae7-116">Namespace ステートメント</span><span class="sxs-lookup"><span data-stu-id="98ae7-116">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="98ae7-117">Visual Basic における名前空間</span><span class="sxs-lookup"><span data-stu-id="98ae7-117">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="98ae7-118">/rootnamespace</span><span class="sxs-lookup"><span data-stu-id="98ae7-118">/rootnamespace</span></span>](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)
- <span data-ttu-id="98ae7-119">[[アプリケーション] ページ (プロジェクト デザイナー)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="98ae7-119">[Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)</span></span>
- [<span data-ttu-id="98ae7-120">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="98ae7-120">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="98ae7-121">Visual Basic の名前付け規則</span><span class="sxs-lookup"><span data-stu-id="98ae7-121">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
