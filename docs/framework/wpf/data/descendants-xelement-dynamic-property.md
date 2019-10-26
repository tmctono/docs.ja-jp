---
title: Descendants (XElement 動的プロパティ)
ms.date: 10/22/2019
ms.topic: reference
ms.openlocfilehash: 8d14b0a94d1a2028a56f649a574f157264ba50fa
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921180"
---
# <a name="descendants-xelement-dynamic-property"></a><span data-ttu-id="49bda-102">Descendants (XElement 動的プロパティ)</span><span class="sxs-lookup"><span data-stu-id="49bda-102">Descendants (XElement dynamic property)</span></span>

<span data-ttu-id="49bda-103">現在の要素の子孫要素のうち指定された拡張名に一致するすべての子孫要素を取得するためのインデクサーを取得します。</span><span class="sxs-lookup"><span data-stu-id="49bda-103">Gets an indexer used to retrieve all the descendant elements of the current element that match the specified expanded name.</span></span>

## <a name="syntax"></a><span data-ttu-id="49bda-104">構文</span><span class="sxs-lookup"><span data-stu-id="49bda-104">Syntax</span></span>

```xaml
elem.Descendants[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a><span data-ttu-id="49bda-105">プロパティ値/戻り値</span><span class="sxs-lookup"><span data-stu-id="49bda-105">Property value/return value</span></span>

<span data-ttu-id="49bda-106">`IEnumerable<XElement> Item(String expandedName)` 型のインデクサー。</span><span class="sxs-lookup"><span data-stu-id="49bda-106">An indexer of the type `IEnumerable<XElement> Item(String expandedName)`.</span></span> <span data-ttu-id="49bda-107">このインデクサーは、指定された子孫要素の拡張名を受け取り、<xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>` コレクション内の一致する子要素を返します。</span><span class="sxs-lookup"><span data-stu-id="49bda-107">This indexer takes the expanded name of the specified descendant elements and returns the matching child elements in an <xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>` collection.</span></span>

## <a name="remarks"></a><span data-ttu-id="49bda-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="49bda-108">Remarks</span></span>

<span data-ttu-id="49bda-109">このプロパティは、<xref:System.Xml.Linq.XContainer.Descendants(System.Xml.Linq.XName)?displayProperty=fullName> クラスの <xref:System.Xml.Linq.XContainer> メソッドに相当します。</span><span class="sxs-lookup"><span data-stu-id="49bda-109">This property is equivalent to the <xref:System.Xml.Linq.XContainer.Descendants(System.Xml.Linq.XName)?displayProperty=fullName> method of the <xref:System.Xml.Linq.XContainer> class.</span></span>

<span data-ttu-id="49bda-110">返されるコレクション内の要素は、XML ソース ドキュメント順になります。</span><span class="sxs-lookup"><span data-stu-id="49bda-110">The elements in the returned collection are in XML source document order.</span></span>

<span data-ttu-id="49bda-111">このプロパティは、遅延実行を使用します。</span><span class="sxs-lookup"><span data-stu-id="49bda-111">This property uses deferred execution.</span></span>

## <a name="see-also"></a><span data-ttu-id="49bda-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="49bda-112">See also</span></span>

- [<span data-ttu-id="49bda-113">XElement クラスの動的プロパティ</span><span class="sxs-lookup"><span data-stu-id="49bda-113">XElement class dynamic properties</span></span>](attribute-xelement-dynamic-property.md)
- [<span data-ttu-id="49bda-114">要素</span><span class="sxs-lookup"><span data-stu-id="49bda-114">Elements</span></span>](elements-xelement-dynamic-property.md)
