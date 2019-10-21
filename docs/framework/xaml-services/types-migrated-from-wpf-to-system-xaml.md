---
title: WPF から System.Xaml に移行した型
ms.date: 03/30/2017
helpviewer_keywords:
- WPF XAML [XAML Services], migration to System.Xaml
- XAML [XAML Services], System.Xaml and WPF
- System.Xaml [XAML Services], types migrated from WPF
ms.assetid: d79dabf5-a2ec-4e8d-a37a-67c4ba8a2b91
ms.openlocfilehash: 943cdb2a21cbf2f95ef7fe2feefe6c0e71f57be4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939684"
---
# <a name="types-migrated-from-wpf-to-systemxaml"></a><span data-ttu-id="2d13c-102">WPF から System.Xaml に移行した型</span><span class="sxs-lookup"><span data-stu-id="2d13c-102">Types Migrated from WPF to System.Xaml</span></span>
<span data-ttu-id="2d13c-103">.NET Framework 3.5 および .NET Framework 3.0 では、 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)]と Windows Workflow Foundation の両方に XAML 言語の実装が含まれていました。</span><span class="sxs-lookup"><span data-stu-id="2d13c-103">In .NET Framework 3.5 and .NET Framework 3.0, both [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] and Windows Workflow Foundation included a XAML language implementation.</span></span> <span data-ttu-id="2d13c-104">WPF XAML 実装に拡張性を与えていたパブリック型の多くは、WindowsBase、PresentationCore、および PresentationFramework アセンブリに存在していました。</span><span class="sxs-lookup"><span data-stu-id="2d13c-104">Many of the public types that provided extensibility for the WPF XAML implementation existed in the WindowsBase, PresentationCore, and PresentationFramework assemblies.</span></span> <span data-ttu-id="2d13c-105">同様に、Windows Workflow Foundation XAML の機能拡張を提供したパブリック型は System.componentmodel アセンブリに存在していました。</span><span class="sxs-lookup"><span data-stu-id="2d13c-105">Likewise, public types that provided extensibility for Windows Workflow Foundation XAML existed in the System.Workflow.ComponentModel assembly.</span></span> <span data-ttu-id="2d13c-106">.NET Framework 4 では、XAML 関連の型の一部が、システムの .Xaml アセンブリに移行されます。</span><span class="sxs-lookup"><span data-stu-id="2d13c-106">In the .NET Framework 4, some of the XAML-related types are migrated to the System.Xaml assembly.</span></span> <span data-ttu-id="2d13c-107">XAML 言語サービスの一般的な .NET Framework 実装により、特定のフレームワークの XAML 実装によって最初に定義された XAML 拡張シナリオの多くが可能になりますが、.NET Framework 4 の XAML 言語サポート全体に含まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="2d13c-107">A common .NET Framework implementation of XAML language services enables many XAML extensibility scenarios that were originally defined by a specific framework's XAML implementation but are now part of overall .NET Framework 4 XAML language support.</span></span> <span data-ttu-id="2d13c-108">このトピックでは、移行された型を紹介し、移行に伴う問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="2d13c-108">This topic lists the types that are migrated and discusses issues related to the migration.</span></span>  
  
<a name="assemblies_and_namespaces"></a>   
## <a name="assemblies-and-namespaces"></a><span data-ttu-id="2d13c-109">アセンブリと名前空間</span><span class="sxs-lookup"><span data-stu-id="2d13c-109">Assemblies and Namespaces</span></span>  
 <span data-ttu-id="2d13c-110">.NET Framework 3.5 および .NET Framework 3.0 では、WPF が XAML をサポートするために実装する型<xref:System.Windows.Markup>は、一般に名前空間にありました。</span><span class="sxs-lookup"><span data-stu-id="2d13c-110">In .NET Framework 3.5 and .NET Framework 3.0, the types that WPF implemented to support XAML were generally in the <xref:System.Windows.Markup> namespace.</span></span> <span data-ttu-id="2d13c-111">これらの型の多くは WindowsBase アセンブリにありました。</span><span class="sxs-lookup"><span data-stu-id="2d13c-111">Most of these types were in the WindowsBase assembly.</span></span>  
  
 <span data-ttu-id="2d13c-112">.NET Framework 4 では、新しい<xref:System.Xaml>名前空間と新しい app.xaml アセンブリがあります。</span><span class="sxs-lookup"><span data-stu-id="2d13c-112">In .NET Framework 4, there is a new <xref:System.Xaml> namespace and a new System.Xaml assembly.</span></span> <span data-ttu-id="2d13c-113">当初は WPF XAML 向けとして実装されていた型の多くが、今では XAML の任意の実装用の機能拡張ポイントまたはサービスとして提供されています。</span><span class="sxs-lookup"><span data-stu-id="2d13c-113">Many of the types that were originally implemented for WPF XAML are now provided as extensibility points or services for any implementation of XAML.</span></span> <span data-ttu-id="2d13c-114">より一般的なシナリオでも使用できるようにするため、型は元の WPF アセンブリから System.Xaml アセンブリに型転送されました。</span><span class="sxs-lookup"><span data-stu-id="2d13c-114">As part of making them available for more general scenarios, the types are type-forwarded from their original WPF assembly to the System.Xaml assembly.</span></span> <span data-ttu-id="2d13c-115">これにより、他のフレームワーク (WPF や Windows Workflow Foundation など) のアセンブリを含めなくても、XAML 拡張シナリオが可能になります。</span><span class="sxs-lookup"><span data-stu-id="2d13c-115">This enables XAML extensibility scenarios without having to include the assemblies of other frameworks (such as WPF and Windows Workflow Foundation).</span></span>  
  
 <span data-ttu-id="2d13c-116">移行した型のほとんどは、 <xref:System.Windows.Markup> 名前空間に残っています。</span><span class="sxs-lookup"><span data-stu-id="2d13c-116">For migrated types, most of the types remain in the <xref:System.Windows.Markup> namespace.</span></span> <span data-ttu-id="2d13c-117">これは、既存の実装で CLR 名前空間マッピングが破損するのをファイルごとに回避するための策でもあります。</span><span class="sxs-lookup"><span data-stu-id="2d13c-117">This was partially to avoid breaking CLR namespace mappings in existing implementations on a per-file basis.</span></span> <span data-ttu-id="2d13c-118">その結果<xref:System.Windows.Markup> 、.NET Framework 4 の名前空間には、xaml 言語の一般的なサポート型 (app.xaml アセンブリ) と wpf xaml の実装に固有の型 (windowsbase およびその他の wpf アセンブリからのもの) が混在しています。</span><span class="sxs-lookup"><span data-stu-id="2d13c-118">As a result, the <xref:System.Windows.Markup> namespace in .NET Framework 4 contains a mixture of general XAML language support types (from the System.Xaml assembly) and types that are specific to the WPF XAML implementation (from WindowsBase and other WPF assemblies).</span></span> <span data-ttu-id="2d13c-119">System.Xaml に移行されたものの、以前は WPF アセンブリにあった型は、バージョン 4 の WPF アセンブリで型転送がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2d13c-119">Any type that was migrated to System.Xaml, but existed previously in a WPF assembly, has type-forwarding support in version 4 of the WPF assembly.</span></span>  
  
### <a name="workflow-xaml-support-types"></a><span data-ttu-id="2d13c-120">ワークフロー XAML サポート型</span><span class="sxs-lookup"><span data-stu-id="2d13c-120">Workflow XAML Support Types</span></span>  
 <span data-ttu-id="2d13c-121">Windows Workflow Foundation XAML サポート型も提供されており、多くの場合、同じ短い名前が WPF と同等のものになっていました。</span><span class="sxs-lookup"><span data-stu-id="2d13c-121">Windows Workflow Foundation also provided XAML support types, and in many cases these had identical short names to a WPF equivalent.</span></span> <span data-ttu-id="2d13c-122">Windows Workflow Foundation XAML サポート型の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2d13c-122">The following is a list of Windows Workflow Foundation XAML support types:</span></span>  
  
- <xref:System.Workflow.ComponentModel.Serialization.ContentPropertyAttribute>  
  
- <xref:System.Workflow.ComponentModel.Serialization.RuntimeNamePropertyAttribute>  
  
- <xref:System.Workflow.ComponentModel.Serialization.XmlnsPrefixAttribute>  
  
 <span data-ttu-id="2d13c-123">これらのサポートの種類は、.NET Framework 4 の Windows Workflow Foundation アセンブリにまだ存在しており、特定の Windows Workflow Foundation アプリケーションで引き続き使用できます。ただし、Windows Workflow Foundation を使用しないアプリケーションまたはフレームワークによって参照されないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d13c-123">These support types still exist in the Windows Workflow Foundation assemblies for .NET Framework 4 and can still be used for specific Windows Workflow Foundation applications; however, they should not be referenced by applications or frameworks that do not use Windows Workflow Foundation.</span></span>  
  
<a name="markupextension"></a>   
## <a name="markupextension"></a><span data-ttu-id="2d13c-124">MarkupExtension</span><span class="sxs-lookup"><span data-stu-id="2d13c-124">MarkupExtension</span></span>  
 <span data-ttu-id="2d13c-125">.NET Framework 3.5 と .NET Framework 3.0 <xref:System.Windows.Markup.MarkupExtension>では、WPF のクラスは windowsbase アセンブリにありました。</span><span class="sxs-lookup"><span data-stu-id="2d13c-125">In the .NET Framework 3.5 and .NET Framework 3.0, the <xref:System.Windows.Markup.MarkupExtension> class for WPF was in the WindowsBase assembly.</span></span> <span data-ttu-id="2d13c-126">Windows Workflow Foundation <xref:System.Workflow.ComponentModel.Serialization.MarkupExtension>の並列クラスは、system.componentmodel アセンブリに存在していました。</span><span class="sxs-lookup"><span data-stu-id="2d13c-126">A parallel class for Windows Workflow Foundation, <xref:System.Workflow.ComponentModel.Serialization.MarkupExtension>, existed in the System.Workflow.ComponentModel assembly.</span></span> <span data-ttu-id="2d13c-127">.NET Framework 4 では、クラス<xref:System.Windows.Markup.MarkupExtension>がシステムの .xaml アセンブリに移行されます。</span><span class="sxs-lookup"><span data-stu-id="2d13c-127">In the .NET Framework 4, the <xref:System.Windows.Markup.MarkupExtension> class is migrated to the System.Xaml assembly.</span></span> <span data-ttu-id="2d13c-128">.NET Framework 4 では、 <xref:System.Windows.Markup.MarkupExtension>は、特定のフレームワーク上に構築される xaml 機能拡張シナリオだけでなく、.NET Framework の xaml サービスを使用するすべての xaml 機能拡張シナリオを対象としています。</span><span class="sxs-lookup"><span data-stu-id="2d13c-128">In the .NET Framework 4, <xref:System.Windows.Markup.MarkupExtension> is intended for any XAML extensibility scenario that uses .NET Framework XAML Services, not just for those that build on specific frameworks.</span></span> <span data-ttu-id="2d13c-129">特定のフレームワーク、またはフレームワーク内のユーザー コードも、可能な限り、XAML 機能拡張の <xref:System.Windows.Markup.MarkupExtension> クラス上に構築する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d13c-129">When possible, specific frameworks or user code in the framework should also build on the <xref:System.Windows.Markup.MarkupExtension> class for XAML extension.</span></span>  
  
<a name="markupextension_supporting_service_classes"></a>   
## <a name="markupextension-supporting-service-classes"></a><span data-ttu-id="2d13c-130">MarkupExtension をサポートするサービス クラス</span><span class="sxs-lookup"><span data-stu-id="2d13c-130">MarkupExtension Supporting Service Classes</span></span>  
 <span data-ttu-id="2d13c-131">.NET Framework 3.5 および .NET Framework 3.0 for WPF では、XAML での型<xref:System.Windows.Markup.MarkupExtension>とプロパティ<xref:System.ComponentModel.TypeConverter>の使用をサポートするために実装および実装で利用できるいくつかのサービスが提供されています。</span><span class="sxs-lookup"><span data-stu-id="2d13c-131">.NET Framework 3.5 and .NET Framework 3.0 for WPF provided several services that were available to <xref:System.Windows.Markup.MarkupExtension> implementers and <xref:System.ComponentModel.TypeConverter> implementations to support type/property usage in XAML.</span></span> <span data-ttu-id="2d13c-132">これらのサービスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="2d13c-132">These services are the following:</span></span>  
  
- <xref:System.Windows.Markup.IProvideValueTarget>  
  
- <xref:System.Windows.Markup.IUriContext>  
  
- <xref:System.Windows.Markup.IXamlTypeResolver>  
  
> [!NOTE]
> <span data-ttu-id="2d13c-133">マークアップ拡張機能に関連する .NET Framework 3.5 の別のサービス<xref:System.Windows.Markup.IReceiveMarkupExtension>は、インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="2d13c-133">Another service from .NET Framework 3.5 that is related to markup extensions is the <xref:System.Windows.Markup.IReceiveMarkupExtension> interface.</span></span> <span data-ttu-id="2d13c-134"><xref:System.Windows.Markup.IReceiveMarkupExtension>は移行されなかった`[Obsolete]`ため、.NET Framework 4 用にマークされています。</span><span class="sxs-lookup"><span data-stu-id="2d13c-134"><xref:System.Windows.Markup.IReceiveMarkupExtension> was not migrated and is marked `[Obsolete]` for .NET Framework 4.</span></span> <span data-ttu-id="2d13c-135">以前に <xref:System.Windows.Markup.IReceiveMarkupExtension> を使用していたシナリオは、代わりに <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute> 属性付きコールバックを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d13c-135">Scenarios that previously used <xref:System.Windows.Markup.IReceiveMarkupExtension> should instead use <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute> attributed callbacks.</span></span> <span data-ttu-id="2d13c-136"><xref:System.Windows.Markup.AcceptedMarkupExtensionExpressionTypeAttribute> も `[Obsolete]`とマーク付けされています。</span><span class="sxs-lookup"><span data-stu-id="2d13c-136"><xref:System.Windows.Markup.AcceptedMarkupExtensionExpressionTypeAttribute> is also marked `[Obsolete]`.</span></span>  
  
<a name="xaml_language_features"></a>   
## <a name="xaml-language-features"></a><span data-ttu-id="2d13c-137">XAML 言語機能</span><span class="sxs-lookup"><span data-stu-id="2d13c-137">XAML Language Features</span></span>  
 <span data-ttu-id="2d13c-138">WPF 向けのいくつかの XAML 言語機能とコンポーネントは、以前は PresentationFramework アセンブリにありました。</span><span class="sxs-lookup"><span data-stu-id="2d13c-138">Several XAML language features and components for WPF previously existed in the PresentationFramework assembly.</span></span> <span data-ttu-id="2d13c-139">これらの機能やコンポーネントは <xref:System.Windows.Markup.MarkupExtension> のサブクラスとして実装され、XAML マークアップでのマークアップ拡張機能の使用を公開していました。</span><span class="sxs-lookup"><span data-stu-id="2d13c-139">These were implemented as a <xref:System.Windows.Markup.MarkupExtension> subclass to expose markup extension usages in XAML markup.</span></span> <span data-ttu-id="2d13c-140">.NET Framework 4 では、これらは app.xaml アセンブリに存在するため、WPF アセンブリを含まないプロジェクトでこれらの XAML 言語レベルの機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2d13c-140">In .NET Framework 4, these exist in the System.Xaml assembly so that projects that do not include WPF assemblies can use these XAML language-level features.</span></span> <span data-ttu-id="2d13c-141">WPF では、これらの同じ実装を .NET Framework 4 アプリケーションに使用します。</span><span class="sxs-lookup"><span data-stu-id="2d13c-141">WPF uses these same implementations for .NET Framework 4 applications.</span></span> <span data-ttu-id="2d13c-142">このトピックで示す他のケースと同様に、サポート型は <xref:System.Windows.Markup> 名前空間に引き続き存在するので、以前の参照は破損されません。</span><span class="sxs-lookup"><span data-stu-id="2d13c-142">As with the other cases that are listed in this topic, the supporting types continue to exist in the <xref:System.Windows.Markup> namespace to avoid breaking previous references.</span></span>  
  
 <span data-ttu-id="2d13c-143">System.Xaml で定義されている XAML 機能のサポート クラスを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="2d13c-143">The following table contains a list of the XAML feature-support classes that are defined in System.Xaml.</span></span>  
  
|<span data-ttu-id="2d13c-144">XAML 言語機能</span><span class="sxs-lookup"><span data-stu-id="2d13c-144">XAML Language Feature</span></span>|<span data-ttu-id="2d13c-145">使用法</span><span class="sxs-lookup"><span data-stu-id="2d13c-145">Usage</span></span>|  
|---------------------------|-----------|  
|<xref:System.Windows.Markup.ArrayExtension>|`<x:Array ...>`|  
|<xref:System.Windows.Markup.NullExtension>|`{x:Null}`|  
|<xref:System.Windows.Markup.StaticExtension>|`{x:Static ...}`|  
|<xref:System.Windows.Markup.TypeExtension>|`{x:Type ...}`|  
  
 <span data-ttu-id="2d13c-146">System.Xaml には特定のサポート クラスはありませんが、XAML 言語の言語機能を処理するための一般的なロジックは System.Xaml にあり、それを実装した XAML リーダーと XAML ライターにも含まれています。</span><span class="sxs-lookup"><span data-stu-id="2d13c-146">Although System.Xaml may not have specific support classes, the general logic for processing language features for the XAML language now resides in System.Xaml and its implemented XAML readers and XAML writers.</span></span> <span data-ttu-id="2d13c-147">たとえば、 `x:TypeArguments` は System.Xaml 実装の XAML リーダーと XAML ライターによって処理される属性です。これは XAML ノード ストリームで示すことができ、既定の (CLR ベースの) XAML スキーマ コンテキストに処理があり、XAML 型システム表現があります。</span><span class="sxs-lookup"><span data-stu-id="2d13c-147">For example, `x:TypeArguments` is an attribute that is processed by XAML readers and XAML writers from System.Xaml implementations; it can be noted in the XAML node stream, has handling in the default (CLR-based) XAML schema context, has a XAML type-system representation, and so on.</span></span> <span data-ttu-id="2d13c-148">その結果、XAML 言語レベルのすべての機能に関するリファレンス ドキュメントは、WPF ドキュメント セットに属する[詳細設定 (Windows Presentation Foundation)](../wpf/advanced/index.md) ではなく (3.5 のドキュメント セットは今でもこちらにあります)、 [XAML Service](index.md)に関するページという扱いで .NET Framework ドキュメント セットの一般分野のサブトピックとして掲載されています。</span><span class="sxs-lookup"><span data-stu-id="2d13c-148">As a result, the reference documentation for all XAML language-level features is a subtopic for [XAML Services](index.md) and that general area of the .NET Framework documentation set, instead of being part of the WPF documentation set as a subtopic of [Advanced (Windows Presentation Foundation)](../wpf/advanced/index.md) (as is still the case in 3.5 documentation sets).</span></span>  
  
<a name="valueserializer_and_supporting_classes"></a>   
## <a name="valueserializer-and-supporting-classes"></a><span data-ttu-id="2d13c-149">ValueSerializer とサポートするクラス</span><span class="sxs-lookup"><span data-stu-id="2d13c-149">ValueSerializer and Supporting Classes</span></span>  
 <span data-ttu-id="2d13c-150"><xref:System.Windows.Markup.ValueSerializer> クラスは、特に、シリアル化のために出力に複数のモードまたはノードが必要となる XAML シリアル化のケースで、文字列への型変換をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2d13c-150">The <xref:System.Windows.Markup.ValueSerializer> class supports type conversion to a string, particularly for XAML serialization cases where serialization may require multiple modes or nodes in the output.</span></span> <span data-ttu-id="2d13c-151">.NET Framework 3.5 および .NET Framework 3.0 では、 <xref:System.Windows.Markup.ValueSerializer> WPF のは windowsbase アセンブリにありました。</span><span class="sxs-lookup"><span data-stu-id="2d13c-151">In .NET Framework 3.5 and .NET Framework 3.0, the <xref:System.Windows.Markup.ValueSerializer> for WPF was in the WindowsBase assembly.</span></span> <span data-ttu-id="2d13c-152">.NET Framework 4 <xref:System.Windows.Markup.ValueSerializer>では、クラスは app.xaml にあり、WPF 上に構築されたものだけでなく、すべての xaml 機能拡張シナリオを対象としています。</span><span class="sxs-lookup"><span data-stu-id="2d13c-152">In the .NET Framework 4, the <xref:System.Windows.Markup.ValueSerializer> class is in System.Xaml and is intended for any XAML extensibility scenario, not just for those that build on WPF.</span></span> <span data-ttu-id="2d13c-153"><xref:System.Windows.Markup.IValueSerializerContext> (サポート サービス) および <xref:System.Windows.Markup.DateTimeValueSerializer> (固有のサブクラス) も System.Xaml に移行されました。</span><span class="sxs-lookup"><span data-stu-id="2d13c-153"><xref:System.Windows.Markup.IValueSerializerContext> (a supporting service) and <xref:System.Windows.Markup.DateTimeValueSerializer> (a specific subclass) are also migrated to System.Xaml.</span></span>  
  
<a name="xamlrelated_attributes"></a>   
## <a name="xaml-related-attributes"></a><span data-ttu-id="2d13c-154">XAML 関連の属性</span><span class="sxs-lookup"><span data-stu-id="2d13c-154">XAML-Related Attributes</span></span>  
 <span data-ttu-id="2d13c-155">WPF XAML には、XAML の動作について何かを示すために CLR 型に適用される属性がいくつか含まれています。</span><span class="sxs-lookup"><span data-stu-id="2d13c-155">WPF XAML included several attributes that can be applied to CLR types to indicate something about their XAML behavior.</span></span> <span data-ttu-id="2d13c-156">.NET Framework 3.5 および .NET Framework 3.0 の WPF アセンブリに存在していた属性の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2d13c-156">The following is a list of the attributes that existed in WPF assemblies in .NET Framework 3.5 and .NET Framework 3.0.</span></span> <span data-ttu-id="2d13c-157">これらの属性は .NET Framework 4 の Page.xaml に移行されます。</span><span class="sxs-lookup"><span data-stu-id="2d13c-157">These attributes are migrated to System.Xaml in .NET Framework 4.</span></span>  
  
- <xref:System.Windows.Markup.AmbientAttribute>  
  
- <xref:System.Windows.Markup.ContentPropertyAttribute>  
  
- <xref:System.Windows.Markup.ContentWrapperAttribute>  
  
- <xref:System.Windows.Markup.DependsOnAttribute>  
  
- <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute>  
  
- <xref:System.Windows.Markup.NameScopePropertyAttribute>  
  
- <xref:System.Windows.Markup.RootNamespaceAttribute>  
  
- <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>  
  
- <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>  
  
- <xref:System.Windows.Markup.ValueSerializerAttribute>  
  
- <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>  
  
- <xref:System.Windows.Markup.XmlLangPropertyAttribute>  
  
- <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>  
  
- <xref:System.Windows.Markup.XmlnsDefinitionAttribute>  
  
- <xref:System.Windows.Markup.XmlnsPrefixAttribute>  
  
<a name="miscellaneous_classes"></a>   
## <a name="miscellaneous-classes"></a><span data-ttu-id="2d13c-158">その他のクラス</span><span class="sxs-lookup"><span data-stu-id="2d13c-158">Miscellaneous Classes</span></span>  
 <span data-ttu-id="2d13c-159">この<xref:System.Windows.Markup.IComponentConnector>インターフェイスは、.NET Framework 3.5 および .NET Framework 3.0 の windowsbase にありましたが、.NET Framework 4 の page.xaml に存在します。</span><span class="sxs-lookup"><span data-stu-id="2d13c-159">The <xref:System.Windows.Markup.IComponentConnector> interface existed in WindowsBase in the .NET Framework 3.5 and .NET Framework 3.0, but exists in System.Xaml in .NET Framework 4.</span></span> <span data-ttu-id="2d13c-160"><xref:System.Windows.Markup.IComponentConnector> は、主にツーリングのサポートと XAML マークアップ コンパイラーを目的としています。</span><span class="sxs-lookup"><span data-stu-id="2d13c-160"><xref:System.Windows.Markup.IComponentConnector> is primarily intended for tooling support and XAML markup compilers.</span></span>  
  
 <span data-ttu-id="2d13c-161">この<xref:System.Windows.Markup.INameScope>インターフェイスは、.NET Framework 3.5 および .NET Framework 3.0 の windowsbase にありましたが、.NET Framework 4 の page.xaml に存在します。</span><span class="sxs-lookup"><span data-stu-id="2d13c-161">The <xref:System.Windows.Markup.INameScope> interface existed in WindowsBase in the .NET Framework 3.5 and .NET Framework 3.0, but exists in System.Xaml in .NET Framework 4.</span></span> <span data-ttu-id="2d13c-162"><xref:System.Windows.Markup.INameScope> は、XAML 名前空間に対する基本的な操作を定義します。</span><span class="sxs-lookup"><span data-stu-id="2d13c-162"><xref:System.Windows.Markup.INameScope> defines basic operations for a XAML namescope.</span></span>  
  
<a name="xamlrelated_classes_with_shared_names_that_exist_in_wpf_and_systemxaml"></a>   
## <a name="xaml-related-classes-with-shared-names-that-exist-in-wpf-and-systemxaml"></a><span data-ttu-id="2d13c-163">WPF と System.Xaml に存在する共通の名前を持つ XAML 関連クラス</span><span class="sxs-lookup"><span data-stu-id="2d13c-163">XAML-related Classes with Shared Names that Exist in WPF and System.Xaml</span></span>  
 <span data-ttu-id="2d13c-164">次のクラスは、.NET Framework 4 の WPF アセンブリと .Xaml アセンブリの両方に存在します。</span><span class="sxs-lookup"><span data-stu-id="2d13c-164">The following classes exist in both the WPF assemblies and the System.Xaml assembly in the .NET Framework 4:</span></span>  
  
 `XamlReader`  
  
 `XamlWriter`  
  
 `XamlParseException`  
  
 <span data-ttu-id="2d13c-165">WPF 実装は、 <xref:System.Windows.Markup> 名前空間にあり、PresentationFramework アセンブリに含まれています。</span><span class="sxs-lookup"><span data-stu-id="2d13c-165">The WPF implementation is found in the <xref:System.Windows.Markup> namespace, and PresentationFramework assembly.</span></span> <span data-ttu-id="2d13c-166">System.Xaml 実装は、 <xref:System.Xaml> 名前空間にあります。</span><span class="sxs-lookup"><span data-stu-id="2d13c-166">The System.Xaml implementation is found in the <xref:System.Xaml> namespace.</span></span> <span data-ttu-id="2d13c-167">WPF 型を使用する場合や、WPF 型から派生する場合は、一般に、System.Xaml 実装ではなく <xref:System.Windows.Markup.XamlReader> および <xref:System.Windows.Markup.XamlWriter> の WPF 実装を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d13c-167">If you are using WPF types or are deriving from WPF types, you should typically use the WPF implementations of <xref:System.Windows.Markup.XamlReader> and <xref:System.Windows.Markup.XamlWriter> instead of the System.Xaml implementations.</span></span> <span data-ttu-id="2d13c-168">詳細については、 <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> および <xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType>の解説セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d13c-168">For more information, see Remarks in <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> and <xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="2d13c-169">WPF アセンブリと System.Xaml の両方を参照しており、 `include` 名前空間と <xref:System.Windows.Markup> 名前空間の両方に対して <xref:System.Xaml> ステートメントを使用している場合は、あいまいさを排除して型を解決するために、これらの API への呼び出しを完全修飾する必要があることがあります。</span><span class="sxs-lookup"><span data-stu-id="2d13c-169">If you are including references to both WPF assemblies and System.Xaml, and you also are using `include` statements for both the <xref:System.Windows.Markup> and <xref:System.Xaml> namespaces, you may need to fully qualify the calls to these APIs in order to resolve the types without ambiguity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d13c-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d13c-170">See also</span></span>

- [<span data-ttu-id="2d13c-171">XAML サービス</span><span class="sxs-lookup"><span data-stu-id="2d13c-171">XAML Services</span></span>](index.md)
