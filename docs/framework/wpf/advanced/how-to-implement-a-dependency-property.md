---
title: '方法: 依存関係プロパティを実装する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dependency properties [WPF], backing properties with
- properties [WPF], backing with dependency properties
ms.assetid: 855fd6d7-19ac-493c-bf5e-2f40b57cdc92
ms.openlocfilehash: 6f2fb9b0824feb6253527de063f58da2427d0c06
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2019
ms.locfileid: "68400355"
---
# <a name="how-to-implement-a-dependency-property"></a><span data-ttu-id="080b6-102">方法: 依存関係プロパティを実装する</span><span class="sxs-lookup"><span data-stu-id="080b6-102">How to: Implement a Dependency Property</span></span>
<span data-ttu-id="080b6-103">この例では、共通言語ランタイム (CLR) プロパティを<xref:System.Windows.DependencyProperty>フィールドで戻して、依存関係プロパティを定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="080b6-103">This example shows how to back a common language runtime (CLR) property with a <xref:System.Windows.DependencyProperty> field, thus defining a dependency property.</span></span> <span data-ttu-id="080b6-104">独自に定義したプロパティが [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] のさまざまな機能、たとえばスタイル、データ バインディング、継承、アニメーション、既定値をサポートできるようにするには、そのプロパティを依存関係プロパティとして実装します。</span><span class="sxs-lookup"><span data-stu-id="080b6-104">When you define your own properties and want them to support many aspects of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] functionality, including styles, data binding, inheritance, animation, and default values, you should implement them as a dependency property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="080b6-105">例</span><span class="sxs-lookup"><span data-stu-id="080b6-105">Example</span></span>  
 <span data-ttu-id="080b6-106">次の例では、最初に<xref:System.Windows.DependencyProperty.Register%2A>メソッドを呼び出して依存関係プロパティを登録します。</span><span class="sxs-lookup"><span data-stu-id="080b6-106">The following example first registers a dependency property by calling the <xref:System.Windows.DependencyProperty.Register%2A> method.</span></span> <span data-ttu-id="080b6-107">依存関係プロパティの名前と特性を格納するために使用する識別子フィールドの名前は、 <xref:System.Windows.DependencyProperty.Name%2A> <xref:System.Windows.DependencyProperty.Register%2A>呼び出しの一部として、依存関係プロパティに対して選択したで、リテラル`Property`文字列によって追加される必要があります。</span><span class="sxs-lookup"><span data-stu-id="080b6-107">The name of the identifier field that you use to store the name and characteristics of the dependency property must be the <xref:System.Windows.DependencyProperty.Name%2A> you chose for the dependency property as part of the <xref:System.Windows.DependencyProperty.Register%2A> call, appended by the literal string `Property`.</span></span> <span data-ttu-id="080b6-108">たとえば、 <xref:System.Windows.DependencyProperty.Name%2A>の`Location`を使用して依存関係プロパティを登録する場合、依存関係プロパティに定義する識別子フィールドの名前`LocationProperty`はにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="080b6-108">For instance, if you register a dependency property with a <xref:System.Windows.DependencyProperty.Name%2A> of `Location`, then the identifier field that you define for the dependency property must be named `LocationProperty`.</span></span>  
  
 <span data-ttu-id="080b6-109">この例で`State`は、依存関係プロパティとその CLR アクセサーの名前はです。識別子フィールドは`StateProperty`です。プロパティの型は<xref:System.Boolean>で、依存関係プロパティ`MyStateControl`を登録する型はです。</span><span class="sxs-lookup"><span data-stu-id="080b6-109">In this example, the name of the dependency property and its CLR accessor is `State`; the identifier field is `StateProperty`; the type of the property is <xref:System.Boolean>; and the type that registers the dependency property is `MyStateControl`.</span></span>  
  
 <span data-ttu-id="080b6-110">このパターンに従って名前が付けられていない場合は、定義したプロパティがデザイナーから正しく報告されず、プロパティ システムのスタイル適用の一部が予期したとおりに動作しなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="080b6-110">If you fail to follow this naming pattern, designers might not report your property correctly, and certain aspects of property system style application might not behave as expected.</span></span>  
  
 <span data-ttu-id="080b6-111">依存関係プロパティの既定のメタデータを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="080b6-111">You can also specify default metadata for a dependency property.</span></span> <span data-ttu-id="080b6-112">`State` 依存関係プロパティの既定値を `false` として登録する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="080b6-112">This example registers the default value of the `State` dependency property to be `false`.</span></span>  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 <span data-ttu-id="080b6-113">プライベートフィールドで CLR プロパティをバックアップするだけではなく、依存関係プロパティを実装する方法と理由の詳細については、「[依存関係プロパティの概要](dependency-properties-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="080b6-113">For more information about how and why to implement a dependency property, as opposed to just backing a CLR property with a private field, see [Dependency Properties Overview](dependency-properties-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="080b6-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="080b6-114">See also</span></span>

- [<span data-ttu-id="080b6-115">依存関係プロパティの概要</span><span class="sxs-lookup"><span data-stu-id="080b6-115">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="080b6-116">方法トピック</span><span class="sxs-lookup"><span data-stu-id="080b6-116">How-to Topics</span></span>](properties-how-to-topics.md)
