---
title: XslCompiledTransform クラスの使用
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: f9b074f6-d6f4-49dd-a093-df510bf0cf7b
ms.openlocfilehash: b9d14a79347610abcd2f770488acb53218ce3e46
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556773"
---
# <a name="using-the-xslcompiledtransform-class"></a><span data-ttu-id="1f103-102">XslCompiledTransform クラスの使用</span><span class="sxs-lookup"><span data-stu-id="1f103-102">Using the XslCompiledTransform Class</span></span>
<span data-ttu-id="1f103-103"><xref:System.Xml.Xsl.XslCompiledTransform> クラスは Microsoft .NET Framework XSLT プロセッサです。</span><span class="sxs-lookup"><span data-stu-id="1f103-103">The <xref:System.Xml.Xsl.XslCompiledTransform> class is the Microsoft .NET Framework XSLT processor.</span></span> <span data-ttu-id="1f103-104">このクラスは、スタイル シートをコンパイルし、XSLT 変換を実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1f103-104">This class is used to compile style sheets and execute XSLT transformations.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1f103-105">全体的なパフォーマンスは <xref:System.Xml.Xsl.XslCompiledTransform> クラスの方が <xref:System.Xml.Xsl.XslTransform> クラスより優れていますが、<xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> クラスの <xref:System.Xml.Xsl.XslCompiledTransform> メソッドが変換で初めて呼び出されたときは、<xref:System.Xml.Xsl.XslTransform.Load%2A> クラスの <xref:System.Xml.Xsl.XslTransform> メソッドよりパフォーマンスが劣る場合があります。</span><span class="sxs-lookup"><span data-stu-id="1f103-105">Although the overall performance of the <xref:System.Xml.Xsl.XslCompiledTransform> class is better than the <xref:System.Xml.Xsl.XslTransform> class, the <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> method of the <xref:System.Xml.Xsl.XslCompiledTransform> class might perform more slowly than the <xref:System.Xml.Xsl.XslTransform.Load%2A> method of the <xref:System.Xml.Xsl.XslTransform> class the first time it is called on a transformation.</span></span> <span data-ttu-id="1f103-106">これは、XSLT ファイルを読み込む前にコンパイルする必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="1f103-106">This is because the XSLT file must be compiled before it is loaded.</span></span> <span data-ttu-id="1f103-107">詳細については、ブログ記事「[XslCompiledTransform Slower than XslTransform?](/archive/blogs/antosha/xslcompiledtransform-slower-than-xsltransform)」(XslCompiledTransform は XslTransform よりも遅いか?) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f103-107">For more information, see the following blog post: [XslCompiledTransform Slower than XslTransform?](/archive/blogs/antosha/xslcompiledtransform-slower-than-xsltransform)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1f103-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1f103-108">In This Section</span></span>  
 [<span data-ttu-id="1f103-109">XslCompiledTransform クラスへの入力</span><span class="sxs-lookup"><span data-stu-id="1f103-109">Inputs to the XslCompiledTransform Class</span></span>](inputs-to-the-xslcompiledtransform-class.md)  
 <span data-ttu-id="1f103-110">使用可能な XSLT 入力オプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1f103-110">Describes the available XSLT input options.</span></span>  
  
 [<span data-ttu-id="1f103-111">XslCompiledTransform クラスの出力オプション</span><span class="sxs-lookup"><span data-stu-id="1f103-111">Output Options on the XslCompiledTransform Class</span></span>](output-options-on-the-xslcompiledtransform-class.md)  
 <span data-ttu-id="1f103-112">使用可能な XSLT 出力オプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1f103-112">Describes the available XSLT output options.</span></span>  
  
 [<span data-ttu-id="1f103-113">XSLT 処理中の外部リソースの解決</span><span class="sxs-lookup"><span data-stu-id="1f103-113">Resolving External Resources During XSLT Processing</span></span>](resolving-external-resources-during-xslt-processing.md)  
 <span data-ttu-id="1f103-114">外部リソースを解決するための <xref:System.Xml.XmlResolver> クラスの使用について説明します。</span><span class="sxs-lookup"><span data-stu-id="1f103-114">Discusses using the <xref:System.Xml.XmlResolver> class to resolve external resources.</span></span>  
  
 [<span data-ttu-id="1f103-115">XSLT スタイル シートの拡張</span><span class="sxs-lookup"><span data-stu-id="1f103-115">Extending XSLT Style Sheets</span></span>](extending-xslt-style-sheets.md)  
 <span data-ttu-id="1f103-116">XSLT の拡張機能のサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1f103-116">Discusses how XSLT extensions are supported.</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="1f103-117">XSLT エラーの解決</span><span class="sxs-lookup"><span data-stu-id="1f103-117">Recoverable XSLT Errors</span></span>](recoverable-xslt-errors.md)|<span data-ttu-id="1f103-118">W3C (World Wide Web Consortium) 勧告『XSLT 1.0』で許可されている随意動作を示し、<xref:System.Xml.Xsl.XslCompiledTransform> クラスによるこれらの動作の処理方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="1f103-118">Lists discretionary behaviors allowed by the World Wide Web Consortium (W3C) XSLT 1.0 recommendation and describes how these behaviors are handled by the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>|  
|[<span data-ttu-id="1f103-119">方法: ノード フラグメントを変換する</span><span class="sxs-lookup"><span data-stu-id="1f103-119">How to: Transform a Node Fragment</span></span>](how-to-transform-a-node-fragment.md)|<span data-ttu-id="1f103-120">ノード フラグメントの変換方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="1f103-120">Describes how to transform a node fragment.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="1f103-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f103-121">Related Sections</span></span>  
 [<span data-ttu-id="1f103-122">XslTransform クラスからの移行</span><span class="sxs-lookup"><span data-stu-id="1f103-122">Migrating From the XslTransform Class</span></span>](migrating-from-the-xsltransform-class.md)  
 <span data-ttu-id="1f103-123"><xref:System.Xml.Xsl.XslTransform> クラスからコードを移行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1f103-123">Discusses how to migrate code from the <xref:System.Xml.Xsl.XslTransform> class</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f103-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f103-124">See also</span></span>

- <xref:System.Xml.Xsl.XsltSettings>
- <xref:System.Xml.Xsl.XsltMessageEncounteredEventArgs>
