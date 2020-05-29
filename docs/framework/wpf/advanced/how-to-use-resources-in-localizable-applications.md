---
title: '方法: ローカライズ可能アプリケーションでリソースを使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- applications [WPF], localizable
- localizable applications [WPF]
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
ms.openlocfilehash: 8f516a86036656b98add23d38c588b5c19be4d7a
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212476"
---
# <a name="how-to-use-resources-in-localizable-apps"></a><span data-ttu-id="d679c-102">方法: ローカライズ可能なアプリでリソースを使用する</span><span class="sxs-lookup"><span data-stu-id="d679c-102">How to: Use resources in localizable apps</span></span>

<span data-ttu-id="d679c-103">ローカライズとは、ユーザー インターフェイスを異なるカルチャに適合させることを意味します。</span><span class="sxs-lookup"><span data-stu-id="d679c-103">Localization means to adapt a user interface to different cultures.</span></span> <span data-ttu-id="d679c-104">そのためには、タイトル、キャプション、リスト ボックス項目などのテキストを翻訳する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d679c-104">To do this, text such as titles, captions, and list box items must be translated.</span></span> <span data-ttu-id="d679c-105">翻訳しやすいように、翻訳される項目はリソース ファイルにまとめられています。</span><span class="sxs-lookup"><span data-stu-id="d679c-105">To make translation easier, the items to be translated are collected into resource files.</span></span> <span data-ttu-id="d679c-106">ローカライズ用のリソース ファイルの作成方法については、「[アプリケーションをローカライズする](how-to-localize-an-application.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d679c-106">See [Localize an app](how-to-localize-an-application.md) for information on how to create a resource file for localization.</span></span> <span data-ttu-id="d679c-107">開発者は、WPF アプリケーションをローカライズ可能にするために、ローカライズ可能なすべてのリソースをリソース アセンブリに組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="d679c-107">To make a WPF application localizable, developers need to build all the localizable resources into a resource assembly.</span></span> <span data-ttu-id="d679c-108">リソース アセンブリはさまざまな言語にローカライズされ、コードビハインドでリソース管理 API が使用されて読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="d679c-108">The resource assembly is localized into different languages, and the code-behind uses resource management API to load.</span></span>

## <a name="example"></a><span data-ttu-id="d679c-109">例</span><span class="sxs-lookup"><span data-stu-id="d679c-109">Example</span></span>

<span data-ttu-id="d679c-110">WPF アプリケーションに必要なファイルの 1 つは、プロジェクト ファイル (.proj) です。</span><span class="sxs-lookup"><span data-stu-id="d679c-110">One of the files required for a WPF application is a project file (.proj).</span></span> <span data-ttu-id="d679c-111">アプリケーションで使用するすべてのリソースをプロジェクト ファイルに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d679c-111">All resources that you use in your application should be included in the project file.</span></span> <span data-ttu-id="d679c-112">次の XAML の例がこれを示します。</span><span class="sxs-lookup"><span data-stu-id="d679c-112">The following XAML example shows this.</span></span>

```xaml
<Resource Include="data\picture1.jpg"/>  
<EmbeddedResource Include="data\stringtable.en-US.restext"/>
```

<span data-ttu-id="d679c-113">アプリケーションでリソースを使用するには、<xref:System.Resources.ResourceManager> をインスタンス化し、使用するリソースを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="d679c-113">To use a resource in your application, instantiate <xref:System.Resources.ResourceManager> and load the resource you want to use.</span></span> <span data-ttu-id="d679c-114">次の C# コードは、この設定方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d679c-114">The following C# code demonstrates how to do this.</span></span>

[!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]

## <a name="see-also"></a><span data-ttu-id="d679c-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="d679c-115">See also</span></span>

- [<span data-ttu-id="d679c-116">アプリをローカライズする</span><span class="sxs-lookup"><span data-stu-id="d679c-116">Localize an app</span></span>](how-to-localize-an-application.md)
