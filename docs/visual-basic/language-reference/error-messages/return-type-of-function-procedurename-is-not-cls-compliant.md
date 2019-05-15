---
title: 関数 '<procedurename>' の戻り値の型は CLS に準拠していません。
ms.date: 07/20/2015
f1_keywords:
- bc40027
- vbc40027
helpviewer_keywords:
- BC40027
ms.assetid: 33c088c7-48e7-400c-920e-6d8967e1f3fc
ms.openlocfilehash: 881726ea2cfb23493d85097635adb15608ed741d
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65642255"
---
# <a name="return-type-of-function-procedurename-is-not-cls-compliant"></a><span data-ttu-id="4a0bc-102">関数の型を返す '\<procedurename >' は CLS 準拠</span><span class="sxs-lookup"><span data-stu-id="4a0bc-102">Return type of function '\<procedurename>' is not CLS-compliant</span></span>
<span data-ttu-id="4a0bc-103">A`Function`プロシージャがマーク`<CLSCompliant(True)>`としてマークされている型を返しますが、 `<CLSCompliant(False)>`、マークされていない、または非準拠の型であるためには修飾されません。</span><span class="sxs-lookup"><span data-stu-id="4a0bc-103">A `Function` procedure is marked as `<CLSCompliant(True)>` but returns a type that is marked as `<CLSCompliant(False)>`, is not marked, or does not qualify because it is a noncompliant type.</span></span>  
  
 <span data-ttu-id="4a0bc-104">プロシージャを[言語への非依存性および言語非依存コンポーネント](../../../standard/language-independence-and-language-independent-components.md) (CLS) に準拠させるには、CLS 準拠型のみを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a0bc-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="4a0bc-105">これは、パラメーターの型、戻り値の型、およびすべてのローカル変数の型に適用されます。</span><span class="sxs-lookup"><span data-stu-id="4a0bc-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span>  
  
 <span data-ttu-id="4a0bc-106">次の Visual Basic データ型は CLS 準拠ではありません。</span><span class="sxs-lookup"><span data-stu-id="4a0bc-106">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
- [<span data-ttu-id="4a0bc-107">SByte データ型</span><span class="sxs-lookup"><span data-stu-id="4a0bc-107">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [<span data-ttu-id="4a0bc-108">UInteger データ型</span><span class="sxs-lookup"><span data-stu-id="4a0bc-108">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [<span data-ttu-id="4a0bc-109">ULong データ型</span><span class="sxs-lookup"><span data-stu-id="4a0bc-109">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [<span data-ttu-id="4a0bc-110">UShort データ型</span><span class="sxs-lookup"><span data-stu-id="4a0bc-110">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="4a0bc-111">プログラミング要素に <xref:System.CLSCompliantAttribute> を適用する場合は、準拠または非準拠を示すために、属性の `isCompliant` パラメーターを `True` または `False` のどちらかに設定します。</span><span class="sxs-lookup"><span data-stu-id="4a0bc-111">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="4a0bc-112">このパラメーターには既定値がありません。値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a0bc-112">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="4a0bc-113">要素に <xref:System.CLSCompliantAttribute> を適用しないと、その要素は非準拠と見なされます。</span><span class="sxs-lookup"><span data-stu-id="4a0bc-113">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="4a0bc-114">既定では、このメッセージは警告です。</span><span class="sxs-lookup"><span data-stu-id="4a0bc-114">By default, this message is a warning.</span></span> <span data-ttu-id="4a0bc-115">警告を非表示にする方法や、警告をエラーとして扱う方法の詳細については、「[Visual Basic での警告の構成](/visualstudio/ide/configuring-warnings-in-visual-basic)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4a0bc-115">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="4a0bc-116">**エラー ID:** BC40027</span><span class="sxs-lookup"><span data-stu-id="4a0bc-116">**Error ID:** BC40027</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4a0bc-117">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="4a0bc-117">To correct this error</span></span>  
  
- <span data-ttu-id="4a0bc-118">場合、`Function`プロシージャがこの特定の型を返す、削除する必要があります、<xref:System.CLSCompliantAttribute>します。</span><span class="sxs-lookup"><span data-stu-id="4a0bc-118">If the `Function` procedure must return this particular type, remove the <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="4a0bc-119">プロシージャは CLS 準拠になりません。</span><span class="sxs-lookup"><span data-stu-id="4a0bc-119">The procedure cannot be CLS-compliant.</span></span>  
  
- <span data-ttu-id="4a0bc-120">場合、`Function`プロシージャが CLS に準拠する、最も近い CLS 準拠型に戻り値の型を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a0bc-120">If the `Function` procedure must be CLS-compliant, change the return type to the closest CLS-compliant type.</span></span> <span data-ttu-id="4a0bc-121">たとえば、2,147,483,647 を超える値の範囲が不要な場合は、 `UInteger` の代わりに `Integer` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4a0bc-121">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="4a0bc-122">拡張範囲が必要な場合は、 `UInteger` の代わりに `Long`を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4a0bc-122">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
- <span data-ttu-id="4a0bc-123">オートメーションまたは COM オブジェクトをやり取りする場合は、一部の種類がある .NET Framework の別のデータ幅よりも注意してください。</span><span class="sxs-lookup"><span data-stu-id="4a0bc-123">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the .NET Framework.</span></span> <span data-ttu-id="4a0bc-124">たとえば、他の多くの環境では `int` は 16 ビットです。</span><span class="sxs-lookup"><span data-stu-id="4a0bc-124">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="4a0bc-125">このようなコンポーネントに 16 ビット整数を返す場合は宣言として`Short`の代わりに`Integer`管理対象の Visual Basic コードです。</span><span class="sxs-lookup"><span data-stu-id="4a0bc-125">If you are returning a 16-bit integer to such a component, declare it as `Short` instead of `Integer` in your managed Visual Basic code.</span></span>
