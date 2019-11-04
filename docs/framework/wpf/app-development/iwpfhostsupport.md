---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 91a29233d12a842a64b7d3dd497312f6dc6742ca
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423647"
---
# <a name="iwpfhostsupport"></a><span data-ttu-id="41cce-102">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="41cce-102">IWpfHostSupport</span></span>
<span data-ttu-id="41cce-103">プレゼンテーションの cluster.exe を介して [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] コンテンツをホストするアプリケーションは、このインターフェイスを実装して、ホストとプレゼンテーションの cluster.exe の間の統合ポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="41cce-103">Applications that host [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content via PresentationHost.exe implement this interface to provide a point of integration between the host and PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41cce-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="41cce-104">Remarks</span></span>  
 <span data-ttu-id="41cce-105">Web ブラウザーなどの [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] アプリケーションは、XAML ブラウザーアプリケーション (Xbap) やルース XAML などの WPF コンテンツをホストできます。</span><span class="sxs-lookup"><span data-stu-id="41cce-105">[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications such as Web browsers can host WPF content, including XAML browser applications (XBAPs) and loose XAML.</span></span> <span data-ttu-id="41cce-106">WPF コンテンツをホストするために、[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] アプリケーションは[WebBrowser コントロール](https://go.microsoft.com/fwlink/?LinkId=97911)のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="41cce-106">To host WPF content, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications create an instance of the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span> <span data-ttu-id="41cce-107">ホストされるようにするために、WPF は、ホストされている WPF コンテンツをホストに提供し、 [WebBrowser コントロール](https://go.microsoft.com/fwlink/?LinkId=97911)に表示するための、プレゼンテーション用の cluster.exe インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="41cce-107">To be hosted, WPF creates an instance of PresentationHost.exe, which provides the hosted WPF content to the host for display in the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span>  
  
 <span data-ttu-id="41cce-108">`IWpfHostSupport` によって有効にされた統合によって、次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="41cce-108">The integration enabled by `IWpfHostSupport` allows PresentationHost.exe to:</span></span>  
  
- <span data-ttu-id="41cce-109">ホストアプリケーションが興味を持っている未加工の入力デバイス (ヒューマンインターフェイスデバイス) を検出し、登録します。</span><span class="sxs-lookup"><span data-stu-id="41cce-109">Discover and register with the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
- <span data-ttu-id="41cce-110">登録されている未加工の入力デバイスから入力メッセージを受信し、適切なメッセージをホストアプリケーションに転送します。</span><span class="sxs-lookup"><span data-stu-id="41cce-110">Receive input messages from the registered raw input devices and forward appropriate messages to the host application.</span></span>  
  
- <span data-ttu-id="41cce-111">ホストアプリケーションに対して、カスタムの進行状況とエラーユーザーインターフェイスを照会します。</span><span class="sxs-lookup"><span data-stu-id="41cce-111">Query the host application for custom progress and error user interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="41cce-112">この API は、ローカル クライアント コンピューターでの使用のみを目的とし、サポートされています。</span><span class="sxs-lookup"><span data-stu-id="41cce-112">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="41cce-113">メンバー</span><span class="sxs-lookup"><span data-stu-id="41cce-113">Members</span></span>  
  
|<span data-ttu-id="41cce-114">メンバー</span><span class="sxs-lookup"><span data-stu-id="41cce-114">Member</span></span>|<span data-ttu-id="41cce-115">説明</span><span class="sxs-lookup"><span data-stu-id="41cce-115">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="41cce-116">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="41cce-116">GetRawInputDevices</span></span>](getrawinputdevices.md)|<span data-ttu-id="41cce-117">PresentationHost.exe が、ホスト アプリケーションに必要な未加工入力デバイス (ヒューマン インターフェイス デバイス) を検出できるようにします。</span><span class="sxs-lookup"><span data-stu-id="41cce-117">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>|  
|[<span data-ttu-id="41cce-118">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="41cce-118">FilterInputMessage</span></span>](filterinputmessage.md)|<span data-ttu-id="41cce-119">E_NOTIMPL が返されない限り、メッセージを受信するたびに PresentationHost.exe によって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="41cce-119">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>|  
|[<span data-ttu-id="41cce-120">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="41cce-120">GetCustomUI</span></span>](getcustomui.md)|<span data-ttu-id="41cce-121">既定では、プレゼンテーションの cluster.exe によって、WPF コンテンツが配置されるときに表示される、独自の配置の進行状況と配置エラーのユーザーインターフェイスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="41cce-121">By default, PresentationHost.exe provides its own deployment progress and deployment error user interfaces that are displayed when WPF content is deployed.</span></span>|
