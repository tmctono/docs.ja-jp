---
title: PresentationOptions:Freeze 属性
ms.date: 03/30/2017
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
ms.openlocfilehash: d3e0cee293a9585b972b0145da953976ed94b74c
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991421"
---
# <a name="presentationoptionsfreeze-attribute"></a><span data-ttu-id="0965a-102">PresentationOptions:Freeze 属性</span><span class="sxs-lookup"><span data-stu-id="0965a-102">PresentationOptions:Freeze Attribute</span></span>
<span data-ttu-id="0965a-103">`true` <xref:System.Windows.Freezable.IsFrozen%2A> 親<xref:System.Windows.Freezable>要素の状態をに設定します。</span><span class="sxs-lookup"><span data-stu-id="0965a-103">Sets the <xref:System.Windows.Freezable.IsFrozen%2A> state to `true` on the containing <xref:System.Windows.Freezable> element.</span></span> <span data-ttu-id="0965a-104">`PresentationOptions:Freeze` <xref:System.Windows.Freezable.IsFrozen%2A> 属性が指定さ<xref:System.Windows.Freezable>れてい<xref:System.Windows.Freezable>ないの既定の動作では、読み込み時にが実行時の一般的な動作に依存します。`false`</span><span class="sxs-lookup"><span data-stu-id="0965a-104">Default behavior for a <xref:System.Windows.Freezable> without the `PresentationOptions:Freeze` attribute specified is that <xref:System.Windows.Freezable.IsFrozen%2A> is `false` at load time, and dependent on general <xref:System.Windows.Freezable> behavior at runtime.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="0965a-105">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="0965a-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="0965a-106">XAML 値</span><span class="sxs-lookup"><span data-stu-id="0965a-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`PresentationOptions`|<span data-ttu-id="0965a-107">Xml 1.0 の仕様に従って、任意の有効なプレフィックス文字列を指定できる XML 名前空間プレフィックス。</span><span class="sxs-lookup"><span data-stu-id="0965a-107">An XML namespace prefix, which can be any valid prefix string, per the XML 1.0 specification.</span></span> <span data-ttu-id="0965a-108">このドキュメント`PresentationOptions`では、識別のためにプレフィックスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="0965a-108">The prefix `PresentationOptions` is used for identification purposes in this documentation.</span></span>|  
|`freezableElement`|<span data-ttu-id="0965a-109">の<xref:System.Windows.Freezable>派生クラスをインスタンス化する要素。</span><span class="sxs-lookup"><span data-stu-id="0965a-109">An element that instantiates any derived class of <xref:System.Windows.Freezable>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0965a-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="0965a-110">Remarks</span></span>  
 <span data-ttu-id="0965a-111">属性は、 `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML 名前空間で定義されている唯一の属性またはその他のプログラミング要素です。 `Freeze`</span><span class="sxs-lookup"><span data-stu-id="0965a-111">The `Freeze` attribute is the only attribute or other programming element defined in the `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML namespace.</span></span> <span data-ttu-id="0965a-112">属性`Freeze`は、ルート要素宣言の一部として[mc: ignorable 属性](mc-ignorable-attribute.md)を使用して、無視可能として指定できるように、この特別な名前空間に存在します。</span><span class="sxs-lookup"><span data-stu-id="0965a-112">The `Freeze` attribute exists in this special namespace specifically so that it can be designated as ignorable, using [mc:Ignorable Attribute](mc-ignorable-attribute.md) as part of the root element declarations.</span></span> <span data-ttu-id="0965a-113">が無視できる`Freeze`理由は、すべて[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]のプロセッサ実装が読み込み時にを<xref:System.Windows.Freezable>フリーズできるわけではないためです。この機能は[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]仕様の一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="0965a-113">The reason that `Freeze` must be able to be ignorable is because not all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementations are able to freeze a <xref:System.Windows.Freezable> at load time; this capability is not part of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] specification.</span></span>  
  
 <span data-ttu-id="0965a-114">`Freeze`属性を処理する機能は、コンパイルされたアプリケーション[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]のを処理[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]するプロセッサに特に組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="0965a-114">The ability to process the `Freeze` attribute is specifically built in to the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor that processes [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] for compiled applications.</span></span> <span data-ttu-id="0965a-115">属性はどのクラスでもサポートされていません。また、属性の構文は拡張または変更できません。</span><span class="sxs-lookup"><span data-stu-id="0965a-115">The attribute is not supported by any class, and the attribute syntax is not extensible or modifiable.</span></span> <span data-ttu-id="0965a-116">独自[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]のプロセッサを実装する場合は、読み込み時に<xref:System.Windows.Freezable>要素の`Freeze`属性を処理[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]するときに、 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]プロセッサのフリーズ動作を並列処理することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="0965a-116">If you are implementing your own [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor you can choose to parallel the freezing behavior of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor when processing the `Freeze` attribute on <xref:System.Windows.Freezable> elements at load time.</span></span>  
  
 <span data-ttu-id="0965a-117">`Freeze` 以外`true`の属性の値 (大文字と小文字は区別されません) は、読み込み時間エラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="0965a-117">Any value for the `Freeze` attribute other than `true` (not case sensitive) generates a load time error.</span></span> <span data-ttu-id="0965a-118">( `Freeze`属性をとし`false`て指定するのはエラーではなく、既に既定値で`false`あるため、をに設定することはできません)。</span><span class="sxs-lookup"><span data-stu-id="0965a-118">(Specifying the `Freeze` attribute as `false` is not an error, but that is already the default, so setting to `false` does nothing).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0965a-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="0965a-119">See also</span></span>

- <xref:System.Windows.Freezable>
- [<span data-ttu-id="0965a-120">Freezable オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="0965a-120">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="0965a-121">mc:Ignorable 属性</span><span class="sxs-lookup"><span data-stu-id="0965a-121">mc:Ignorable Attribute</span></span>](mc-ignorable-attribute.md)
