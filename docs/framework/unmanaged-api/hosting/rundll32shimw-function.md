---
title: RunDll32ShimW 関数
ms.date: 03/30/2017
api_name:
- RunDll32ShimW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- RunDll32ShimW
helpviewer_keywords:
- RunDll32ShimW function [.NET Framework hosting]
ms.assetid: 9ea07b57-96e2-44df-8711-8fe6c119087f
topic_type:
- apiref
ms.openlocfilehash: e661bd82ecf6d804e852cca4a4478084edf303c5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141505"
---
# <a name="rundll32shimw-function"></a><span data-ttu-id="123dd-102">RunDll32ShimW 関数</span><span class="sxs-lookup"><span data-stu-id="123dd-102">RunDll32ShimW Function</span></span>
<span data-ttu-id="123dd-103">指定されたコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="123dd-103">Executes the specified command.</span></span>  
  
 <span data-ttu-id="123dd-104">この関数は .NET Framework 4 で非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="123dd-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="123dd-105">構文</span><span class="sxs-lookup"><span data-stu-id="123dd-105">Syntax</span></span>  
  
```cpp  
HRESULT RunDll32ShimW (  
    [in] HWND        hwnd,  
    [in] HINSTANCE   hinst,  
    [in] LPCWSTR     lpszCmdLine,  
    [in] int         nCmdShow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="123dd-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="123dd-106">Parameters</span></span>  
 `hwnd`  
 <span data-ttu-id="123dd-107">からコマンドの出力が表示されるウィンドウへのハンドル。</span><span class="sxs-lookup"><span data-stu-id="123dd-107">[in] A handle to a window in which the command output will be displayed.</span></span>  
  
 `hinst`  
 <span data-ttu-id="123dd-108">からコマンドが格納されているライブラリへのハンドル。</span><span class="sxs-lookup"><span data-stu-id="123dd-108">[in] A handle to the library that contains the command.</span></span>  
  
 `lpszCmdLine`  
 <span data-ttu-id="123dd-109">から実行するコマンドを指定する文字列です。</span><span class="sxs-lookup"><span data-stu-id="123dd-109">[in] A string that specifies the command to be executed.</span></span>  
  
 `nCmdShow`  
 <span data-ttu-id="123dd-110">から出力ウィンドウの表示モードを指定する整数。</span><span class="sxs-lookup"><span data-stu-id="123dd-110">[in] An integer that specifies the display mode for the output window.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="123dd-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="123dd-111">Requirements</span></span>  
 <span data-ttu-id="123dd-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="123dd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="123dd-113">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="123dd-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="123dd-114">**ライブラリ:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="123dd-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="123dd-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="123dd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="123dd-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="123dd-116">See also</span></span>

- [<span data-ttu-id="123dd-117">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="123dd-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
