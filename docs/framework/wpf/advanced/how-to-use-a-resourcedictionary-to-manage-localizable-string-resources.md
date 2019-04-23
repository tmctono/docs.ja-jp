---
title: '方法: ResourceDictionary を使用してローカライズ可能な文字列リソースを管理する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resources [WPF], packaging string resources
- packaging string resources [WPF]
- ResourceDictionary [WPF]
- localization [WPF], packaging string resources
ms.assetid: 19e7d9a5-20df-4ad3-b157-fe6515902e5e
ms.openlocfilehash: b56a307ed31fc8f7573215eac70350ac5e4b9de1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59772116"
---
# <a name="how-to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="a7f63-102">方法: ResourceDictionary を使用してローカライズ可能な文字列リソースを管理する</span><span class="sxs-lookup"><span data-stu-id="a7f63-102">How to: Use a ResourceDictionary to Manage Localizable String Resources</span></span>
<span data-ttu-id="a7f63-103">この例は、使用する方法を示します、 <xref:System.Windows.ResourceDictionary> Windows Presentation Foundation (WPF) アプリケーションのローカライズ可能な文字列リソースをパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="a7f63-103">This example shows how to use a <xref:System.Windows.ResourceDictionary> to package localizable string resources for Windows Presentation Foundation (WPF) applications.</span></span>  
  
### <a name="to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="a7f63-104">ResourceDictionary を使用してローカライズ可能な文字列リソースを管理するには</span><span class="sxs-lookup"><span data-stu-id="a7f63-104">To use a ResourceDictionary to manage localizable string resources</span></span>  
  
1. <span data-ttu-id="a7f63-105">作成、<xref:System.Windows.ResourceDictionary>にローカライズする文字列を格納しています。</span><span class="sxs-lookup"><span data-stu-id="a7f63-105">Create a <xref:System.Windows.ResourceDictionary> that contains the strings you would like to localize.</span></span> <span data-ttu-id="a7f63-106">次のコードは一例を示しています。</span><span class="sxs-lookup"><span data-stu-id="a7f63-106">The following code shows an example.</span></span>  
  
     [!code-xaml[StringLocalizationSample#StringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/StringResources.xaml#stringresourcedictionary)]  
  
     <span data-ttu-id="a7f63-107">このコードでは、文字列リソースを定義します。 `localizedMessage`、型の<xref:System.String>、から、 <xref:System> mscorlib.dll に名前空間。</span><span class="sxs-lookup"><span data-stu-id="a7f63-107">This code defines a string resource, `localizedMessage`, of type <xref:System.String>, from the <xref:System> namespace in mscorlib.dll.</span></span>  
  
2. <span data-ttu-id="a7f63-108">追加、<xref:System.Windows.ResourceDictionary>アプリケーションには、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="a7f63-108">Add the <xref:System.Windows.ResourceDictionary> to your application, using the following code.</span></span>  
  
     [!code-xaml[StringLocalizationSample#ReferencingStringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/App.xaml#referencingstringresourcedictionary)]  
  
3. <span data-ttu-id="a7f63-109">マークアップの文字列リソースを使用して、使用して[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]次のようにします。</span><span class="sxs-lookup"><span data-stu-id="a7f63-109">Use the string resource from markup, using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] like the following.</span></span>  
  
     [!code-xaml[StringLocalizationSample#GetLocalizedResourceFromMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml#getlocalizedresourcefrommarkup)]  
  
4. <span data-ttu-id="a7f63-110">次のようなコードを使用して、コードビハインドから文字列リソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="a7f63-110">Use the string resource from code-behind, using code like the following.</span></span>  
  
     [!code-csharp[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml.cs#getlocalizedresourcefromcode)]
     [!code-vb[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StringLocalizationSample/VisualBasic/MainWindow.xaml.vb#getlocalizedresourcefromcode)]  
  
5. <span data-ttu-id="a7f63-111">アプリケーションをローカライズします。</span><span class="sxs-lookup"><span data-stu-id="a7f63-111">Localize the application.</span></span> <span data-ttu-id="a7f63-112">詳細については、次を参照してください。[アプリケーションをローカライズする](how-to-localize-an-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="a7f63-112">For more information, see [Localize an Application](how-to-localize-an-application.md).</span></span>
