---
title: Attribute (XElement 動的プロパティ)
ms.date: 10/22/2019
ms.topic: reference
ms.openlocfilehash: 2b645575a5b6876ffbb52a999c4e05a2de037493
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921204"
---
# <a name="attribute-xelement-dynamic-property"></a><span data-ttu-id="10d59-102">Attribute (XElement 動的プロパティ)</span><span class="sxs-lookup"><span data-stu-id="10d59-102">Attribute (XElement dynamic property)</span></span>

<span data-ttu-id="10d59-103">指定された展開名に対応する属性のインスタンスの取得に使用するインデクサーを取得します。</span><span class="sxs-lookup"><span data-stu-id="10d59-103">Gets an indexer used to retrieve the attribute instance that corresponds to the specified expanded name.</span></span>

## <a name="syntax"></a><span data-ttu-id="10d59-104">構文</span><span class="sxs-lookup"><span data-stu-id="10d59-104">Syntax</span></span>

```xaml
elem.Attribute[{namespaceName}attribName]
```

## <a name="property-valuereturn-value"></a><span data-ttu-id="10d59-105">プロパティ値/戻り値</span><span class="sxs-lookup"><span data-stu-id="10d59-105">Property value/return value</span></span>

<span data-ttu-id="10d59-106">`XAttribute Item(String expandedName)` 型のインデクサー。</span><span class="sxs-lookup"><span data-stu-id="10d59-106">An indexer of the type `XAttribute Item(String expandedName)`.</span></span> <span data-ttu-id="10d59-107">このインデクサーは、指定された属性の展開名を受け取り、対応する <xref:System.Xml.Linq.XAttribute> を返します。指定された名前を持つ属性がない場合は、`null` を返します。</span><span class="sxs-lookup"><span data-stu-id="10d59-107">This indexer takes the expanded name of the specified attribute and returns the corresponding <xref:System.Xml.Linq.XAttribute>, or `null` if there is no attribute with the specified name.</span></span>

## <a name="remarks"></a><span data-ttu-id="10d59-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="10d59-108">Remarks</span></span>

<span data-ttu-id="10d59-109">このプロパティは、<xref:System.Xml.Linq.XElement.Attribute%2A> クラスの <xref:System.Xml.Linq.XElement?displayProperty=fullName> メソッドに相当します。</span><span class="sxs-lookup"><span data-stu-id="10d59-109">This property is equivalent to the <xref:System.Xml.Linq.XElement.Attribute%2A> method of the <xref:System.Xml.Linq.XElement?displayProperty=fullName> class.</span></span>

## <a name="see-also"></a><span data-ttu-id="10d59-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="10d59-110">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName>
- [<span data-ttu-id="10d59-111">XElement クラスの動的プロパティ</span><span class="sxs-lookup"><span data-stu-id="10d59-111">XElement Class Dynamic Properties</span></span>](attribute-xelement-dynamic-property.md)
- <span data-ttu-id="10d59-112">[[値]](value-xattribute-dynamic-property.md)</span><span class="sxs-lookup"><span data-stu-id="10d59-112">[Value](value-xattribute-dynamic-property.md)</span></span>
