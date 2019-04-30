---
title: x:Reference のマークアップ拡張機能
ms.date: 03/30/2017
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
ms.openlocfilehash: 960f5c0e4192df72090c1a571dfc2fc5e3fd8ba3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938880"
---
# <a name="xreference-markup-extension"></a><span data-ttu-id="04e5d-102">x:Reference のマークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="04e5d-102">x:Reference Markup Extension</span></span>
<span data-ttu-id="04e5d-103">XAML マークアップで他の場所で宣言されているインスタンスを参照します。</span><span class="sxs-lookup"><span data-stu-id="04e5d-103">References an instance that is declared elsewhere in XAML markup.</span></span> <span data-ttu-id="04e5d-104">参照が指す要素の`x:Name`します。</span><span class="sxs-lookup"><span data-stu-id="04e5d-104">The reference refers to an element's `x:Name`.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="04e5d-105">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="04e5d-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Reference instancexName}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="04e5d-106">XAML オブジェクト要素の使用方法</span><span class="sxs-lookup"><span data-stu-id="04e5d-106">XAML Object Element Usage</span></span>  
  
```xaml  
<object>  
  <object.property>  
    <x:Reference Name="instancexName"/>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="04e5d-107">XAML 値</span><span class="sxs-lookup"><span data-stu-id="04e5d-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`instancexName`|<span data-ttu-id="04e5d-108">`x:Name`値 (またはの値、 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-プロパティを識別) の参照先のインスタンス。</span><span class="sxs-lookup"><span data-stu-id="04e5d-108">The `x:Name` value (or value of the <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-identified property) of the referenced instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04e5d-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="04e5d-109">Remarks</span></span>  
 <span data-ttu-id="04e5d-110">`x:Reference` WPF などの特定のフレームワークで実装された場合は要素の参照の概念の XAML 言語レベルのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="04e5d-110">`x:Reference` provides XAML language-level support for an element reference concept that was otherwise implemented in specific frameworks such as WPF.</span></span>  
  
## <a name="xreference-and-wpf"></a><span data-ttu-id="04e5d-111">X:reference と WPF</span><span class="sxs-lookup"><span data-stu-id="04e5d-111">x:Reference and WPF</span></span>  
 <span data-ttu-id="04e5d-112">WPF および XAML 2006 では、要素の参照は、フレームワーク レベルの機能のによってアドレス指定<xref:System.Windows.Data.Binding.ElementName%2A>バインドします。</span><span class="sxs-lookup"><span data-stu-id="04e5d-112">In WPF and XAML 2006, element references are addressed by the framework-level feature of <xref:System.Windows.Data.Binding.ElementName%2A> binding.</span></span> <span data-ttu-id="04e5d-113">ほとんどの WPF アプリケーションとシナリオでは、<xref:System.Windows.Data.Binding.ElementName%2A>引き続きバインドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04e5d-113">For most WPF applications and scenarios, <xref:System.Windows.Data.Binding.ElementName%2A> binding should still be used.</span></span> <span data-ttu-id="04e5d-114">この一般的なガイダンスの例外には可能性がありますがあるデータ コンテキスト、またはその他のスコープの考慮事項は実用的でないデータ バインディングを構成する場合、およびマークアップのコンパイルが含まれていない場合、ケースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="04e5d-114">Exceptions to this general guidance might include cases where there are data context or other scoping considerations that make data binding impractical and where markup compilation is not involved.</span></span>  
  
 <span data-ttu-id="04e5d-115">`x:Reference` コンストラクトは、XAML 2009 で定義されます。</span><span class="sxs-lookup"><span data-stu-id="04e5d-115">`x:Reference` is a construct defined in XAML 2009.</span></span> <span data-ttu-id="04e5d-116">WPF では XAML 2009 の機能を使用できますが、WPF マークアップ コンパイルされていない XAML に限定されます。</span><span class="sxs-lookup"><span data-stu-id="04e5d-116">In WPF, you can use XAML 2009 features, but only for XAML that is not WPF markup-compiled.</span></span> <span data-ttu-id="04e5d-117">マークアップ コンパイルされた XAML、および XAML の BAML 形式は、現在、XAML 2009 言語のキーワードと機能をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="04e5d-117">Markup-compiled XAML and the BAML form of XAML do not currently support the XAML 2009 language keywords and features.</span></span>
