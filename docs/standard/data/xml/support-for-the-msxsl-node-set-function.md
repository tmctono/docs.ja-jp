---
title: msxsl:node-set() 関数のサポート
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: d0cbf517-d9f6-4097-9851-4fa62903decd
ms.openlocfilehash: 30652d8cbaac333cc1cb35954742b16dc7c4764b
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071990"
---
# <a name="support-for-the-msxslnode-set-function"></a><span data-ttu-id="be06b-102">msxsl:node-set() 関数のサポート</span><span class="sxs-lookup"><span data-stu-id="be06b-102">Support for the msxsl:node-set() Function</span></span>
<span data-ttu-id="be06b-103">`msxsl:node-set` 関数を使用すると、結果ツリー フラグメントをノード セットに変換できます。</span><span class="sxs-lookup"><span data-stu-id="be06b-103">The `msxsl:node-set` function enables you to convert a result tree fragment into a node set.</span></span> <span data-ttu-id="be06b-104">結果として得られるノード セットには、常に単一のノードが含まれています。また、このノード セットは、常にそのツリーのルート ノードです。</span><span class="sxs-lookup"><span data-stu-id="be06b-104">The resulting node set always contains a single node and is the root node of the tree.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="be06b-105">.NET Framework 2.0 では <xref:System.Xml.Xsl.XslTransform> クラスが廃止されています。</span><span class="sxs-lookup"><span data-stu-id="be06b-105">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="be06b-106"><xref:System.Xml.Xsl.XslCompiledTransform> クラスを使用して XSLT (Extensible Stylesheet Language for Transformations) 変換を実行できます。</span><span class="sxs-lookup"><span data-stu-id="be06b-106">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="be06b-107">詳しくは、「[XslCompiledTransform クラスの使用](using-the-xslcompiledtransform-class.md)」および「[XslTransform クラスからの移行](migrating-from-the-xsltransform-class.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="be06b-107">See [Using the XslCompiledTransform Class](using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="be06b-108">`msxsl:node-set` 関数を使用すると、結果ツリー フラグメントをノード セットに変換できます。</span><span class="sxs-lookup"><span data-stu-id="be06b-108">The `msxsl:node-set` function enables you to convert a result tree fragment into a node set.</span></span> <span data-ttu-id="be06b-109">結果として得られるノード セットには、常に単一のノードが含まれています。また、このノード セットは、常にそのツリーのルート ノードです。</span><span class="sxs-lookup"><span data-stu-id="be06b-109">The resulting node set always contains a single node and is the root node of the tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be06b-110">例</span><span class="sxs-lookup"><span data-stu-id="be06b-110">Example</span></span>  
 <span data-ttu-id="be06b-111">`$books` という変数がスタイル シート内のノード ツリーである例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="be06b-111">In the following example, `$books` is a variable that is a node tree in the style sheet.</span></span> <span data-ttu-id="be06b-112">for-each ステートメントを `node-set` 関数と組み合わせて使用すれば、このノード ツリーをノード セットとして反復処理できます。</span><span class="sxs-lookup"><span data-stu-id="be06b-112">The for-each statement combined with the `node-set` function allows the user to iterate over this node tree as a node set.</span></span>  
  
## <a name="nodesetxsl"></a><span data-ttu-id="be06b-113">nodeset.xsl</span><span class="sxs-lookup"><span data-stu-id="be06b-113">nodeset.xsl</span></span>  
  
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
  
## <a name="output"></a><span data-ttu-id="be06b-114">Output</span><span class="sxs-lookup"><span data-stu-id="be06b-114">Output</span></span>  
 <span data-ttu-id="be06b-115">変換による出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="be06b-115">The output of the transformation is</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<authors><author>Michael Howard</author><author>Michael Kay</author></authors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="be06b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="be06b-116">See also</span></span>

- [<span data-ttu-id="be06b-117">XslTransform クラスによる XSLT プロセッサの実装</span><span class="sxs-lookup"><span data-stu-id="be06b-117">XslTransform Class Implements the XSLT Processor</span></span>](xsltransform-class-implements-the-xslt-processor.md)
