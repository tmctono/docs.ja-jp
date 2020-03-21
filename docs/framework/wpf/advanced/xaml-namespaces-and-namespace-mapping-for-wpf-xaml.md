---
title: XAML 名前空間と名前空間マッピング
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
ms.openlocfilehash: 9b01643e8f8d77073595253580ebea60fabfd23b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186234"
---
# <a name="xaml-namespaces-and-namespace-mapping-for-wpf-xaml"></a><span data-ttu-id="2974b-102">XAML 名前空間および WPF XAML の名前空間の割り当て</span><span class="sxs-lookup"><span data-stu-id="2974b-102">XAML Namespaces and Namespace Mapping for WPF XAML</span></span>
<span data-ttu-id="2974b-103">このトピックでは、WPF XAML ファイルのルート タグでよく見られる 2 つの XAML 名前空間マッピングの存在と目的についてさらに説明します。</span><span class="sxs-lookup"><span data-stu-id="2974b-103">This topic further explains the presence and purpose of the two XAML namespace mappings as often found in the root tag of a WPF XAML file.</span></span> <span data-ttu-id="2974b-104">また、独自のコードで定義された要素や、個別のアセンブリ内で定義されている要素を使用するための同様のマッピングを生成する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="2974b-104">It also describes how to produce similar mappings for using elements that are defined in your own code, and/or within separate assemblies.</span></span>  

## <a name="what-is-a-xaml-namespace"></a><span data-ttu-id="2974b-105">XAML 名前空間とは何ですか?</span><span class="sxs-lookup"><span data-stu-id="2974b-105">What is a XAML Namespace?</span></span>  
 <span data-ttu-id="2974b-106">XAML 名前空間は、XML 名前空間の概念の拡張です。</span><span class="sxs-lookup"><span data-stu-id="2974b-106">A XAML namespace is really an extension of the concept of an XML namespace.</span></span> <span data-ttu-id="2974b-107">XAML 名前空間を指定する手法は、XML 名前空間構文、名前空間識別子として URI を使用する規則、プレフィックスを使用して、同じマークアップ ソースから複数の名前空間を参照する手段などを使用します。</span><span class="sxs-lookup"><span data-stu-id="2974b-107">The techniques of specifying a XAML namespace rely on the XML namespace syntax, the convention of using URIs as namespace identifiers, using prefixes to provide a means to reference multiple namespaces from the same markup source, and so on.</span></span> <span data-ttu-id="2974b-108">XML 名前空間の XAML 定義に追加される主な概念は、XAML 名前空間はマークアップの使用に対して一意性のスコープを意味し、マークアップ エンティティが特定の CLR 名前空間によって潜在的にサポートされ、参照される方法に影響を与えるということです。アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="2974b-108">The primary concept that is added to the XAML definition of the XML namespace is that a XAML namespace implies both a scope of uniqueness for the markup usages, and also influences how markup entities are potentially backed by specific CLR namespaces and referenced assemblies.</span></span> <span data-ttu-id="2974b-109">この後者の考慮事項は、XAML スキーマ コンテキストの概念によっても影響されます。</span><span class="sxs-lookup"><span data-stu-id="2974b-109">This latter consideration is also influenced by the concept of a XAML schema context.</span></span> <span data-ttu-id="2974b-110">しかし、WPF が XAML 名前空間を使用する方法を目的として、XAML 名前空間は、通常、既定の XAML 名前空間、XAML 言語名前空間、および XAML マークアップによって特定のバッキング CLR に直接マップされた XAML 名前空間を考えることができます。名前空間と参照アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="2974b-110">But for purposes of how WPF works with XAML namespaces, you can generally think of XAML namespaces in terms of a default XAML namespace, the XAML language namespace, and any further XAML namespaces as mapped by your XAML markup directly to specific backing CLR namespaces and referenced assemblies.</span></span>  
  
<a name="The_WPF_and_XAML_Namespace_Declarations"></a>
## <a name="the-wpf-and-xaml-namespace-declarations"></a><span data-ttu-id="2974b-111">WPF 名前空間宣言と XAML 名前空間宣言</span><span class="sxs-lookup"><span data-stu-id="2974b-111">The WPF and XAML Namespace Declarations</span></span>  
 <span data-ttu-id="2974b-112">多くの XAML ファイルのルート タグ内の名前空間宣言内では、通常 2 つの XML 名前空間宣言があることがわかります。</span><span class="sxs-lookup"><span data-stu-id="2974b-112">Within the namespace declarations in the root tag of many XAML files, you will see that there are typically two XML namespace declarations.</span></span> <span data-ttu-id="2974b-113">最初の宣言では、WPF クライアント /フレームワーク XAML 名前空間全体が既定としてマップされます。</span><span class="sxs-lookup"><span data-stu-id="2974b-113">The first declaration maps the overall WPF client / framework XAML namespace as the default:</span></span>  
  
 `xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"`  
  
 <span data-ttu-id="2974b-114">2 番目の宣言は、個別の XAML 名前空間をマップし`x:`、(通常は) プレフィックスに対応付けます。</span><span class="sxs-lookup"><span data-stu-id="2974b-114">The second declaration maps a separate XAML namespace, mapping it (typically) to the `x:` prefix.</span></span>  
  
 `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`  
  
 <span data-ttu-id="2974b-115">これらの宣言間の関係は、`x:`プレフィックス マッピングが XAML 言語定義の一部である組み込み関数[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]をサポートし、XAML を言語として使用し、XAML のオブジェクトのボキャブラリを定義する 1 つの実装です。</span><span class="sxs-lookup"><span data-stu-id="2974b-115">The relationship between these declarations is that the `x:` prefix mapping supports the intrinsics that are part of the XAML language definition, and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] is one implementation that uses XAML as a language and defines a vocabulary of its objects for XAML.</span></span> <span data-ttu-id="2974b-116">WPF ボキャブラリの使用法は XAML 組み込み関数の使用法よりもはるかに一般的であるため、WPF ボキャブラリは既定としてマップされます。</span><span class="sxs-lookup"><span data-stu-id="2974b-116">Because the WPF vocabulary's usages will be far more common than the XAML intrinsics usages, the WPF vocabulary is mapped as the default.</span></span>  
  
 <span data-ttu-id="2974b-117">XAML`x:`言語組み込みサポートをマッピングするためのプレフィックス規則の後には、プロジェクト テンプレート、サンプル コード、およびこの SDK 内の言語機能のドキュメントが続きます。</span><span class="sxs-lookup"><span data-stu-id="2974b-117">The `x:` prefix convention for mapping the XAML language intrinsics support is followed by project templates, sample code, and the documentation of language features within this SDK.</span></span> <span data-ttu-id="2974b-118">XAML 名前空間は、基本的な WPF アプリケーションにも必要な、一般的に使用される多くの機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="2974b-118">The XAML namespace defines many commonly-used features that are necessary even for basic WPF  applications.</span></span> <span data-ttu-id="2974b-119">たとえば、部分クラスを通じて分離コードを XAML ファイルに結合するには、関連する XAML ファイルのルート要素`x:Class`の属性としてそのクラスに名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="2974b-119">For instance, in order to join any code-behind to a XAML file through a partial class, you must name that class as the `x:Class` attribute in the root element of the relevant XAML file.</span></span> <span data-ttu-id="2974b-120">または、キー付きリソースとしてアクセスする XAML ページで定義されている要素には、対象の`x:Key`要素に属性が設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2974b-120">Or, any element as defined in a XAML page that you wish to access as a keyed resource should have the `x:Key` attribute set on the element in question.</span></span> <span data-ttu-id="2974b-121">XAML のこれらの側面と他の側面の詳細については、「 [XAML の概要 (WPF)](../../../desktop-wpf/fundamentals/xaml.md)または[XAML 構文の詳細](xaml-syntax-in-detail.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2974b-121">For more information on these and other aspects of XAML see [XAML Overview (WPF)](../../../desktop-wpf/fundamentals/xaml.md) or [XAML Syntax In Detail](xaml-syntax-in-detail.md).</span></span>  
  
<a name="Mapping_To_Custom_Classes_and_Assemblies"></a>
## <a name="mapping-to-custom-classes-and-assemblies"></a><span data-ttu-id="2974b-122">カスタム クラスおよびカスタム アセンブリへのマッピング</span><span class="sxs-lookup"><span data-stu-id="2974b-122">Mapping to Custom Classes and Assemblies</span></span>  
 <span data-ttu-id="2974b-123">標準 WPF および XAML 組み込み XAML 名前空間`xmlns`がプレフィックスにマップされるのと同様に、プレフィックス宣言内の一連のトークンを使用して、XML 名前空間をアセンブリにマップできます。</span><span class="sxs-lookup"><span data-stu-id="2974b-123">You can map XML namespaces to assemblies using a series of tokens within an `xmlns` prefix declaration, similar to how the standard WPF and XAML-intrinsics XAML namespaces are mapped to prefixes.</span></span>  
  
 <span data-ttu-id="2974b-124">構文には、次の名前付きトークンと次の値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2974b-124">The syntax takes the following possible named tokens and following values:</span></span>  
  
 <span data-ttu-id="2974b-125">`clr-namespace:`要素として公開するパブリック型を含むアセンブリ内で宣言された CLR 名前空間。</span><span class="sxs-lookup"><span data-stu-id="2974b-125">`clr-namespace:` The CLR namespace declared within the assembly that contains the public types to expose as elements.</span></span>  
  
 <span data-ttu-id="2974b-126">`assembly=`参照先 CLR 名前空間の一部またはすべてを含むアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="2974b-126">`assembly=` The assembly that contains some or all of the referenced CLR namespace.</span></span> <span data-ttu-id="2974b-127">この値は、通常、パスではなく、アセンブリの名前に過ぎず、拡張子 (.dll や .exe など) は含まれません。</span><span class="sxs-lookup"><span data-stu-id="2974b-127">This value is typically just the name of the assembly, not the path, and does not include the extension (such as .dll or .exe).</span></span> <span data-ttu-id="2974b-128">そのアセンブリへのパスは、マップする XAML を含むプロジェクト ファイル内のプロジェクト参照として確立する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2974b-128">The path to that assembly must be established as a project reference in the project file that contains the XAML you are trying to map.</span></span> <span data-ttu-id="2974b-129">バージョニングと厳密な名前の署名を組み込`assembly`むために、値は単純な文字列名<xref:System.Reflection.AssemblyName>ではなく、 で定義された文字列にすることができます。</span><span class="sxs-lookup"><span data-stu-id="2974b-129">In order to incorporate versioning and strong-name signing, the `assembly` value can be a string as defined by <xref:System.Reflection.AssemblyName>, rather than the simple string name.</span></span>  
  
 <span data-ttu-id="2974b-130">トークンとその値を`clr-namespace`区切る文字はコロン (:)一方、トークンとその値`assembly`を区切る文字は等号 (=) です。</span><span class="sxs-lookup"><span data-stu-id="2974b-130">Note that the character separating the `clr-namespace` token from its value is a colon (:) whereas the character separating the `assembly` token from its value is an equals sign (=).</span></span> <span data-ttu-id="2974b-131">これらの 2 つのトークンの間で使用する文字はセミコロンです。</span><span class="sxs-lookup"><span data-stu-id="2974b-131">The character to use between these two tokens is a semicolon.</span></span> <span data-ttu-id="2974b-132">また、宣言のどこにも空白を含まないでください。</span><span class="sxs-lookup"><span data-stu-id="2974b-132">Also, do not include any white space anywhere in the declaration.</span></span>  
  
### <a name="a-basic-custom-mapping-example"></a><span data-ttu-id="2974b-133">基本的なカスタム マッピングの例</span><span class="sxs-lookup"><span data-stu-id="2974b-133">A Basic Custom Mapping Example</span></span>  
 <span data-ttu-id="2974b-134">次のコードは、カスタム クラスの例を定義しています。</span><span class="sxs-lookup"><span data-stu-id="2974b-134">The following code defines an example custom class:</span></span>  
  
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
  
 <span data-ttu-id="2974b-135">このカスタム クラスはライブラリにコンパイルされ、プロジェクト設定 (図示せず) に従って`SDKSampleLibrary`という名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="2974b-135">This custom class is then compiled into a library, which per the project settings (not shown) is named `SDKSampleLibrary`.</span></span>  
  
 <span data-ttu-id="2974b-136">このカスタム クラスを参照するには、Visual Studio のソリューション エクスプローラー UI を使用する、現在のプロジェクトの参照としてこのクラスを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="2974b-136">In order to reference this custom class, you also need to include it as a reference for your current project, which you would typically do using the Solution Explorer UI in Visual Studio.</span></span>  
  
 <span data-ttu-id="2974b-137">クラスを含むライブラリとプロジェクト設定での参照ができたので、XAML のルート要素の一部として次のプレフィックス マッピングを追加できます。</span><span class="sxs-lookup"><span data-stu-id="2974b-137">Now that you have a library containing a class, and a reference to it in project settings, you can add the following prefix mapping as part of your root element in XAML:</span></span>  
  
 `xmlns:custom="clr-namespace:SDKSample;assembly=SDKSampleLibrary"`  
  
 <span data-ttu-id="2974b-138">すべてをまとめると、ルート タグの一般的な既定と x: マッピングと共にカスタム マッピングを含む XAML を次`ExampleClass`に示します。</span><span class="sxs-lookup"><span data-stu-id="2974b-138">To put it all together, the following is XAML that includes the custom mapping along with the typical default and x: mappings in the root tag, then uses a prefixed reference to instantiate `ExampleClass` in that UI:</span></span>  
  
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
  
### <a name="mapping-to-current-assemblies"></a><span data-ttu-id="2974b-139">現在のアセンブリへのマッピング</span><span class="sxs-lookup"><span data-stu-id="2974b-139">Mapping to Current Assemblies</span></span>  
 <span data-ttu-id="2974b-140">`assembly`参照先がカスタム クラス`clr-namespace`を参照しているアプリケーション コードと同じアセンブリ内で定義されている場合は省略できます。</span><span class="sxs-lookup"><span data-stu-id="2974b-140">`assembly` can be omitted if the `clr-namespace` referenced is being defined within the same assembly as the application code that is referencing the custom classes.</span></span> <span data-ttu-id="2974b-141">または、等号の後に文字列トークンを指定`assembly=`しない、 この場合の同等の構文を指定します。</span><span class="sxs-lookup"><span data-stu-id="2974b-141">Or, an equivalent syntax for this case is to specify `assembly=`, with no string token following the equals sign.</span></span>  
  
 <span data-ttu-id="2974b-142">同じアセンブリで定義されている場合、カスタム クラスをページのルート要素として使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="2974b-142">Custom classes cannot be used as the root element of a page if defined in the same assembly.</span></span> <span data-ttu-id="2974b-143">部分クラスをマップする必要はありません。XAML の要素として参照する場合は、アプリケーションのページの部分クラスではないクラスのみをマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2974b-143">Partial classes do not need to be mapped; only classes that are not the partial class of a page in your application need to be mapped if you intend to reference them as elements in XAML.</span></span>  
  
<a name="Mapping_CLR_Namespaces_to_XML_Namespaces_in_an"></a>
## <a name="mapping-clr-namespaces-to-xml-namespaces-in-an-assembly"></a><span data-ttu-id="2974b-144">CLR 名前空間をアセンブリ内の XML 名前空間にマップする</span><span class="sxs-lookup"><span data-stu-id="2974b-144">Mapping CLR Namespaces to XML Namespaces in an Assembly</span></span>  
 <span data-ttu-id="2974b-145">WPF では、複数の CLR 名前空間を 1 つの XAML 名前空間にマップするために、XAML プロセッサによって使用される CLR 属性を定義します。</span><span class="sxs-lookup"><span data-stu-id="2974b-145">WPF defines a CLR attribute that is consumed by XAML processors in order to map multiple CLR namespaces to a single XAML namespace.</span></span> <span data-ttu-id="2974b-146">この属性は<xref:System.Windows.Markup.XmlnsDefinitionAttribute>、アセンブリを生成するソース コードのアセンブリ レベルに配置されます。</span><span class="sxs-lookup"><span data-stu-id="2974b-146">This attribute, <xref:System.Windows.Markup.XmlnsDefinitionAttribute>, is placed at the assembly level in the source code that produces the assembly.</span></span> <span data-ttu-id="2974b-147">WPF アセンブリ ソース コードでは、この属性を使用して、 や<xref:System.Windows><xref:System.Windows.Controls>などのさまざまな一般的`http://schemas.microsoft.com/winfx/2006/xaml/presentation`な名前空間を名前空間にマップします。</span><span class="sxs-lookup"><span data-stu-id="2974b-147">The WPF assembly source code uses this attribute to map the various common namespaces, such as <xref:System.Windows> and <xref:System.Windows.Controls>, to the `http://schemas.microsoft.com/winfx/2006/xaml/presentation` namespace.</span></span>  
  
 <span data-ttu-id="2974b-148">には<xref:System.Windows.Markup.XmlnsDefinitionAttribute>、XML/XAML 名前空間名と CLR 名前空間名の 2 つのパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="2974b-148">The <xref:System.Windows.Markup.XmlnsDefinitionAttribute> takes two parameters: the XML/XAML namespace name, and the CLR namespace name.</span></span> <span data-ttu-id="2974b-149">複数の<xref:System.Windows.Markup.XmlnsDefinitionAttribute>CLR 名前空間を同じ XML 名前空間にマップするために複数存在できます。</span><span class="sxs-lookup"><span data-stu-id="2974b-149">More than one <xref:System.Windows.Markup.XmlnsDefinitionAttribute> can exist to map multiple CLR namespaces to the same XML namespace.</span></span> <span data-ttu-id="2974b-150">いったんマップされた名前空間のメンバーは、部分クラスの分離コード ページに適切な`using`ステートメントを提供することで、必要に応じて完全な修飾なしで参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="2974b-150">Once mapped, members of those namespaces can also be referenced without full qualification if desired by providing the appropriate `using` statement in the partial-class code-behind page.</span></span> <span data-ttu-id="2974b-151">詳細については、「<xref:System.Windows.Markup.XmlnsDefinitionAttribute>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2974b-151">For more details, see <xref:System.Windows.Markup.XmlnsDefinitionAttribute>.</span></span>  
  
## <a name="designer-namespaces-and-other-prefixes-from-xaml-templates"></a><span data-ttu-id="2974b-152">XAML テンプレートからのデザイナー名前空間とその他のプレフィックス</span><span class="sxs-lookup"><span data-stu-id="2974b-152">Designer Namespaces and Other Prefixes From XAML Templates</span></span>  
 <span data-ttu-id="2974b-153">WPF XAML の開発環境やデザイン ツールを使用している場合は、XAML マークアップ内に他の定義済みの XAML 名前空間やプレフィックスがあることに気付く場合があります。</span><span class="sxs-lookup"><span data-stu-id="2974b-153">If you are working with development environments and/or design tools for WPF XAML, you may notice that there are other defined XAML namespaces / prefixes within the XAML markup.</span></span>  
  
 <span data-ttu-id="2974b-154">Visual Studio の WPF デザイナーでは、通常はプレフィックス`d:`にマップされるデザイナー名前空間を使用します。</span><span class="sxs-lookup"><span data-stu-id="2974b-154">WPF Designer for Visual Studio uses a designer namespace that is typically mapped to the prefix `d:`.</span></span> <span data-ttu-id="2974b-155">WPF の最近のプロジェクト テンプレートでは、この XAML 名前空間を事前にマップして、Visual Studio 用 WPF デザイナーと他のデザイン環境との間で XAML の交換をサポートする場合があります。</span><span class="sxs-lookup"><span data-stu-id="2974b-155">More recent project templates for WPF might pre-map this XAML namespace to support interchange of the XAML between WPF Designer for Visual Studio and other design environments.</span></span> <span data-ttu-id="2974b-156">このデザイン XAML 名前空間は、デザイナーで XAML ベースの UI をラウンドしながらデザイン状態を永続化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2974b-156">This design XAML namespace is used to perpetuate design state while roundtripping XAML-based UI in the designer.</span></span> <span data-ttu-id="2974b-157">また、デザイナーでランタイム データ`d:IsDataSource`ソースを有効にする などの機能にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="2974b-157">It is also used for features such as `d:IsDataSource`, which enable runtime data sources in a designer.</span></span>  
  
 <span data-ttu-id="2974b-158">マップされたもう 1 つのプレフィックス`mc:`は です。</span><span class="sxs-lookup"><span data-stu-id="2974b-158">Another prefix you might see mapped is `mc:`.</span></span> <span data-ttu-id="2974b-159">`mc:`はマークアップの互換性を保つために使用され、必ずしも XAML 固有ではないマークアップ互換性パターンを利用しています。</span><span class="sxs-lookup"><span data-stu-id="2974b-159">`mc:` is for markup compatibility, and is leveraging a markup compatibility pattern that is not necessarily XAML-specific.</span></span> <span data-ttu-id="2974b-160">ある程度、マークアップ互換性機能を使用して、フレームワーク間またはバッキング実装の他の境界を越えて XAML を交換したり、XAML スキーマ コンテキスト間での作業、デザイナーのモードが制限されている場合に互換性を提供したりできます。</span><span class="sxs-lookup"><span data-stu-id="2974b-160">To some extent, the markup compatibility features can be used to exchange XAML between frameworks or across other boundaries of backing implementation, work between XAML schema contexts, provide compatibility for limited modes in designers, and so on.</span></span> <span data-ttu-id="2974b-161">マークアップ互換性の概念と、それらが WPF とどのように関連しているかについて詳しくは、[マークアップ互換性 (mc:) を参照してください。言語機能](markup-compatibility-mc-language-features.md):</span><span class="sxs-lookup"><span data-stu-id="2974b-161">For more information on markup compatibility concepts and how they relate to WPF, see  [Markup Compatibility (mc:) Language Features](markup-compatibility-mc-language-features.md).</span></span>  
  
## <a name="wpf-and-assembly-loading"></a><span data-ttu-id="2974b-162">WPF とアセンブリの読み込み</span><span class="sxs-lookup"><span data-stu-id="2974b-162">WPF and Assembly Loading</span></span>  
 <span data-ttu-id="2974b-163">WPF の XAML スキーマ コンテキストは、WPF アプリケーション モデルと統合され、CLR で定義<xref:System.AppDomain>された概念の を使用します。</span><span class="sxs-lookup"><span data-stu-id="2974b-163">The XAML schema context for WPF integrates with the WPF application model, which in turn uses the CLR-defined concept of <xref:System.AppDomain>.</span></span> <span data-ttu-id="2974b-164">次のシーケンスでは、実行時またはデザイン時に、WPF の使用やその他の要因に基づいて、XAML スキーマ コンテキストがどのようにしてアセンブリを読<xref:System.AppDomain>み込むか、またはデザイン時に型を検索するかを解釈する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2974b-164">The following sequence describes how XAML schema context interprets how to either load assemblies or find types at run time or design time, based on the WPF use of <xref:System.AppDomain> and other factors.</span></span>  
  
1. <span data-ttu-id="2974b-165"><xref:System.AppDomain>を反復処理して、最後に読み込まれたアセンブリから始めて、名前のすべての側面に一致する既に読み込まれたアセンブリを探します。</span><span class="sxs-lookup"><span data-stu-id="2974b-165">Iterate through the <xref:System.AppDomain>, looking for an already-loaded assembly that matches all aspects of the name, starting from the most recently loaded assembly.</span></span>  
  
2. <span data-ttu-id="2974b-166">名前が修飾されている場合は、<xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>修飾名を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2974b-166">If the name is qualified, call <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> on the qualified name.</span></span>  
  
3. <span data-ttu-id="2974b-167">修飾名の短縮名 + 公開キー トークンが、マークアップの読み込み元のアセンブリと一致する場合は、そのアセンブリを返します。</span><span class="sxs-lookup"><span data-stu-id="2974b-167">If the short name + public key token of a qualified name matches the assembly that the markup was loaded from, return that assembly.</span></span>  
  
4. <span data-ttu-id="2974b-168">短縮名 + 公開鍵トークンを使用<xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>して を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2974b-168">Use the short name + public key token to call <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>.</span></span>  
  
5. <span data-ttu-id="2974b-169">名前が修飾されていない場合は、<xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2974b-169">If the name is unqualified, call <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="2974b-170">ルーズ XAML では手順 3 は使用されません。読み込みからアセンブリがありません。</span><span class="sxs-lookup"><span data-stu-id="2974b-170">Loose XAML does not use Step 3; there is no loaded-from assembly.</span></span>  
  
 <span data-ttu-id="2974b-171">WPF 用にコンパイルされた XAML (XamlBuildTask を使用して生成) は<xref:System.AppDomain>、既に読み込まれているアセンブリを使用しません (手順 1)。</span><span class="sxs-lookup"><span data-stu-id="2974b-171">Compiled XAML for WPF (generated via XamlBuildTask) does not use the already-loaded assemblies from <xref:System.AppDomain> (Step 1).</span></span> <span data-ttu-id="2974b-172">また、名前は XamlBuildTask 出力から修飾されないようにする必要があるため、手順 5 は適用されません。</span><span class="sxs-lookup"><span data-stu-id="2974b-172">Also, the name should never be unqualified from XamlBuildTask output, so Step 5 does not apply.</span></span>  
  
 <span data-ttu-id="2974b-173">コンパイルされた BAML (プレゼンテーションビルドタスクを介して生成された) はすべての手順を使用しますが、BAML には非修飾のアセンブリ名も含めるべきではありません。</span><span class="sxs-lookup"><span data-stu-id="2974b-173">Compiled BAML (generated via PresentationBuildTask) uses all steps, although BAML also should not contain unqualified assembly names.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2974b-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="2974b-174">See also</span></span>

- <span data-ttu-id="2974b-175">[XML 名前空間について](https://docs.microsoft.com/previous-versions/aa468565(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="2974b-175">[Understanding XML Namespaces](https://docs.microsoft.com/previous-versions/aa468565(v=msdn.10))</span></span>
- [<span data-ttu-id="2974b-176">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="2974b-176">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
