---
title: msxsl:node-set() 関数のサポート
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: d0cbf517-d9f6-4097-9851-4fa62903decd
ms.openlocfilehash: 5022b298cb20796edbc54e951d8b06043697d832
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "78155595"
---
# <a name="support-for-the-msxslnode-set-function"></a><span data-ttu-id="9581f-102">msxsl:node-set() 関数のサポート</span><span class="sxs-lookup"><span data-stu-id="9581f-102">Support for the msxsl:node-set() Function</span></span>
<span data-ttu-id="9581f-103">`msxsl:node-set` 関数を使用すると、結果ツリー フラグメントをノード セットに変換できます。</span><span class="sxs-lookup"><span data-stu-id="9581f-103">The `msxsl:node-set` function enables you to convert a result tree fragment into a node set.</span></span> <span data-ttu-id="9581f-104">結果として得られるノード セットには、常に単一のノードが含まれています。また、このノード セットは、常にそのツリーのルート ノードです。</span><span class="sxs-lookup"><span data-stu-id="9581f-104">The resulting node set always contains a single node and is the root node of the tree.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9581f-105">.NET Framework 2.0 では <xref:System.Xml.Xsl.XslTransform> クラスが廃止されています。</span><span class="sxs-lookup"><span data-stu-id="9581f-105">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="9581f-106"><xref:System.Xml.Xsl.XslCompiledTransform> クラスを使用して XSLT (Extensible Stylesheet Language for Transformations) 変換を実行できます。</span><span class="sxs-lookup"><span data-stu-id="9581f-106">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="9581f-107">詳細については、「[XslCompiledTransform クラスの使用](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)」と「[XslTransform クラスからの移行](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9581f-107">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="9581f-108">`msxsl:node-set` 関数を使用すると、結果ツリー フラグメントをノード セットに変換できます。</span><span class="sxs-lookup"><span data-stu-id="9581f-108">The `msxsl:node-set` function enables you to convert a result tree fragment into a node set.</span></span> <span data-ttu-id="9581f-109">結果として得られるノード セットには、常に単一のノードが含まれています。また、このノード セットは、常にそのツリーのルート ノードです。</span><span class="sxs-lookup"><span data-stu-id="9581f-109">The resulting node set always contains a single node and is the root node of the tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9581f-110">例</span><span class="sxs-lookup"><span data-stu-id="9581f-110">Example</span></span>  
 <span data-ttu-id="9581f-111">`$var` という変数がスタイル シート内のノード ツリーである例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9581f-111">In the following example, `$var` is a variable that is a node tree in the style sheet.</span></span> <span data-ttu-id="9581f-112">for-each ステートメントを `node-set` 関数と組み合わせて使用すれば、このノード ツリーをノード セットとして反復処理できます。</span><span class="sxs-lookup"><span data-stu-id="9581f-112">The for-each statement combined with the `node-set` function allows the user to iterate over this node tree as a node set.</span></span>  
  
## <a name="nodesetxsl"></a><span data-ttu-id="9581f-113">nodeset.xsl</span><span class="sxs-lookup"><span data-stu-id="9581f-113">nodeset.xsl</span></span>  
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
                xmlns:msxsl="urn:schemas-microsoft-com:xslt"  
                xmlns:user="http://www.contoso.com"  
                version="1.0">  
    <xsl:variable name="books">  
        <book author="Michael Howard">Writing Secure Code</book>  
        <book author="Michael Kay">XSLT Reference</book>  
    </xsl:variable>  
  
    <xsl:template match="/">  
        <authors>  
            <xsl:for-each select="msxsl:node-set($books)/book">
                <author><xsl:value-of select="@author"/></author>  
            </xsl:for-each>  
        </authors>  
    </xsl:template>  
</xsl:stylesheet>  
```  
  
## <a name="output"></a><span data-ttu-id="9581f-114">Output</span><span class="sxs-lookup"><span data-stu-id="9581f-114">Output</span></span>  
 <span data-ttu-id="9581f-115">変換による出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9581f-115">The output of the transformation is</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<authors><author>Michael Howard</author><author>Michael Kay</author></authors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9581f-116">参照</span><span class="sxs-lookup"><span data-stu-id="9581f-116">See also</span></span>

- [<span data-ttu-id="9581f-117">XslTransform クラスによる XSLT プロセッサの実装</span><span class="sxs-lookup"><span data-stu-id="9581f-117">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
