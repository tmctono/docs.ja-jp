---
title: GetRawInputDevices
ms.date: 03/30/2017
helpviewer_keywords:
- raw input [WPF]
ms.assetid: c4d37ecd-065a-4d1c-9e6c-26804ae968ca
ms.openlocfilehash: 3531ff9f42289a3ad3b029f090f2dd4987e5886c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59199405"
---
# <a name="getrawinputdevices"></a><span data-ttu-id="10701-102">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="10701-102">GetRawInputDevices</span></span>
<span data-ttu-id="10701-103">PresentationHost.exe が、ホスト アプリケーションに必要な未加工入力デバイス (ヒューマン インターフェイス デバイス) を検出できるようにします。</span><span class="sxs-lookup"><span data-stu-id="10701-103">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10701-104">構文</span><span class="sxs-lookup"><span data-stu-id="10701-104">Syntax</span></span>  
  
```  
HRESULT GetRawInputDevices( [out] IEnumRAWINPUTDEVICE **ppEnum );  
```  
  
## <a name="parameters"></a><span data-ttu-id="10701-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="10701-105">Parameters</span></span>  
 `ppEnum`  
  
 <span data-ttu-id="10701-106">[out]ポインター、 [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md)未加工入力デバイスを列挙するためです。</span><span class="sxs-lookup"><span data-stu-id="10701-106">[out] A pointer to an [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) for enumerating the raw input devices.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="10701-107">プロパティ値/戻り値</span><span class="sxs-lookup"><span data-stu-id="10701-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="10701-108">HRESULT:</span><span class="sxs-lookup"><span data-stu-id="10701-108">HRESULT:</span></span>  
  
 <span data-ttu-id="10701-109">S_OK - [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) S_OK が返された場合のみ PresentationHost.exe によってに使用されます。</span><span class="sxs-lookup"><span data-stu-id="10701-109">S_OK - [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) will only be used by PresentationHost.exe if S_OK is returned.</span></span>  
  
 <span data-ttu-id="10701-110">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="10701-110">E_NOTIMPL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10701-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="10701-111">Remarks</span></span>  
 <span data-ttu-id="10701-112">未加工入力デバイスは、キーボード、マウス、およびリモート コントロールのような比較的新しいデバイスを含む入力デバイスのセットです。</span><span class="sxs-lookup"><span data-stu-id="10701-112">Raw input devices are the set of input devices that includes keyboards, mice, and less traditional devices like remote controls.</span></span>  
  
 <span data-ttu-id="10701-113">未加工の入力デバイスの一覧を取得すると、PresentationHost.exe は WM_INPUT 通知メッセージを受信するデバイスを登録します。</span><span class="sxs-lookup"><span data-stu-id="10701-113">Once the list of raw input devices has been retrieved, PresentationHost.exe registers with the devices to receive WM_INPUT notification messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10701-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="10701-114">See also</span></span>

- [<span data-ttu-id="10701-115">GetRawInputDeviceList</span><span class="sxs-lookup"><span data-stu-id="10701-115">GetRawInputDeviceList</span></span>](/windows/desktop/api/winuser/nf-winuser-getrawinputdevicelist)
- [<span data-ttu-id="10701-116">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="10701-116">FilterInputMessage</span></span>](filterinputmessage.md)
