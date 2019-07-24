---
title: '方法: 依存関係プロパティの所有者の種類を追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes [WPF], adding as owners of dependency properties
- dependency properties [WPF], adding classes as owners of
ms.assetid: edcce050-0576-4edb-a31a-3f909637b452
ms.openlocfilehash: 5ddc85d159b4bf81751428c13c234c5e53be8ad4
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401133"
---
# <a name="how-to-add-an-owner-type-for-a-dependency-property"></a><span data-ttu-id="5dc91-102">方法: 依存関係プロパティの所有者の種類を追加する</span><span class="sxs-lookup"><span data-stu-id="5dc91-102">How to: Add an Owner Type for a Dependency Property</span></span>
<span data-ttu-id="5dc91-103">この例では、別の型に登録されている依存関係プロパティの所有者としてクラスを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5dc91-103">This example shows how to add a class as an owner of a dependency property registered for a different type.</span></span> <span data-ttu-id="5dc91-104">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] これ[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]により、リーダーとプロパティシステムは、クラスをプロパティの追加所有者として認識できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5dc91-104">By doing this, the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reader and property system are both able to recognize the class as an additional owner of the property.</span></span> <span data-ttu-id="5dc91-105">所有者として追加すると、追加クラスで型固有のメタデータを提供できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5dc91-105">Adding as owner optionally allows the adding class to provide type-specific metadata.</span></span>  
  
 <span data-ttu-id="5dc91-106">次の例では`StateProperty` 、は`MyStateControl`クラスによって登録されるプロパティです。</span><span class="sxs-lookup"><span data-stu-id="5dc91-106">In the following example, `StateProperty` is a property registered by the `MyStateControl` class.</span></span> <span data-ttu-id="5dc91-107">クラス`UnrelatedStateControl`は、 <xref:System.Windows.DependencyProperty.AddOwner%2A>メソッドを使用して、 `StateProperty`それ自体をの所有者として追加します。特に、追加する型に存在する依存関係プロパティの新しいメタデータを許可する署名を使用します。</span><span class="sxs-lookup"><span data-stu-id="5dc91-107">The class `UnrelatedStateControl` adds itself as an owner of the `StateProperty` using the <xref:System.Windows.DependencyProperty.AddOwner%2A> method, specifically using the signature that allows for new metadata for the dependency property as it exists on the adding type.</span></span> <span data-ttu-id="5dc91-108">「[依存関係プロパティの実装](how-to-implement-a-dependency-property.md)」の例に示すように、プロパティの共通言語ランタイム (CLR) アクセサーを提供する必要があることに注意してください。また、所有者として追加されるクラスの依存関係プロパティの識別子を再公開することもできます。</span><span class="sxs-lookup"><span data-stu-id="5dc91-108">Notice that you should provide common language runtime (CLR) accessors for the property similar to the example shown in the [Implement a Dependency Property](how-to-implement-a-dependency-property.md) example, as well as re-expose the dependency property identifier on the class being added as owner.</span></span>  
  
 <span data-ttu-id="5dc91-109">ラッパーがない場合でも、依存関係プロパティはまたは<xref:System.Windows.DependencyObject.GetValue%2A> <xref:System.Windows.DependencyObject.SetValue%2A>を使用したプログラムによるアクセスの観点から機能します。</span><span class="sxs-lookup"><span data-stu-id="5dc91-109">Without wrappers, the dependency property would still work from the perspective of programmatic access using <xref:System.Windows.DependencyObject.GetValue%2A> or <xref:System.Windows.DependencyObject.SetValue%2A>.</span></span> <span data-ttu-id="5dc91-110">ただし、通常は、このプロパティシステムの動作を CLR プロパティラッパーと並列にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5dc91-110">But you typically want to parallel this property-system behavior with the CLR property wrappers.</span></span> <span data-ttu-id="5dc91-111">ラッパーを使用すると、依存関係プロパティをプログラムで設定しやすくなり、プロパティを属性と[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]して設定できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5dc91-111">The wrappers make it easier to set the dependency property programmatically, and make it possible to set the properties as [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attributes.</span></span>  
  
 <span data-ttu-id="5dc91-112">既定のメタデータをオーバーライドする方法については、「[依存関係プロパティのメタデータのオーバーライド](how-to-override-metadata-for-a-dependency-property.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5dc91-112">To find out how to override default metadata, see [Override Metadata for a Dependency Property](how-to-override-metadata-for-a-dependency-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5dc91-113">例</span><span class="sxs-lookup"><span data-stu-id="5dc91-113">Example</span></span>  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## <a name="see-also"></a><span data-ttu-id="5dc91-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="5dc91-114">See also</span></span>

- [<span data-ttu-id="5dc91-115">カスタム依存関係プロパティ</span><span class="sxs-lookup"><span data-stu-id="5dc91-115">Custom Dependency Properties</span></span>](custom-dependency-properties.md)
- [<span data-ttu-id="5dc91-116">依存関係プロパティの概要</span><span class="sxs-lookup"><span data-stu-id="5dc91-116">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
