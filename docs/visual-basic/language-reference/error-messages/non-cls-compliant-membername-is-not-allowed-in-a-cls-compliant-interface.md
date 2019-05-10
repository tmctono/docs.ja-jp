---
title: CLS に準拠していない <membername> は、CLS に準拠しているインターフェイスに使用できません。
ms.date: 07/20/2015
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
ms.openlocfilehash: 68e1fb4f55d9f9b140f1b54cfde2bc5f60952dd2
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592137"
---
# <a name="non-cls-compliant-membername-is-not-allowed-in-a-cls-compliant-interface"></a><span data-ttu-id="79b74-102">非 CLS 準拠\<membername > は CLS 準拠インターフェイスでは許可されていません</span><span class="sxs-lookup"><span data-stu-id="79b74-102">Non-CLS-compliant \<membername> is not allowed in a CLS-compliant interface</span></span>
<span data-ttu-id="79b74-103">プロパティ、プロシージャ、またはインターフェイスでイベントがマーク`<CLSCompliant(True)>`インターフェイス自体としてマークされている場合`<CLSCompliant(False)>`またはマークされていません。</span><span class="sxs-lookup"><span data-stu-id="79b74-103">A property, procedure, or event in an interface is marked as `<CLSCompliant(True)>` when the interface itself is marked as `<CLSCompliant(False)>` or is not marked.</span></span>  
  
 <span data-ttu-id="79b74-104">準拠するためのインターフェイスの[Language Independence and Language-independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS) にすべてのメンバーは、準拠である必要があります。</span><span class="sxs-lookup"><span data-stu-id="79b74-104">For an interface to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), all its members must be compliant.</span></span>  
  
 <span data-ttu-id="79b74-105">プログラミング要素に <xref:System.CLSCompliantAttribute> を適用する場合は、準拠または非準拠を示すために、属性の `isCompliant` パラメーターを `True` または `False` のどちらかに設定します。</span><span class="sxs-lookup"><span data-stu-id="79b74-105">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="79b74-106">このパラメーターには既定値がありません。値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79b74-106">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="79b74-107">要素に <xref:System.CLSCompliantAttribute> を適用しないと、その要素は非準拠と見なされます。</span><span class="sxs-lookup"><span data-stu-id="79b74-107">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="79b74-108">既定では、このメッセージは警告です。</span><span class="sxs-lookup"><span data-stu-id="79b74-108">By default, this message is a warning.</span></span> <span data-ttu-id="79b74-109">警告を非表示にする方法や、警告をエラーとして扱う方法の詳細については、「[Visual Basic での警告の構成](/visualstudio/ide/configuring-warnings-in-visual-basic)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="79b74-109">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="79b74-110">**エラー ID:** BC40033</span><span class="sxs-lookup"><span data-stu-id="79b74-110">**Error ID:** BC40033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="79b74-111">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="79b74-111">To correct this error</span></span>  
  
- <span data-ttu-id="79b74-112">CLS 準拠をする必要があり、インターフェイスのソース コードを制御、マーク、インターフェイスとして`<CLSCompliant(True)>`すべてのメンバーが準拠している場合。</span><span class="sxs-lookup"><span data-stu-id="79b74-112">If you require CLS compliance and have control over the interface source code, mark the interface as `<CLSCompliant(True)>` if all its members are compliant.</span></span>  
  
- <span data-ttu-id="79b74-113">インターフェイスのソース コードを制御することはできません、CLS 準拠が必要な場合、または準拠しているが明確でない場合は、このメンバーを別のインターフェイスを定義します。</span><span class="sxs-lookup"><span data-stu-id="79b74-113">If you require CLS compliance and do not have control over the interface source code, or if it does not qualify to be compliant, define this member within a different interface.</span></span>  
  
- <span data-ttu-id="79b74-114">このメンバーが、現在のインターフェイス内に維持されることが必要な場合は、削除、<xref:System.CLSCompliantAttribute>その定義からとしてマークまたは`<CLSCompliant(False)>`します。</span><span class="sxs-lookup"><span data-stu-id="79b74-114">If you require that this member remain within its current interface, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79b74-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="79b74-115">See also</span></span>

- [<span data-ttu-id="79b74-116">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="79b74-116">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
