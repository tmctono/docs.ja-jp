---
title: カスタム型およびライブラリの XAML 関連の CLR 属性
ms.date: 03/30/2017
helpviewer_keywords:
- CLR attributes for custom types [XAML Services]
ms.assetid: 5dfb299a-b6e2-41b8-8694-e6ac987547f1
ms.openlocfilehash: 5481d02e4d393312fa0f0dd13b45c54acc567e13
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432984"
---
# <a name="xaml-related-clr-attributes-for-custom-types-and-libraries"></a><span data-ttu-id="801cb-102">カスタム型とカスタム ライブラリの XAML 関連の CLR 属性</span><span class="sxs-lookup"><span data-stu-id="801cb-102">XAML-related CLR attributes for custom types and libraries</span></span>

<span data-ttu-id="801cb-103">このトピックでは、.NET XAML サービスによって定義される共通言語ランタイム (CLR) 属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="801cb-103">This topic describes the common language runtime (CLR) attributes that are defined by .NET XAML Services.</span></span> <span data-ttu-id="801cb-104">また、アセンブリまたは型へのアプリケーションの XAML 関連のシナリオを持つ .NET で定義されている他の CLR 属性についても説明します。</span><span class="sxs-lookup"><span data-stu-id="801cb-104">It also describes other CLR attributes that are defined in .NET that have a XAML-related scenario for application to assemblies or types.</span></span> <span data-ttu-id="801cb-105">これらの CLR 属性を持つアセンブリ、型、またはメンバーに対する属性は、型に関連する XAML 型システム情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="801cb-105">Attributing assemblies, types, or members with these CLR attributes provides XAML type system information related to your types.</span></span> <span data-ttu-id="801cb-106">情報は、XAML ノード ストリームを直接処理するために .NET XAML サービスを使用する任意の XAML コンシューマーに提供されるか、専用の XAML リーダーと XAML ライターを介して提供されます。</span><span class="sxs-lookup"><span data-stu-id="801cb-106">Information is provided to any XAML consumer that uses .NET XAML Services for processing the XAML node stream directly or through the dedicated XAML readers and XAML writers.</span></span>

## <a name="xaml-related-clr-attributes-for-custom-types-and-custom-members"></a><span data-ttu-id="801cb-107">カスタム型とカスタム メンバーの XAML 関連の CLR 属性</span><span class="sxs-lookup"><span data-stu-id="801cb-107">XAML-Related CLR Attributes for Custom Types and Custom Members</span></span>

<span data-ttu-id="801cb-108">CLR 属性を使用すると、CLR 全体を使用して型を定義することになります。</span><span class="sxs-lookup"><span data-stu-id="801cb-108">Using CLR attributes entails that you are using the overall CLR to define your types, otherwise such attributes are not available.</span></span> <span data-ttu-id="801cb-109">CLR を使用して型バッキングを定義する場合、.NET XAML サービス XAML ライターが使用する既定の XAML スキーマ コンテキストは、アセンブリのバッキングに対するリフレクションを通じて CLR 属性を読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="801cb-109">If you use the CLR to define type backing, then the default XAML schema context used by .NET XAML Services XAML writers can read CLR attribution through reflection against backing assemblies.</span></span>

<span data-ttu-id="801cb-110">次のセクションでは、カスタム型またはカスタム メンバーに適用できる XAML 関連の属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="801cb-110">The following sections describe the XAML-related attributes that you can apply to custom types or custom members.</span></span> <span data-ttu-id="801cb-111">各 CLR 属性は、XAML 型システムに関連する情報を伝達します。</span><span class="sxs-lookup"><span data-stu-id="801cb-111">Each CLR attribute communicates information that is relevant to a XAML type system.</span></span> <span data-ttu-id="801cb-112">読み込みパスでは、属性付き情報は、XAML リーダーが有効な XAML ノード ストリームを形成するのに役立つか、XAML ライターが有効なオブジェクト グラフを生成するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="801cb-112">In the load path, the attributed information either helps the XAML reader form a valid XAML node stream, or it helps the XAML writer produce a valid object graph.</span></span> <span data-ttu-id="801cb-113">保存パスでは、属性付きの情報は、XAML リーダーが XAML 型システム情報を再構成する有効な XAML ノード ストリームを形成するのに役立ちます。または、XAML ライターまたはその他の XAML コンシューマーのシリアル化ヒントまたは要件を宣言します。</span><span class="sxs-lookup"><span data-stu-id="801cb-113">In the save path, the attributed information either helps the XAML reader form a valid XAML node stream that reconstitutes XAML type system information; or it declares serialization hints or requirements for the XAML writer or other XAML consumers.</span></span>

### <a name="ambientattribute"></a><span data-ttu-id="801cb-114">アンビエント属性</span><span class="sxs-lookup"><span data-stu-id="801cb-114">AmbientAttribute</span></span>

<span data-ttu-id="801cb-115">**リファレンス ドキュメント:**<xref:System.Windows.Markup.AmbientAttribute></span><span class="sxs-lookup"><span data-stu-id="801cb-115">**Reference Documentation:** <xref:System.Windows.Markup.AmbientAttribute></span></span>

<span data-ttu-id="801cb-116">**適用対象:** アタッチ可能なプロパティを`get`サポートするクラス、プロパティ、またはアクセサーのメンバー。</span><span class="sxs-lookup"><span data-stu-id="801cb-116">**Applies to:** Class, property, or `get` accessor members that support attachable properties.</span></span>

<span data-ttu-id="801cb-117">**引数:** なし</span><span class="sxs-lookup"><span data-stu-id="801cb-117">**Arguments:** None</span></span>

<span data-ttu-id="801cb-118"><xref:System.Windows.Markup.AmbientAttribute>プロパティ、または属性付きの型を受け取るすべてのプロパティは、XAML のアンビエント プロパティの概念の下で解釈されることを示します。</span><span class="sxs-lookup"><span data-stu-id="801cb-118"><xref:System.Windows.Markup.AmbientAttribute> indicates that the property, or all properties that take the attributed type, should be interpreted under the ambient property concept in XAML.</span></span> <span data-ttu-id="801cb-119">アンビエントの概念は XAML プロセッサがメンバーの型の所有者を確認する方法と関連します。</span><span class="sxs-lookup"><span data-stu-id="801cb-119">The ambient concept relates to how XAML processors determine type owners of members.</span></span> <span data-ttu-id="801cb-120">アンビエント プロパティは、オブジェクト グラフを作成するときにパーサー コンテキストで値が使用できると予想されるが、作成される直接の XAML ノード セットに対して通常の型メンバー検索が中断されるプロパティです。</span><span class="sxs-lookup"><span data-stu-id="801cb-120">An ambient property is a property where the value is expected to be available in the parser context when creating an object graph, but where typical type-member lookup is suspended for the immediate XAML node set being created.</span></span>

<span data-ttu-id="801cb-121">アンビエント概念は、CLR 属性が定義<xref:System.AttributeTargets>する方法のプロパティとして表されないアタッチ可能なメンバーに適用できます。</span><span class="sxs-lookup"><span data-stu-id="801cb-121">The ambient concept can be applied to attachable members, which are not represented as properties in terms of how CLR attribution defines <xref:System.AttributeTargets>.</span></span> <span data-ttu-id="801cb-122">メソッドのアトリビューションの使用方法は、XAML のアタッチ`get`可能な使用法をサポートするアクセサーにのみ適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="801cb-122">The method attribution usage should be applied only for a `get` accessor that supports attachable usage for XAML.</span></span>

### <a name="constructorargumentattribute"></a><span data-ttu-id="801cb-123">コンストラクター属性</span><span class="sxs-lookup"><span data-stu-id="801cb-123">ConstructorArgumentAttribute</span></span>

<span data-ttu-id="801cb-124">**リファレンス ドキュメント:**  <xref:System.Windows.Markup.ConstructorArgumentAttribute></span><span class="sxs-lookup"><span data-stu-id="801cb-124">**Reference Documentation:**  <xref:System.Windows.Markup.ConstructorArgumentAttribute></span></span>

<span data-ttu-id="801cb-125">**適用対象:** クラス</span><span class="sxs-lookup"><span data-stu-id="801cb-125">**Applies to:** Class</span></span>

<span data-ttu-id="801cb-126">**引数:** 1 つのコンストラクター引数に一致するプロパティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="801cb-126">**Arguments:** A string that specifies the name of the property that matches a single constructor argument.</span></span>

<span data-ttu-id="801cb-127"><xref:System.Windows.Markup.ConstructorArgumentAttribute>パラメーターなしのコンストラクター構文を使用してオブジェクトを初期化できること、および指定した名前のプロパティが構築情報を提供することを指定します。</span><span class="sxs-lookup"><span data-stu-id="801cb-127"><xref:System.Windows.Markup.ConstructorArgumentAttribute> specifies that an object can be initialized by using a non-parameterless constructor syntax, and that a property of the specified name supplies construction information.</span></span> <span data-ttu-id="801cb-128">この情報は主に XAML シリアル化用です。</span><span class="sxs-lookup"><span data-stu-id="801cb-128">This information is primarily for XAML serialization.</span></span> <span data-ttu-id="801cb-129">詳細については、「<xref:System.Windows.Markup.ConstructorArgumentAttribute>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="801cb-129">For more information, see <xref:System.Windows.Markup.ConstructorArgumentAttribute>.</span></span>

### <a name="contentpropertyattribute"></a><span data-ttu-id="801cb-130">プロパティ属性</span><span class="sxs-lookup"><span data-stu-id="801cb-130">ContentPropertyAttribute</span></span>

<span data-ttu-id="801cb-131">**リファレンス ドキュメント:**  <xref:System.Windows.Markup.ContentPropertyAttribute></span><span class="sxs-lookup"><span data-stu-id="801cb-131">**Reference Documentation:**  <xref:System.Windows.Markup.ContentPropertyAttribute></span></span>

<span data-ttu-id="801cb-132">**適用対象:** クラス</span><span class="sxs-lookup"><span data-stu-id="801cb-132">**Applies to:** Class</span></span>

<span data-ttu-id="801cb-133">**引数:** 属性付き型のメンバーの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="801cb-133">**Arguments:** A string that specifies the name of a member of the attributed type.</span></span>

<span data-ttu-id="801cb-134"><xref:System.Windows.Markup.ContentPropertyAttribute>は、引数によって指定されたプロパティが、その型の XAML コンテンツ プロパティとして機能することを示します。</span><span class="sxs-lookup"><span data-stu-id="801cb-134"><xref:System.Windows.Markup.ContentPropertyAttribute> indicates that the property as named by the argument should serve as the XAML content property for that type.</span></span> <span data-ttu-id="801cb-135">XAML コンテンツ プロパティ定義は、定義する型に割り当て可能なすべての派生型に継承されます。</span><span class="sxs-lookup"><span data-stu-id="801cb-135">The XAML content property definition inherits to all derived types that are assignable to the defining type.</span></span> <span data-ttu-id="801cb-136">特定の派生型に適用することで、特定の派生型の<xref:System.Windows.Markup.ContentPropertyAttribute>定義をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="801cb-136">You can override the definition on a specific derived type by applying <xref:System.Windows.Markup.ContentPropertyAttribute> on the specific derived type.</span></span>

<span data-ttu-id="801cb-137">XAML コンテンツ プロパティとして機能するプロパティの場合、プロパティのプロパティ要素のタグ付けを XAML の使用法で省略できます。</span><span class="sxs-lookup"><span data-stu-id="801cb-137">For the property that serves as the XAML content property, property element tagging for the property can be omitted in the XAML usage.</span></span> <span data-ttu-id="801cb-138">通常、コンテンツ モデルとコンテインメント モデルの合理化された XAML マークアップを昇格させる XAML コンテンツ プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="801cb-138">Typically, you designate XAML content properties that promote a streamlined XAML markup for your content and containment models.</span></span> <span data-ttu-id="801cb-139">XAML コンテンツ プロパティとして指定できるメンバーは 1 つだけであるため、XAML コンテンツ プロパティとして指定する必要がある型のコンテナー プロパティの中から、デザインを選択できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="801cb-139">Because only one member can be designated as the XAML content property, you sometimes have design choices to make regarding which of several container properties of a type should be designated as the XAML content property.</span></span> <span data-ttu-id="801cb-140">その他のコンテナー プロパティは、明示的なプロパティ要素と共に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="801cb-140">The other container properties must be used with explicit property elements.</span></span>

<span data-ttu-id="801cb-141">XAML ノード ストリームでは、XAML コンテンツ`StartMember`プロパティ`EndMember`は引き続き生成され、ノードは<xref:System.Xaml.XamlMember>.</span><span class="sxs-lookup"><span data-stu-id="801cb-141">In the XAML node stream, XAML content properties still produce `StartMember` and `EndMember` nodes, using the name of the property for the <xref:System.Xaml.XamlMember>.</span></span> <span data-ttu-id="801cb-142">メンバーが XAML コンテンツ プロパティかどうかを確認するには、位置<xref:System.Xaml.XamlType>から値を`StartObject`調べ、の値を<xref:System.Xaml.XamlType.ContentProperty%2A>取得します。</span><span class="sxs-lookup"><span data-stu-id="801cb-142">To determine whether a member is the XAML content property, examine the <xref:System.Xaml.XamlType> value from the `StartObject` position and obtain the value of <xref:System.Xaml.XamlType.ContentProperty%2A>.</span></span>

### <a name="contentwrapperattribute"></a><span data-ttu-id="801cb-143">コンテンツラッパー属性</span><span class="sxs-lookup"><span data-stu-id="801cb-143">ContentWrapperAttribute</span></span>

<span data-ttu-id="801cb-144">**リファレンス ドキュメント:**  <xref:System.Windows.Markup.ContentWrapperAttribute></span><span class="sxs-lookup"><span data-stu-id="801cb-144">**Reference Documentation:**  <xref:System.Windows.Markup.ContentWrapperAttribute></span></span>

<span data-ttu-id="801cb-145">**適用対象:** クラス、特にコレクション型。</span><span class="sxs-lookup"><span data-stu-id="801cb-145">**Applies to:** Class, specifically collection types.</span></span>

<span data-ttu-id="801cb-146">**引数:** 外部<xref:System.Type>コンテンツのコンテンツ ラッパー型として使用する型を指定する A。</span><span class="sxs-lookup"><span data-stu-id="801cb-146">**Arguments:** A <xref:System.Type> that specifies the type to use as the content wrapper type for foreign content.</span></span>

<span data-ttu-id="801cb-147"><xref:System.Windows.Markup.ContentWrapperAttribute>外部コンテンツのラップに使用される、関連付けられたコレクション型の 1 つ以上の型を指定します。</span><span class="sxs-lookup"><span data-stu-id="801cb-147"><xref:System.Windows.Markup.ContentWrapperAttribute> specifies one or more types on the associated collection type that will be used to wrap foreign content.</span></span> <span data-ttu-id="801cb-148">外部コンテンツとは、コンテンツ プロパティの型に対する型システムの制約が、所有する型の XAML の使用がサポートする可能性のあるコンテンツ ケースのすべてをキャプチャしない場合を指します。</span><span class="sxs-lookup"><span data-stu-id="801cb-148">Foreign content refers to cases where the type system constraints on the type of the content property do not capture all of the possible content cases that XAML usage for the owning type would support.</span></span> <span data-ttu-id="801cb-149">たとえば、特定の型のコンテンツに対する XAML サポートは、厳密に型<xref:System.Collections.ObjectModel.Collection%601>指定されたジェネリック の文字列をサポートする場合があります。</span><span class="sxs-lookup"><span data-stu-id="801cb-149">For example, XAML support for content of a particular type might support strings in a strongly typed generic <xref:System.Collections.ObjectModel.Collection%601>.</span></span> <span data-ttu-id="801cb-150">コンテンツ ラッパーは、テキスト関連のコンテンツ モデルの移行など、既存のマークアップ規則を XAML のコレクションに割り当て可能な値の概念に移行する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="801cb-150">Content wrappers are useful for migrating pre-existing markup conventions into XAML's conception of assignable values for collections, such as migrating text-related content models.</span></span>

<span data-ttu-id="801cb-151">複数のコンテンツ ラッパー タイプを指定するには、属性を複数回適用します。</span><span class="sxs-lookup"><span data-stu-id="801cb-151">To specify more than one content wrapper type, apply the attribute multiple times.</span></span>

### <a name="dependsonattribute"></a><span data-ttu-id="801cb-152">属性の指定</span><span class="sxs-lookup"><span data-stu-id="801cb-152">DependsOnAttribute</span></span>

<span data-ttu-id="801cb-153">**リファレンス ドキュメント:**  <xref:System.Windows.Markup.DependsOnAttribute></span><span class="sxs-lookup"><span data-stu-id="801cb-153">**Reference Documentation:**  <xref:System.Windows.Markup.DependsOnAttribute></span></span>

<span data-ttu-id="801cb-154">**適用対象:** プロパティ</span><span class="sxs-lookup"><span data-stu-id="801cb-154">**Applies to:** Property</span></span>

<span data-ttu-id="801cb-155">**引数:** 属性付き型の別のメンバーの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="801cb-155">**Arguments:** A string that specifies the name of another member of the attributed type.</span></span>

<span data-ttu-id="801cb-156"><xref:System.Windows.Markup.DependsOnAttribute>属性付きプロパティが別のプロパティの値に依存することを示します。</span><span class="sxs-lookup"><span data-stu-id="801cb-156"><xref:System.Windows.Markup.DependsOnAttribute> indicates that the attributed property depends on the value of another property.</span></span> <span data-ttu-id="801cb-157">この属性をプロパティ定義に適用すると、XAML オブジェクトの書き込み時に、依存プロパティが最初に処理されるようになります。</span><span class="sxs-lookup"><span data-stu-id="801cb-157">Applying this attribute to a property definition ensures that the dependent properties are processed first in XAML object writing.</span></span> <span data-ttu-id="801cb-158">の使用法<xref:System.Windows.Markup.DependsOnAttribute>は、有効なオブジェクトの作成のために解析の特定の順序に従う必要がある型のプロパティの例外的なケースを指定します。</span><span class="sxs-lookup"><span data-stu-id="801cb-158">Usages of <xref:System.Windows.Markup.DependsOnAttribute> specify the exceptional cases of properties on types where a specific order of parsing must be followed for valid object creation.</span></span>

<span data-ttu-id="801cb-159">プロパティ定義には複数<xref:System.Windows.Markup.DependsOnAttribute>のケースを適用できます。</span><span class="sxs-lookup"><span data-stu-id="801cb-159">You can apply multiple <xref:System.Windows.Markup.DependsOnAttribute> cases to a property definition.</span></span>

### <a name="markupextensionreturntypeattribute"></a><span data-ttu-id="801cb-160">プロパティの一種</span><span class="sxs-lookup"><span data-stu-id="801cb-160">MarkupExtensionReturnTypeAttribute</span></span>

<span data-ttu-id="801cb-161">**リファレンス ドキュメント:**  <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute></span><span class="sxs-lookup"><span data-stu-id="801cb-161">**Reference Documentation:**  <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute></span></span>

<span data-ttu-id="801cb-162">**適用対象:**<xref:System.Windows.Markup.MarkupExtension>派生型であることが予想されるクラス。</span><span class="sxs-lookup"><span data-stu-id="801cb-162">**Applies to:** Class, which is expected to be a <xref:System.Windows.Markup.MarkupExtension> derived type.</span></span>

<span data-ttu-id="801cb-163">**引数:** 属性<xref:System.Type>付`ProvideValue`<xref:System.Windows.Markup.MarkupExtension>きの結果として予想される最も正確な型を指定する A。</span><span class="sxs-lookup"><span data-stu-id="801cb-163">**Arguments:** A <xref:System.Type> that specifies the most precise type to expect as the `ProvideValue` result of the attributed <xref:System.Windows.Markup.MarkupExtension>.</span></span>

<span data-ttu-id="801cb-164">詳細については、「 [XAML の概要のマークアップ拡張機能](markup-extensions-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="801cb-164">For more information, see [Markup Extensions for XAML Overview](markup-extensions-overview.md).</span></span>

### <a name="namescopepropertyattribute"></a><span data-ttu-id="801cb-165">プロパティ属性</span><span class="sxs-lookup"><span data-stu-id="801cb-165">NameScopePropertyAttribute</span></span>

<span data-ttu-id="801cb-166">**リファレンス ドキュメント:**  <xref:System.Windows.Markup.NameScopePropertyAttribute></span><span class="sxs-lookup"><span data-stu-id="801cb-166">**Reference Documentation:**  <xref:System.Windows.Markup.NameScopePropertyAttribute></span></span>

<span data-ttu-id="801cb-167">**適用対象:** クラス</span><span class="sxs-lookup"><span data-stu-id="801cb-167">**Applies to:** Class</span></span>

<span data-ttu-id="801cb-168">**引数:** アトリビューションの 2 つの形式をサポートします。</span><span class="sxs-lookup"><span data-stu-id="801cb-168">**Arguments:** Supports two forms of attribution:</span></span>

- <span data-ttu-id="801cb-169">属性付き型のプロパティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="801cb-169">A string that specifies the name of a property on the attributed type.</span></span>

- <span data-ttu-id="801cb-170">プロパティの名前を指定する文字列と、名前付き<xref:System.Type>プロパティを定義する型のを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="801cb-170">A string that specifies the name of a property, and a <xref:System.Type> for the type that defines the named property.</span></span> <span data-ttu-id="801cb-171">このフォームは、XAML 名前スコープ プロパティとしてアタッチ可能なメンバーを指定するためのフォームです。</span><span class="sxs-lookup"><span data-stu-id="801cb-171">This form is for specifying an attachable member as the XAML namescope property.</span></span>

<span data-ttu-id="801cb-172"><xref:System.Windows.Markup.NameScopePropertyAttribute>属性付きクラスの XAML 名前スコープ値を提供するプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="801cb-172"><xref:System.Windows.Markup.NameScopePropertyAttribute> specifies a property that provides the XAML namescope value for the attributed class.</span></span> <span data-ttu-id="801cb-173">XAML 名前スコープ プロパティは、実際の XAML 名前<xref:System.Windows.Markup.INameScope>スコープ、ストア、および動作を実装し、保持するオブジェクトを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="801cb-173">The XAML namescope property is expected to reference an object that implements <xref:System.Windows.Markup.INameScope> and holds the actual XAML namescope, its store, and its behavior.</span></span>

### <a name="runtimenamepropertyattribute"></a><span data-ttu-id="801cb-174">プロパティ属性</span><span class="sxs-lookup"><span data-stu-id="801cb-174">RuntimeNamePropertyAttribute</span></span>

<span data-ttu-id="801cb-175">**リファレンス ドキュメント:**  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute></span><span class="sxs-lookup"><span data-stu-id="801cb-175">**Reference Documentation:**  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute></span></span>

<span data-ttu-id="801cb-176">**適用対象:** クラス</span><span class="sxs-lookup"><span data-stu-id="801cb-176">**Applies to:** Class</span></span>

<span data-ttu-id="801cb-177">**引数:** 属性付き型のランタイム名プロパティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="801cb-177">**Arguments:** A string that specifies the name of the run-time name property on the attributed type.</span></span>

<span data-ttu-id="801cb-178"><xref:System.Windows.Markup.RuntimeNamePropertyAttribute>は、 XAML [x:Name ディレクティブ](xname-directive.md)にマップされる属性付き型のプロパティを報告します。</span><span class="sxs-lookup"><span data-stu-id="801cb-178"><xref:System.Windows.Markup.RuntimeNamePropertyAttribute> reports a property of the attributed type that maps to the XAML [x:Name Directive](xname-directive.md).</span></span> <span data-ttu-id="801cb-179">プロパティは、読み取<xref:System.String>り/書き込み可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="801cb-179">The property must be of type <xref:System.String> and must be read/write.</span></span>

<span data-ttu-id="801cb-180">定義は、定義する型に割り当て可能なすべての派生型を継承します。</span><span class="sxs-lookup"><span data-stu-id="801cb-180">The definition inherits to all derived types that are assignable to the defining type.</span></span> <span data-ttu-id="801cb-181">特定の派生型に適用することで、特定の派生型の<xref:System.Windows.Markup.RuntimeNamePropertyAttribute>定義をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="801cb-181">You can override the definition on a specific derived type by applying <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> on the specific derived type.</span></span>

### <a name="trimsurroundingwhitespaceattribute"></a><span data-ttu-id="801cb-182">トリム周辺空白属性</span><span class="sxs-lookup"><span data-stu-id="801cb-182">TrimSurroundingWhitespaceAttribute</span></span>

<span data-ttu-id="801cb-183">**リファレンス ドキュメント:**  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute></span><span class="sxs-lookup"><span data-stu-id="801cb-183">**Reference Documentation:**  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute></span></span>

<span data-ttu-id="801cb-184">**適用対象:** 種類</span><span class="sxs-lookup"><span data-stu-id="801cb-184">**Applies to:** Types</span></span>

<span data-ttu-id="801cb-185">**引数:** なし。</span><span class="sxs-lookup"><span data-stu-id="801cb-185">**Arguments:** None.</span></span>

<span data-ttu-id="801cb-186"><xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>は、空白の重要なコンテンツ (が含まれるコレクションによって保持されるコンテンツ) 内の子要素として表示<xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>される特定の型に適用されます。</span><span class="sxs-lookup"><span data-stu-id="801cb-186"><xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> is applied to specific types that might appear as child elements within white-space significant content (content held by a collection that has <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>).</span></span> <span data-ttu-id="801cb-187"><xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>は主に保存パスに関連していますが、 を調べること<xref:System.Xaml.XamlType.TrimSurroundingWhitespace%2A?displayProperty=nameWithType>によって、ロード パスの XAML 型システムで使用できます。</span><span class="sxs-lookup"><span data-stu-id="801cb-187"><xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> is mainly relevant to the save path, but is available in the XAML type system in the load path by examining <xref:System.Xaml.XamlType.TrimSurroundingWhitespace%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="801cb-188">詳細については、「 [XAML での空白の処理](white-space-processing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="801cb-188">For more information, see [White-space processing in XAML](white-space-processing.md).</span></span>

### <a name="typeconverterattribute"></a><span data-ttu-id="801cb-189">TypeConverterAttribute</span><span class="sxs-lookup"><span data-stu-id="801cb-189">TypeConverterAttribute</span></span>

<span data-ttu-id="801cb-190">**リファレンス ドキュメント:**  <xref:System.ComponentModel.TypeConverterAttribute></span><span class="sxs-lookup"><span data-stu-id="801cb-190">**Reference Documentation:**  <xref:System.ComponentModel.TypeConverterAttribute></span></span>

<span data-ttu-id="801cb-191">**適用対象:** クラス、プロパティ、メソッド (XAML で有効なメソッドの唯`get`一のケースは、アタッチ可能なメンバーをサポートするアクセサーです)。</span><span class="sxs-lookup"><span data-stu-id="801cb-191">**Applies to:** Class, property, method (the only XAML-valid method case is a `get` accessor that supports an attachable member).</span></span>

<span data-ttu-id="801cb-192">**引数:** の<xref:System.Type>. <xref:System.ComponentModel.TypeConverter></span><span class="sxs-lookup"><span data-stu-id="801cb-192">**Arguments:** The <xref:System.Type> of the <xref:System.ComponentModel.TypeConverter>.</span></span>

<span data-ttu-id="801cb-193"><xref:System.ComponentModel.TypeConverterAttribute>XAML コンテキストでカスタム<xref:System.ComponentModel.TypeConverter>を参照します。</span><span class="sxs-lookup"><span data-stu-id="801cb-193"><xref:System.ComponentModel.TypeConverterAttribute> in a XAML context references a custom <xref:System.ComponentModel.TypeConverter>.</span></span> <span data-ttu-id="801cb-194">これにより<xref:System.ComponentModel.TypeConverter>、カスタム型またはその型のメンバーに対する型変換動作が提供されます。</span><span class="sxs-lookup"><span data-stu-id="801cb-194">This <xref:System.ComponentModel.TypeConverter> provides type conversion behavior for custom types, or members of that type.</span></span>

<span data-ttu-id="801cb-195">型コンバーター<xref:System.ComponentModel.TypeConverterAttribute>の実装を参照して、型に属性を適用します。</span><span class="sxs-lookup"><span data-stu-id="801cb-195">Apply the <xref:System.ComponentModel.TypeConverterAttribute> attribute to your type, referencing your type converter implementation.</span></span> <span data-ttu-id="801cb-196">クラス、構造体、またはインターフェイスに XAML の型コンバーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="801cb-196">You can define type converters for XAML on classes, structures, or interfaces.</span></span> <span data-ttu-id="801cb-197">列挙型の型変換を提供する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="801cb-197">You do not need to provide type conversion for enumerations, that conversion is enabled natively.</span></span>

<span data-ttu-id="801cb-198">型コンバーターは、マークアップ内の属性または初期化テキストに使用される文字列から目的の変換先の型に変換できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="801cb-198">Your type converter should be able to convert from a string that is used for attributes or initialization text in markup, into your intended destination type.</span></span> <span data-ttu-id="801cb-199">詳細については、「[型コンバーターと XAML](../../framework/wpf/advanced/typeconverters-and-xaml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="801cb-199">For more information, see [TypeConverters and XAML](../../framework/wpf/advanced/typeconverters-and-xaml.md).</span></span>

<span data-ttu-id="801cb-200">型のすべての値に適用するのではなく、XAML の型コンバーターの動作を特定のプロパティに対して確立することもできます。</span><span class="sxs-lookup"><span data-stu-id="801cb-200">Rather than applying to all values of a type, a type converter behavior for XAML can also be established on a specific property.</span></span> <span data-ttu-id="801cb-201">この場合、プロパティ定義<xref:System.ComponentModel.TypeConverterAttribute>(特定`get`の定義と`set`定義ではなく外側の定義) に適用されます。</span><span class="sxs-lookup"><span data-stu-id="801cb-201">In this case, you apply <xref:System.ComponentModel.TypeConverterAttribute> to the property definition (the outer definition, not the specific `get` and `set` definitions).</span></span>

<span data-ttu-id="801cb-202">カスタムアタッチ可能なメンバーの XAML 使用法の型コンバーターの動作は、XAML<xref:System.ComponentModel.TypeConverterAttribute>の`get`使用法をサポートするメソッド アクセサーに適用することで割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="801cb-202">A type converter behavior for XAML usage of a custom attachable member can be assigned by applying <xref:System.ComponentModel.TypeConverterAttribute> to the `get` method accessor that supports the XAML usage.</span></span>

<span data-ttu-id="801cb-203">と同様<xref:System.ComponentModel.TypeConverter>に<xref:System.ComponentModel.TypeConverterAttribute>、XAML が存在する前に .NET に存在し、型コンバーター モデルは他の目的を果たしました。</span><span class="sxs-lookup"><span data-stu-id="801cb-203">Similar to <xref:System.ComponentModel.TypeConverter>, <xref:System.ComponentModel.TypeConverterAttribute> existed in .NET prior to the existence of XAML, and the type converter model served other purposes.</span></span> <span data-ttu-id="801cb-204">を参照して使用<xref:System.ComponentModel.TypeConverterAttribute>するには、完全に修飾するか、ステートメントを`using`提供する<xref:System.ComponentModel>必要があります。</span><span class="sxs-lookup"><span data-stu-id="801cb-204">In order to reference and use <xref:System.ComponentModel.TypeConverterAttribute>, you must fully qualify it or provide a `using` statement for <xref:System.ComponentModel>.</span></span> <span data-ttu-id="801cb-205">プロジェクトにシステム アセンブリも含めます。</span><span class="sxs-lookup"><span data-stu-id="801cb-205">Also include the System assembly in your project.</span></span>

### <a name="uidpropertyattribute"></a><span data-ttu-id="801cb-206">プロパティ属性</span><span class="sxs-lookup"><span data-stu-id="801cb-206">UidPropertyAttribute</span></span>

<span data-ttu-id="801cb-207">**リファレンス ドキュメント:**  <xref:System.Windows.Markup.UidPropertyAttribute></span><span class="sxs-lookup"><span data-stu-id="801cb-207">**Reference Documentation:**  <xref:System.Windows.Markup.UidPropertyAttribute></span></span>

<span data-ttu-id="801cb-208">**適用対象:** クラス</span><span class="sxs-lookup"><span data-stu-id="801cb-208">**Applies to:** Class</span></span>

<span data-ttu-id="801cb-209">**引数:** 関連するプロパティを名前で参照する文字列。</span><span class="sxs-lookup"><span data-stu-id="801cb-209">**Arguments:** A string that references the relevant property by name.</span></span>

<span data-ttu-id="801cb-210">[x:Uid ディレクティブ](xuid-directive.md)をエイリアスするクラスの CLR プロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="801cb-210">Indicates the CLR property of a class that aliases the [x:Uid Directive](xuid-directive.md).</span></span>

### <a name="usableduringinitializationattribute"></a><span data-ttu-id="801cb-211">初期化中に使用できる属性</span><span class="sxs-lookup"><span data-stu-id="801cb-211">UsableDuringInitializationAttribute</span></span>

<span data-ttu-id="801cb-212">**リファレンス ドキュメント:**  <xref:System.Windows.Markup.UsableDuringInitializationAttribute></span><span class="sxs-lookup"><span data-stu-id="801cb-212">**Reference Documentation:**  <xref:System.Windows.Markup.UsableDuringInitializationAttribute></span></span>

<span data-ttu-id="801cb-213">**適用対象:** クラス</span><span class="sxs-lookup"><span data-stu-id="801cb-213">**Applies to:** Class</span></span>

<span data-ttu-id="801cb-214">**引数:** ブール値。</span><span class="sxs-lookup"><span data-stu-id="801cb-214">**Arguments:** A Boolean.</span></span> <span data-ttu-id="801cb-215">属性の目的に使用する場合は、値を に設定する`true`必要があります。</span><span class="sxs-lookup"><span data-stu-id="801cb-215">If used for the attribute's intended purpose, the value should be set to `true`.</span></span>

<span data-ttu-id="801cb-216">XAML オブジェクト グラフの作成時に型をトップダウンで構築するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="801cb-216">Indicates whether the type is built top-down during XAML object graph creation.</span></span> <span data-ttu-id="801cb-217">これは高度な概念であり、おそらくプログラミング モデルの定義と密接に関連しています。</span><span class="sxs-lookup"><span data-stu-id="801cb-217">This is an advanced concept, which is probably closely related to the definition of your programming model.</span></span> <span data-ttu-id="801cb-218">詳細については、「<xref:System.Windows.Markup.UsableDuringInitializationAttribute>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="801cb-218">For more information, see <xref:System.Windows.Markup.UsableDuringInitializationAttribute>.</span></span>

### <a name="valueserializerattribute"></a><span data-ttu-id="801cb-219">属性</span><span class="sxs-lookup"><span data-stu-id="801cb-219">ValueSerializerAttribute</span></span>

<span data-ttu-id="801cb-220">**リファレンス ドキュメント:**  <xref:System.Windows.Markup.ValueSerializerAttribute></span><span class="sxs-lookup"><span data-stu-id="801cb-220">**Reference Documentation:**  <xref:System.Windows.Markup.ValueSerializerAttribute></span></span>

<span data-ttu-id="801cb-221">**適用対象:** クラス、プロパティ、メソッド (XAML で有効なメソッドの唯`get`一のケースは、アタッチ可能なメンバーをサポートするアクセサーです)。</span><span class="sxs-lookup"><span data-stu-id="801cb-221">**Applies to:** Class, property, method (the only XAML-valid method case is a `get` accessor that supports an attachable member).</span></span>

<span data-ttu-id="801cb-222">**引数:** 属性<xref:System.Type>付き型のすべてのプロパティ、または特定の属性付きプロパティをシリアル化するときに使用する、値シリアライザー サポート クラスを指定する A。</span><span class="sxs-lookup"><span data-stu-id="801cb-222">**Arguments:** A <xref:System.Type> that specifies the value serializer support class to use when serializing all properties of the attributed type, or the specific attributed property.</span></span>

<span data-ttu-id="801cb-223"><xref:System.Windows.Markup.ValueSerializer>は、より多くの状態とコンテキストを必要とする値の<xref:System.ComponentModel.TypeConverter>シリアル化クラスを指定します。</span><span class="sxs-lookup"><span data-stu-id="801cb-223"><xref:System.Windows.Markup.ValueSerializer> specifies a value serialization class that requires more state and context than a <xref:System.ComponentModel.TypeConverter> does.</span></span> <span data-ttu-id="801cb-224"><xref:System.Windows.Markup.ValueSerializer>アタッチ可能なメンバーの静的<xref:System.Windows.Markup.ValueSerializerAttribute>`get`アクセサー メソッドに属性を適用することで、アタッチ可能なメンバーに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="801cb-224"><xref:System.Windows.Markup.ValueSerializer> can be associated with an attachable member by applying the <xref:System.Windows.Markup.ValueSerializerAttribute> attribute on the static `get` accessor method for the attachable member.</span></span> <span data-ttu-id="801cb-225">値のシリアル化は、列挙体、インターフェイス、および構造体にも適用できますが、デリゲートには適用できません。</span><span class="sxs-lookup"><span data-stu-id="801cb-225">Value serialization is also applicable for enumerations, interfaces, and structures, but not for delegates.</span></span>

### <a name="whitespacesignificantcollectionattribute"></a><span data-ttu-id="801cb-226">クラス名の属性</span><span class="sxs-lookup"><span data-stu-id="801cb-226">WhitespaceSignificantCollectionAttribute</span></span>

<span data-ttu-id="801cb-227">**リファレンス ドキュメント:**  <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute></span><span class="sxs-lookup"><span data-stu-id="801cb-227">**Reference Documentation:**  <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute></span></span>

<span data-ttu-id="801cb-228">**適用対象:** クラス、特に、オブジェクト要素の周囲の空白が UI 表現にとって重要である場合に、混在したコンテンツをホストすることが期待されるコレクション型。</span><span class="sxs-lookup"><span data-stu-id="801cb-228">**Applies to:** Class, specifically collection types that are expected to host mixed content, where white space around object elements might be significant for UI representation.</span></span>

<span data-ttu-id="801cb-229">**引数:** なし。</span><span class="sxs-lookup"><span data-stu-id="801cb-229">**Arguments:** None.</span></span>

<span data-ttu-id="801cb-230"><xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>コレクション型は、コレクション内の XAML ノード ストリームの値ノードの構築に影響を与える XAML プロセッサによって重要な空白として処理する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="801cb-230"><xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> indicates that a collection type should be processed as white-space significant by a XAML processor, which influences the construction of the XAML node stream's value nodes within the collection.</span></span> <span data-ttu-id="801cb-231">詳細については、「 [XAML での空白の処理](white-space-processing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="801cb-231">For more information, see [White-space processing in XAML](white-space-processing.md).</span></span>

### <a name="xamldeferloadattribute"></a><span data-ttu-id="801cb-232">属性を保留にします。</span><span class="sxs-lookup"><span data-stu-id="801cb-232">XamlDeferLoadAttribute</span></span>

<span data-ttu-id="801cb-233">**リファレンス ドキュメント:**  <xref:System.Windows.Markup.XamlDeferLoadAttribute></span><span class="sxs-lookup"><span data-stu-id="801cb-233">**Reference Documentation:**  <xref:System.Windows.Markup.XamlDeferLoadAttribute></span></span>

<span data-ttu-id="801cb-234">**適用対象:** クラス、プロパティ。</span><span class="sxs-lookup"><span data-stu-id="801cb-234">**Applies to:** Class, property.</span></span>

<span data-ttu-id="801cb-235">**引数:** 2 つのアトリビューション フォーム型を文字列として、または<xref:System.Type>型としてサポートします。</span><span class="sxs-lookup"><span data-stu-id="801cb-235">**Arguments:** Supports two attribution forms types as strings, or types as <xref:System.Type>.</span></span> <span data-ttu-id="801cb-236">[https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview](<xref:System.Windows.Markup.XamlDeferLoadAttribute> ) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="801cb-236">See <xref:System.Windows.Markup.XamlDeferLoadAttribute>.</span></span>

<span data-ttu-id="801cb-237">クラスまたはプロパティに XAML の遅延読み込みの使用 (テンプレート動作など) が含まれていることを示し、遅延動作を有効にするクラスと、その宛先/コンテンツ タイプを報告します。</span><span class="sxs-lookup"><span data-stu-id="801cb-237">Indicates that a class or property has a deferred load usage for XAML (such as a template behavior), and reports the class that enables the deferring behavior and its destination/content type.</span></span>

### <a name="xamlsetmarkupextensionattribute"></a><span data-ttu-id="801cb-238">属性</span><span class="sxs-lookup"><span data-stu-id="801cb-238">XamlSetMarkupExtensionAttribute</span></span>

<span data-ttu-id="801cb-239">**リファレンス ドキュメント:**  <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute></span><span class="sxs-lookup"><span data-stu-id="801cb-239">**Reference Documentation:**  <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute></span></span>

<span data-ttu-id="801cb-240">**適用対象:** クラス</span><span class="sxs-lookup"><span data-stu-id="801cb-240">**Applies to:** Class</span></span>

<span data-ttu-id="801cb-241">**引数:** コールバックの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="801cb-241">**Arguments:** Names the callback.</span></span>

<span data-ttu-id="801cb-242">クラスがマークアップ拡張機能を使用して 1 つ以上のプロパティの値を提供できることを示し、クラスの任意のプロパティに対してマークアップ拡張機能の設定操作を実行する前に XAML ライターが呼び出す必要があるハンドラーを参照します。</span><span class="sxs-lookup"><span data-stu-id="801cb-242">Indicates that a class can use a markup extension to provide a value for one or more of its properties, and references a handler that a XAML writer should call before performing a markup extension set operation on any property of the class.</span></span>

### <a name="xamlsettypeconverterattribute"></a><span data-ttu-id="801cb-243">クラスの種類の属性</span><span class="sxs-lookup"><span data-stu-id="801cb-243">XamlSetTypeConverterAttribute</span></span>

<span data-ttu-id="801cb-244">**リファレンス ドキュメント:**  <xref:System.Windows.Markup.XamlSetTypeConverterAttribute></span><span class="sxs-lookup"><span data-stu-id="801cb-244">**Reference Documentation:**  <xref:System.Windows.Markup.XamlSetTypeConverterAttribute></span></span>

<span data-ttu-id="801cb-245">**適用対象:** クラス</span><span class="sxs-lookup"><span data-stu-id="801cb-245">**Applies to:** Class</span></span>

<span data-ttu-id="801cb-246">**引数:** コールバックの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="801cb-246">**Arguments:** Names the callback.</span></span>

<span data-ttu-id="801cb-247">クラスが型コンバーターを使用して 1 つ以上のプロパティの値を提供できることを示し、クラスの任意のプロパティに対して型コンバーターのセット操作を実行する前に XAML ライターが呼び出す必要があるハンドラーを参照します。</span><span class="sxs-lookup"><span data-stu-id="801cb-247">Indicates that a class can use a type converter to provide a value for one or more of its properties, and references a handler that a XAML writer should call before performing a type converter set operation on any property of the class.</span></span>

### <a name="xmllangpropertyattribute"></a><span data-ttu-id="801cb-248">プロパティ属性</span><span class="sxs-lookup"><span data-stu-id="801cb-248">XmlLangPropertyAttribute</span></span>

<span data-ttu-id="801cb-249">**リファレンス ドキュメント:**  <xref:System.Windows.Markup.XmlLangPropertyAttribute></span><span class="sxs-lookup"><span data-stu-id="801cb-249">**Reference Documentation:**  <xref:System.Windows.Markup.XmlLangPropertyAttribute></span></span>

<span data-ttu-id="801cb-250">**適用対象:** クラス</span><span class="sxs-lookup"><span data-stu-id="801cb-250">**Applies to:** Class</span></span>

<span data-ttu-id="801cb-251">**引数:** 属性付き型でエイリアス`xml:lang`するプロパティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="801cb-251">**Arguments:** A string that specifies the name of the property to alias to `xml:lang` on the attributed type.</span></span>

<span data-ttu-id="801cb-252"><xref:System.Windows.Markup.XmlLangPropertyAttribute>は、XML`lang`ディレクティブにマップされる属性付きの型のプロパティを報告します。</span><span class="sxs-lookup"><span data-stu-id="801cb-252"><xref:System.Windows.Markup.XmlLangPropertyAttribute> reports a property of the attributed type that maps to the XML `lang` directive.</span></span> <span data-ttu-id="801cb-253">プロパティは必ずしも型<xref:System.String>ではありませんが、文字列から割り当て可能である必要があります (代入は、型コンバーターをプロパティの型に関連付けることによって行われるか、特定のプロパティに関連付けることによって行うことができます)。</span><span class="sxs-lookup"><span data-stu-id="801cb-253">The property is not necessarily of type <xref:System.String> but must be assignable from a string (assignment could be accomplished by associating a type converter with the property's type or with the specific property).</span></span> <span data-ttu-id="801cb-254">プロパティは読み取り/書き込み可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="801cb-254">The property must be read/write.</span></span>

<span data-ttu-id="801cb-255">マッピング`xml:lang`のシナリオは、XMLDOM を使用して特別に処理することなく、ランタイム オブジェクト モデルが XML で指定された言語情報にアクセスできるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="801cb-255">The scenario for mapping `xml:lang` is so that a runtime object model has access to XML-specified language information without specifically processing with an XMLDOM.</span></span>

<span data-ttu-id="801cb-256">定義は、定義する型に割り当て可能なすべての派生型を継承します。</span><span class="sxs-lookup"><span data-stu-id="801cb-256">The definition inherits to all derived types that are assignable to the defining type.</span></span> <span data-ttu-id="801cb-257">特定の派生型に適用することで<xref:System.Windows.Markup.XmlLangPropertyAttribute>、特定の派生型の定義をオーバーライドできますが、これは一般的なシナリオではありません。</span><span class="sxs-lookup"><span data-stu-id="801cb-257">You can override the definition on a specific derived type by applying <xref:System.Windows.Markup.XmlLangPropertyAttribute> on the specific derived type, although that is an uncommon scenario.</span></span>

## <a name="xaml-related-clr-attributes-at-the-assembly-level"></a><span data-ttu-id="801cb-258">アセンブリ レベルでの XAML 関連の CLR 属性</span><span class="sxs-lookup"><span data-stu-id="801cb-258">XAML-Related CLR Attributes at the Assembly Level</span></span>

<span data-ttu-id="801cb-259">次のセクションでは、型またはメンバー定義には適用されず、代わりにアセンブリに適用される XAML 関連の属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="801cb-259">The following sections describe the XAML-related attributes that are not applied to types or member definitions, but are instead applied to assemblies.</span></span> <span data-ttu-id="801cb-260">これらの属性は、XAML で使用するカスタム型を含むライブラリを定義するという全体的な目標に関連しています。</span><span class="sxs-lookup"><span data-stu-id="801cb-260">These attributes are pertinent to the overall goal of defining a library that contains custom types to use in XAML.</span></span> <span data-ttu-id="801cb-261">属性の一部は、必ずしも XAML ノード ストリームに直接影響を与えるわけではありませんが、他のコンシューマーが使用するためにノード ストリームに渡されます。</span><span class="sxs-lookup"><span data-stu-id="801cb-261">Some of the attributes do not necessarily influence the XAML node stream directly, but are passed on in the node stream for other consumers to use.</span></span> <span data-ttu-id="801cb-262">情報のコンシューマーには、XAML 名前空間情報と関連付けられたプレフィックス情報を必要とするデザイン環境やシリアル化プロセスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="801cb-262">Consumers for the information include design environments or serialization processes that need XAML namespace information and associated prefix information.</span></span> <span data-ttu-id="801cb-263">XAML スキーマ コンテキスト (.NET XAML サービスの既定値を含む) もこの情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="801cb-263">A XAML schema context (including the .NET XAML Services default) also uses this information.</span></span>

### <a name="xmlnscompatiblewithattribute"></a><span data-ttu-id="801cb-264">属性と互換性のある Xmlns</span><span class="sxs-lookup"><span data-stu-id="801cb-264">XmlnsCompatibleWithAttribute</span></span>

<span data-ttu-id="801cb-265">**リファレンス ドキュメント:**  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute></span><span class="sxs-lookup"><span data-stu-id="801cb-265">**Reference Documentation:**  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute></span></span>

<span data-ttu-id="801cb-266">**引数:**</span><span class="sxs-lookup"><span data-stu-id="801cb-266">**Arguments:**</span></span>

- <span data-ttu-id="801cb-267">使用する XAML 名前空間の識別子を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="801cb-267">A string that specifies the identifier of the XAML namespace to subsume.</span></span>

- <span data-ttu-id="801cb-268">前の引数から XAML 名前空間を使用できる XAML 名前空間の識別子を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="801cb-268">A string that specifies the identifier of the XAML namespace that can subsume the XAML namespace from the previous argument.</span></span>

  <span data-ttu-id="801cb-269"><xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>XAML 名前空間を別の XAML 名前空間に含めることができることを指定します。</span><span class="sxs-lookup"><span data-stu-id="801cb-269"><xref:System.Windows.Markup.XmlnsCompatibleWithAttribute> specifies that a XAML namespace can be subsumed by another XAML namespace.</span></span> <span data-ttu-id="801cb-270">通常、包含する側の XAML 名前空間は、あらかじめ定義した <xref:System.Windows.Markup.XmlnsDefinitionAttribute> で示されます。</span><span class="sxs-lookup"><span data-stu-id="801cb-270">Typically, the subsuming XAML namespace is indicated in a previously defined <xref:System.Windows.Markup.XmlnsDefinitionAttribute>.</span></span> <span data-ttu-id="801cb-271">この方法は、ライブラリ内の XAML ボキャブラリのバージョン管理や、以前に定義されたマークアップと以前に定義されたバージョンのボキャブラリに対する互換性を持たせるために使用できます。</span><span class="sxs-lookup"><span data-stu-id="801cb-271">This technique can be used for versioning a XAML vocabulary in a library and to make it compatible with previously defined markup against the earlier versioned vocabulary.</span></span>

### <a name="xmlnsdefinitionattribute"></a><span data-ttu-id="801cb-272">属性</span><span class="sxs-lookup"><span data-stu-id="801cb-272">XmlnsDefinitionAttribute</span></span>

<span data-ttu-id="801cb-273">**リファレンス ドキュメント:**  <xref:System.Windows.Markup.XmlnsDefinitionAttribute></span><span class="sxs-lookup"><span data-stu-id="801cb-273">**Reference Documentation:**  <xref:System.Windows.Markup.XmlnsDefinitionAttribute></span></span>

<span data-ttu-id="801cb-274">**引数:**</span><span class="sxs-lookup"><span data-stu-id="801cb-274">**Arguments:**</span></span>

- <span data-ttu-id="801cb-275">定義する XAML 名前空間の識別子を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="801cb-275">A string that specifies the identifier of the XAML namespace to define.</span></span>

- <span data-ttu-id="801cb-276">CLR 名前空間の名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="801cb-276">A string that names a CLR namespace.</span></span> <span data-ttu-id="801cb-277">CLR 名前空間はアセンブリ内でパブリック型を定義する必要があり、少なくとも 1 つの CLR 名前空間型は XAML の使用を目的としている必要があります。</span><span class="sxs-lookup"><span data-stu-id="801cb-277">The CLR namespace should define public types in your assembly, and at least one of the CLR namespace types should be intended for XAML usage.</span></span>

  <span data-ttu-id="801cb-278"><xref:System.Windows.Markup.XmlnsDefinitionAttribute>XAML 名前空間と CLR 名前空間の間のアセンブリごとにマッピングを指定します。</span><span class="sxs-lookup"><span data-stu-id="801cb-278"><xref:System.Windows.Markup.XmlnsDefinitionAttribute> specifies a mapping on a per-assembly basis between a XAML namespace and a CLR namespace, which is then used for type resolution by a XAML object writer or XAML schema context.</span></span>

  <span data-ttu-id="801cb-279">アセンブリ<xref:System.Windows.Markup.XmlnsDefinitionAttribute>には複数の方法を適用できます。</span><span class="sxs-lookup"><span data-stu-id="801cb-279">More than one <xref:System.Windows.Markup.XmlnsDefinitionAttribute> can be applied to an assembly.</span></span> <span data-ttu-id="801cb-280">これは、次の理由の任意の組み合わせで行われます。</span><span class="sxs-lookup"><span data-stu-id="801cb-280">This might be done for any combination of the following reasons:</span></span>

- <span data-ttu-id="801cb-281">ライブラリ設計には、ランタイム API アクセスの論理編成用の複数の CLR 名前空間が含まれています。ただし、同じ XAML 名前空間を参照することで、これらの名前空間のすべての型を XAML で使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="801cb-281">The library design contains multiple CLR namespaces for logical organization of run-time API access; however, you want all types in those namespaces to be XAML-usable by referencing the same XAML namespace.</span></span> <span data-ttu-id="801cb-282">この場合、同じ<xref:System.Windows.Markup.XmlnsDefinitionAttribute><xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A>値を使用して異なる<xref:System.Windows.Markup.XmlnsDefinitionAttribute.ClrNamespace%2A>値を使用して複数の属性を適用します。</span><span class="sxs-lookup"><span data-stu-id="801cb-282">In this case, you apply several <xref:System.Windows.Markup.XmlnsDefinitionAttribute> attributes using the same <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> value but different <xref:System.Windows.Markup.XmlnsDefinitionAttribute.ClrNamespace%2A> values.</span></span> <span data-ttu-id="801cb-283">これは、フレームワークまたはアプリケーションが共通の使用法で既定の XAML 名前空間にする XAML 名前空間のマッピングを定義する場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="801cb-283">This is especially useful if you are defining mappings for the XAML namespace that your framework or application intends to be the default XAML namespace in common usage.</span></span>

- <span data-ttu-id="801cb-284">ライブラリデザインには複数の CLR 名前空間が含まれ、これらの CLR 名前空間での型の使用法を意図的に XAML 名前空間で分離する必要があります。</span><span class="sxs-lookup"><span data-stu-id="801cb-284">The library design contains multiple CLR namespaces, and you want a deliberate XAML namespace separation between the usages of types in those CLR namespaces.</span></span>

- <span data-ttu-id="801cb-285">アセンブリ内で CLR 名前空間を定義し、複数の XAML 名前空間を介してアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="801cb-285">You define a CLR namespace in the assembly, and you want it to be accessible through more than one XAML namespace.</span></span> <span data-ttu-id="801cb-286">このシナリオは、同じコードベースで複数のボキャブラリをサポートしている場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="801cb-286">This scenario occurs when you are supporting multiple vocabularies with the same codebase.</span></span>

- <span data-ttu-id="801cb-287">1 つ以上の CLR 名前空間で XAML 言語サポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="801cb-287">You define XAML language support in one or more CLR namespaces.</span></span> <span data-ttu-id="801cb-288">この場合、値は<xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A>にする`http://schemas.microsoft.com/winfx/2006/xaml`必要があります。</span><span class="sxs-lookup"><span data-stu-id="801cb-288">In this case, the <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> value should be `http://schemas.microsoft.com/winfx/2006/xaml`.</span></span>

### <a name="xmlnsprefixattribute"></a><span data-ttu-id="801cb-289">属性</span><span class="sxs-lookup"><span data-stu-id="801cb-289">XmlnsPrefixAttribute</span></span>

<span data-ttu-id="801cb-290">**リファレンス ドキュメント:**  <xref:System.Windows.Markup.XmlnsPrefixAttribute></span><span class="sxs-lookup"><span data-stu-id="801cb-290">**Reference Documentation:**  <xref:System.Windows.Markup.XmlnsPrefixAttribute></span></span>

<span data-ttu-id="801cb-291">**引数:**</span><span class="sxs-lookup"><span data-stu-id="801cb-291">**Arguments:**</span></span>

- <span data-ttu-id="801cb-292">XAML 名前空間の識別子を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="801cb-292">A string that specifies the identifier of a XAML namespace.</span></span>

- <span data-ttu-id="801cb-293">推奨されるプレフィックスを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="801cb-293">A string that specifies a recommended prefix.</span></span>

  <span data-ttu-id="801cb-294"><xref:System.Windows.Markup.XmlnsDefinitionAttribute>XAML 名前空間に使用する推奨プレフィックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="801cb-294"><xref:System.Windows.Markup.XmlnsDefinitionAttribute> specifies a recommended prefix to use for a XAML namespace.</span></span> <span data-ttu-id="801cb-295">このプレフィックスは、.NET XAML サービス<xref:System.Xaml.XamlXmlWriter>によってシリアル化された XAML ファイルに要素と属性を書き込む場合、または XAML を実装するライブラリが XAML 編集機能を備えたデザイン環境と対話する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="801cb-295">The prefix is useful when writing elements and attributes in a XAML file that is serialized by .NET XAML Services <xref:System.Xaml.XamlXmlWriter>, or when a XAML-implementing library interacts with a design environment that has XAML editing features.</span></span>

  <span data-ttu-id="801cb-296">アセンブリ<xref:System.Windows.Markup.XmlnsPrefixAttribute>には複数の方法を適用できます。</span><span class="sxs-lookup"><span data-stu-id="801cb-296">More than one <xref:System.Windows.Markup.XmlnsPrefixAttribute> can be applied to an assembly.</span></span> <span data-ttu-id="801cb-297">これは、次の理由の任意の組み合わせで行われます。</span><span class="sxs-lookup"><span data-stu-id="801cb-297">This might be done for any combination of the following reasons:</span></span>

- <span data-ttu-id="801cb-298">アセンブリでは、複数の XAML 名前空間の型を定義しています。</span><span class="sxs-lookup"><span data-stu-id="801cb-298">Your assembly defines types for more than one XAML namespace.</span></span> <span data-ttu-id="801cb-299">この場合は、XAML 名前空間ごとに異なるプレフィックス値を定義します。</span><span class="sxs-lookup"><span data-stu-id="801cb-299">In this case, define different prefix values for each XAML namespace.</span></span>

- <span data-ttu-id="801cb-300">複数のボキャブラリをサポートしており、各ボキャブラリと XAML 名前空間に異なるプレフィックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="801cb-300">You are supporting multiple vocabularies, and you use different prefixes for each vocabulary and XAML namespace.</span></span>

- <span data-ttu-id="801cb-301">アセンブリで XAML 言語サポートを定義し、 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> `http://schemas.microsoft.com/winfx/2006/xaml`の を持ちます。</span><span class="sxs-lookup"><span data-stu-id="801cb-301">You define XAML language support in the assembly and have a <xref:System.Windows.Markup.XmlnsDefinitionAttribute> for `http://schemas.microsoft.com/winfx/2006/xaml`.</span></span> <span data-ttu-id="801cb-302">この場合、通常はプレフィックス`x`を昇格させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="801cb-302">In this case, you typically should promote the prefix `x`.</span></span>

> [!NOTE]
> <span data-ttu-id="801cb-303">.NET XAML サービスは、XAML 関連<xref:System.Windows.Markup.RootNamespaceAttribute>の属性も定義します。</span><span class="sxs-lookup"><span data-stu-id="801cb-303">.NET XAML Services also defines the XAML-related attribute <xref:System.Windows.Markup.RootNamespaceAttribute>.</span></span> <span data-ttu-id="801cb-304">この属性は、プロジェクト システムサポートのアセンブリ レベルの属性であり、XAML カスタム型には関係ありません。</span><span class="sxs-lookup"><span data-stu-id="801cb-304">This attribute is an assembly-level attribute for project system support, and it is not relevant for XAML custom types.</span></span>

## <a name="see-also"></a><span data-ttu-id="801cb-305">関連項目</span><span class="sxs-lookup"><span data-stu-id="801cb-305">See also</span></span>

- <xref:System.Attribute>
- [<span data-ttu-id="801cb-306">.NET XAML サービスで使用するカスタム型の定義</span><span class="sxs-lookup"><span data-stu-id="801cb-306">Defining Custom Types for Use with .NET XAML Services</span></span>](define-custom-types.md)
