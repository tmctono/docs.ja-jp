---
title: DOM を読み込むときの空白および有意の空白の処理
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1b141a0a-50d8-4ebd-83cd-a84449bb22b2
ms.openlocfilehash: 834644a07d790401a1131d6d901f144ef90dc495
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710025"
---
# <a name="white-space-and-significant-white-space-handling-when-loading-the-dom"></a><span data-ttu-id="7bb7d-102">DOM を読み込むときの空白および有意の空白の処理</span><span class="sxs-lookup"><span data-stu-id="7bb7d-102">White Space and Significant White Space Handling when Loading the DOM</span></span>
<span data-ttu-id="7bb7d-103">ドキュメントを読み込むときには、空白を保持するオプションを設定して、ドキュメント ツリーに **XmlWhitespace** ノードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="7bb7d-103">When loading the document, you can set the option to preserve white space and create **XmlWhitespace** nodes in the document tree.</span></span> <span data-ttu-id="7bb7d-104">空白ノードを作成するには、**PreserveWhitespace** プロパティを true に設定します。</span><span class="sxs-lookup"><span data-stu-id="7bb7d-104">To create white space nodes, set the **PreserveWhitespace** property to true.</span></span> <span data-ttu-id="7bb7d-105">このプロパティが既定の **false** に設定されている場合、空白ノードは作成されません。</span><span class="sxs-lookup"><span data-stu-id="7bb7d-105">If the property is set to **false**, which is the default, white space nodes are not created.</span></span> <span data-ttu-id="7bb7d-106">**PreserveWhitespace** フラグの設定に関係なく、有意の空白ノードは常に保持され、そのデータを表す **XmlSignificantWhitespace** ノードが常にメモリ内に作成されます。</span><span class="sxs-lookup"><span data-stu-id="7bb7d-106">Significant white spaces nodes are always preserved, and **XmlSignificantWhitespace** nodes are always created in memory to represent this data, regardless of the setting of the **PreserveWhitespace** flag.</span></span>  
  
 <span data-ttu-id="7bb7d-107">ドキュメントがリーダーから読み込まれた場合は、**XmlTextReader** の **WhitespaceHandling** プロパティが **WhitespaceHandling.None** に設定されていない場合にのみ、**XmlDocument** クラスの **PreserveWhitespace** フラグ プロパティの設定が **XmlWhitespace** ノードの作成に影響を及ぼします。</span><span class="sxs-lookup"><span data-stu-id="7bb7d-107">If the document is loaded from a reader, then setting of the **PreserveWhitespace** flag property on the **XmlDocument** class affects the creation of **XmlWhitespace** nodes only when the **WhitespaceHandling** property on the **XmlTextReader** is not set to **WhitespaceHandling.None**.</span></span> <span data-ttu-id="7bb7d-108">リーダーの **WhitespaceHandling** プロパティの値の方が **XmlDocument** のこのフラグの設定より優先されます。</span><span class="sxs-lookup"><span data-stu-id="7bb7d-108">It is the value of the **WhitespaceHandling** property on the reader that takes precedence over the setting of that flag on the **XmlDocument**.</span></span> <span data-ttu-id="7bb7d-109">**XmlSignificantWhitespace** の詳細については、「<xref:System.Xml.XmlSignificantWhitespace>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bb7d-109">For more information on **XmlSignificantWhitespace**, see <xref:System.Xml.XmlSignificantWhitespace>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bb7d-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="7bb7d-110">See also</span></span>

- [<span data-ttu-id="7bb7d-111">XML ドキュメント オブジェクト モデル (DOM)</span><span class="sxs-lookup"><span data-stu-id="7bb7d-111">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
