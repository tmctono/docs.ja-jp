---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 97a120c57624ada32e6661bd8a613c4ea1d01b2f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64591389"
---
# <a name="iwpfhostsupport"></a><span data-ttu-id="194f9-102">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="194f9-102">IWpfHostSupport</span></span>
<span data-ttu-id="194f9-103">アプリケーションをホストする[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]PresentationHost.exe でコンテンツがホストと PresentationHost.exe 間の統合のポイントを提供するには、このインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="194f9-103">Applications that host [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content via PresentationHost.exe implement this interface to provide a point of integration between the host and PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="194f9-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="194f9-104">Remarks</span></span>  
 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] <span data-ttu-id="194f9-105">Web ブラウザーなどのアプリケーションをホストできます[!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)]コンテンツを含む[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]XAML が失われるとします。</span><span class="sxs-lookup"><span data-stu-id="194f9-105">applications such as Web browsers can host [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content, including [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose XAML.</span></span> <span data-ttu-id="194f9-106">ホストに[!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)]コンテンツ、[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]アプリケーションのインスタンスを作成する、 [WebBrowser コントロール](https://go.microsoft.com/fwlink/?LinkId=97911)します。</span><span class="sxs-lookup"><span data-stu-id="194f9-106">To host [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications create an instance of the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span> <span data-ttu-id="194f9-107">ホストされる[!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)]PresentationHost.exe、提供、ホスト型のインスタンスを作成します[!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)]コンテンツ ホストに表示するために、 [WebBrowser コントロール](https://go.microsoft.com/fwlink/?LinkId=97911)します。</span><span class="sxs-lookup"><span data-stu-id="194f9-107">To be hosted, [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] creates an instance of PresentationHost.exe, which provides the hosted [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content to the host for display in the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span>  
  
 <span data-ttu-id="194f9-108">有効になっている統合`IWpfHostSupport`PresentationHost.exe できます。</span><span class="sxs-lookup"><span data-stu-id="194f9-108">The integration enabled by `IWpfHostSupport` allows PresentationHost.exe to:</span></span>  
  
- <span data-ttu-id="194f9-109">検出し、ホスト アプリケーションが関心を未加工入力デバイス (ヒューマン インターフェイス デバイス) を登録します。</span><span class="sxs-lookup"><span data-stu-id="194f9-109">Discover and register with the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
- <span data-ttu-id="194f9-110">未加工入力デバイスを登録し、適切なメッセージを転送から、ホスト アプリケーションへの入力メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="194f9-110">Receive input messages from the registered raw input devices and forward appropriate messages to the host application.</span></span>  
  
- <span data-ttu-id="194f9-111">ホスト アプリケーションの進行状況とエラーのカスタム ユーザー インターフェイスをクエリします。</span><span class="sxs-lookup"><span data-stu-id="194f9-111">Query the host application for custom progress and error user interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="194f9-112">この API は、ローカル クライアント コンピューターでの使用のみを目的とし、サポートされています。</span><span class="sxs-lookup"><span data-stu-id="194f9-112">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="194f9-113">メンバー</span><span class="sxs-lookup"><span data-stu-id="194f9-113">Members</span></span>  
  
|<span data-ttu-id="194f9-114">メンバー</span><span class="sxs-lookup"><span data-stu-id="194f9-114">Member</span></span>|<span data-ttu-id="194f9-115">説明</span><span class="sxs-lookup"><span data-stu-id="194f9-115">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="194f9-116">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="194f9-116">GetRawInputDevices</span></span>](getrawinputdevices.md)|<span data-ttu-id="194f9-117">PresentationHost.exe が、ホスト アプリケーションに必要な未加工入力デバイス (ヒューマン インターフェイス デバイス) を検出できるようにします。</span><span class="sxs-lookup"><span data-stu-id="194f9-117">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>|  
|[<span data-ttu-id="194f9-118">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="194f9-118">FilterInputMessage</span></span>](filterinputmessage.md)|<span data-ttu-id="194f9-119">E_NOTIMPL が返されない限り、メッセージを受信するたびに PresentationHost.exe によって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="194f9-119">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>|  
|[<span data-ttu-id="194f9-120">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="194f9-120">GetCustomUI</span></span>](getcustomui.md)|<span data-ttu-id="194f9-121">既定では、PresentationHost.exe は、独自のデプロイの進行状況と配置エラー WPF コンテンツが展開されているときに表示されるユーザー インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="194f9-121">By default, PresentationHost.exe provides its own deployment progress and deployment error user interfaces that are displayed when WPF content is deployed.</span></span>|
