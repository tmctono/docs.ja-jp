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
ms.openlocfilehash: c5ce0d4ac2b95dc4d51e785e3a00026f56c13d2c
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2018
ms.locfileid: "50220708"
---
# <a name="passing-a-uri-to-the-windows-runtime"></a><span data-ttu-id="8862b-102">Windows ランタイムへの URI の引き渡し</span><span class="sxs-lookup"><span data-stu-id="8862b-102">Passing a URI to the Windows Runtime</span></span>
<span data-ttu-id="8862b-103">Windows ランタイムのメソッドは絶対 URI だけを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8862b-103">Windows Runtime methods accept only absolute URIs.</span></span> <span data-ttu-id="8862b-104">[!INCLUDE[wrt](../../../includes/wrt-md.md)] メソッドに相対 URI を渡すと、<xref:System.ArgumentException> 例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="8862b-104">If you pass a relative URI to a [!INCLUDE[wrt](../../../includes/wrt-md.md)] method, an <xref:System.ArgumentException> exception is thrown.</span></span> <span data-ttu-id="8862b-105">その理由を次に示します: を使用すると、 [!INCLUDE[wrt](../../../includes/wrt-md.md)] 、.NET Framework コードで、<xref:Windows.Foundation.Uri?displayProperty=nameWithType>クラスとして表示されます<xref:System.Uri?displayProperty=nameWithType>Intellisense にします。</span><span class="sxs-lookup"><span data-stu-id="8862b-105">Here's why: When you use the [!INCLUDE[wrt](../../../includes/wrt-md.md)] in .NET Framework code, the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class appears as <xref:System.Uri?displayProperty=nameWithType> in Intellisense.</span></span> <span data-ttu-id="8862b-106"><xref:System.Uri?displayProperty=nameWithType>クラスは、相対 Uri を使用できますが、<xref:Windows.Foundation.Uri?displayProperty=nameWithType>クラスはありません。</span><span class="sxs-lookup"><span data-stu-id="8862b-106">The <xref:System.Uri?displayProperty=nameWithType> class allows relative URIs, but the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class does not.</span></span> <span data-ttu-id="8862b-107">[!INCLUDE[wrt](../../../includes/wrt-md.md)] コンポーネントで公開するメソッドでも同様です。</span><span class="sxs-lookup"><span data-stu-id="8862b-107">This is also true for methods you expose in [!INCLUDE[wrt](../../../includes/wrt-md.md)] Components.</span></span> <span data-ttu-id="8862b-108">URI を受け取るメソッドをコンポーネントで公開する場合、コードのシグネチャには <xref:System.Uri?displayProperty=nameWithType> が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8862b-108">If your component exposes a method that takes a URI, the signature in your code includes <xref:System.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="8862b-109">ただし、コンポーネントのユーザーに、署名は<xref:Windows.Foundation.Uri?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="8862b-109">However, to users of your component, the signature includes <xref:Windows.Foundation.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="8862b-110">コンポーネントに渡す URI は、絶対 URI でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="8862b-110">A URI that is passed to your component must be an absolute URI.</span></span>  
  
<span data-ttu-id="8862b-111">このトピックでは、絶対 URI を検出する方法と、アプリ パッケージ内のリソースを参照するときに絶対 URI を作成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="8862b-111">This topic shows how to detect an absolute URI and how to create one when referring to a resource in the app package.</span></span>  
  
## <a name="detecting-and-using-an-absolute-uri"></a><span data-ttu-id="8862b-112">絶対 URI の検出と使用</span><span class="sxs-lookup"><span data-stu-id="8862b-112">Detecting and using an absolute URI</span></span>  
<span data-ttu-id="8862b-113">URI を <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType>に渡す前にそれが絶対 URI であることを確認するには、[!INCLUDE[wrt](../../../includes/wrt-md.md)] プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="8862b-113">Use the <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> property to ensure that a URI is absolute before passing it to the [!INCLUDE[wrt](../../../includes/wrt-md.md)].</span></span> <span data-ttu-id="8862b-114">このプロパティを使用する方が、<xref:System.ArgumentException> 例外をキャッチして処理するより効率的です。</span><span class="sxs-lookup"><span data-stu-id="8862b-114">Using this property is more efficient than catching and handling the <xref:System.ArgumentException> exception.</span></span>  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a><span data-ttu-id="8862b-115">アプリ パッケージのリソースに対する絶対 URI の使用</span><span class="sxs-lookup"><span data-stu-id="8862b-115">Using an absolute URI for a resource in the app package</span></span>  
<span data-ttu-id="8862b-116">アプリのパッケージに含まれるリソースに対して URI を指定するには、`ms-appx` スキームまたは `ms-appx-web` スキームを使用して絶対 URI を作成します。</span><span class="sxs-lookup"><span data-stu-id="8862b-116">If you want to specify a URI for a resource that your app package contains, you can use the `ms-appx` or `ms-appx-web` scheme to create an absolute URI.</span></span>  
  
<span data-ttu-id="8862b-117">次の例は、設定する方法を示します、<xref:Windows.UI.Xaml.Controls.WebView.Source%2A>プロパティを<xref:Windows.UI.Xaml.Controls.WebView>コントロールと<xref:Windows.UI.Xaml.Controls.Image.Source%2A>プロパティを<xref:Windows.UI.Xaml.Controls.Image>XAML とコードの両方を使用して、ページをという名前のフォルダーに格納されているリソースへの制御。</span><span class="sxs-lookup"><span data-stu-id="8862b-117">The following example shows how to set the <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> property for a <xref:Windows.UI.Xaml.Controls.WebView> control and the <xref:Windows.UI.Xaml.Controls.Image.Source%2A> property for an <xref:Windows.UI.Xaml.Controls.Image> control to resources that are contained in a folder named Pages, using both XAML and code.</span></span>  
  
[!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
<span data-ttu-id="8862b-118">これらのスキームの詳細については、[URI スキーム](/windows/uwp/app-resources/uri-schemes)、Windows デベロッパー センターでを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8862b-118">For more information about these schemes, see [URI schemes](/windows/uwp/app-resources/uri-schemes) in the Windows Dev Center.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8862b-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="8862b-119">See also</span></span>

- [<span data-ttu-id="8862b-120">Windows ストア アプリおよび Windows ランタイムのための .NET Framework サポート</span><span class="sxs-lookup"><span data-stu-id="8862b-120">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
