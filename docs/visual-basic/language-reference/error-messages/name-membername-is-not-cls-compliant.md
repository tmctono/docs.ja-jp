---
title: 名前 <membername> は CLS に準拠していません。
ms.date: 07/20/2015
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
ms.openlocfilehash: 2d89d3588b854c9e77445a9980530d8dd53c33c3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592018"
---
# <a name="name-membername-is-not-cls-compliant"></a><span data-ttu-id="abcd6-102">名前\<membername > CLS 準拠ではありません</span><span class="sxs-lookup"><span data-stu-id="abcd6-102">Name \<membername> is not CLS-compliant</span></span>
<span data-ttu-id="abcd6-103">アセンブリをマーク`<CLSCompliant(True)>`アンダー スコアで始まる名前を持つメンバーを公開しますが、(`_`)。</span><span class="sxs-lookup"><span data-stu-id="abcd6-103">An assembly is marked as `<CLSCompliant(True)>` but exposes a member with a name that begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="abcd6-104">プログラミング要素ですが準拠するため、1 つまたは複数アンダー スコアを含めることができます、 [Language Independence and Language-independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS) にする必要がありますされませんアンダー スコアで始まりです。</span><span class="sxs-lookup"><span data-stu-id="abcd6-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="abcd6-105">「[宣言された要素の名前](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abcd6-105">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="abcd6-106">プログラミング要素に <xref:System.CLSCompliantAttribute> を適用する場合は、準拠または非準拠を示すために、属性の `isCompliant` パラメーターを `True` または `False` のどちらかに設定します。</span><span class="sxs-lookup"><span data-stu-id="abcd6-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="abcd6-107">このパラメーターには既定値がありません。値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abcd6-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="abcd6-108">要素に <xref:System.CLSCompliantAttribute> を適用しないと、その要素は非準拠と見なされます。</span><span class="sxs-lookup"><span data-stu-id="abcd6-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="abcd6-109">既定では、このメッセージは警告です。</span><span class="sxs-lookup"><span data-stu-id="abcd6-109">By default, this message is a warning.</span></span> <span data-ttu-id="abcd6-110">警告を非表示にする方法や、警告をエラーとして扱う方法の詳細については、「[Visual Basic での警告の構成](/visualstudio/ide/configuring-warnings-in-visual-basic)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="abcd6-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="abcd6-111">**エラー ID:** BC40031</span><span class="sxs-lookup"><span data-stu-id="abcd6-111">**Error ID:** BC40031</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="abcd6-112">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="abcd6-112">To correct this error</span></span>  
  
- <span data-ttu-id="abcd6-113">ソース コード制御を使用する場合は、メンバー名を変更してから、アンダー スコアで始まらないようにします。</span><span class="sxs-lookup"><span data-stu-id="abcd6-113">If you have control over the source code, change the member name so that it does not begin with an underscore.</span></span>  
  
- <span data-ttu-id="abcd6-114">メンバー名が変わらない場合は、削除、<xref:System.CLSCompliantAttribute>その定義からとしてマークまたは`<CLSCompliant(False)>`します。</span><span class="sxs-lookup"><span data-stu-id="abcd6-114">If you require that the member name remain unchanged, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span> <span data-ttu-id="abcd6-115">アセンブリをマークすることも`<CLSCompliant(True)>`します。</span><span class="sxs-lookup"><span data-stu-id="abcd6-115">You can still mark the assembly as `<CLSCompliant(True)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abcd6-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="abcd6-116">See also</span></span>

- [<span data-ttu-id="abcd6-117">宣言された要素の名前</span><span class="sxs-lookup"><span data-stu-id="abcd6-117">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="abcd6-118">Visual Basic の名前付け規則</span><span class="sxs-lookup"><span data-stu-id="abcd6-118">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
