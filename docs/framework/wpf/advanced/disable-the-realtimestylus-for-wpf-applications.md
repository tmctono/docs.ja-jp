---
title: リアルタイムスタイラスを無効にする
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: c2500b494f76c85e4b23823a44a180d85d5092ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186077"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a><span data-ttu-id="4f021-102">WPF アプリケーションのリアルタイムなスタイラス入力を無効にする</span><span class="sxs-lookup"><span data-stu-id="4f021-102">Disable the RealTimeStylus for WPF Applications</span></span>

<span data-ttu-id="4f021-103">Windows プレゼンテーションファンデーション (WPF) は、Windows 7 タッチ入力の処理のサポートを組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="4f021-103">Windows Presentation Foundation (WPF) has built in support for processing Windows 7 touch input.</span></span> <span data-ttu-id="4f021-104">サポートは、タブレット プラットフォームのリアルタイムスタイラス入力 、 、<xref:System.Windows.UIElement.OnStylusDown%2A><xref:System.Windows.UIElement.OnStylusUp%2A>および<xref:System.Windows.UIElement.OnStylusMove%2A>イベントを介して提供されます。</span><span class="sxs-lookup"><span data-stu-id="4f021-104">The support comes through the tablet platform’s real-time stylus input as <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, and <xref:System.Windows.UIElement.OnStylusMove%2A> events.</span></span> <span data-ttu-id="4f021-105">Windows 7 では、ウィンドウ メッセージの Win32 WM_TOUCHマルチタッチ入力も提供されます。</span><span class="sxs-lookup"><span data-stu-id="4f021-105">Windows 7 also provides multi-touch input as Win32 WM_TOUCH window messages.</span></span> <span data-ttu-id="4f021-106">これら 2 つの API は、同じ HWND 上で相互に排他的です。</span><span class="sxs-lookup"><span data-stu-id="4f021-106">These two APIs are mutually exclusive on the same HWND.</span></span> <span data-ttu-id="4f021-107">タブレット プラットフォーム (WPF アプリケーションの既定値) を介してタッチ入力を有効にすると、WM_TOUCHメッセージが無効になります。</span><span class="sxs-lookup"><span data-stu-id="4f021-107">Enabling touch input via the tablet platform (the default for WPF applications) disables WM_TOUCH messages.</span></span> <span data-ttu-id="4f021-108">その結果、WM_TOUCHを使用して WPF ウィンドウからタッチ メッセージを受信するには、WPF で組み込みのスタイラス サポートを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f021-108">As a result, to use WM_TOUCH to receive touch messages from a WPF window, you must disable the built-in stylus support in WPF.</span></span> <span data-ttu-id="4f021-109">これは、WM_TOUCHを使用するコンポーネントをホストする WPF ウィンドウなどのシナリオに適用されます。</span><span class="sxs-lookup"><span data-stu-id="4f021-109">This is applicable in a scenario such as a WPF window hosting a component that uses WM_TOUCH.</span></span>  
  
 <span data-ttu-id="4f021-110">スタイラス入力をリッスンする WPF を無効にするには、WPF ウィンドウによって追加されたタブレット サポートを削除します。</span><span class="sxs-lookup"><span data-stu-id="4f021-110">To disable WPF listening to stylus input, remove any tablet support added by the WPF window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f021-111">例</span><span class="sxs-lookup"><span data-stu-id="4f021-111">Example</span></span>  
 <span data-ttu-id="4f021-112">次のサンプル コードは、リフレクションを使用して既定のタブレット プラットフォーム サポートを削除する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4f021-112">The following sample code shows how to remove the default tablet platform support by using reflection.</span></span>  
  
```csharp  
public static void DisableWPFTabletSupport()  
{  
    // Get a collection of the tablet devices for this window.
    TabletDeviceCollection devices = System.Windows.Input.Tablet.TabletDevices;  
  
    if (devices.Count > 0)  
    {
        // Get the Type of InputManager.  
        Type inputManagerType = typeof(System.Windows.Input.InputManager);  
  
        // Call the StylusLogic method on the InputManager.Current instance.  
        object stylusLogic = inputManagerType.InvokeMember("StylusLogic",  
                    BindingFlags.GetProperty | BindingFlags.Instance | BindingFlags.NonPublic,  
                    null, InputManager.Current, null);  
  
        if (stylusLogic != null)  
        {  
            //  Get the type of the stylusLogic returned from the call to StylusLogic.  
            Type stylusLogicType = stylusLogic.GetType();  
  
            // Loop until there are no more devices to remove.  
            while (devices.Count > 0)  
            {  
                // Remove the first tablet device in the devices collection.  
                stylusLogicType.InvokeMember("OnTabletRemoved",  
                        BindingFlags.InvokeMethod | BindingFlags.Instance | BindingFlags.NonPublic,  
                        null, stylusLogic, new object[] { (uint)0 });  
            }
        }  
  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="4f021-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f021-113">See also</span></span>

- [<span data-ttu-id="4f021-114">スタイラスからの入力のインターセプト</span><span class="sxs-lookup"><span data-stu-id="4f021-114">Intercepting Input from the Stylus</span></span>](intercepting-input-from-the-stylus.md)
