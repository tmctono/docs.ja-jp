---
title: PresentationOptions:Freeze 属性
ms.date: 03/30/2017
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
ms.openlocfilehash: e60c4a505db42936f188354f52edd7832fb9632b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772841"
---
# <a name="presentationoptionsfreeze-attribute"></a><span data-ttu-id="bcec9-102">PresentationOptions:Freeze 属性</span><span class="sxs-lookup"><span data-stu-id="bcec9-102">PresentationOptions:Freeze Attribute</span></span>
<span data-ttu-id="bcec9-103">セット、<xref:System.Windows.Freezable.IsFrozen%2A>状態`true`で格納している<xref:System.Windows.Freezable>要素。</span><span class="sxs-lookup"><span data-stu-id="bcec9-103">Sets the <xref:System.Windows.Freezable.IsFrozen%2A> state to `true` on the containing <xref:System.Windows.Freezable> element.</span></span> <span data-ttu-id="bcec9-104">既定の動作を<xref:System.Windows.Freezable>せず、`PresentationOptions:Freeze`属性が指定される<xref:System.Windows.Freezable.IsFrozen%2A>は`false`の読み込み時間、および [全般] に依存<xref:System.Windows.Freezable>時の動作。</span><span class="sxs-lookup"><span data-stu-id="bcec9-104">Default behavior for a <xref:System.Windows.Freezable> without the `PresentationOptions:Freeze` attribute specified is that <xref:System.Windows.Freezable.IsFrozen%2A> is `false` at load time, and dependent on general <xref:System.Windows.Freezable> behavior at runtime.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="bcec9-105">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="bcec9-105">XAML Attribute Usage</span></span>  
  
```  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="bcec9-106">XAML 値</span><span class="sxs-lookup"><span data-stu-id="bcec9-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`PresentationOptions`|<span data-ttu-id="bcec9-107">XML 1.0 仕様に従って、任意の有効なプレフィックス文字列を指定できる XML 名前空間プレフィックス。</span><span class="sxs-lookup"><span data-stu-id="bcec9-107">An XML namespace prefix, which can be any valid prefix string, per the XML 1.0 specification.</span></span> <span data-ttu-id="bcec9-108">プレフィックス`PresentationOptions`はこのドキュメントでの識別目的で使用します。</span><span class="sxs-lookup"><span data-stu-id="bcec9-108">The prefix `PresentationOptions` is used for identification purposes in this documentation.</span></span>|  
|`freezableElement`|<span data-ttu-id="bcec9-109">いずれかをインスタンス化する要素のクラスを派生する<xref:System.Windows.Freezable>します。</span><span class="sxs-lookup"><span data-stu-id="bcec9-109">An element that instantiates any derived class of <xref:System.Windows.Freezable>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bcec9-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="bcec9-110">Remarks</span></span>  
 <span data-ttu-id="bcec9-111">`Freeze`属性は、唯一の属性またはその他のプログラミング要素で定義されて、 `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML 名前空間。</span><span class="sxs-lookup"><span data-stu-id="bcec9-111">The `Freeze` attribute is the only attribute or other programming element defined in the `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML namespace.</span></span> <span data-ttu-id="bcec9-112">`Freeze` Ignorable としてを使用して、指定することができますように具体的には、この特別な名前空間の属性が存在する[mc: Ignorable 属性](mc-ignorable-attribute.md)ルート要素の宣言の一部として。</span><span class="sxs-lookup"><span data-stu-id="bcec9-112">The `Freeze` attribute exists in this special namespace specifically so that it can be designated as ignorable, using [mc:Ignorable Attribute](mc-ignorable-attribute.md) as part of the root element declarations.</span></span> <span data-ttu-id="bcec9-113">理由を`Freeze`が無視できる必要がありますでないため、すべて[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]プロセッサの実装に固定することは、<xref:System.Windows.Freezable>ロード時にこの機能はありませんの一部、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]仕様。</span><span class="sxs-lookup"><span data-stu-id="bcec9-113">The reason that `Freeze` must be able to be ignorable is because not all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementations are able to freeze a <xref:System.Windows.Freezable> at load time; this capability is not part of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] specification.</span></span>  
  
 <span data-ttu-id="bcec9-114">処理する機能、`Freeze`属性は、具体的に組み込まれている、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]処理プロセッサ[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]用にコンパイルされたアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="bcec9-114">The ability to process the `Freeze` attribute is specifically built in to the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor that processes [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] for compiled applications.</span></span> <span data-ttu-id="bcec9-115">属性は、任意のクラスでサポートされていないと、属性構文が拡張または変更します。</span><span class="sxs-lookup"><span data-stu-id="bcec9-115">The attribute is not supported by any class, and the attribute syntax is not extensible or modifiable.</span></span> <span data-ttu-id="bcec9-116">独自に実装している場合[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]プロセッサの固定動作することもできます、 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]プロセッサの処理時に、`Freeze`属性<xref:System.Windows.Freezable>の読み込み時に要素。</span><span class="sxs-lookup"><span data-stu-id="bcec9-116">If you are implementing your own [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor you can choose to parallel the freezing behavior of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor when processing the `Freeze` attribute on <xref:System.Windows.Freezable> elements at load time.</span></span>  
  
 <span data-ttu-id="bcec9-117">任意の値、`Freeze`以外の属性`true`(いない大文字小文字を区別)、負荷時のエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="bcec9-117">Any value for the `Freeze` attribute other than `true` (not case sensitive) generates a load time error.</span></span> <span data-ttu-id="bcec9-118">(を指定する、`Freeze`属性として`false`、エラーではありませんが、既定値設定するためにはない`false`は何も行いません)。</span><span class="sxs-lookup"><span data-stu-id="bcec9-118">(Specifying the `Freeze` attribute as `false` is not an error, but that is already the default, so setting to `false` does nothing).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcec9-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="bcec9-119">See also</span></span>

- <xref:System.Windows.Freezable>
- [<span data-ttu-id="bcec9-120">Freezable オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="bcec9-120">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="bcec9-121">mc:Ignorable 属性</span><span class="sxs-lookup"><span data-stu-id="bcec9-121">mc:Ignorable Attribute</span></span>](mc-ignorable-attribute.md)
