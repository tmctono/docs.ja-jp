---
title: XAML 名前空間と名前空間マッピング
description: Windows Presentation Foundation XAML ファイルのルート タグでよく目にする 2 つの XAML 名前空間マッピングの存在と目的について詳しく学習します。
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
ms.openlocfilehash: 42808df8e7483f60b1420fda890fe374493538f1
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168368"
---
# <a name="xaml-namespaces-and-namespace-mapping-for-wpf-xaml"></a><span data-ttu-id="ebefb-103">XAML 名前空間および WPF XAML の名前空間の割り当て</span><span class="sxs-lookup"><span data-stu-id="ebefb-103">XAML Namespaces and Namespace Mapping for WPF XAML</span></span>
<span data-ttu-id="ebefb-104">このトピックでは、WPF XAML ファイルのルート タグでよく目にする 2 つの XAML 名前空間マッピングの存在と目的について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="ebefb-104">This topic further explains the presence and purpose of the two XAML namespace mappings as often found in the root tag of a WPF XAML file.</span></span> <span data-ttu-id="ebefb-105">また、独自のコードや別のアセンブリ内で定義されている要素を使用するために、同様のマッピングを生成する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="ebefb-105">It also describes how to produce similar mappings for using elements that are defined in your own code, and/or within separate assemblies.</span></span>  

## <a name="what-is-a-xaml-namespace"></a><span data-ttu-id="ebefb-106">XAML 名前空間とは</span><span class="sxs-lookup"><span data-stu-id="ebefb-106">What is a XAML Namespace?</span></span>  
 <span data-ttu-id="ebefb-107">XAML 名前空間は、実際には XML 名前空間の概念を拡張したものです。</span><span class="sxs-lookup"><span data-stu-id="ebefb-107">A XAML namespace is really an extension of the concept of an XML namespace.</span></span> <span data-ttu-id="ebefb-108">XAML 名前空間を指定する手法は、XML 名前空間の構文、URI を名前空間の識別子として使用する規則、同じマークアップ ソースから複数の名前空間を参照するための手段を提供するプレフィックスの使用などに依存します。</span><span class="sxs-lookup"><span data-stu-id="ebefb-108">The techniques of specifying a XAML namespace rely on the XML namespace syntax, the convention of using URIs as namespace identifiers, using prefixes to provide a means to reference multiple namespaces from the same markup source, and so on.</span></span> <span data-ttu-id="ebefb-109">XML 名前空間の XAML 定義に追加された主な概念として、XAML 名前空間は、マークアップ使用の一意性の範囲を暗黙的に示し、特定の CLR 名前空間と参照アセンブリによってマークアップ エンティティがサポートされる可能性のある方法にも影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="ebefb-109">The primary concept that is added to the XAML definition of the XML namespace is that a XAML namespace implies both a scope of uniqueness for the markup usages, and also influences how markup entities are potentially backed by specific CLR namespaces and referenced assemblies.</span></span> <span data-ttu-id="ebefb-110">この 2 つ目の考慮事項は、XAML スキーマ コンテキストの概念によっても影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="ebefb-110">This latter consideration is also influenced by the concept of a XAML schema context.</span></span> <span data-ttu-id="ebefb-111">ただし、WPF での XAML 名前空間の使用方法については、一般に、既定の XAML 名前空間、XAML 言語の名前空間、および XAML マークアップによって特定のバッキング CLR 名前空間と参照アセンブリに直接マップされる XAML 名前空間に関して、XAML 名前空間を考えることができます。</span><span class="sxs-lookup"><span data-stu-id="ebefb-111">But for purposes of how WPF works with XAML namespaces, you can generally think of XAML namespaces in terms of a default XAML namespace, the XAML language namespace, and any further XAML namespaces as mapped by your XAML markup directly to specific backing CLR namespaces and referenced assemblies.</span></span>  
  
<a name="The_WPF_and_XAML_Namespace_Declarations"></a>
## <a name="the-wpf-and-xaml-namespace-declarations"></a><span data-ttu-id="ebefb-112">WPF と XAML 名前空間の宣言</span><span class="sxs-lookup"><span data-stu-id="ebefb-112">The WPF and XAML Namespace Declarations</span></span>  
 <span data-ttu-id="ebefb-113">多くの XAML ファイルのルート タグでの名前空間宣言には、通常、2 つの XML 名前空間宣言があります。</span><span class="sxs-lookup"><span data-stu-id="ebefb-113">Within the namespace declarations in the root tag of many XAML files, you will see that there are typically two XML namespace declarations.</span></span> <span data-ttu-id="ebefb-114">1 つ目の宣言では、WPF クライアントとフレームワークの全体的な XAML 名前空間が既定値としてマップされます。</span><span class="sxs-lookup"><span data-stu-id="ebefb-114">The first declaration maps the overall WPF client / framework XAML namespace as the default:</span></span>  
  
 `xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"`  
  
 <span data-ttu-id="ebefb-115">2 つ目の宣言では、別の XAML 名前空間がマップされ、その名前空間が (通常は) `x:` プレフィックスにマップされます。</span><span class="sxs-lookup"><span data-stu-id="ebefb-115">The second declaration maps a separate XAML namespace, mapping it (typically) to the `x:` prefix.</span></span>  
  
 `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`  
  
 <span data-ttu-id="ebefb-116">これらの宣言の間には、`x:` プレフィックス マッピングは XAML 言語定義の一部である組み込みをサポートし、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] は、XAML を言語として使用し、XAML 用にオブジェクトのボキャブラリを定義する 1 つの実装である、という関係があります。</span><span class="sxs-lookup"><span data-stu-id="ebefb-116">The relationship between these declarations is that the `x:` prefix mapping supports the intrinsics that are part of the XAML language definition, and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] is one implementation that uses XAML as a language and defines a vocabulary of its objects for XAML.</span></span> <span data-ttu-id="ebefb-117">WPF のボキャブラリの使用は、XAML の組み込みの使用法よりはるかに一般的であるため、WPF のボキャブラリは既定値としてマップされます。</span><span class="sxs-lookup"><span data-stu-id="ebefb-117">Because the WPF vocabulary's usages will be far more common than the XAML intrinsics usages, the WPF vocabulary is mapped as the default.</span></span>  
  
 <span data-ttu-id="ebefb-118">この SDK 内の言語機能のプロジェクト テンプレート、サンプル コード、およびドキュメントは、XAML 言語組み込みサポートのマッピングに対する `x:` プレフィックスの規則に従っています。</span><span class="sxs-lookup"><span data-stu-id="ebefb-118">The `x:` prefix convention for mapping the XAML language intrinsics support is followed by project templates, sample code, and the documentation of language features within this SDK.</span></span> <span data-ttu-id="ebefb-119">XAML 名前空間では、基本的な WPF アプリケーションでも必要な、よく使用される多くの機能が定義されています。</span><span class="sxs-lookup"><span data-stu-id="ebefb-119">The XAML namespace defines many commonly-used features that are necessary even for basic WPF  applications.</span></span> <span data-ttu-id="ebefb-120">たとえば、部分クラスを使用して XAML ファイルにコードビハインドを結合するには、関連する XAML ファイルのルート要素の `x:Class` 属性として、そのクラスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebefb-120">For instance, in order to join any code-behind to a XAML file through a partial class, you must name that class as the `x:Class` attribute in the root element of the relevant XAML file.</span></span> <span data-ttu-id="ebefb-121">または、キー付きリソースとしてアクセスする XAML ページで定義されているすべての要素で、`x:Key` 属性を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebefb-121">Or, any element as defined in a XAML page that you wish to access as a keyed resource should have the `x:Key` attribute set on the element in question.</span></span> <span data-ttu-id="ebefb-122">XAML のこれらおよび他の側面の詳細については、「[XAML の概要 (WPF)](../../../desktop-wpf/fundamentals/xaml.md)」または「[XAML 構文の詳細](xaml-syntax-in-detail.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebefb-122">For more information on these and other aspects of XAML see [XAML Overview (WPF)](../../../desktop-wpf/fundamentals/xaml.md) or [XAML Syntax In Detail](xaml-syntax-in-detail.md).</span></span>  
  
<a name="Mapping_To_Custom_Classes_and_Assemblies"></a>
## <a name="mapping-to-custom-classes-and-assemblies"></a><span data-ttu-id="ebefb-123">カスタム クラスとアセンブリへのマッピング</span><span class="sxs-lookup"><span data-stu-id="ebefb-123">Mapping to Custom Classes and Assemblies</span></span>  
 <span data-ttu-id="ebefb-124">標準の WPF および XAML 組み込み XAML 名前空間がプレフィックスにマップされる方法と同じように、`xmlns` プレフィックス宣言内の一連のトークンを使用して、XML 名前空間をアセンブリにマップできます。</span><span class="sxs-lookup"><span data-stu-id="ebefb-124">You can map XML namespaces to assemblies using a series of tokens within an `xmlns` prefix declaration, similar to how the standard WPF and XAML-intrinsics XAML namespaces are mapped to prefixes.</span></span>  
  
 <span data-ttu-id="ebefb-125">構文では、次の名前付きトークンと値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ebefb-125">The syntax takes the following possible named tokens and following values:</span></span>  
  
 <span data-ttu-id="ebefb-126">`clr-namespace:` 要素として公開するパブリック型が含まれる、アセンブリ内で宣言されている CLR 名前空間。</span><span class="sxs-lookup"><span data-stu-id="ebefb-126">`clr-namespace:` The CLR namespace declared within the assembly that contains the public types to expose as elements.</span></span>  
  
 <span data-ttu-id="ebefb-127">`assembly=` 参照されている CLR 名前空間の一部または全部が含まれるアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="ebefb-127">`assembly=` The assembly that contains some or all of the referenced CLR namespace.</span></span> <span data-ttu-id="ebefb-128">通常、この値はパスではなくアセンブリの名前だけであり、拡張子 (.dll や .exe など) は含まれません。</span><span class="sxs-lookup"><span data-stu-id="ebefb-128">This value is typically just the name of the assembly, not the path, and does not include the extension (such as .dll or .exe).</span></span> <span data-ttu-id="ebefb-129">そのアセンブリへのパスは、マップしようとしている XAML が含まれるプロジェクト ファイルでプロジェクト参照として設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebefb-129">The path to that assembly must be established as a project reference in the project file that contains the XAML you are trying to map.</span></span> <span data-ttu-id="ebefb-130">バージョン管理と厳密な名前の署名を組み込むには、`assembly` の値を、単純な文字列名ではなく、<xref:System.Reflection.AssemblyName> で定義されている文字列にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ebefb-130">In order to incorporate versioning and strong-name signing, the `assembly` value can be a string as defined by <xref:System.Reflection.AssemblyName>, rather than the simple string name.</span></span>  
  
 <span data-ttu-id="ebefb-131">`clr-namespace` トークンとその値を区切る文字がコロン (:) であることに注意してください。一方、`assembly` トークンとその値を区切る文字は等号 (=) です。</span><span class="sxs-lookup"><span data-stu-id="ebefb-131">Note that the character separating the `clr-namespace` token from its value is a colon (:) whereas the character separating the `assembly` token from its value is an equals sign (=).</span></span> <span data-ttu-id="ebefb-132">これら 2 つのトークンの間に使用する文字はセミコロンです。</span><span class="sxs-lookup"><span data-stu-id="ebefb-132">The character to use between these two tokens is a semicolon.</span></span> <span data-ttu-id="ebefb-133">また、宣言のどこにも空白文字を入れないでください。</span><span class="sxs-lookup"><span data-stu-id="ebefb-133">Also, do not include any white space anywhere in the declaration.</span></span>  
  
### <a name="a-basic-custom-mapping-example"></a><span data-ttu-id="ebefb-134">基本的なカスタム マッピングの例</span><span class="sxs-lookup"><span data-stu-id="ebefb-134">A Basic Custom Mapping Example</span></span>  
 <span data-ttu-id="ebefb-135">次のコードは、カスタム クラスを定義する例です。</span><span class="sxs-lookup"><span data-stu-id="ebefb-135">The following code defines an example custom class:</span></span>  
  
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
  
 <span data-ttu-id="ebefb-136">このカスタム クラスは、プロジェクトの設定 (図には示されていません) に従って、`SDKSampleLibrary` という名前のライブラリにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="ebefb-136">This custom class is then compiled into a library, which per the project settings (not shown) is named `SDKSampleLibrary`.</span></span>  
  
 <span data-ttu-id="ebefb-137">このカスタム クラスを参照するには、現在のプロジェクトに対する参照として、それを含める必要もあります。これを行うには、通常、Visual Studio のソリューション エクスプローラーの UI を使用します。</span><span class="sxs-lookup"><span data-stu-id="ebefb-137">In order to reference this custom class, you also need to include it as a reference for your current project, which you would typically do using the Solution Explorer UI in Visual Studio.</span></span>  
  
 <span data-ttu-id="ebefb-138">クラスが含まれるライブラリを作成し、プロジェクトの設定でそれを参照したので、XAML でのルート要素の一部として、次のプレフィックス マッピングを追加できます。</span><span class="sxs-lookup"><span data-stu-id="ebefb-138">Now that you have a library containing a class, and a reference to it in project settings, you can add the following prefix mapping as part of your root element in XAML:</span></span>  
  
 `xmlns:custom="clr-namespace:SDKSample;assembly=SDKSampleLibrary"`  
  
 <span data-ttu-id="ebefb-139">まとめると、次の XAML には、カスタム マッピングと共に一般的な既定のマッピングと x: マッピングがルート タグに含まれており、プレフィックス付き参照を使用して、その UI で `ExampleClass` をインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="ebefb-139">To put it all together, the following is XAML that includes the custom mapping along with the typical default and x: mappings in the root tag, then uses a prefixed reference to instantiate `ExampleClass` in that UI:</span></span>  
  
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
  
### <a name="mapping-to-current-assemblies"></a><span data-ttu-id="ebefb-140">現在のアセンブリへのマッピング</span><span class="sxs-lookup"><span data-stu-id="ebefb-140">Mapping to Current Assemblies</span></span>  
 <span data-ttu-id="ebefb-141">`assembly` は、参照されている `clr-namespace` が、カスタム クラスを参照しているアプリケーション コードと同じアセンブリ内で定義されている場合は、省略できます。</span><span class="sxs-lookup"><span data-stu-id="ebefb-141">`assembly` can be omitted if the `clr-namespace` referenced is being defined within the same assembly as the application code that is referencing the custom classes.</span></span> <span data-ttu-id="ebefb-142">または、等号の後に文字列トークンを明示せずに `assembly=` を指定しても同じです。</span><span class="sxs-lookup"><span data-stu-id="ebefb-142">Or, an equivalent syntax for this case is to specify `assembly=`, with no string token following the equals sign.</span></span>  
  
 <span data-ttu-id="ebefb-143">同じアセンブリ内で定義されている場合、カスタム クラスをページのルート要素として使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="ebefb-143">Custom classes cannot be used as the root element of a page if defined in the same assembly.</span></span> <span data-ttu-id="ebefb-144">部分クラスをマップする必要はありません。アプリケーション内のページの部分クラスではないクラスを、XAML の要素として参照する場合にのみ、それをマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebefb-144">Partial classes do not need to be mapped; only classes that are not the partial class of a page in your application need to be mapped if you intend to reference them as elements in XAML.</span></span>  
  
<a name="Mapping_CLR_Namespaces_to_XML_Namespaces_in_an"></a>
## <a name="mapping-clr-namespaces-to-xml-namespaces-in-an-assembly"></a><span data-ttu-id="ebefb-145">アセンブリ内の XML 名前空間に対する CLR 名前空間のマッピング</span><span class="sxs-lookup"><span data-stu-id="ebefb-145">Mapping CLR Namespaces to XML Namespaces in an Assembly</span></span>  
 <span data-ttu-id="ebefb-146">WPF では、複数の CLR 名前空間を 1 つの XAML 名前空間にマップするために XAML プロセッサによって使用される CLR 属性が定義されています。</span><span class="sxs-lookup"><span data-stu-id="ebefb-146">WPF defines a CLR attribute that is consumed by XAML processors in order to map multiple CLR namespaces to a single XAML namespace.</span></span> <span data-ttu-id="ebefb-147">この属性 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> は、アセンブリを生成するソース コードのアセンブリ レベルに配置します。</span><span class="sxs-lookup"><span data-stu-id="ebefb-147">This attribute, <xref:System.Windows.Markup.XmlnsDefinitionAttribute>, is placed at the assembly level in the source code that produces the assembly.</span></span> <span data-ttu-id="ebefb-148">WPF アセンブリのソース コードでは、この属性を使用して、<xref:System.Windows> や <xref:System.Windows.Controls> などのさまざまな共通名前空間を、`http://schemas.microsoft.com/winfx/2006/xaml/presentation` 名前空間にマップします。</span><span class="sxs-lookup"><span data-stu-id="ebefb-148">The WPF assembly source code uses this attribute to map the various common namespaces, such as <xref:System.Windows> and <xref:System.Windows.Controls>, to the `http://schemas.microsoft.com/winfx/2006/xaml/presentation` namespace.</span></span>  
  
 <span data-ttu-id="ebefb-149"><xref:System.Windows.Markup.XmlnsDefinitionAttribute> は、XML/XAML 名前空間名と CLR 名前空間名の 2 つのパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ebefb-149">The <xref:System.Windows.Markup.XmlnsDefinitionAttribute> takes two parameters: the XML/XAML namespace name, and the CLR namespace name.</span></span> <span data-ttu-id="ebefb-150">複数の <xref:System.Windows.Markup.XmlnsDefinitionAttribute> を使用して、複数の CLR 名前空間を同じ XML 名前空間にマップすることができます。</span><span class="sxs-lookup"><span data-stu-id="ebefb-150">More than one <xref:System.Windows.Markup.XmlnsDefinitionAttribute> can exist to map multiple CLR namespaces to the same XML namespace.</span></span> <span data-ttu-id="ebefb-151">マップした後は、必要に応じて、それらの名前空間のメンバーを、部分クラスの分離コード ページで適切な `using` ステートメントを指定することにより、完全修飾なしで参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="ebefb-151">Once mapped, members of those namespaces can also be referenced without full qualification if desired by providing the appropriate `using` statement in the partial-class code-behind page.</span></span> <span data-ttu-id="ebefb-152">詳細については、「<xref:System.Windows.Markup.XmlnsDefinitionAttribute>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebefb-152">For more details, see <xref:System.Windows.Markup.XmlnsDefinitionAttribute>.</span></span>  
  
## <a name="designer-namespaces-and-other-prefixes-from-xaml-templates"></a><span data-ttu-id="ebefb-153">XAML テンプレートからのデザイナー名前空間とその他のプレフィックス</span><span class="sxs-lookup"><span data-stu-id="ebefb-153">Designer Namespaces and Other Prefixes From XAML Templates</span></span>  
 <span data-ttu-id="ebefb-154">WPF XAML に対して開発環境ツールやデザイン ツールを使用している場合、XAML マークアップ内に他の定義済みの XAML 名前空間やプレフィックスがあることに気付く場合があります。</span><span class="sxs-lookup"><span data-stu-id="ebefb-154">If you are working with development environments and/or design tools for WPF XAML, you may notice that there are other defined XAML namespaces / prefixes within the XAML markup.</span></span>  
  
 <span data-ttu-id="ebefb-155">Visual Studio 用の WPF デザイナーでは、通常はプレフィックス `d:` にマップされるデザイナー名前空間が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ebefb-155">WPF Designer for Visual Studio uses a designer namespace that is typically mapped to the prefix `d:`.</span></span> <span data-ttu-id="ebefb-156">さらに最近の WPF 用プロジェクト テンプレートでは、Visual Studio 用 WPF デザイナーと他のデザイン環境の間での XAML の交換をサポートするため、この XAML 名前空間があらかじめマップされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="ebefb-156">More recent project templates for WPF might pre-map this XAML namespace to support interchange of the XAML between WPF Designer for Visual Studio and other design environments.</span></span> <span data-ttu-id="ebefb-157">このデザイン XAML 名前空間は、デザイナーの XAML ベースの UI をラウンドトリップする間もデザイン状態を持続させるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ebefb-157">This design XAML namespace is used to perpetuate design state while roundtripping XAML-based UI in the designer.</span></span> <span data-ttu-id="ebefb-158">また、デザイナーで実行時データ ソースを有効にする `d:IsDataSource` などの機能にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="ebefb-158">It is also used for features such as `d:IsDataSource`, which enable runtime data sources in a designer.</span></span>  
  
 <span data-ttu-id="ebefb-159">マップされていると思われるもう 1 つのプレフィックスは `mc:` です。</span><span class="sxs-lookup"><span data-stu-id="ebefb-159">Another prefix you might see mapped is `mc:`.</span></span> <span data-ttu-id="ebefb-160">`mc:` は、マークアップの互換性のためのものであり、必ずしも XAML 固有ではないマークアップ互換性パターンが利用されています。</span><span class="sxs-lookup"><span data-stu-id="ebefb-160">`mc:` is for markup compatibility, and is leveraging a markup compatibility pattern that is not necessarily XAML-specific.</span></span> <span data-ttu-id="ebefb-161">ある程度まで、マークアップ互換性機能を使用して、フレームワーク間や、バッキング実装の他の境界間での XAML の交換、XAML スキーマ コンテキスト間での作業、デザイナーでの制限されたモードに対する互換性の提供などを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ebefb-161">To some extent, the markup compatibility features can be used to exchange XAML between frameworks or across other boundaries of backing implementation, work between XAML schema contexts, provide compatibility for limited modes in designers, and so on.</span></span> <span data-ttu-id="ebefb-162">マークアップ互換性の概念と WPF との関係の詳細については、「[マークアップの互換性 (mc:) 言語機能](markup-compatibility-mc-language-features.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebefb-162">For more information on markup compatibility concepts and how they relate to WPF, see  [Markup Compatibility (mc:) Language Features](markup-compatibility-mc-language-features.md).</span></span>  
  
## <a name="wpf-and-assembly-loading"></a><span data-ttu-id="ebefb-163">WPF とアセンブリの読み込み</span><span class="sxs-lookup"><span data-stu-id="ebefb-163">WPF and Assembly Loading</span></span>  
 <span data-ttu-id="ebefb-164">WPF の XAML スキーマ コンテキストは WPF アプリケーション モデルと統合され、そのモデルでは CLR で定義された <xref:System.AppDomain> の概念が使用されています。</span><span class="sxs-lookup"><span data-stu-id="ebefb-164">The XAML schema context for WPF integrates with the WPF application model, which in turn uses the CLR-defined concept of <xref:System.AppDomain>.</span></span> <span data-ttu-id="ebefb-165">WPF での <xref:System.AppDomain> と他の要素の使用に基づいて、実行時またはデザイン時に、XAML スキーマ コンテキストによって、アセンブリの読み込み方法または型の検索方法が解釈される流れを、次に示します。</span><span class="sxs-lookup"><span data-stu-id="ebefb-165">The following sequence describes how XAML schema context interprets how to either load assemblies or find types at run time or design time, based on the WPF use of <xref:System.AppDomain> and other factors.</span></span>  
  
1. <span data-ttu-id="ebefb-166">最後に読み込まれたアセンブリから始めて、<xref:System.AppDomain> を反復処理し、既に読み込まれているアセンブリから、名前のすべての部分が一致するものを検索します。</span><span class="sxs-lookup"><span data-stu-id="ebefb-166">Iterate through the <xref:System.AppDomain>, looking for an already-loaded assembly that matches all aspects of the name, starting from the most recently loaded assembly.</span></span>  
  
2. <span data-ttu-id="ebefb-167">名前が修飾されている場合は、修飾された名前に対して <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ebefb-167">If the name is qualified, call <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> on the qualified name.</span></span>  
  
3. <span data-ttu-id="ebefb-168">修飾された名前の短い名前と公開キー トークンが、マークアップの読み込み元のアセンブリと一致する場合は、そのアセンブリを返します。</span><span class="sxs-lookup"><span data-stu-id="ebefb-168">If the short name + public key token of a qualified name matches the assembly that the markup was loaded from, return that assembly.</span></span>  
  
4. <span data-ttu-id="ebefb-169">短い名前と公開キー トークンを使用して、<xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ebefb-169">Use the short name + public key token to call <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>.</span></span>  
  
5. <span data-ttu-id="ebefb-170">名前が修飾されていない場合は、<xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ebefb-170">If the name is unqualified, call <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="ebefb-171">Loose XAML では、ステップ 3 は使用されません。読み込み元のアセンブリはありません。</span><span class="sxs-lookup"><span data-stu-id="ebefb-171">Loose XAML does not use Step 3; there is no loaded-from assembly.</span></span>  
  
 <span data-ttu-id="ebefb-172">WPF 用にコンパイルされた XAML (XamlBuildTask で生成されたもの) では、<xref:System.AppDomain> から既に読み込まれているアセンブリは使用されません (ステップ 1)。</span><span class="sxs-lookup"><span data-stu-id="ebefb-172">Compiled XAML for WPF (generated via XamlBuildTask) does not use the already-loaded assemblies from <xref:System.AppDomain> (Step 1).</span></span> <span data-ttu-id="ebefb-173">また、XamlBuildTask の出力で名前を修飾してはならないため、ステップ 5 は適用されません。</span><span class="sxs-lookup"><span data-stu-id="ebefb-173">Also, the name should never be unqualified from XamlBuildTask output, so Step 5 does not apply.</span></span>  
  
 <span data-ttu-id="ebefb-174">(PresentationBuildTask によって生成される) コンパイル済みの BAML ではすべてのステップが使用されますが、BAML には修飾されていないアセンブリ名を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="ebefb-174">Compiled BAML (generated via PresentationBuildTask) uses all steps, although BAML also should not contain unqualified assembly names.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebefb-175">関連項目</span><span class="sxs-lookup"><span data-stu-id="ebefb-175">See also</span></span>

- <span data-ttu-id="ebefb-176">[XML 名前空間について](https://docs.microsoft.com/previous-versions/aa468565(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="ebefb-176">[Understanding XML Namespaces](https://docs.microsoft.com/previous-versions/aa468565(v=msdn.10))</span></span>
- [<span data-ttu-id="ebefb-177">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="ebefb-177">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
