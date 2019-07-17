---
title: '方法: ローカライズ可能アプリケーションでリソースを使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- applications [WPF], localizable
- localizable applications [WPF]
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
ms.openlocfilehash: 3634bb72cbacfb02b0a1230a47a1664cb8ce5009
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68238462"
---
# <a name="how-to-use-resources-in-localizable-applications"></a><span data-ttu-id="1e2b6-102">方法: ローカライズ可能アプリケーションでリソースを使用する</span><span class="sxs-lookup"><span data-stu-id="1e2b6-102">How to: Use Resources in Localizable Applications</span></span>
<span data-ttu-id="1e2b6-103">ローカライズを調整すること、[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]を異なるカルチャにします。</span><span class="sxs-lookup"><span data-stu-id="1e2b6-103">Localization means to adapt a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to different cultures.</span></span> <span data-ttu-id="1e2b6-104">そのためには、タイトル、キャプション、リスト ボックス項目などのテキストを翻訳する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e2b6-104">To do this, text such as titles, captions, list box items and so forth have to be translated.</span></span> <span data-ttu-id="1e2b6-105">翻訳しやすいように、翻訳される項目はリソース ファイルにまとめられています。</span><span class="sxs-lookup"><span data-stu-id="1e2b6-105">To make translation easier the items to be translated are collected into resource files.</span></span> <span data-ttu-id="1e2b6-106">参照してください[アプリケーションをローカライズする](how-to-localize-an-application.md)ローカリゼーション用リソース ファイルを作成する方法についてはします。</span><span class="sxs-lookup"><span data-stu-id="1e2b6-106">See [Localize an Application](how-to-localize-an-application.md) for information on how to create a resource file for localization.</span></span> <span data-ttu-id="1e2b6-107">させる、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーションをローカライズ可能で、開発者がローカライズ可能なすべてのリソースをリソース アセンブリにビルドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e2b6-107">To make a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application localizable, developers need to build all the localizable resources into a resource assembly.</span></span> <span data-ttu-id="1e2b6-108">さまざまな言語にローカライズされたリソース アセンブリと分離コードでは、リソース管理 API を使用して、読み込みます。</span><span class="sxs-lookup"><span data-stu-id="1e2b6-108">The resource assembly is localized into different languages, and the code-behind uses resource management API to load.</span></span> <span data-ttu-id="1e2b6-109">必要なファイルのいずれかを[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーションは、プロジェクト ファイル (.proj) です。</span><span class="sxs-lookup"><span data-stu-id="1e2b6-109">One of the files required for a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application is a project file (.proj).</span></span> <span data-ttu-id="1e2b6-110">アプリケーションで使用するすべてのリソースをプロジェクト ファイルに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e2b6-110">All resources that you use in your application should be included in the project file.</span></span> <span data-ttu-id="1e2b6-111">このコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1e2b6-111">The following code example shows this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e2b6-112">例</span><span class="sxs-lookup"><span data-stu-id="1e2b6-112">Example</span></span>  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
 `<Resource Include="data\picture1.jpg"/>`  
  
 `<EmbeddedResource Include="data\stringtable.en-US.restext"/>`  
  
 <span data-ttu-id="1e2b6-113">インスタンス化する、アプリケーションで、リソースを使用する<xref:System.Resources.ResourceManager>を使用するリソースを読み込むとします。</span><span class="sxs-lookup"><span data-stu-id="1e2b6-113">To use a resource in your application, you instantiate <xref:System.Resources.ResourceManager> and load the resource you want to use.</span></span> <span data-ttu-id="1e2b6-114">その方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1e2b6-114">The following demonstrates how to do this.</span></span>  
  
 [!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]
