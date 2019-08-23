---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 994e5146e9cf49a9b31396d0b51e7be83bbb3cfb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964784"
---
# <a name="iwpfhostsupport"></a><span data-ttu-id="65bbe-102">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="65bbe-102">IWpfHostSupport</span></span>
<span data-ttu-id="65bbe-103">プレゼンテーションの cluster.exe [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]を使用してコンテンツをホストするアプリケーションは、このインターフェイスを実装して、ホストとプレゼンテーションの cluster.exe 間の統合ポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="65bbe-103">Applications that host [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content via PresentationHost.exe implement this interface to provide a point of integration between the host and PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65bbe-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="65bbe-104">Remarks</span></span>  
 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]<span data-ttu-id="65bbe-105">Web ブラウザーなどのアプリケーションは、 [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] XAML など[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]のコンテンツをホストできます。</span><span class="sxs-lookup"><span data-stu-id="65bbe-105">applications such as Web browsers can host [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content, including [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose XAML.</span></span> <span data-ttu-id="65bbe-106">コンテンツを[!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)]ホストする[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]ために、アプリケーションは[WebBrowser コントロール](https://go.microsoft.com/fwlink/?LinkId=97911)のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="65bbe-106">To host [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications create an instance of the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span> <span data-ttu-id="65bbe-107">ホストされるため[!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)]に、は、 [WebBrowser コントロール](https://go.microsoft.com/fwlink/?LinkId=97911)に表示するホストにホストさ[!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)]れたコンテンツを提供する、プレゼンテーションの cluster.exe のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="65bbe-107">To be hosted, [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] creates an instance of PresentationHost.exe, which provides the hosted [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content to the host for display in the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span>  
  
 <span data-ttu-id="65bbe-108">によって有効`IWpfHostSupport`にされた統合によって、次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="65bbe-108">The integration enabled by `IWpfHostSupport` allows PresentationHost.exe to:</span></span>  
  
- <span data-ttu-id="65bbe-109">ホストアプリケーションが興味を持っている未加工の入力デバイス (ヒューマンインターフェイスデバイス) を検出し、登録します。</span><span class="sxs-lookup"><span data-stu-id="65bbe-109">Discover and register with the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
- <span data-ttu-id="65bbe-110">登録されている未加工の入力デバイスから入力メッセージを受信し、適切なメッセージをホストアプリケーションに転送します。</span><span class="sxs-lookup"><span data-stu-id="65bbe-110">Receive input messages from the registered raw input devices and forward appropriate messages to the host application.</span></span>  
  
- <span data-ttu-id="65bbe-111">ホストアプリケーションに対して、カスタムの進行状況とエラーユーザーインターフェイスを照会します。</span><span class="sxs-lookup"><span data-stu-id="65bbe-111">Query the host application for custom progress and error user interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="65bbe-112">この API は、ローカル クライアント コンピューターでの使用のみを目的とし、サポートされています。</span><span class="sxs-lookup"><span data-stu-id="65bbe-112">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="65bbe-113">メンバー</span><span class="sxs-lookup"><span data-stu-id="65bbe-113">Members</span></span>  
  
|<span data-ttu-id="65bbe-114">メンバー</span><span class="sxs-lookup"><span data-stu-id="65bbe-114">Member</span></span>|<span data-ttu-id="65bbe-115">説明</span><span class="sxs-lookup"><span data-stu-id="65bbe-115">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="65bbe-116">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="65bbe-116">GetRawInputDevices</span></span>](getrawinputdevices.md)|<span data-ttu-id="65bbe-117">PresentationHost.exe が、ホスト アプリケーションに必要な未加工入力デバイス (ヒューマン インターフェイス デバイス) を検出できるようにします。</span><span class="sxs-lookup"><span data-stu-id="65bbe-117">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>|  
|[<span data-ttu-id="65bbe-118">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="65bbe-118">FilterInputMessage</span></span>](filterinputmessage.md)|<span data-ttu-id="65bbe-119">E_NOTIMPL が返されない限り、メッセージを受信するたびに PresentationHost.exe によって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="65bbe-119">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>|  
|[<span data-ttu-id="65bbe-120">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="65bbe-120">GetCustomUI</span></span>](getcustomui.md)|<span data-ttu-id="65bbe-121">既定では、プレゼンテーションの cluster.exe によって、WPF コンテンツが配置されるときに表示される、独自の配置の進行状況と配置エラーのユーザーインターフェイスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="65bbe-121">By default, PresentationHost.exe provides its own deployment progress and deployment error user interfaces that are displayed when WPF content is deployed.</span></span>|
