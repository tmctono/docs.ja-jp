---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 85309e46403b2f22f9afb760d4c4ae370c39246b
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004097"
---
# <a name="iwpfhostsupport"></a><span data-ttu-id="6e898-102">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="6e898-102">IWpfHostSupport</span></span>
<span data-ttu-id="6e898-103">プレゼンテーションの cluster.exe を介して [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] のコンテンツをホストするアプリケーションは、このインターフェイスを実装して、ホストとプレゼンテーションの cluster.exe の間の統合ポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="6e898-103">Applications that host [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content via PresentationHost.exe implement this interface to provide a point of integration between the host and PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e898-104">コメント</span><span class="sxs-lookup"><span data-stu-id="6e898-104">Remarks</span></span>  
 <span data-ttu-id="6e898-105">Web ブラウザーなどの @no__t 0 のアプリケーションは、[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]、ルース XAML などの WPF コンテンツをホストできます。</span><span class="sxs-lookup"><span data-stu-id="6e898-105">[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications such as Web browsers can host WPF content, including [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose XAML.</span></span> <span data-ttu-id="6e898-106">WPF コンテンツをホストするために、[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] のアプリケーションは[WebBrowser コントロール](https://go.microsoft.com/fwlink/?LinkId=97911)のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e898-106">To host WPF content, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications create an instance of the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span> <span data-ttu-id="6e898-107">ホストされるようにするために、WPF は、ホストされている WPF コンテンツをホストに提供し、 [WebBrowser コントロール](https://go.microsoft.com/fwlink/?LinkId=97911)に表示するための、プレゼンテーション用の cluster.exe インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e898-107">To be hosted, WPF creates an instance of PresentationHost.exe, which provides the hosted WPF content to the host for display in the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span>  
  
 <span data-ttu-id="6e898-108">@No__t-0 によって有効にされた統合によって、次のようなプレゼンテーションを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6e898-108">The integration enabled by `IWpfHostSupport` allows PresentationHost.exe to:</span></span>  
  
- <span data-ttu-id="6e898-109">ホストアプリケーションが興味を持っている未加工の入力デバイス (ヒューマンインターフェイスデバイス) を検出し、登録します。</span><span class="sxs-lookup"><span data-stu-id="6e898-109">Discover and register with the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
- <span data-ttu-id="6e898-110">登録されている未加工の入力デバイスから入力メッセージを受信し、適切なメッセージをホストアプリケーションに転送します。</span><span class="sxs-lookup"><span data-stu-id="6e898-110">Receive input messages from the registered raw input devices and forward appropriate messages to the host application.</span></span>  
  
- <span data-ttu-id="6e898-111">ホストアプリケーションに対して、カスタムの進行状況とエラーユーザーインターフェイスを照会します。</span><span class="sxs-lookup"><span data-stu-id="6e898-111">Query the host application for custom progress and error user interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6e898-112">この API は、ローカル クライアント コンピューターでの使用のみを目的とし、サポートされています。</span><span class="sxs-lookup"><span data-stu-id="6e898-112">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="6e898-113">メンバー</span><span class="sxs-lookup"><span data-stu-id="6e898-113">Members</span></span>  
  
|<span data-ttu-id="6e898-114">メンバー</span><span class="sxs-lookup"><span data-stu-id="6e898-114">Member</span></span>|<span data-ttu-id="6e898-115">説明</span><span class="sxs-lookup"><span data-stu-id="6e898-115">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6e898-116">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="6e898-116">GetRawInputDevices</span></span>](getrawinputdevices.md)|<span data-ttu-id="6e898-117">PresentationHost.exe が、ホスト アプリケーションに必要な未加工入力デバイス (ヒューマン インターフェイス デバイス) を検出できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6e898-117">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>|  
|[<span data-ttu-id="6e898-118">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="6e898-118">FilterInputMessage</span></span>](filterinputmessage.md)|<span data-ttu-id="6e898-119">E_NOTIMPL が返されない限り、メッセージを受信するたびに PresentationHost.exe によって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="6e898-119">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>|  
|[<span data-ttu-id="6e898-120">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="6e898-120">GetCustomUI</span></span>](getcustomui.md)|<span data-ttu-id="6e898-121">既定では、プレゼンテーションの cluster.exe によって、WPF コンテンツが配置されるときに表示される、独自の配置の進行状況と配置エラーのユーザーインターフェイスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="6e898-121">By default, PresentationHost.exe provides its own deployment progress and deployment error user interfaces that are displayed when WPF content is deployed.</span></span>|
