---
title: XAML 名前空間および WPF XAML の名前空間の割り当て
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom classes [WPF], mapping namespaces to
- XAML [WPF], namespaces
- namespace mapping [WPF]
- assemblies [WPF], mapping namespaces to
- mapping namespaces [WPF]
- XAML [WPF], namespace mapping
- classes [WPF], mapping namespaces to
- namespaces [WPF]
ms.assetid: 5c0854e3-7470-435d-9fe2-93eec9d3634e
ms.openlocfilehash: c238bd3c014c07c541bed0c8f7bc12fc5a910f1b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59301036"
---
# <a name="xaml-namespaces-and-namespace-mapping-for-wpf-xaml"></a><span data-ttu-id="ec34d-102">XAML 名前空間および WPF XAML の名前空間の割り当て</span><span class="sxs-lookup"><span data-stu-id="ec34d-102">XAML Namespaces and Namespace Mapping for WPF XAML</span></span>
<span data-ttu-id="ec34d-103">さらに、このトピックでは、プレゼンスと WPF XAML ファイルのルート タグによく見られる 2 つの XAML 名前空間マッピングの目的について説明します。</span><span class="sxs-lookup"><span data-stu-id="ec34d-103">This topic further explains the presence and purpose of the two XAML namespace mappings as often found in the root tag of a WPF XAML file.</span></span> <span data-ttu-id="ec34d-104">また、独自のコードで、または個別のアセンブリ内に定義されている要素を使用するためのようなマッピングを生成する方法も説明します。</span><span class="sxs-lookup"><span data-stu-id="ec34d-104">It also describes how to produce similar mappings for using elements that are defined in your own code, and/or within separate assemblies.</span></span>  

## <a name="what-is-a-xaml-namespace"></a><span data-ttu-id="ec34d-105">XAML Namespace とは何ですか。</span><span class="sxs-lookup"><span data-stu-id="ec34d-105">What is a XAML Namespace?</span></span>  
 <span data-ttu-id="ec34d-106">XAML 名前空間は、実際には、XML 名前空間の概念の拡張です。</span><span class="sxs-lookup"><span data-stu-id="ec34d-106">A XAML namespace is really an extension of the concept of an XML namespace.</span></span> <span data-ttu-id="ec34d-107">XAML 名前空間を指定するための手法では、XML 名前空間の構文、Uri を使用して、同じマークアップ ソースから複数の名前空間を参照するための手段を提供するプレフィックスを使用して、名前空間の識別子としての規則に依存しにします。</span><span class="sxs-lookup"><span data-stu-id="ec34d-107">The techniques of specifying a XAML namespace rely on the XML namespace syntax, the convention of using URIs as namespace identifiers, using prefixes to provide a means to reference multiple namespaces from the same markup source, and so on.</span></span> <span data-ttu-id="ec34d-108">XML 名前空間の XAML 定義に追加される主要な概念は XAML 名前空間が両方の一意性のスコープ マークアップの使用を意味し、マークアップのエンティティが可能性のある特定の CLR 名前空間に支えし、参照されている方法にも影響を与えますアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="ec34d-108">The primary concept that is added to the XAML definition of the XML namespace is that a XAML namespace implies both a scope of uniqueness for the markup usages, and also influences how markup entities are potentially backed by specific CLR namespaces and referenced assemblies.</span></span> <span data-ttu-id="ec34d-109">後者の考慮事項は、XAML スキーマ コンテキストの概念の影響も受けます。</span><span class="sxs-lookup"><span data-stu-id="ec34d-109">This latter consideration is also influenced by the concept of a XAML schema context.</span></span> <span data-ttu-id="ec34d-110">WPF の XAML 名前空間を持つ動作方法のために、考えることができます一般に、既定の XAML 名前空間、言語の XAML 名前空間、およびさらに XAML 名前空間によって、XAML マークアップは、特定のバッキング CLR を直接マップされるよう面での XAML 名前空間が、名前空間と参照アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="ec34d-110">But for purposes of how WPF works with XAML namespaces, you can generally think of XAML namespaces in terms of a default XAML namespace, the XAML language namespace, and any further XAML namespaces as mapped by your XAML markup directly to specific backing CLR namespaces and referenced assemblies.</span></span>  
  
<a name="The_WPF_and_XAML_Namespace_Declarations"></a>   
## <a name="the-wpf-and-xaml-namespace-declarations"></a><span data-ttu-id="ec34d-111">WPF と XAML Namespace 宣言</span><span class="sxs-lookup"><span data-stu-id="ec34d-111">The WPF and XAML Namespace Declarations</span></span>  
 <span data-ttu-id="ec34d-112">多くの XAML ファイルのルート タグにある名前空間宣言内では、2 つの XML 名前空間宣言は通常、参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec34d-112">Within the namespace declarations in the root tag of many XAML files, you will see that there are typically two XML namespace declarations.</span></span> <span data-ttu-id="ec34d-113">最初の宣言のマップ全体の WPF クライアント/フレームワーク、既定値としての XAML 名前空間。</span><span class="sxs-lookup"><span data-stu-id="ec34d-113">The first declaration maps the overall WPF client / framework XAML namespace as the default:</span></span>  
  
 `xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"`  
  
 <span data-ttu-id="ec34d-114">2 番目の宣言にマップされます (通常は) にマップすること、別の XAML 名前空間、`x:`プレフィックス。</span><span class="sxs-lookup"><span data-stu-id="ec34d-114">The second declaration maps a separate XAML namespace, mapping it (typically) to the `x:` prefix.</span></span>  
  
 `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`  
  
 <span data-ttu-id="ec34d-115">これらの宣言の間のリレーションシップは、`x:`プレフィックスのマッピングは、組み込み XAML 言語の定義の一部であるをサポートしていると[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]言語として XAML を使用しのボキャブラリの定義を 1 つの実装は、そのXAML のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ec34d-115">The relationship between these declarations is that the `x:` prefix mapping supports the intrinsics that are part of the XAML language definition, and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] is one implementation that uses XAML as a language and defines a vocabulary of its objects for XAML.</span></span> <span data-ttu-id="ec34d-116">WPF の語彙の使用は XAML の組み込みの使用よりもはるかに一般的になる、ために、WPF ボキャブラリは、既定値としてマップされます。</span><span class="sxs-lookup"><span data-stu-id="ec34d-116">Because the WPF vocabulary's usages will be far more common than the XAML intrinsics usages, the WPF vocabulary is mapped as the default.</span></span>  
  
 <span data-ttu-id="ec34d-117">`x:`プレフィックス規則、プロジェクト テンプレートの後に、XAML 言語の組み込みサポートをマッピングのサンプル コード、および言語のドキュメントがこの機能[!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="ec34d-117">The `x:` prefix convention for mapping the XAML language intrinsics support is followed by project templates, sample code, and the documentation of language features within this [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)].</span></span> <span data-ttu-id="ec34d-118">XAML 名前空間は、基本的な WPF アプリケーションにも必要なは一般的に使用される多くの機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="ec34d-118">The XAML namespace defines many commonly-used features that are necessary even for basic WPF  applications.</span></span> <span data-ttu-id="ec34d-119">たとえば、部分クラスを XAML ファイルに分離コードを結合するには名前を付けてとしてそのクラス、`x:Class`関連する XAML ファイルのルート要素の属性。</span><span class="sxs-lookup"><span data-stu-id="ec34d-119">For instance, in order to join any code-behind to a XAML file through a partial class, you must name that class as the `x:Class` attribute in the root element of the relevant XAML file.</span></span> <span data-ttu-id="ec34d-120">または、任意の要素へのアクセス キーを持つリソースが必要とする XAML ページで定義されている、`x:Key`属性が「問題の要素に設定します。</span><span class="sxs-lookup"><span data-stu-id="ec34d-120">Or, any element as defined in a XAML page that you wish to access as a keyed resource should have the `x:Key` attribute set on the element in question.</span></span> <span data-ttu-id="ec34d-121">これらやその他のさまざまな XAML の詳細については、次を参照してください。 [XAML の概要 (WPF)](xaml-overview-wpf.md)または[XAML 構文の詳細](xaml-syntax-in-detail.md)します。</span><span class="sxs-lookup"><span data-stu-id="ec34d-121">For more information on these and other aspects of XAML see [XAML Overview (WPF)](xaml-overview-wpf.md) or [XAML Syntax In Detail](xaml-syntax-in-detail.md).</span></span>  
  
<a name="Mapping_To_Custom_Classes_and_Assemblies"></a>   
## <a name="mapping-to-custom-classes-and-assemblies"></a><span data-ttu-id="ec34d-122">カスタム クラスとアセンブリへのマッピング</span><span class="sxs-lookup"><span data-stu-id="ec34d-122">Mapping to Custom Classes and Assemblies</span></span>  
 <span data-ttu-id="ec34d-123">XML 名前空間をマップするには、一連の内のトークンを使用してアセンブリを`xmlns`プレフィックスの宣言では、標準的な WPF および XAML 組み込み XAML 名前空間をプレフィックスにマップする方法に似ています。</span><span class="sxs-lookup"><span data-stu-id="ec34d-123">You can map XML namespaces to assemblies using a series of tokens within an `xmlns` prefix declaration, similar to how the standard WPF and XAML-intrinsics XAML namespaces are mapped to prefixes.</span></span>  
  
 <span data-ttu-id="ec34d-124">構文には、次の考えられる名前付きのトークンと次の値の場合:</span><span class="sxs-lookup"><span data-stu-id="ec34d-124">The syntax takes the following possible named tokens and following values:</span></span>  
  
 <span data-ttu-id="ec34d-125">`clr-namespace:` CLR 名前空間は、要素として公開するパブリック型を含むアセンブリ内で宣言します。</span><span class="sxs-lookup"><span data-stu-id="ec34d-125">`clr-namespace:` The CLR namespace declared within the assembly that contains the public types to expose as elements.</span></span>  
  
 <span data-ttu-id="ec34d-126">`assembly=` 参照先の一部またはすべてを含むアセンブリ[!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]名前空間。</span><span class="sxs-lookup"><span data-stu-id="ec34d-126">`assembly=` The assembly that contains some or all of the referenced [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] namespace.</span></span> <span data-ttu-id="ec34d-127">この値は、パスではなく、アセンブリの名前だけでは、通常、(.dll または .exe) などの拡張機能は含まれません。</span><span class="sxs-lookup"><span data-stu-id="ec34d-127">This value is typically just the name of the assembly, not the path, and does not include the extension (such as .dll or .exe).</span></span> <span data-ttu-id="ec34d-128">マップしようとして XAML を含むプロジェクト ファイル内のプロジェクト参照としては、そのアセンブリへのパスを確立する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec34d-128">The path to that assembly must be established as a project reference in the project file that contains the XAML you are trying to map.</span></span> <span data-ttu-id="ec34d-129">バージョン管理と厳密な名前の署名を反映するために、`assembly`で定義されている値が文字列を指定できる<xref:System.Reflection.AssemblyName>、単純な文字列名ではなく。</span><span class="sxs-lookup"><span data-stu-id="ec34d-129">In order to incorporate versioning and strong-name signing, the `assembly` value can be a string as defined by <xref:System.Reflection.AssemblyName>, rather than the simple string name.</span></span>  
  
 <span data-ttu-id="ec34d-130">区切る文字に注意してください、`clr-namespace`値からトークンがありますが、コロン (:) 文字の分離、`assembly`トークンその値からは、等号 (=)。</span><span class="sxs-lookup"><span data-stu-id="ec34d-130">Note that the character separating the `clr-namespace` token from its value is a colon (:) whereas the character separating the `assembly` token from its value is an equals sign (=).</span></span> <span data-ttu-id="ec34d-131">これら 2 つのトークンの間で使用する文字は、セミコロンです。</span><span class="sxs-lookup"><span data-stu-id="ec34d-131">The character to use between these two tokens is a semicolon.</span></span> <span data-ttu-id="ec34d-132">また、任意の空白任意の場所に含めない宣言。</span><span class="sxs-lookup"><span data-stu-id="ec34d-132">Also, do not include any white space anywhere in the declaration.</span></span>  
  
### <a name="a-basic-custom-mapping-example"></a><span data-ttu-id="ec34d-133">基本的なカスタム マッピング例</span><span class="sxs-lookup"><span data-stu-id="ec34d-133">A Basic Custom Mapping Example</span></span>  
 <span data-ttu-id="ec34d-134">次のコードでは、サンプルのカスタム クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="ec34d-134">The following code defines an example custom class:</span></span>  
  
```csharp  
namespace SDKSample {  
    public class ExampleClass : ContentControl {  
        public ExampleClass() {  
        ...  
        }  
    }  
}  
```  
  
```vb  
Namespace SDKSample  
    Public Class ExampleClass  
        Inherits ContentControl  
         ...  
        Public Sub New()  
        End Sub  
    End Class  
End Namespace  
```  
  
 <span data-ttu-id="ec34d-135">このカスタム クラスは、プロジェクトの設定 (非表示) と呼ばれるライブラリにコンパイルし、`SDKSampleLibrary`します。</span><span class="sxs-lookup"><span data-stu-id="ec34d-135">This custom class is then compiled into a library, which per the project settings (not shown) is named `SDKSampleLibrary`.</span></span>  
  
 <span data-ttu-id="ec34d-136">このカスタム クラスを参照するためにも含める必要があることは、現在のプロジェクトへの参照として Visual Studio のソリューション エクスプ ローラーの UI を使用します。</span><span class="sxs-lookup"><span data-stu-id="ec34d-136">In order to reference this custom class, you also need to include it as a reference for your current project, which you would typically do using the Solution Explorer UI in Visual Studio.</span></span>  
  
 <span data-ttu-id="ec34d-137">クラス、およびへの参照をプロジェクト設定を含むライブラリがある場合は、できた XAML ルート要素の一部として、次のプレフィックス マッピングを追加できます。</span><span class="sxs-lookup"><span data-stu-id="ec34d-137">Now that you have a library containing a class, and a reference to it in project settings, you can add the following prefix mapping as part of your root element in XAML:</span></span>  
  
 `xmlns:custom="clr-namespace:SDKSample;assembly=SDKSampleLibrary"`  
  
 <span data-ttu-id="ec34d-138">次にルート タグに代表的な既定とカスタム マッピングと x: マッピングが含まれていますし、プレフィックス付きの参照を使用して、インスタンス化する XAML をまとめて配置する`ExampleClass`その UI で。</span><span class="sxs-lookup"><span data-stu-id="ec34d-138">To put it all together, the following is XAML that includes the custom mapping along with the typical default and x: mappings in the root tag, then uses a prefixed reference to instantiate `ExampleClass` in that UI:</span></span>  
  
```xaml  
<Page x:Class="WPFApplication1.MainPage"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"   
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:custom="clr-namespace:SDKSample;assembly=SDKSampleLibrary">  
  ...  
  <custom:ExampleClass/>  
...  
</Page>  
```  
  
### <a name="mapping-to-current-assemblies"></a><span data-ttu-id="ec34d-139">現在のアセンブリへのマッピング</span><span class="sxs-lookup"><span data-stu-id="ec34d-139">Mapping to Current Assemblies</span></span>  
 <span data-ttu-id="ec34d-140">`assembly` 場合は省略可能、`clr-namespace`参照されているカスタム クラスを参照しているアプリケーション コードと同じアセンブリ内で定義されています。</span><span class="sxs-lookup"><span data-stu-id="ec34d-140">`assembly` can be omitted if the `clr-namespace` referenced is being defined within the same assembly as the application code that is referencing the custom classes.</span></span> <span data-ttu-id="ec34d-141">この場合の同等の構文は、指定することです。 または、 `assembly=`、なし文字列トークンを、等号の後にします。</span><span class="sxs-lookup"><span data-stu-id="ec34d-141">Or, an equivalent syntax for this case is to specify `assembly=`, with no string token following the equals sign.</span></span>  
  
 <span data-ttu-id="ec34d-142">カスタム クラスは、同じアセンブリで定義されている場合は、ページのルート要素として使用できません。</span><span class="sxs-lookup"><span data-stu-id="ec34d-142">Custom classes cannot be used as the root element of a page if defined in the same assembly.</span></span> <span data-ttu-id="ec34d-143">部分クラスが割り当てる必要はありません。アプリケーションが必要となる XAML で要素として参照する場合にマップするページの部分クラスではないクラスのみです。</span><span class="sxs-lookup"><span data-stu-id="ec34d-143">Partial classes do not need to be mapped; only classes that are not the partial class of a page in your application need to be mapped if you intend to reference them as elements in XAML.</span></span>  
  
<a name="Mapping_CLR_Namespaces_to_XML_Namespaces_in_an"></a>   
## <a name="mapping-clr-namespaces-to-xml-namespaces-in-an-assembly"></a><span data-ttu-id="ec34d-144">アセンブリ内の XML 名前空間への CLR 名前空間のマッピング</span><span class="sxs-lookup"><span data-stu-id="ec34d-144">Mapping CLR Namespaces to XML Namespaces in an Assembly</span></span>  
 <span data-ttu-id="ec34d-145">WPF では、複数の CLR 名前空間を単一の XAML 名前空間にマップするために、XAML プロセッサによって使用される CLR 属性を定義します。</span><span class="sxs-lookup"><span data-stu-id="ec34d-145">WPF defines a CLR attribute that is consumed by XAML processors in order to map multiple CLR namespaces to a single XAML namespace.</span></span> <span data-ttu-id="ec34d-146">この属性は、<xref:System.Windows.Markup.XmlnsDefinitionAttribute>アセンブリを生成するソース コードにアセンブリ レベルで配置されます。</span><span class="sxs-lookup"><span data-stu-id="ec34d-146">This attribute, <xref:System.Windows.Markup.XmlnsDefinitionAttribute>, is placed at the assembly level in the source code that produces the assembly.</span></span> <span data-ttu-id="ec34d-147">WPF アセンブリのソース コードでは、この属性を使用するなど、さまざまな一般的な名前空間をマップ<xref:System.Windows>と<xref:System.Windows.Controls>を[!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)]名前空間。</span><span class="sxs-lookup"><span data-stu-id="ec34d-147">The WPF assembly source code uses this attribute to map the various common namespaces, such as <xref:System.Windows> and <xref:System.Windows.Controls>, to the [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)] namespace.</span></span>  
  
 <span data-ttu-id="ec34d-148"><xref:System.Windows.Markup.XmlnsDefinitionAttribute>は 2 つのパラメーターを受け取ります。 XML と XAML 名前空間の名前と CLR 名前空間の名前。</span><span class="sxs-lookup"><span data-stu-id="ec34d-148">The <xref:System.Windows.Markup.XmlnsDefinitionAttribute> takes two parameters: the XML/XAML namespace name, and the CLR namespace name.</span></span> <span data-ttu-id="ec34d-149">1 つ以上<xref:System.Windows.Markup.XmlnsDefinitionAttribute>同じ XML 名前空間に複数の CLR 名前空間にマップする存在できます。</span><span class="sxs-lookup"><span data-stu-id="ec34d-149">More than one <xref:System.Windows.Markup.XmlnsDefinitionAttribute> can exist to map multiple CLR namespaces to the same XML namespace.</span></span> <span data-ttu-id="ec34d-150">マップされると、それらの名前空間のメンバーもせずに参照できる完全に修飾、適切な提供することで必要な場合は`using`部分クラスの分離コード ページ内のステートメント。</span><span class="sxs-lookup"><span data-stu-id="ec34d-150">Once mapped, members of those namespaces can also be referenced without full qualification if desired by providing the appropriate `using` statement in the partial-class code-behind page.</span></span> <span data-ttu-id="ec34d-151">詳細については、「<xref:System.Windows.Markup.XmlnsDefinitionAttribute>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec34d-151">For more details, see <xref:System.Windows.Markup.XmlnsDefinitionAttribute>.</span></span>  
  
## <a name="designer-namespaces-and-other-prefixes-from-xaml-templates"></a><span data-ttu-id="ec34d-152">デザイナーの名前空間と XAML テンプレートから他のプレフィックス</span><span class="sxs-lookup"><span data-stu-id="ec34d-152">Designer Namespaces and Other Prefixes From XAML Templates</span></span>  
 <span data-ttu-id="ec34d-153">WPF XAML の開発環境やデザイン ツールで操作している場合、他の定義済みの XAML 名前空間があることを確認する]、[XAML マークアップ内のプレフィックスします。</span><span class="sxs-lookup"><span data-stu-id="ec34d-153">If you are working with development environments and/or design tools for WPF XAML, you may notice that there are other defined XAML namespaces / prefixes within the XAML markup.</span></span>  
  
 [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] <span data-ttu-id="ec34d-154">通常、プレフィックスにマップされるデザイナー名前空間を使用して`d:`します。</span><span class="sxs-lookup"><span data-stu-id="ec34d-154">uses a designer namespace that is typically mapped to the prefix `d:`.</span></span> <span data-ttu-id="ec34d-155">WPF の最近のプロジェクト テンプレートは、XAML との間の交換をサポートするためにこの XAML 名前空間をマップ事前可能性があります[!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)]や他のデザイン環境。</span><span class="sxs-lookup"><span data-stu-id="ec34d-155">More recent project templates for WPF might pre-map this XAML namespace to support interchange of the XAML between [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] and other design environments.</span></span> <span data-ttu-id="ec34d-156">このデザインの XAML 名前空間は、デザイナーで XAML ベースの UI をラウンドト リップのときにデザイン状態を永続化に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ec34d-156">This design XAML namespace is used to perpetuate design state while roundtripping XAML-based UI in the designer.</span></span> <span data-ttu-id="ec34d-157">などの機能を使用するがも、`d:IsDataSource`デザイナーでの実行時データ ソースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ec34d-157">It is also used for features such as `d:IsDataSource`, which enable runtime data sources in a designer.</span></span>  
  
 <span data-ttu-id="ec34d-158">マップされている別のプレフィックス「可能性がありますが`mc:`します。</span><span class="sxs-lookup"><span data-stu-id="ec34d-158">Another prefix you might see mapped is `mc:`.</span></span> <span data-ttu-id="ec34d-159">`mc:` マークアップの互換性、必ずしも XAML に固有でないマークアップ互換性パターンを活用することです。</span><span class="sxs-lookup"><span data-stu-id="ec34d-159">`mc:` is for markup compatibility, and is leveraging a markup compatibility pattern that is not necessarily XAML-specific.</span></span> <span data-ttu-id="ec34d-160">ある程度はマークアップの互換性機能は、フレームワーク間または他の境界のバッキング実装の間で XAML を交換するために使用できます XAML スキーマ コンテキスト間での作業、デザイナーでは、制限付きのモードの互換性を提供および具合です。</span><span class="sxs-lookup"><span data-stu-id="ec34d-160">To some extent, the markup compatibility features can be used to exchange XAML between frameworks or across other boundaries of backing implementation, work between XAML schema contexts, provide compatibility for limited modes in designers, and so on.</span></span> <span data-ttu-id="ec34d-161">マークアップの互換性の概念とどのように関連する WPF の詳細については、次を参照してください[マークアップの互換性 (mc:)。言語機能](markup-compatibility-mc-language-features.md)します。</span><span class="sxs-lookup"><span data-stu-id="ec34d-161">For more information on markup compatibility concepts and how they relate to WPF, see  [Markup Compatibility (mc:) Language Features](markup-compatibility-mc-language-features.md).</span></span>  
  
## <a name="wpf-and-assembly-loading"></a><span data-ttu-id="ec34d-162">WPF およびアセンブリの読み込み</span><span class="sxs-lookup"><span data-stu-id="ec34d-162">WPF and Assembly Loading</span></span>  
 <span data-ttu-id="ec34d-163">WPF の XAML スキーマ コンテキストと統合の CLR で定義された概念を使用して、WPF アプリケーション モデル、<xref:System.AppDomain>します。</span><span class="sxs-lookup"><span data-stu-id="ec34d-163">The XAML schema context for WPF integrates with the WPF application model, which in turn uses the CLR-defined concept of <xref:System.AppDomain>.</span></span> <span data-ttu-id="ec34d-164">次の順序は、XAML スキーマ コンテキストでアセンブリを読み込むかの WPF の使用状況に基づいて実行時またはデザイン時に、型を検索する方法を解釈する方法について説明します<xref:System.AppDomain>およびその他の要因です。</span><span class="sxs-lookup"><span data-stu-id="ec34d-164">The following sequence describes how XAML schema context interprets how to either load assemblies or find types at run time or design time, based on the WPF use of <xref:System.AppDomain> and other factors.</span></span>  
  
1. <span data-ttu-id="ec34d-165">反復処理、<xref:System.AppDomain>名前のすべての側面に一致する読み込み済みアセンブリを探して、読み込まれたアセンブリを最近開始します。</span><span class="sxs-lookup"><span data-stu-id="ec34d-165">Iterate through the <xref:System.AppDomain>, looking for an already-loaded assembly that matches all aspects of the name, starting from the most recently loaded assembly.</span></span>  
  
2. <span data-ttu-id="ec34d-166">名前が修飾されている場合に呼び出す<xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>修飾名にします。</span><span class="sxs-lookup"><span data-stu-id="ec34d-166">If the name is qualified, call <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> on the qualified name.</span></span>  
  
3. <span data-ttu-id="ec34d-167">短い名前と修飾名の公開キー トークンは、マークアップから読み込まれたアセンブリに一致すると、そのアセンブリを返します。</span><span class="sxs-lookup"><span data-stu-id="ec34d-167">If the short name + public key token of a qualified name matches the assembly that the markup was loaded from, return that assembly.</span></span>  
  
4. <span data-ttu-id="ec34d-168">短い名前と公開キー トークンを使用して呼び出す<xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="ec34d-168">Use the short name + public key token to call <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>.</span></span>  
  
5. <span data-ttu-id="ec34d-169">名前が修飾されていない場合は、呼び出す<xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="ec34d-169">If the name is unqualified, call <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="ec34d-170">Loose XAML は、手順 3; を使用しません読み込まれたアセンブリがありません。</span><span class="sxs-lookup"><span data-stu-id="ec34d-170">Loose XAML does not use Step 3; there is no loaded-from assembly.</span></span>  
  
 <span data-ttu-id="ec34d-171">WPF (XamlBuildTask 経由で生成された) にコンパイルされた XAML がから既に読み込まれたアセンブリを使用しない<xref:System.AppDomain>(ステップ 1)。</span><span class="sxs-lookup"><span data-stu-id="ec34d-171">Compiled XAML for WPF (generated via XamlBuildTask) does not use the already-loaded assemblies from <xref:System.AppDomain> (Step 1).</span></span> <span data-ttu-id="ec34d-172">また、名前べきでは、XamlBuildTask 出力から不適切なため、手順 5 が適用されません。</span><span class="sxs-lookup"><span data-stu-id="ec34d-172">Also, the name should never be unqualified from XamlBuildTask output, so Step 5 does not apply.</span></span>  
  
 <span data-ttu-id="ec34d-173">BAML にはもする必要がありますが含まれていない非修飾アセンブリ名が、コンパイル済みの BAML (PresentationBuildTask を使用して生成) は、すべての手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="ec34d-173">Compiled BAML (generated via PresentationBuildTask) uses all steps, although BAML also should not contain unqualified assembly names.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec34d-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="ec34d-174">See also</span></span>

- [<span data-ttu-id="ec34d-175">XML 名前空間を理解します。</span><span class="sxs-lookup"><span data-stu-id="ec34d-175">Understanding XML Namespaces</span></span>](https://go.microsoft.com/fwlink/?LinkId=98069)
- [<span data-ttu-id="ec34d-176">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="ec34d-176">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
