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
ms.openlocfilehash: 4fc88f1e32b8ddce6abccad085b0c44a5c716e8b
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2019
ms.locfileid: "68400806"
---
# <a name="xaml-namespaces-and-namespace-mapping-for-wpf-xaml"></a><span data-ttu-id="3f5d4-102">XAML 名前空間および WPF XAML の名前空間の割り当て</span><span class="sxs-lookup"><span data-stu-id="3f5d4-102">XAML Namespaces and Namespace Mapping for WPF XAML</span></span>
<span data-ttu-id="3f5d4-103">このトピックでは、WPF XAML ファイルのルートタグでよく見られる2つの XAML 名前空間マッピングの存在と目的について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-103">This topic further explains the presence and purpose of the two XAML namespace mappings as often found in the root tag of a WPF XAML file.</span></span> <span data-ttu-id="3f5d4-104">また、独自のコードで定義されている要素、または別のアセンブリ内に定義されている要素を使用するために、同様のマッピングを生成する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-104">It also describes how to produce similar mappings for using elements that are defined in your own code, and/or within separate assemblies.</span></span>  

## <a name="what-is-a-xaml-namespace"></a><span data-ttu-id="3f5d4-105">XAML 名前空間とは何ですか。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-105">What is a XAML Namespace?</span></span>  
 <span data-ttu-id="3f5d4-106">XAML 名前空間は、実際には XML 名前空間の概念を拡張したものです。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-106">A XAML namespace is really an extension of the concept of an XML namespace.</span></span> <span data-ttu-id="3f5d4-107">XAML 名前空間を指定する方法は、XML 名前空間の構文、Uri を名前空間の識別子として使用する規則、同じマークアップソースから複数の名前空間を参照する手段を提供するプレフィックスを使用する方法などに依存します。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-107">The techniques of specifying a XAML namespace rely on the XML namespace syntax, the convention of using URIs as namespace identifiers, using prefixes to provide a means to reference multiple namespaces from the same markup source, and so on.</span></span> <span data-ttu-id="3f5d4-108">XML 名前空間の XAML 定義に追加される主な概念は、XAML 名前空間がマークアップ使用の一意性の範囲を示すことです。また、特定の CLR 名前空間および参照によってマークアップエンティティがどのようにサポートされるかにも影響します。アセンブリ.</span><span class="sxs-lookup"><span data-stu-id="3f5d4-108">The primary concept that is added to the XAML definition of the XML namespace is that a XAML namespace implies both a scope of uniqueness for the markup usages, and also influences how markup entities are potentially backed by specific CLR namespaces and referenced assemblies.</span></span> <span data-ttu-id="3f5d4-109">この2つ目の考慮事項は、XAML スキーマコンテキストの概念にも影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-109">This latter consideration is also influenced by the concept of a XAML schema context.</span></span> <span data-ttu-id="3f5d4-110">ただし、WPF で XAML 名前空間を使用する方法については、一般に、xaml 名前空間、xaml 言語の名前空間、および XAML マークアップによって特定のバッキング CLR に直接マップされる xaml 名前空間に関して、xaml 名前空間について考えることができます。名前空間と参照されるアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-110">But for purposes of how WPF works with XAML namespaces, you can generally think of XAML namespaces in terms of a default XAML namespace, the XAML language namespace, and any further XAML namespaces as mapped by your XAML markup directly to specific backing CLR namespaces and referenced assemblies.</span></span>  
  
<a name="The_WPF_and_XAML_Namespace_Declarations"></a>   
## <a name="the-wpf-and-xaml-namespace-declarations"></a><span data-ttu-id="3f5d4-111">WPF および XAML 名前空間の宣言</span><span class="sxs-lookup"><span data-stu-id="3f5d4-111">The WPF and XAML Namespace Declarations</span></span>  
 <span data-ttu-id="3f5d4-112">多くの XAML ファイルのルートタグ内の名前空間宣言内では、通常、2つの XML 名前空間宣言があることがわかります。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-112">Within the namespace declarations in the root tag of many XAML files, you will see that there are typically two XML namespace declarations.</span></span> <span data-ttu-id="3f5d4-113">最初の宣言は、WPF クライアント/フレームワークの全体的な XAML 名前空間を既定値としてマップします。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-113">The first declaration maps the overall WPF client / framework XAML namespace as the default:</span></span>  
  
 `xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"`  
  
 <span data-ttu-id="3f5d4-114">2番目の宣言は、別の XAML 名前空間をマップし、 `x:`これを (通常は) プレフィックスに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-114">The second declaration maps a separate XAML namespace, mapping it (typically) to the `x:` prefix.</span></span>  
  
 `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`  
  
 <span data-ttu-id="3f5d4-115">これらの宣言の間の関係は`x:` 、プレフィックスマッピングが xaml 言語定義の一部である組み込みをサポートする[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ことです。また、xaml を言語として使用する1つの実装で、XAML のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-115">The relationship between these declarations is that the `x:` prefix mapping supports the intrinsics that are part of the XAML language definition, and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] is one implementation that uses XAML as a language and defines a vocabulary of its objects for XAML.</span></span> <span data-ttu-id="3f5d4-116">WPF のボキャブラリの使用は XAML 組み込みの使用法よりはるかに一般的であるため、WPF のボキャブラリは既定値としてマップされます。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-116">Because the WPF vocabulary's usages will be far more common than the XAML intrinsics usages, the WPF vocabulary is mapped as the default.</span></span>  
  
 <span data-ttu-id="3f5d4-117">XAML 言語の組み込みサポートをマップするための[!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)]プレフィックス規則には、プロジェクトテンプレート、サンプルコード、およびこの内の言語機能のドキュメントが続きます。`x:`</span><span class="sxs-lookup"><span data-stu-id="3f5d4-117">The `x:` prefix convention for mapping the XAML language intrinsics support is followed by project templates, sample code, and the documentation of language features within this [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)].</span></span> <span data-ttu-id="3f5d4-118">XAML 名前空間は、基本的な WPF アプリケーションでも必要な一般的に使用される多くの機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-118">The XAML namespace defines many commonly-used features that are necessary even for basic WPF  applications.</span></span> <span data-ttu-id="3f5d4-119">たとえば、部分クラスを使用して xaml ファイルに分離コードを結合するには、そのクラスに関連する xaml ファイルの`x:Class`ルート要素の属性として名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-119">For instance, in order to join any code-behind to a XAML file through a partial class, you must name that class as the `x:Class` attribute in the root element of the relevant XAML file.</span></span> <span data-ttu-id="3f5d4-120">または、キー付きリソースとしてアクセスする XAML ページで定義されている要素は、 `x:Key`対象の要素に対して属性を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-120">Or, any element as defined in a XAML page that you wish to access as a keyed resource should have the `x:Key` attribute set on the element in question.</span></span> <span data-ttu-id="3f5d4-121">これらの XAML の詳細については、「 [xaml の概要 (WPF)](xaml-overview-wpf.md) 」または「 [Xaml 構文の詳細](xaml-syntax-in-detail.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-121">For more information on these and other aspects of XAML see [XAML Overview (WPF)](xaml-overview-wpf.md) or [XAML Syntax In Detail](xaml-syntax-in-detail.md).</span></span>  
  
<a name="Mapping_To_Custom_Classes_and_Assemblies"></a>   
## <a name="mapping-to-custom-classes-and-assemblies"></a><span data-ttu-id="3f5d4-122">カスタムクラスとアセンブリへのマッピング</span><span class="sxs-lookup"><span data-stu-id="3f5d4-122">Mapping to Custom Classes and Assemblies</span></span>  
 <span data-ttu-id="3f5d4-123">`xmlns`プレフィックス宣言内の一連のトークンを使用して、XML 名前空間をアセンブリにマップできます。これは、標準の WPF および xaml 組み込みの xaml 名前空間をプレフィックスにマップする方法と似ています。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-123">You can map XML namespaces to assemblies using a series of tokens within an `xmlns` prefix declaration, similar to how the standard WPF and XAML-intrinsics XAML namespaces are mapped to prefixes.</span></span>  
  
 <span data-ttu-id="3f5d4-124">構文では、次の名前付きトークンと次の値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-124">The syntax takes the following possible named tokens and following values:</span></span>  
  
 <span data-ttu-id="3f5d4-125">`clr-namespace:`要素として公開するパブリック型を格納しているアセンブリ内で宣言されている CLR 名前空間。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-125">`clr-namespace:` The CLR namespace declared within the assembly that contains the public types to expose as elements.</span></span>  
  
 <span data-ttu-id="3f5d4-126">`assembly=`参照されている CLR 名前空間の一部またはすべてを含むアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-126">`assembly=` The assembly that contains some or all of the referenced CLR namespace.</span></span> <span data-ttu-id="3f5d4-127">通常、この値はパスではなくアセンブリの名前にすぎず、拡張子 (.dll や .exe など) は含まれません。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-127">This value is typically just the name of the assembly, not the path, and does not include the extension (such as .dll or .exe).</span></span> <span data-ttu-id="3f5d4-128">このアセンブリへのパスは、マップしようとしている XAML を含むプロジェクトファイル内のプロジェクト参照として設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-128">The path to that assembly must be established as a project reference in the project file that contains the XAML you are trying to map.</span></span> <span data-ttu-id="3f5d4-129">バージョン管理と厳密な名前の署名`assembly`を組み込むために、値には、単純な文字列名ではなく、で<xref:System.Reflection.AssemblyName>定義されている文字列を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-129">In order to incorporate versioning and strong-name signing, the `assembly` value can be a string as defined by <xref:System.Reflection.AssemblyName>, rather than the simple string name.</span></span>  
  
 <span data-ttu-id="3f5d4-130">`clr-namespace`トークンを値から区切る文字がコロン (:) であることに注意してください。一方、トークンを`assembly`値から区切る文字は等号 (=) です。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-130">Note that the character separating the `clr-namespace` token from its value is a colon (:) whereas the character separating the `assembly` token from its value is an equals sign (=).</span></span> <span data-ttu-id="3f5d4-131">これら2つのトークンの間で使用する文字はセミコロンです。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-131">The character to use between these two tokens is a semicolon.</span></span> <span data-ttu-id="3f5d4-132">また、宣言のどこにも空白を入れないでください。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-132">Also, do not include any white space anywhere in the declaration.</span></span>  
  
### <a name="a-basic-custom-mapping-example"></a><span data-ttu-id="3f5d4-133">基本的なカスタムマッピングの例</span><span class="sxs-lookup"><span data-stu-id="3f5d4-133">A Basic Custom Mapping Example</span></span>  
 <span data-ttu-id="3f5d4-134">次のコードでは、カスタムクラスの例を定義しています。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-134">The following code defines an example custom class:</span></span>  
  
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
  
 <span data-ttu-id="3f5d4-135">このカスタムクラスは、プロジェクト設定 (図に示されていません) ごとにという`SDKSampleLibrary`名前のライブラリにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-135">This custom class is then compiled into a library, which per the project settings (not shown) is named `SDKSampleLibrary`.</span></span>  
  
 <span data-ttu-id="3f5d4-136">このカスタムクラスを参照するには、現在のプロジェクトの参照としても含める必要があります。これは通常、Visual Studio のソリューションエクスプローラー UI を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-136">In order to reference this custom class, you also need to include it as a reference for your current project, which you would typically do using the Solution Explorer UI in Visual Studio.</span></span>  
  
 <span data-ttu-id="3f5d4-137">クラスが含まれているライブラリと、プロジェクト設定にそのライブラリへの参照があるので、次のプレフィックスマッピングを XAML のルート要素の一部として追加できます。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-137">Now that you have a library containing a class, and a reference to it in project settings, you can add the following prefix mapping as part of your root element in XAML:</span></span>  
  
 `xmlns:custom="clr-namespace:SDKSample;assembly=SDKSampleLibrary"`  
  
 <span data-ttu-id="3f5d4-138">すべてをまとめて配置するには、次の XAML を使用します。これには、ルートタグ内の一般的な default および x: マッピングと共にカスタム`ExampleClass`マッピングが含まれます。その後、プレフィックス付きの参照を使用して、その UI でインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-138">To put it all together, the following is XAML that includes the custom mapping along with the typical default and x: mappings in the root tag, then uses a prefixed reference to instantiate `ExampleClass` in that UI:</span></span>  
  
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
  
### <a name="mapping-to-current-assemblies"></a><span data-ttu-id="3f5d4-139">現在のアセンブリへのマッピング</span><span class="sxs-lookup"><span data-stu-id="3f5d4-139">Mapping to Current Assemblies</span></span>  
 <span data-ttu-id="3f5d4-140">`assembly`参照先のが、 `clr-namespace`カスタムクラスを参照しているアプリケーションコードと同じアセンブリ内に定義されている場合は、を省略できます。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-140">`assembly` can be omitted if the `clr-namespace` referenced is being defined within the same assembly as the application code that is referencing the custom classes.</span></span> <span data-ttu-id="3f5d4-141">または、この場合と同等の構文では`assembly=`、等号の後に文字列トークンを指定せずに、を指定します。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-141">Or, an equivalent syntax for this case is to specify `assembly=`, with no string token following the equals sign.</span></span>  
  
 <span data-ttu-id="3f5d4-142">カスタムクラスは、同じアセンブリ内で定義されている場合、ページのルート要素として使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-142">Custom classes cannot be used as the root element of a page if defined in the same assembly.</span></span> <span data-ttu-id="3f5d4-143">部分クラスをマップする必要はありません。XAML の要素として参照する場合は、アプリケーション内のページの部分クラスではないクラスのみをマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-143">Partial classes do not need to be mapped; only classes that are not the partial class of a page in your application need to be mapped if you intend to reference them as elements in XAML.</span></span>  
  
<a name="Mapping_CLR_Namespaces_to_XML_Namespaces_in_an"></a>   
## <a name="mapping-clr-namespaces-to-xml-namespaces-in-an-assembly"></a><span data-ttu-id="3f5d4-144">アセンブリ内の XML 名前空間への CLR 名前空間のマッピング</span><span class="sxs-lookup"><span data-stu-id="3f5d4-144">Mapping CLR Namespaces to XML Namespaces in an Assembly</span></span>  
 <span data-ttu-id="3f5d4-145">WPF では、複数の CLR 名前空間を1つの XAML 名前空間にマップするために XAML プロセッサによって使用される CLR 属性を定義します。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-145">WPF defines a CLR attribute that is consumed by XAML processors in order to map multiple CLR namespaces to a single XAML namespace.</span></span> <span data-ttu-id="3f5d4-146">この属性<xref:System.Windows.Markup.XmlnsDefinitionAttribute>は、アセンブリを生成するソースコードのアセンブリレベルに配置されます。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-146">This attribute, <xref:System.Windows.Markup.XmlnsDefinitionAttribute>, is placed at the assembly level in the source code that produces the assembly.</span></span> <span data-ttu-id="3f5d4-147">WPF アセンブリソースコードは、この属性を使用して<xref:System.Windows> 、や<xref:System.Windows.Controls>などのさまざまな共通名前空間[!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)]を名前空間にマップします。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-147">The WPF assembly source code uses this attribute to map the various common namespaces, such as <xref:System.Windows> and <xref:System.Windows.Controls>, to the [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)] namespace.</span></span>  
  
 <span data-ttu-id="3f5d4-148">は<xref:System.Windows.Markup.XmlnsDefinitionAttribute> 、XML/XAML 名前空間名と CLR 名前空間名の2つのパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-148">The <xref:System.Windows.Markup.XmlnsDefinitionAttribute> takes two parameters: the XML/XAML namespace name, and the CLR namespace name.</span></span> <span data-ttu-id="3f5d4-149">複数の CLR 名前空間を同じ XML 名前空間にマップするために、複数存在することができます。<xref:System.Windows.Markup.XmlnsDefinitionAttribute></span><span class="sxs-lookup"><span data-stu-id="3f5d4-149">More than one <xref:System.Windows.Markup.XmlnsDefinitionAttribute> can exist to map multiple CLR namespaces to the same XML namespace.</span></span> <span data-ttu-id="3f5d4-150">マッピングが完了すると、部分クラスの分離コードページに適切な`using`ステートメントを指定することで、必要に応じて完全修飾なしでこれらの名前空間のメンバーを参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-150">Once mapped, members of those namespaces can also be referenced without full qualification if desired by providing the appropriate `using` statement in the partial-class code-behind page.</span></span> <span data-ttu-id="3f5d4-151">詳細については、「<xref:System.Windows.Markup.XmlnsDefinitionAttribute>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-151">For more details, see <xref:System.Windows.Markup.XmlnsDefinitionAttribute>.</span></span>  
  
## <a name="designer-namespaces-and-other-prefixes-from-xaml-templates"></a><span data-ttu-id="3f5d4-152">デザイナーの名前空間と XAML テンプレートからのその他のプレフィックス</span><span class="sxs-lookup"><span data-stu-id="3f5d4-152">Designer Namespaces and Other Prefixes From XAML Templates</span></span>  
 <span data-ttu-id="3f5d4-153">WPF XAML 用の開発環境やデザインツールで作業している場合は、xaml マークアップ内に他の定義済みの XAML 名前空間/プレフィックスがあることがわかります。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-153">If you are working with development environments and/or design tools for WPF XAML, you may notice that there are other defined XAML namespaces / prefixes within the XAML markup.</span></span>  
  
 [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)]<span data-ttu-id="3f5d4-154">は、通常、プレフィックス`d:`にマップされているデザイナーの名前空間を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-154">uses a designer namespace that is typically mapped to the prefix `d:`.</span></span> <span data-ttu-id="3f5d4-155">WPF の新しいプロジェクトテンプレートでは、この xaml 名前空間を事前にマップして、と[!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)]他のデザイン環境間での xaml のインターチェンジをサポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-155">More recent project templates for WPF might pre-map this XAML namespace to support interchange of the XAML between [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] and other design environments.</span></span> <span data-ttu-id="3f5d4-156">このデザインの XAML 名前空間は、デザイナーの XAML ベースの UI を roundtripping しながら、デザイン状態を perpetuate するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-156">This design XAML namespace is used to perpetuate design state while roundtripping XAML-based UI in the designer.</span></span> <span data-ttu-id="3f5d4-157">また`d:IsDataSource`、デザイナーでランタイムデータソースを有効にするなどの機能にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-157">It is also used for features such as `d:IsDataSource`, which enable runtime data sources in a designer.</span></span>  
  
 <span data-ttu-id="3f5d4-158">マップされていると思わ`mc:`れるもう1つのプレフィックスはです。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-158">Another prefix you might see mapped is `mc:`.</span></span> <span data-ttu-id="3f5d4-159">`mc:`は、マークアップ互換性のためのものであり、必ずしも XAML 固有ではないマークアップ互換性パターンを利用しています。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-159">`mc:` is for markup compatibility, and is leveraging a markup compatibility pattern that is not necessarily XAML-specific.</span></span> <span data-ttu-id="3f5d4-160">また、マークアップ互換性機能を使用して、フレームワーク間、またはバッキング実装の他の境界間で XAML を交換したり、XAML スキーマコンテキスト間で作業したり、デザイナーで制限されたモードの互換性を提供したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-160">To some extent, the markup compatibility features can be used to exchange XAML between frameworks or across other boundaries of backing implementation, work between XAML schema contexts, provide compatibility for limited modes in designers, and so on.</span></span> <span data-ttu-id="3f5d4-161">マークアップ互換性の概念と WPF との関係の詳細について[は、「マークアップの互換性 (mc:)」を参照してください。言語機能](markup-compatibility-mc-language-features.md)。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-161">For more information on markup compatibility concepts and how they relate to WPF, see  [Markup Compatibility (mc:) Language Features](markup-compatibility-mc-language-features.md).</span></span>  
  
## <a name="wpf-and-assembly-loading"></a><span data-ttu-id="3f5d4-162">WPF とアセンブリの読み込み</span><span class="sxs-lookup"><span data-stu-id="3f5d4-162">WPF and Assembly Loading</span></span>  
 <span data-ttu-id="3f5d4-163">WPF の XAML スキーマコンテキストは WPF アプリケーションモデルと統合され、さらにの<xref:System.AppDomain>CLR 定義概念が使用されます。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-163">The XAML schema context for WPF integrates with the WPF application model, which in turn uses the CLR-defined concept of <xref:System.AppDomain>.</span></span> <span data-ttu-id="3f5d4-164">次に、XAML スキーマコンテキストで、WPF の<xref:System.AppDomain>使用方法やその他の要因に基づいて、アセンブリを読み込む方法、または実行時に型を検索する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-164">The following sequence describes how XAML schema context interprets how to either load assemblies or find types at run time or design time, based on the WPF use of <xref:System.AppDomain> and other factors.</span></span>  
  
1. <span data-ttu-id="3f5d4-165">を反復処理し、最後に読み込まれたアセンブリから開始して、名前のすべての側面に一致する、既に読み込まれているアセンブリを探します。<xref:System.AppDomain></span><span class="sxs-lookup"><span data-stu-id="3f5d4-165">Iterate through the <xref:System.AppDomain>, looking for an already-loaded assembly that matches all aspects of the name, starting from the most recently loaded assembly.</span></span>  
  
2. <span data-ttu-id="3f5d4-166">名前が修飾されている<xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>場合は、修飾名でを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-166">If the name is qualified, call <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> on the qualified name.</span></span>  
  
3. <span data-ttu-id="3f5d4-167">修飾名の短い名前と公開キートークンが、マークアップが読み込まれたアセンブリと一致する場合は、そのアセンブリを返します。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-167">If the short name + public key token of a qualified name matches the assembly that the markup was loaded from, return that assembly.</span></span>  
  
4. <span data-ttu-id="3f5d4-168">を呼び出す<xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>には、短い名前と公開キートークンを使用します。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-168">Use the short name + public key token to call <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>.</span></span>  
  
5. <span data-ttu-id="3f5d4-169">名前が修飾されてい<xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>ない場合は、を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-169">If the name is unqualified, call <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="3f5d4-170">ルース XAML では、手順 3; が使用されません。アセンブリが読み込まれていません。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-170">Loose XAML does not use Step 3; there is no loaded-from assembly.</span></span>  
  
 <span data-ttu-id="3f5d4-171">WPF 用にコンパイルされた XAML (xamlbuildtask を使用して生成) では<xref:System.AppDomain> 、既に読み込まれているアセンブリ (手順 1) は使用されません。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-171">Compiled XAML for WPF (generated via XamlBuildTask) does not use the already-loaded assemblies from <xref:System.AppDomain> (Step 1).</span></span> <span data-ttu-id="3f5d4-172">また、XamlBuildTask の出力から名前を修飾しないでください。そのため、手順5は適用されません。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-172">Also, the name should never be unqualified from XamlBuildTask output, so Step 5 does not apply.</span></span>  
  
 <span data-ttu-id="3f5d4-173">(プレゼンテーション Buildtask によって生成される) コンパイル済みの BAML はすべての手順を使用しますが、BAML には修飾されていないアセンブリ名を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="3f5d4-173">Compiled BAML (generated via PresentationBuildTask) uses all steps, although BAML also should not contain unqualified assembly names.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f5d4-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f5d4-174">See also</span></span>

- [<span data-ttu-id="3f5d4-175">XML 名前空間について</span><span class="sxs-lookup"><span data-stu-id="3f5d4-175">Understanding XML Namespaces</span></span>](https://go.microsoft.com/fwlink/?LinkId=98069)
- [<span data-ttu-id="3f5d4-176">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="3f5d4-176">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
