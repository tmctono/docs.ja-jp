---
title: Elements (XElement 動的プロパティ)
ms.date: 10/22/2019
ms.topic: reference
apiname:
- XElement.Elements
apitype: Assembly
ms.openlocfilehash: 812adabd3bfb01fd9313ce3f35e6cb0a5e23344e
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921150"
---
# <a name="elements-xelement-dynamic-property"></a><span data-ttu-id="f9b33-102">Elements (XElement 動的プロパティ)</span><span class="sxs-lookup"><span data-stu-id="f9b33-102">Elements (XElement dynamic property)</span></span>

<span data-ttu-id="f9b33-103">現在の要素の子要素のうち指定された拡張名に一致する子要素の取得に使用するインデクサーを取得します。</span><span class="sxs-lookup"><span data-stu-id="f9b33-103">Gets an indexer used to retrieve the child elements of the current element that match the specified expanded name.</span></span>

## <a name="syntax"></a><span data-ttu-id="f9b33-104">構文</span><span class="sxs-lookup"><span data-stu-id="f9b33-104">Syntax</span></span>

```xaml
elem.Elements[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a><span data-ttu-id="f9b33-105">プロパティ値/戻り値</span><span class="sxs-lookup"><span data-stu-id="f9b33-105">Property value/return value</span></span>

<span data-ttu-id="f9b33-106">`IEnumerable<XElement> Item(String expandedName)` 型のインデクサー。</span><span class="sxs-lookup"><span data-stu-id="f9b33-106">An indexer of the type `IEnumerable<XElement> Item(String expandedName)`.</span></span> <span data-ttu-id="f9b33-107">このインデクサーは、目的の子要素の拡張名を取得し、<xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>` コレクション内の一致する子要素を返します。</span><span class="sxs-lookup"><span data-stu-id="f9b33-107">This indexer takes the expanded name of the desired child elements and returns the matching child elements in an <xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>` collection.</span></span>

## <a name="remarks"></a><span data-ttu-id="f9b33-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="f9b33-108">Remarks</span></span>

<span data-ttu-id="f9b33-109">このプロパティは、<xref:System.Xml.Linq.XContainer.Elements(System.Xml.Linq.XName)?displayProperty=fullName> クラスの <xref:System.Xml.Linq.XContainer> メソッドに相当します。</span><span class="sxs-lookup"><span data-stu-id="f9b33-109">This property is equivalent to the <xref:System.Xml.Linq.XContainer.Elements(System.Xml.Linq.XName)?displayProperty=fullName> method of the <xref:System.Xml.Linq.XContainer> class.</span></span>

<span data-ttu-id="f9b33-110">返されるコレクション内の要素は、XML ソース ドキュメント順になります。</span><span class="sxs-lookup"><span data-stu-id="f9b33-110">The elements in the returned collection are in XML source document order.</span></span>

<span data-ttu-id="f9b33-111">このプロパティは、遅延実行を使用します。</span><span class="sxs-lookup"><span data-stu-id="f9b33-111">This property uses deferred execution.</span></span>

## <a name="see-also"></a><span data-ttu-id="f9b33-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9b33-112">See also</span></span>

- [<span data-ttu-id="f9b33-113">XElement クラスの動的プロパティ</span><span class="sxs-lookup"><span data-stu-id="f9b33-113">XElement class dynamic properties</span></span>](attribute-xelement-dynamic-property.md)
- [<span data-ttu-id="f9b33-114">要素</span><span class="sxs-lookup"><span data-stu-id="f9b33-114">Element</span></span>](element-xelement-dynamic-property.md)
- [<span data-ttu-id="f9b33-115">子孫</span><span class="sxs-lookup"><span data-stu-id="f9b33-115">Descendants</span></span>](descendants-xelement-dynamic-property.md)
