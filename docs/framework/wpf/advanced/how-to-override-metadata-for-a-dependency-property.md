---
title: '方法: 依存関係プロパティのメタデータをオーバーライドする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- metadata [WPF], overriding for dependency properties
- dependency properties [WPF], overriding metadata for
- overriding metadata for dependency properties [WPF]
ms.assetid: f90f026e-60d8-428a-933d-edf0dba4441f
ms.openlocfilehash: ef0309ae0d03c8278134012e645960996c6f93c4
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2019
ms.locfileid: "67610510"
---
# <a name="how-to-override-metadata-for-a-dependency-property"></a><span data-ttu-id="7e79a-102">方法: 依存関係プロパティのメタデータをオーバーライドする</span><span class="sxs-lookup"><span data-stu-id="7e79a-102">How to: Override Metadata for a Dependency Property</span></span>
<span data-ttu-id="7e79a-103">この例は、呼び出すことによって、継承されたクラスからは既定の依存関係プロパティ メタデータをオーバーライドする方法を示します、<xref:System.Windows.DependencyProperty.OverrideMetadata%2A>メソッドと型固有のメタデータを提供します。</span><span class="sxs-lookup"><span data-stu-id="7e79a-103">This example shows how to override default dependency property metadata that comes from an inherited class, by calling the <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> method and providing type-specific metadata.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e79a-104">例</span><span class="sxs-lookup"><span data-stu-id="7e79a-104">Example</span></span>  
 <span data-ttu-id="7e79a-105">定義することでその<xref:System.Windows.PropertyMetadata>クラスの既定値とプロパティ システム コールバックなどの依存関係プロパティの動作を定義できます。</span><span class="sxs-lookup"><span data-stu-id="7e79a-105">By defining its <xref:System.Windows.PropertyMetadata>, a class can define the dependency property's behaviors, such as its default value and property system callbacks.</span></span> <span data-ttu-id="7e79a-106">多くの依存関係プロパティ クラスで、登録プロセスの一部として既定のメタデータが既に確立されています。</span><span class="sxs-lookup"><span data-stu-id="7e79a-106">Many dependency property classes already have default metadata established as part of their registration process.</span></span> <span data-ttu-id="7e79a-107">一部である依存関係プロパティが含まれます、 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] API。</span><span class="sxs-lookup"><span data-stu-id="7e79a-107">This includes the dependency properties that are part of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] API.</span></span> <span data-ttu-id="7e79a-108">クラス継承により依存関係プロパティを継承するクラスは、メタデータで変更できるプロパティの特性がサブクラス固有の要件に合致するように、元のメタデータをオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="7e79a-108">A class that inherits the dependency property through its class inheritance can override the original metadata so that the characteristics of the property that can be altered through metadata will match any subclass-specific requirements.</span></span>  
  
 <span data-ttu-id="7e79a-109">依存関係プロパティでのメタデータのオーバーライドは、そのプロパティがプロパティ システムによって使用される (プロパティを登録するオブジェクトの特定のインスタンスがインスタンス化されるタイミングに相当) 前に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e79a-109">Overriding metadata on a dependency property must be done prior to that property being placed in use by the property system (this equates to the time that specific instances of objects that register the property are instantiated).</span></span> <span data-ttu-id="7e79a-110">呼び出す<xref:System.Windows.DependencyProperty.OverrideMetadata%2A>として自体を提供する型の静的コンス トラクター内で実行する必要があります、`forType`パラメーターの<xref:System.Windows.DependencyProperty.OverrideMetadata%2A>します。</span><span class="sxs-lookup"><span data-stu-id="7e79a-110">Calls to <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> must be performed within the static constructors of the type that provides itself as the `forType` parameter of <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>.</span></span> <span data-ttu-id="7e79a-111">所有者型のインスタンスが存在する場合にメタデータを変更しようとすると、例外は発生しませんが、プロパティ システムに不整合な動作が発生します。</span><span class="sxs-lookup"><span data-stu-id="7e79a-111">If you attempt to change metadata once instances of the owner type exist, this will not raise exceptions, but will result in inconsistent behaviors in the property system.</span></span> <span data-ttu-id="7e79a-112">また、メタデータは 1 つの型につき 1 回しかオーバーライドできません。</span><span class="sxs-lookup"><span data-stu-id="7e79a-112">Also, metadata can only be overridden once per type.</span></span> <span data-ttu-id="7e79a-113">それ以降に同じ型のメタデータをオーバーライドしようとすると、例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="7e79a-113">Subsequent attempts to override metadata on the same type will raise an exception.</span></span>  
  
 <span data-ttu-id="7e79a-114">次の例では、`MyAdvancedStateControl` カスタム クラスが、`MyAdvancedStateControl` によって `StateProperty` に提供されるメタデータを、新しいプロパティ メタデータでオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="7e79a-114">In the following example, the custom class `MyAdvancedStateControl` overrides the metadata provided for `StateProperty` by `MyAdvancedStateControl` with new property metadata.</span></span> <span data-ttu-id="7e79a-115">たとえば、新しく構築された `MyAdvancedStateControl` インスタンスでプロパティが照会されると、`StateProperty` の既定値は `true` となります。</span><span class="sxs-lookup"><span data-stu-id="7e79a-115">For instance, the default value of the `StateProperty` is now `true` when the property is queried on a newly constructed `MyAdvancedStateControl` instance.</span></span>  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#MyAdvancedStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#myadvancedstatecontrol)]
[!code-vb[PropertySystemEsoterics#MyAdvancedStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#myadvancedstatecontrol)]  
  
## <a name="see-also"></a><span data-ttu-id="7e79a-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e79a-116">See also</span></span>

- <xref:System.Windows.DependencyProperty>
- [<span data-ttu-id="7e79a-117">依存関係プロパティの概要</span><span class="sxs-lookup"><span data-stu-id="7e79a-117">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="7e79a-118">カスタム依存関係プロパティ</span><span class="sxs-lookup"><span data-stu-id="7e79a-118">Custom Dependency Properties</span></span>](custom-dependency-properties.md)
- [<span data-ttu-id="7e79a-119">方法トピック</span><span class="sxs-lookup"><span data-stu-id="7e79a-119">How-to Topics</span></span>](properties-how-to-topics.md)
