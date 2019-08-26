---
title: msxsl:node-set() 関数のサポート
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: d0cbf517-d9f6-4097-9851-4fa62903decd
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3670803ff20351fd9ff6892a0cef48b9caa70199
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939518"
---
# <a name="support-for-the-msxslnode-set-function"></a><span data-ttu-id="27955-102">msxsl:node-set() 関数のサポート</span><span class="sxs-lookup"><span data-stu-id="27955-102">Support for the msxsl:node-set() Function</span></span>
<span data-ttu-id="27955-103">`msxsl:node-set` 関数を使用すると、結果ツリー フラグメントをノード セットに変換できます。</span><span class="sxs-lookup"><span data-stu-id="27955-103">The `msxsl:node-set` function enables you to convert a result tree fragment into a node set.</span></span> <span data-ttu-id="27955-104">結果として得られるノード セットには、常に単一のノードが含まれています。また、このノード セットは、常にそのツリーのルート ノードです。</span><span class="sxs-lookup"><span data-stu-id="27955-104">The resulting node set always contains a single node and is the root node of the tree.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="27955-105">.NET Framework 2.0 では <xref:System.Xml.Xsl.XslTransform> クラスが廃止されています。</span><span class="sxs-lookup"><span data-stu-id="27955-105">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="27955-106"><xref:System.Xml.Xsl.XslCompiledTransform> クラスを使用して XSLT (Extensible Stylesheet Language for Transformations) 変換を実行できます。</span><span class="sxs-lookup"><span data-stu-id="27955-106">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="27955-107">詳しくは、「[XslCompiledTransform クラスの使用](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)」および「[XslTransform クラスからの移行](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="27955-107">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="27955-108">`msxsl:node-set` 関数を使用すると、結果ツリー フラグメントをノード セットに変換できます。</span><span class="sxs-lookup"><span data-stu-id="27955-108">The `msxsl:node-set` function enables you to convert a result tree fragment into a node set.</span></span> <span data-ttu-id="27955-109">結果として得られるノード セットには、常に単一のノードが含まれています。また、このノード セットは、常にそのツリーのルート ノードです。</span><span class="sxs-lookup"><span data-stu-id="27955-109">The resulting node set always contains a single node and is the root node of the tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27955-110">例</span><span class="sxs-lookup"><span data-stu-id="27955-110">Example</span></span>  
 <span data-ttu-id="27955-111">`$var` という変数がスタイル シート内のノード ツリーである例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="27955-111">In the following example, `$var` is a variable that is a node tree in the style sheet.</span></span> <span data-ttu-id="27955-112">for-each ステートメントを `node-set` 関数と組み合わせて使用すれば、このノード ツリーをノード セットとして反復処理できます。</span><span class="sxs-lookup"><span data-stu-id="27955-112">The for-each statement combined with the `node-set` function allows the user to iterate over this node tree as a node set.</span></span>  
  
## <a name="nodesetxsl"></a><span data-ttu-id="27955-113">nodeset.xsl</span><span class="sxs-lookup"><span data-stu-id="27955-113">nodeset.xsl</span></span>  
  
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
  
## <a name="output"></a><span data-ttu-id="27955-114">Output</span><span class="sxs-lookup"><span data-stu-id="27955-114">Output</span></span>  
 <span data-ttu-id="27955-115">変換による出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="27955-115">The output of the transformation is</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<authors><author>Michael Howard</author><author>Michael Kay</author></authors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="27955-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="27955-116">See also</span></span>

- [<span data-ttu-id="27955-117">XslTransform クラスによる XSLT プロセッサの実装</span><span class="sxs-lookup"><span data-stu-id="27955-117">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
