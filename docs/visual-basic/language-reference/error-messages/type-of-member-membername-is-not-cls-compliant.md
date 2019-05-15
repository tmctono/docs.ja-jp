---
title: メンバー '<membername>' の型は CLS に準拠していません。
ms.date: 07/20/2015
f1_keywords:
- bc40025
- vbc40025
helpviewer_keywords:
- BC40025
ms.assetid: adbd34bb-43d2-4266-90e7-cd1afaf49b4e
ms.openlocfilehash: f6f66617774dccff4450cce42904126acf5c3769
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65590689"
---
# <a name="type-of-member-membername-is-not-cls-compliant"></a><span data-ttu-id="1fccd-102">メンバーの型 '\<membername >' は CLS 準拠</span><span class="sxs-lookup"><span data-stu-id="1fccd-102">Type of member '\<membername>' is not CLS-compliant</span></span>
<span data-ttu-id="1fccd-103">このメンバーが指定されたデータ型の一部、 [Language Independence and Language-independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS)。</span><span class="sxs-lookup"><span data-stu-id="1fccd-103">The data type specified for this member is not part of the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span> <span data-ttu-id="1fccd-104">これは、.NET Framework および Visual Basic は、このデータ型をサポートするため、コンポーネント内でエラーではありません。</span><span class="sxs-lookup"><span data-stu-id="1fccd-104">This is not an error within your component, because the .NET Framework and Visual Basic support this data type.</span></span> <span data-ttu-id="1fccd-105">ただし、厳密に CLS 準拠コードで記述された別のコンポーネントでは、このデータ型がサポートしない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1fccd-105">However, another component written in strictly CLS-compliant code might not support this data type.</span></span> <span data-ttu-id="1fccd-106">このようなコンポーネントはできないコンポーネントを正常にやり取りすることがあります。</span><span class="sxs-lookup"><span data-stu-id="1fccd-106">Such a component might not be able to interact successfully with your component.</span></span>  
  
 <span data-ttu-id="1fccd-107">次の Visual Basic データ型は CLS 準拠ではありません。</span><span class="sxs-lookup"><span data-stu-id="1fccd-107">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
- [<span data-ttu-id="1fccd-108">SByte データ型</span><span class="sxs-lookup"><span data-stu-id="1fccd-108">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [<span data-ttu-id="1fccd-109">UInteger データ型</span><span class="sxs-lookup"><span data-stu-id="1fccd-109">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [<span data-ttu-id="1fccd-110">ULong データ型</span><span class="sxs-lookup"><span data-stu-id="1fccd-110">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [<span data-ttu-id="1fccd-111">UShort データ型</span><span class="sxs-lookup"><span data-stu-id="1fccd-111">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="1fccd-112">既定では、このメッセージは警告です。</span><span class="sxs-lookup"><span data-stu-id="1fccd-112">By default, this message is a warning.</span></span> <span data-ttu-id="1fccd-113">警告を非表示にする方法や、警告をエラーとして扱う方法の詳細については、「 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fccd-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="1fccd-114">**エラー ID:** BC40025</span><span class="sxs-lookup"><span data-stu-id="1fccd-114">**Error ID:** BC40025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1fccd-115">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="1fccd-115">To correct this error</span></span>  
  
- <span data-ttu-id="1fccd-116">コンポーネントは、のみ、他の .NET Framework コンポーネントとのインターフェイスまたはその他のコンポーネントとやり取りしません、何も変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1fccd-116">If your component interfaces only with other .NET Framework components, or does not interface with any other components, you do not need to change anything.</span></span>  
  
- <span data-ttu-id="1fccd-117">いない .NET Framework 用に記述されたコンポーネントをやり取りする場合がありますできるリフレクションまたはドキュメントについてからのいずれかを判断するこのデータ型がサポートしているかどうか。</span><span class="sxs-lookup"><span data-stu-id="1fccd-117">If you are interfacing with a component not written for the .NET Framework, you might be able to determine, either through reflection or from documentation, whether it supports this data type.</span></span> <span data-ttu-id="1fccd-118">その場合、何も変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1fccd-118">If it does, you do not need to change anything.</span></span>  
  
- <span data-ttu-id="1fccd-119">このデータ型をサポートしていないコンポーネントとやり取りする場合は、最も近い CLS 準拠型で置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fccd-119">If you are interfacing with a component that does not support this data type, you must replace it with the closest CLS-compliant type.</span></span> <span data-ttu-id="1fccd-120">たとえば、2,147,483,647 を超える値の範囲が不要な場合は、 `UInteger` の代わりに `Integer` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1fccd-120">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="1fccd-121">拡張範囲が必要な場合は、 `UInteger` の代わりに `Long`を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1fccd-121">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
- <span data-ttu-id="1fccd-122">オートメーションまたは COM オブジェクトをやり取りする場合は、一部の種類がある .NET Framework の別のデータ幅よりも注意してください。</span><span class="sxs-lookup"><span data-stu-id="1fccd-122">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the .NET Framework.</span></span> <span data-ttu-id="1fccd-123">たとえば、他の多くの環境では `uint` は 16 ビットです。</span><span class="sxs-lookup"><span data-stu-id="1fccd-123">For example, `uint` is often 16 bits in other environments.</span></span> <span data-ttu-id="1fccd-124">このようなコンポーネントに 16 ビットの引数を渡す場合の宣言として`UShort`の代わりに`UInteger`管理対象の Visual Basic コードです。</span><span class="sxs-lookup"><span data-stu-id="1fccd-124">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fccd-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="1fccd-125">See also</span></span>

- [<span data-ttu-id="1fccd-126">リフレクション</span><span class="sxs-lookup"><span data-stu-id="1fccd-126">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)
