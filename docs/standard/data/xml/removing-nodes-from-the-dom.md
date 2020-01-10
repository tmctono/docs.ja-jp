---
title: DOM からのノードの削除
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 0a98e0ca-0555-45c1-ab69-0d8d20ca1abd
ms.openlocfilehash: a34b92abc59215c3cb2b94afd88e2e30405b4e9a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710311"
---
# <a name="removing-nodes-from-the-dom"></a><span data-ttu-id="02aa6-102">DOM からのノードの削除</span><span class="sxs-lookup"><span data-stu-id="02aa6-102">Removing Nodes from the DOM</span></span>
<span data-ttu-id="02aa6-103">XML ドキュメント オブジェクト モデル (DOM) からノードを削除するには、<xref:System.Xml.XmlNode.RemoveChild%2A> メソッドを使用して特定のノードを削除します。</span><span class="sxs-lookup"><span data-stu-id="02aa6-103">To remove a node from the XML Document Object Model (DOM), use the <xref:System.Xml.XmlNode.RemoveChild%2A> method to remove a specific node.</span></span> <span data-ttu-id="02aa6-104">ノードを削除すると、削除しようとしたノードがリーフ ノードでない場合は、そのノードに含まれるサブツリーも削除されます。</span><span class="sxs-lookup"><span data-stu-id="02aa6-104">When you remove a node, the method removes the subtree belonging to the node being removed; that is, if it is not a leaf node.</span></span>  
  
 <span data-ttu-id="02aa6-105">DOM から複数のノードを削除するには、<xref:System.Xml.XmlNode.RemoveAll%2A> メソッドを使用します。現在のノードに子や属性があれば、それらがすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="02aa6-105">To remove multiple nodes from the DOM, use the <xref:System.Xml.XmlNode.RemoveAll%2A> method to remove all the children and attributes, if applicable, of the current node.</span></span>  
  
 <span data-ttu-id="02aa6-106"><xref:System.Xml.XmlNamedNodeMap> を使用している場合は、<xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A> メソッドを使用してノードを削除できます。</span><span class="sxs-lookup"><span data-stu-id="02aa6-106">If you are working with an <xref:System.Xml.XmlNamedNodeMap>, you can remove a node using the <xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A> method.</span></span>  
  
 <span data-ttu-id="02aa6-107">属性を削除するには、「[DOM の要素ノードからの属性の削除](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02aa6-107">To remove attributes, see [Removing Attributes from an Element Node in the DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02aa6-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="02aa6-108">See also</span></span>

- [<span data-ttu-id="02aa6-109">XML ドキュメント オブジェクト モデル (DOM)</span><span class="sxs-lookup"><span data-stu-id="02aa6-109">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
