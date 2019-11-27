---
title: プロジェクトのカスタマイズと My の拡張
ms.date: 07/20/2015
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: 06ca80b9-1192-4eb5-8537-8ef5edfb9be0
ms.openlocfilehash: e6ed43aeff90295f71590bcee180ca1e0f88e5ff
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330336"
---
# <a name="customizing-projects-and-extending-my-with-visual-basic"></a><span data-ttu-id="4a673-102">Visual Basic でのプロジェクトのカスタマイズと My の拡張</span><span class="sxs-lookup"><span data-stu-id="4a673-102">Customizing Projects and Extending My with Visual Basic</span></span>

<span data-ttu-id="4a673-103">プロジェクトテンプレートをカスタマイズして、追加の `My` オブジェクトを提供できます。</span><span class="sxs-lookup"><span data-stu-id="4a673-103">You can customize project templates to provide additional `My` objects.</span></span> <span data-ttu-id="4a673-104">これにより、他の開発者がオブジェクトを簡単に見つけて使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4a673-104">This makes it easy for other developers to find and use your objects.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="4a673-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4a673-105">In this section</span></span>

- [<span data-ttu-id="4a673-106">Visual Basic における My 名前空間の拡張</span><span class="sxs-lookup"><span data-stu-id="4a673-106">Extending the My Namespace in Visual Basic</span></span>](extending-the-my-namespace.md)  
 <span data-ttu-id="4a673-107">Visual Basic の `My` 名前空間にカスタムメンバーと値を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4a673-107">Describes how to add custom members and values to the `My` namespace in Visual Basic.</span></span>
- [<span data-ttu-id="4a673-108">カスタム My 拡張のパッケージ化と配置</span><span class="sxs-lookup"><span data-stu-id="4a673-108">Packaging and Deploying Custom My Extensions</span></span>](packaging-and-deploying-custom-my-extensions.md)  
 <span data-ttu-id="4a673-109">Visual Studio テンプレートを使用して、カスタム `My` 名前空間拡張を発行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4a673-109">Describes how to publish custom `My` namespace extensions by using Visual Studio templates.</span></span>
- [<span data-ttu-id="4a673-110">Visual Basic アプリケーション モデルの拡張</span><span class="sxs-lookup"><span data-stu-id="4a673-110">Extending the Visual Basic Application Model</span></span>](extending-the-visual-basic-application-model.md)  
 <span data-ttu-id="4a673-111"><xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> クラスのメンバーをオーバーライドして、アプリケーションモデルに独自の拡張機能を指定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4a673-111">Describes how to specify your own extensions to the application model by overriding members of the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> class.</span></span>
- [<span data-ttu-id="4a673-112">My で利用可能なオブジェクトのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="4a673-112">Customizing Which Objects are Available in My</span></span>](customizing-which-objects-are-available-in-my.md)  
 <span data-ttu-id="4a673-113">プロジェクトの \_MYTYPE の条件付きコンパイル定数を設定することによって、どの `My` オブジェクトを有効にするかを制御する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4a673-113">Describes how to control which `My` objects are enabled by setting your project's \_MYTYPE conditional-compilation constant.</span></span>

## <a name="related-sections"></a><span data-ttu-id="4a673-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a673-114">Related sections</span></span>

- [<span data-ttu-id="4a673-115">My による開発</span><span class="sxs-lookup"><span data-stu-id="4a673-115">Development with My</span></span>](../development-with-my/index.md)  
 <span data-ttu-id="4a673-116">既定では、さまざまなプロジェクトの種類で使用できる `My` オブジェクトについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4a673-116">Describes which `My` objects are available in different project types by default.</span></span>
- [<span data-ttu-id="4a673-117">Visual Basic アプリケーション モデルの概要</span><span class="sxs-lookup"><span data-stu-id="4a673-117">Overview of the Visual Basic Application Model</span></span>](../development-with-my/overview-of-the-visual-basic-application-model.md)  
 <span data-ttu-id="4a673-118">Windows フォームアプリケーションの動作を制御するための Visual Basic のモデルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4a673-118">Describes Visual Basic's model for controlling the behavior of Windows Forms applications.</span></span>
- [<span data-ttu-id="4a673-119">プロジェクトの種類に応じた My の機能</span><span class="sxs-lookup"><span data-stu-id="4a673-119">How My Depends on Project Type</span></span>](../development-with-my/how-my-depends-on-project-type.md)  
 <span data-ttu-id="4a673-120">既定では、さまざまなプロジェクトの種類で使用できる `My` オブジェクトについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4a673-120">Describes which `My` objects are available in different project types by default.</span></span>
- [<span data-ttu-id="4a673-121">条件付きコンパイル</span><span class="sxs-lookup"><span data-stu-id="4a673-121">Conditional Compilation</span></span>](../../programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="4a673-122">コンパイラが条件付きコンパイルを使用してコードの特定のセクションを選択し、コンパイルして他のセクションを除外する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4a673-122">Discusses how the compiler uses conditional-compilation to select particular sections of code to compile and exclude other sections.</span></span>
- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <span data-ttu-id="4a673-123">現在のアプリケーションに関連するプロパティ、メソッド、およびイベントを提供する `My` オブジェクトについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4a673-123">Describes the `My` object that provides properties, methods, and events related to the current application.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a673-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a673-124">See also</span></span>

- [<span data-ttu-id="4a673-125">Visual Basic でのアプリケーションの開発</span><span class="sxs-lookup"><span data-stu-id="4a673-125">Developing Applications with Visual Basic</span></span>](../index.md)
