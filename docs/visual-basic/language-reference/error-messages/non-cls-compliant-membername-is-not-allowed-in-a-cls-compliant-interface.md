---
title: CLS に準拠していない <membername> は、CLS に準拠しているインターフェイスに使用できません。
ms.date: 07/20/2015
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
ms.openlocfilehash: e572189b958612bf9527c82ce702df3ab929a23f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409401"
---
# <a name="non-cls-compliant-membername-is-not-allowed-in-a-cls-compliant-interface"></a><span data-ttu-id="41dee-102">CLS に準拠していない \<membername> は、CLS に準拠しているインターフェイスに使用できません。</span><span class="sxs-lookup"><span data-stu-id="41dee-102">Non-CLS-compliant \<membername> is not allowed in a CLS-compliant interface</span></span>
<span data-ttu-id="41dee-103">インターフェイス自体が `<CLSCompliant(False)>` としてマークされているか、またはマークされていない場合、インターフェイス内のプロパティ、プロシージャ、またはイベントは `<CLSCompliant(True)>` としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="41dee-103">A property, procedure, or event in an interface is marked as `<CLSCompliant(True)>` when the interface itself is marked as `<CLSCompliant(False)>` or is not marked.</span></span>  
  
 <span data-ttu-id="41dee-104">インターフェイスを[言語への非依存性および言語非依存コンポーネント](../../../standard/language-independence-and-language-independent-components.md) (CLS) に準拠させるには、そのすべてのメンバーが準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="41dee-104">For an interface to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), all its members must be compliant.</span></span>  
  
 <span data-ttu-id="41dee-105">プログラミング要素に <xref:System.CLSCompliantAttribute> を適用する場合は、属性の `isCompliant` パラメーターを `True` または `False` のどちらかに設定して、準拠または非準拠を示します。</span><span class="sxs-lookup"><span data-stu-id="41dee-105">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="41dee-106">このパラメーターには既定値がありません。値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41dee-106">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="41dee-107">要素に <xref:System.CLSCompliantAttribute> を適用しないと、その要素は非準拠と見なされます。</span><span class="sxs-lookup"><span data-stu-id="41dee-107">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="41dee-108">既定では、このメッセージは警告です。</span><span class="sxs-lookup"><span data-stu-id="41dee-108">By default, this message is a warning.</span></span> <span data-ttu-id="41dee-109">警告を非表示にする方法や、警告をエラーとして扱う方法の詳細については、「 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="41dee-109">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="41dee-110">**エラー ID:** BC40033</span><span class="sxs-lookup"><span data-stu-id="41dee-110">**Error ID:** BC40033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="41dee-111">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="41dee-111">To correct this error</span></span>  
  
- <span data-ttu-id="41dee-112">CLS への準拠が必要なときに、インターフェイスのソース コードを制御できる場合、そのすべてのメンバーが準拠している場合はインターフェイスを `<CLSCompliant(True)>` としてマークします。</span><span class="sxs-lookup"><span data-stu-id="41dee-112">If you require CLS compliance and have control over the interface source code, mark the interface as `<CLSCompliant(True)>` if all its members are compliant.</span></span>  
  
- <span data-ttu-id="41dee-113">CLS への準拠が必要なときに、インターフェイスのソース コードを制御できない場合や、インターフェイスのソース コードが準拠のための要件を満たしていない場合は、このメンバーを別のクラス内で定義します。</span><span class="sxs-lookup"><span data-stu-id="41dee-113">If you require CLS compliance and do not have control over the interface source code, or if it does not qualify to be compliant, define this member within a different interface.</span></span>  
  
- <span data-ttu-id="41dee-114">このメンバーを現在のインターフェイス内に残すことが必要な場合は、<xref:System.CLSCompliantAttribute> をその定義から削除するか、または `<CLSCompliant(False)>` としてマークします。</span><span class="sxs-lookup"><span data-stu-id="41dee-114">If you require that this member remain within its current interface, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41dee-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="41dee-115">See also</span></span>

- [<span data-ttu-id="41dee-116">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="41dee-116">Interface Statement</span></span>](../statements/interface-statement.md)
