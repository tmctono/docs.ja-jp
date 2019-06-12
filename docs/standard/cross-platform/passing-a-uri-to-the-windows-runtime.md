---
title: Windows ランタイムへの URI の引き渡し
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Runtime, .NET Framework support for
- Windows Runtime, passing a URI to
ms.assetid: 3eb5ce6f-f304-4f87-8e81-0f25092f5ad4
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c489ec893ea335c8fafc904cf2a12162580ec266
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025440"
---
# <a name="passing-a-uri-to-the-windows-runtime"></a><span data-ttu-id="80b8e-102">Windows ランタイムへの URI の引き渡し</span><span class="sxs-lookup"><span data-stu-id="80b8e-102">Passing a URI to the Windows Runtime</span></span>
<span data-ttu-id="80b8e-103">Windows ランタイムのメソッドは絶対 URI だけを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="80b8e-103">Windows Runtime methods accept only absolute URIs.</span></span> <span data-ttu-id="80b8e-104">Windows ランタイム メソッドに相対 URI を渡す場合、<xref:System.ArgumentException>例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="80b8e-104">If you pass a relative URI to a Windows Runtime method, an <xref:System.ArgumentException> exception is thrown.</span></span> <span data-ttu-id="80b8e-105">その理由を説明します.NET Framework のコードで、Windows ランタイムを使用すると、<xref:Windows.Foundation.Uri?displayProperty=nameWithType>クラスとして表示されます<xref:System.Uri?displayProperty=nameWithType>Intellisense にします。</span><span class="sxs-lookup"><span data-stu-id="80b8e-105">Here's why: When you use the Windows Runtime in .NET Framework code, the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class appears as <xref:System.Uri?displayProperty=nameWithType> in Intellisense.</span></span> <span data-ttu-id="80b8e-106"><xref:System.Uri?displayProperty=nameWithType>クラスは、相対 Uri を使用できますが、<xref:Windows.Foundation.Uri?displayProperty=nameWithType>クラスはありません。</span><span class="sxs-lookup"><span data-stu-id="80b8e-106">The <xref:System.Uri?displayProperty=nameWithType> class allows relative URIs, but the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class does not.</span></span> <span data-ttu-id="80b8e-107">またこれは、Windows ランタイム コンポーネントで公開するメソッドに当てはまります。</span><span class="sxs-lookup"><span data-stu-id="80b8e-107">This is also true for methods you expose in Windows Runtime Components.</span></span> <span data-ttu-id="80b8e-108">URI を受け取るメソッドをコンポーネントで公開する場合、コードのシグネチャには <xref:System.Uri?displayProperty=nameWithType> が含まれます。</span><span class="sxs-lookup"><span data-stu-id="80b8e-108">If your component exposes a method that takes a URI, the signature in your code includes <xref:System.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="80b8e-109">ただし、コンポーネントのユーザーに、署名は<xref:Windows.Foundation.Uri?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="80b8e-109">However, to users of your component, the signature includes <xref:Windows.Foundation.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="80b8e-110">コンポーネントに渡す URI は、絶対 URI でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="80b8e-110">A URI that is passed to your component must be an absolute URI.</span></span>  
  
<span data-ttu-id="80b8e-111">このトピックでは、絶対 URI を検出する方法と、アプリ パッケージ内のリソースを参照するときに絶対 URI を作成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="80b8e-111">This topic shows how to detect an absolute URI and how to create one when referring to a resource in the app package.</span></span>  
  
## <a name="detecting-and-using-an-absolute-uri"></a><span data-ttu-id="80b8e-112">絶対 URI の検出と使用</span><span class="sxs-lookup"><span data-stu-id="80b8e-112">Detecting and using an absolute URI</span></span>  
<span data-ttu-id="80b8e-113">使用して、<xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType>プロパティを Windows ランタイムに渡す前に、URI が絶対であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="80b8e-113">Use the <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> property to ensure that a URI is absolute before passing it to the Windows Runtime.</span></span> <span data-ttu-id="80b8e-114">このプロパティを使用する方が、<xref:System.ArgumentException> 例外をキャッチして処理するより効率的です。</span><span class="sxs-lookup"><span data-stu-id="80b8e-114">Using this property is more efficient than catching and handling the <xref:System.ArgumentException> exception.</span></span>  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a><span data-ttu-id="80b8e-115">アプリ パッケージのリソースに対する絶対 URI の使用</span><span class="sxs-lookup"><span data-stu-id="80b8e-115">Using an absolute URI for a resource in the app package</span></span>  
<span data-ttu-id="80b8e-116">アプリのパッケージに含まれるリソースに対して URI を指定するには、`ms-appx` スキームまたは `ms-appx-web` スキームを使用して絶対 URI を作成します。</span><span class="sxs-lookup"><span data-stu-id="80b8e-116">If you want to specify a URI for a resource that your app package contains, you can use the `ms-appx` or `ms-appx-web` scheme to create an absolute URI.</span></span>  
  
<span data-ttu-id="80b8e-117">次の例は、設定する方法を示します、<xref:Windows.UI.Xaml.Controls.WebView.Source%2A>プロパティを<xref:Windows.UI.Xaml.Controls.WebView>コントロールと<xref:Windows.UI.Xaml.Controls.Image.Source%2A>プロパティを<xref:Windows.UI.Xaml.Controls.Image>XAML とコードの両方を使用して、ページをという名前のフォルダーに格納されているリソースへの制御。</span><span class="sxs-lookup"><span data-stu-id="80b8e-117">The following example shows how to set the <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> property for a <xref:Windows.UI.Xaml.Controls.WebView> control and the <xref:Windows.UI.Xaml.Controls.Image.Source%2A> property for an <xref:Windows.UI.Xaml.Controls.Image> control to resources that are contained in a folder named Pages, using both XAML and code.</span></span>  
  
[!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
<span data-ttu-id="80b8e-118">これらのスキームの詳細については、次を参照してください。 [URI スキーム](/windows/uwp/app-resources/uri-schemes)、Windows デベロッパー センターでします。</span><span class="sxs-lookup"><span data-stu-id="80b8e-118">For more information about these schemes, see [URI schemes](/windows/uwp/app-resources/uri-schemes) in the Windows Dev Center.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80b8e-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="80b8e-119">See also</span></span>

- [<span data-ttu-id="80b8e-120">Windows ストア アプリおよび Windows ランタイムのための .NET Framework サポート</span><span class="sxs-lookup"><span data-stu-id="80b8e-120">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
