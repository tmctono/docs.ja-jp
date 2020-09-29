---
title: 名前 <membername> は CLS に準拠していません。
ms.date: 07/20/2015
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
ms.openlocfilehash: 33b60b2212d25737330dc93d7ba2715e4d5865b7
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873700"
---
# <a name="name-membername-is-not-cls-compliant"></a><span data-ttu-id="5a765-102">名前 \<membername> は CLS に準拠していません。</span><span class="sxs-lookup"><span data-stu-id="5a765-102">Name \<membername> is not CLS-compliant</span></span>

<span data-ttu-id="5a765-103">アセンブリが `<CLSCompliant(True)>` としてマークされているのに、アンダースコア (`_`) で始まる名前のメンバーを公開しています。</span><span class="sxs-lookup"><span data-stu-id="5a765-103">An assembly is marked as `<CLSCompliant(True)>` but exposes a member with a name that begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="5a765-104">プログラミング要素には 1 つ以上のアンダースコアを含めることができますが、[言語への非依存性、および言語非依存コンポーネント](../../../standard/language-independence-and-language-independent-components.md) (CLS) に準拠するためには、先頭をアンダースコアにしてはなりません。</span><span class="sxs-lookup"><span data-stu-id="5a765-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="5a765-105">「 [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a765-105">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="5a765-106">プログラミング要素に <xref:System.CLSCompliantAttribute> を適用する場合は、属性の `isCompliant` パラメーターを `True` または `False` のどちらかに設定して、準拠または非準拠を示します。</span><span class="sxs-lookup"><span data-stu-id="5a765-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="5a765-107">このパラメーターには既定値がありません。値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a765-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="5a765-108">要素に <xref:System.CLSCompliantAttribute> を適用しないと、その要素は非準拠と見なされます。</span><span class="sxs-lookup"><span data-stu-id="5a765-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="5a765-109">既定では、このメッセージは警告です。</span><span class="sxs-lookup"><span data-stu-id="5a765-109">By default, this message is a warning.</span></span> <span data-ttu-id="5a765-110">警告を非表示にする方法や、警告をエラーとして扱う方法の詳細については、「 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5a765-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="5a765-111">**エラー ID:** BC40031</span><span class="sxs-lookup"><span data-stu-id="5a765-111">**Error ID:** BC40031</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5a765-112">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="5a765-112">To correct this error</span></span>  
  
- <span data-ttu-id="5a765-113">ソース コードを制御できる場合は、アンダースコアで始まらないようにメンバー名を変更します。</span><span class="sxs-lookup"><span data-stu-id="5a765-113">If you have control over the source code, change the member name so that it does not begin with an underscore.</span></span>  
  
- <span data-ttu-id="5a765-114">メンバーの名前が変更されないようにする必要がある場合は、その定義から <xref:System.CLSCompliantAttribute> を削除するか、`<CLSCompliant(False)>` としてマークします。</span><span class="sxs-lookup"><span data-stu-id="5a765-114">If you require that the member name remain unchanged, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span> <span data-ttu-id="5a765-115">アセンブリを `<CLSCompliant(True)>` としてマークすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5a765-115">You can still mark the assembly as `<CLSCompliant(True)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a765-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a765-116">See also</span></span>

- [<span data-ttu-id="5a765-117">宣言された要素の名前</span><span class="sxs-lookup"><span data-stu-id="5a765-117">Declared Element Names</span></span>](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="5a765-118">Visual Basic の名前付け規則</span><span class="sxs-lookup"><span data-stu-id="5a765-118">Visual Basic Naming Conventions</span></span>](../../programming-guide/program-structure/naming-conventions.md)
