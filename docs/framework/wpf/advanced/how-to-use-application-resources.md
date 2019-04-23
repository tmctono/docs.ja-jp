---
title: '方法: アプリケーション リソースを使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- application resources [WPF]
- resources [WPF], application resources
ms.assetid: 507ea937-5191-406b-8797-0a3d9f94156d
ms.openlocfilehash: 70dff8089c4da70fdc61247a0c604cf7ee85d02b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59088204"
---
# <a name="how-to-use-application-resources"></a><span data-ttu-id="f78ab-102">方法: アプリケーション リソースを使用する</span><span class="sxs-lookup"><span data-stu-id="f78ab-102">How to: Use Application Resources</span></span>
<span data-ttu-id="f78ab-103">この例では、アプリケーション リソースを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f78ab-103">This example shows how to use application resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f78ab-104">例</span><span class="sxs-lookup"><span data-stu-id="f78ab-104">Example</span></span>  
 <span data-ttu-id="f78ab-105">次の例は、アプリケーション定義ファイルを示しています。</span><span class="sxs-lookup"><span data-stu-id="f78ab-105">The following example shows an application definition file.</span></span> <span data-ttu-id="f78ab-106">アプリケーション定義ファイルがリソース セクションを定義します (値を<xref:System.Windows.Application.Resources%2A>プロパティ)。</span><span class="sxs-lookup"><span data-stu-id="f78ab-106">The application definition file defines a resource section (a value for the <xref:System.Windows.Application.Resources%2A> property).</span></span> <span data-ttu-id="f78ab-107">アプリケーション レベルで定義されているリソースには、そのアプリケーションの一部であるその他すべてのページからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f78ab-107">Resources defined at the application level can be accessed by all other pages that are part of the application.</span></span> <span data-ttu-id="f78ab-108">この例では、リソースは宣言済みのスタイルです。</span><span class="sxs-lookup"><span data-stu-id="f78ab-108">In this case, the resource is a declared style.</span></span> <span data-ttu-id="f78ab-109">この例で、コントロール テンプレート内で定義されているを省略コントロール テンプレートを含む完全なスタイル指定できますが、時間がかかるため、<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>スタイルのプロパティ set アクセス操作子。</span><span class="sxs-lookup"><span data-stu-id="f78ab-109">Because a complete style that includes a control template can be lengthy, this example omits the control template that is defined within the <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> property setter of the style.</span></span>  
  
 [!code-xaml[ResourcesApplication#PreTemplateResource](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#pretemplateresource)]  
[!code-xaml[ResourcesApplication#PostTemplateResource](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#posttemplateresource)]  
  
 <span data-ttu-id="f78ab-110">次の例は、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]前の例で定義されているアプリケーション レベルのリソースを参照するページ。</span><span class="sxs-lookup"><span data-stu-id="f78ab-110">The following example shows a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page that references the application-level resource that the previous example defined.</span></span> <span data-ttu-id="f78ab-111">使用してリソースを参照する、 [StaticResource マークアップ拡張機能](staticresource-markup-extension.md)要求されたリソースの一意のリソース キーを指定します。</span><span class="sxs-lookup"><span data-stu-id="f78ab-111">The resource is referenced by using a     [StaticResource Markup Extension](staticresource-markup-extension.md) that specifies the unique resource key for the requested resource.</span></span> <span data-ttu-id="f78ab-112">"GelButton" というキーを持つリソースが、現在のページで見つからないため、要求されているリソースのリソース ルックアップ スコープは、現在のページを越えて、定義されているアプリケーション レベルのリソースまで継続されます。</span><span class="sxs-lookup"><span data-stu-id="f78ab-112">No resource with key of "GelButton" is found in the current page, so the resource lookup scope for the requested resource continues beyond the current page and into the defined application-level resources.</span></span>  
  
 [!code-xaml[ResourcesApplication#ConsumingPage](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/page1.xaml#consumingpage)]  
  
## <a name="see-also"></a><span data-ttu-id="f78ab-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="f78ab-113">See also</span></span>

- [<span data-ttu-id="f78ab-114">XAML リソース</span><span class="sxs-lookup"><span data-stu-id="f78ab-114">XAML Resources</span></span>](xaml-resources.md)
- [<span data-ttu-id="f78ab-115">アプリケーション管理の概要</span><span class="sxs-lookup"><span data-stu-id="f78ab-115">Application Management Overview</span></span>](../app-development/application-management-overview.md)
- [<span data-ttu-id="f78ab-116">方法トピック</span><span class="sxs-lookup"><span data-stu-id="f78ab-116">How-to Topics</span></span>](resources-how-to-topics.md)
