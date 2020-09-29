---
title: 型 <typename> は CLS に準拠していません。
ms.date: 07/20/2015
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
ms.openlocfilehash: 369516fb12b24981eaecfe467bf421dec279aa01
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875097"
---
# <a name="type-typename-is-not-cls-compliant"></a><span data-ttu-id="b6b1c-102">型 \<typename> は CLS に準拠していません。</span><span class="sxs-lookup"><span data-stu-id="b6b1c-102">Type \<typename> is not CLS-compliant</span></span>

<span data-ttu-id="b6b1c-103">変数、プロパティ、または関数の戻り値が、CLS に準拠していないデータ型で宣言されています。</span><span class="sxs-lookup"><span data-stu-id="b6b1c-103">A variable, property, or function return is declared with a data type that is not CLS-compliant.</span></span>  
  
 <span data-ttu-id="b6b1c-104">アプリケーションを[言語への非依存性および言語非依存コンポーネント](../../../standard/language-independence-and-language-independent-components.md) (CLS) に準拠させるには、CLS 準拠型のみを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6b1c-104">For an application to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span>  
  
 <span data-ttu-id="b6b1c-105">次の Visual Basic データ型は CLS に準拠していません。</span><span class="sxs-lookup"><span data-stu-id="b6b1c-105">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
- [<span data-ttu-id="b6b1c-106">SByte データ型</span><span class="sxs-lookup"><span data-stu-id="b6b1c-106">SByte Data Type</span></span>](../data-types/sbyte-data-type.md)  
  
- [<span data-ttu-id="b6b1c-107">UInteger データ型</span><span class="sxs-lookup"><span data-stu-id="b6b1c-107">UInteger Data Type</span></span>](../data-types/uinteger-data-type.md)  
  
- [<span data-ttu-id="b6b1c-108">ULong データ型</span><span class="sxs-lookup"><span data-stu-id="b6b1c-108">ULong Data Type</span></span>](../data-types/ulong-data-type.md)  
  
- [<span data-ttu-id="b6b1c-109">UShort データ型</span><span class="sxs-lookup"><span data-stu-id="b6b1c-109">UShort Data Type</span></span>](../data-types/ushort-data-type.md)  
  
 <span data-ttu-id="b6b1c-110">**エラー ID:** BC40041</span><span class="sxs-lookup"><span data-stu-id="b6b1c-110">**Error ID:** BC40041</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b6b1c-111">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="b6b1c-111">To correct this error</span></span>  
  
- <span data-ttu-id="b6b1c-112">アプリケーションを CLS 準拠にする必要がある場合は、この要素のデータ型を、最も近い CLS 準拠型に変更します。</span><span class="sxs-lookup"><span data-stu-id="b6b1c-112">If your application needs to be CLS-compliant, change the data type of this element to the closest CLS-compliant type.</span></span> <span data-ttu-id="b6b1c-113">たとえば、2,147,483,647 を超える値の範囲が不要な場合は、 `UInteger` の代わりに `Integer` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6b1c-113">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="b6b1c-114">拡張範囲が必要な場合は、 `UInteger` の代わりに `Long`を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6b1c-114">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
- <span data-ttu-id="b6b1c-115">アプリケーションを CLS 準拠にする必要がない場合は、何も変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b6b1c-115">If your application does not need to be CLS-compliant, you do not need to change anything.</span></span> <span data-ttu-id="b6b1c-116">ただし、準拠していないことを認識している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6b1c-116">You should be aware of its noncompliance, however.</span></span>
