---
title: パラメーター '<parametername>' の型は CLS に準拠していません。
ms.date: 07/20/2015
f1_keywords:
- vbc40028
- bc40028
helpviewer_keywords:
- BC40028
ms.assetid: dfa1f6f9-bb88-44ad-b85f-149144363d41
ms.openlocfilehash: a719b3f1cbd972e79d057730ac1d89e5d91d97e5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64664309"
---
# <a name="type-of-parameter-parametername-is-not-cls-compliant"></a><span data-ttu-id="61417-102">パラメーターの型 '\<parametername >' は CLS 準拠</span><span class="sxs-lookup"><span data-stu-id="61417-102">Type of parameter '\<parametername>' is not CLS-compliant</span></span>
<span data-ttu-id="61417-103">プロシージャがマーク`<CLSCompliant(True)>`としてマークされている型のパラメーターを宣言しますが、 `<CLSCompliant(False)>`、マークされていない、または非準拠の型であるためには修飾されません。</span><span class="sxs-lookup"><span data-stu-id="61417-103">A procedure is marked as `<CLSCompliant(True)>` but declares a parameter with a type that is marked as `<CLSCompliant(False)>`, is not marked, or does not qualify because it is a noncompliant type.</span></span>  
  
 <span data-ttu-id="61417-104">プロシージャを[言語への非依存性および言語非依存コンポーネント](../../../standard/language-independence-and-language-independent-components.md) (CLS) に準拠させるには、CLS 準拠型のみを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61417-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="61417-105">これは、パラメーターの型、戻り値の型、およびすべてのローカル変数の型に適用されます。</span><span class="sxs-lookup"><span data-stu-id="61417-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span>  
  
 <span data-ttu-id="61417-106">次の Visual Basic データ型は CLS 準拠ではありません。</span><span class="sxs-lookup"><span data-stu-id="61417-106">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
- [<span data-ttu-id="61417-107">SByte データ型</span><span class="sxs-lookup"><span data-stu-id="61417-107">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [<span data-ttu-id="61417-108">UInteger データ型</span><span class="sxs-lookup"><span data-stu-id="61417-108">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [<span data-ttu-id="61417-109">ULong データ型</span><span class="sxs-lookup"><span data-stu-id="61417-109">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [<span data-ttu-id="61417-110">UShort データ型</span><span class="sxs-lookup"><span data-stu-id="61417-110">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="61417-111">プログラミング要素に <xref:System.CLSCompliantAttribute> を適用する場合は、準拠または非準拠を示すために、属性の `isCompliant` パラメーターを `True` または `False` のどちらかに設定します。</span><span class="sxs-lookup"><span data-stu-id="61417-111">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="61417-112">このパラメーターには既定値がありません。値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61417-112">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="61417-113">要素に <xref:System.CLSCompliantAttribute> を適用しないと、その要素は非準拠と見なされます。</span><span class="sxs-lookup"><span data-stu-id="61417-113">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="61417-114">既定では、このメッセージは警告です。</span><span class="sxs-lookup"><span data-stu-id="61417-114">By default, this message is a warning.</span></span> <span data-ttu-id="61417-115">警告を非表示にする方法や、警告をエラーとして扱う方法の詳細については、「[Visual Basic での警告の構成](/visualstudio/ide/configuring-warnings-in-visual-basic)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="61417-115">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="61417-116">**エラー ID:** BC40028</span><span class="sxs-lookup"><span data-stu-id="61417-116">**Error ID:** BC40028</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="61417-117">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="61417-117">To correct this error</span></span>  
  
- <span data-ttu-id="61417-118">プロシージャは、この特定の型のパラメーターを受け取る必要があります、削除、<xref:System.CLSCompliantAttribute>します。</span><span class="sxs-lookup"><span data-stu-id="61417-118">If the procedure must take a parameter of this particular type, remove the <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="61417-119">プロシージャは CLS 準拠になりません。</span><span class="sxs-lookup"><span data-stu-id="61417-119">The procedure cannot be CLS-compliant.</span></span>  
  
- <span data-ttu-id="61417-120">プロシージャは、CLS に準拠する必要があります、最も近い CLS 準拠型にこのパラメーターの型を変更します。</span><span class="sxs-lookup"><span data-stu-id="61417-120">If the procedure must be CLS-compliant, change the type of this parameter to the closest CLS-compliant type.</span></span> <span data-ttu-id="61417-121">たとえば、2,147,483,647 を超える値の範囲が不要な場合は、 `UInteger` の代わりに `Integer` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="61417-121">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="61417-122">拡張範囲が必要な場合は、 `UInteger` の代わりに `Long`を使用できます。</span><span class="sxs-lookup"><span data-stu-id="61417-122">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
- <span data-ttu-id="61417-123">オートメーション オブジェクトや COM オブジェクトとやり取りする場合は、一部の型のデータ幅が [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] とは異なることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="61417-123">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="61417-124">たとえば、他の多くの環境では `int` は 16 ビットです。</span><span class="sxs-lookup"><span data-stu-id="61417-124">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="61417-125">このようなコンポーネントから 16 ビット整数を受け取る場合宣言として`Short`の代わりに`Integer`管理対象の Visual Basic コードです。</span><span class="sxs-lookup"><span data-stu-id="61417-125">If you are accepting a 16-bit integer from such a component, declare it as `Short` instead of `Integer` in your managed Visual Basic code.</span></span>