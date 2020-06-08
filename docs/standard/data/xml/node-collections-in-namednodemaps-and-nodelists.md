---
title: NamedNodeMaps と NodeLists のノード コレクション
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 025954b8-7aa8-47c5-a1c1-f81064fb4d65
ms.openlocfilehash: 3d721e9a6cff87adbf8896b1b37c0e2dfa55fa71
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288772"
---
# <a name="node-collections-in-namednodemaps-and-nodelists"></a><span data-ttu-id="5544a-102">NamedNodeMaps と NodeLists のノード コレクション</span><span class="sxs-lookup"><span data-stu-id="5544a-102">Node Collections in NamedNodeMaps and NodeLists</span></span>
<span data-ttu-id="5544a-103">ノードのセットを取得し、順序付けられた、または順序付けられていないコレクションに格納できます。</span><span class="sxs-lookup"><span data-stu-id="5544a-103">You can retrieve a set of nodes and put it in an ordered or unordered collection.</span></span> <span data-ttu-id="5544a-104">ノード セットが格納された順序付けられていないコレクションは、W3C (World Wide Web Consortium) では NamedNodeMap と呼ばれています。このタイプのコレクションからは、名前またはインデックスによってデータを取得できます。</span><span class="sxs-lookup"><span data-stu-id="5544a-104">When putting a set of nodes into an unordered collection, the set is called a NamedNodeMap by the World Wide Web Consortium (W3C); you can retrieve the data by name or index in this type of collection.</span></span> <span data-ttu-id="5544a-105">ノード セットが格納された順序付けられたコレクションは、W3C では NodeList と呼ばれています。このコレクションのデータは、0 から始まるインデックスによって取得できます。</span><span class="sxs-lookup"><span data-stu-id="5544a-105">Putting a set of nodes in an ordered collection is called a NodeList by the W3C, and the data can be retrieved by a zero-based index.</span></span> <span data-ttu-id="5544a-106">NamedNodeMaps および NodeLists は、W3C で規定されています。</span><span class="sxs-lookup"><span data-stu-id="5544a-106">NamedNodeMaps and NodeLists are described by the W3C.</span></span> <span data-ttu-id="5544a-107">Microsoft .NET Framework での NamedNodeMap の実装は **XmlNamedNodeMap** であり、NodeList の実装は **XmlNodeList** です。</span><span class="sxs-lookup"><span data-stu-id="5544a-107">The implementations in the Microsoft .NET Framework for the NamedNodeMap is the **XmlNamedNodeMap**, and the NodeList is implemented by the **XmlNodeList**.</span></span>  
  
 <span data-ttu-id="5544a-108">順序付けられていないコレクションについては、「[名前またはインデックスによる順序付けられていないノードの取得](unordered-node-retrieval-by-name-or-index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5544a-108">For information on the unordered collection, see [Unordered Node Retrieval by Name or Index](unordered-node-retrieval-by-name-or-index.md).</span></span> <span data-ttu-id="5544a-109">順序付けられたコレクションについては、「[インデックスによる順序付けられたノードの取得](ordered-node-retrieval-by-index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5544a-109">For information on the ordered collection, see [Ordered Node Retrieval by Index](ordered-node-retrieval-by-index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5544a-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="5544a-110">See also</span></span>

- [<span data-ttu-id="5544a-111">XML ドキュメント オブジェクト モデル (DOM)</span><span class="sxs-lookup"><span data-stu-id="5544a-111">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
