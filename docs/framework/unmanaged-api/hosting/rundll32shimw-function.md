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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 569efa9d14ef10d8c5cf735091778a6c78882815
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781160"
---
# <a name="rundll32shimw-function"></a><span data-ttu-id="3467b-102">RunDll32ShimW 関数</span><span class="sxs-lookup"><span data-stu-id="3467b-102">RunDll32ShimW Function</span></span>
<span data-ttu-id="3467b-103">指定されたコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3467b-103">Executes the specified command.</span></span>  
  
 <span data-ttu-id="3467b-104">この関数は、.NET Framework 4 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="3467b-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3467b-105">構文</span><span class="sxs-lookup"><span data-stu-id="3467b-105">Syntax</span></span>  
  
```cpp  
HRESULT RunDll32ShimW (  
    [in] HWND        hwnd,  
    [in] HINSTANCE   hinst,  
    [in] LPCWSTR     lpszCmdLine,  
    [in] int         nCmdShow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3467b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3467b-106">Parameters</span></span>  
 `hwnd`  
 <span data-ttu-id="3467b-107">[in]コマンドの出力が表示されます ウィンドウへのハンドル。</span><span class="sxs-lookup"><span data-stu-id="3467b-107">[in] A handle to a window in which the command output will be displayed.</span></span>  
  
 `hinst`  
 <span data-ttu-id="3467b-108">[in]コマンドが含まれているライブラリへのハンドル。</span><span class="sxs-lookup"><span data-stu-id="3467b-108">[in] A handle to the library that contains the command.</span></span>  
  
 `lpszCmdLine`  
 <span data-ttu-id="3467b-109">[in]実行するコマンドを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="3467b-109">[in] A string that specifies the command to be executed.</span></span>  
  
 `nCmdShow`  
 <span data-ttu-id="3467b-110">[in]出力ウィンドウの表示モードを指定する整数。</span><span class="sxs-lookup"><span data-stu-id="3467b-110">[in] An integer that specifies the display mode for the output window.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3467b-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="3467b-111">Requirements</span></span>  
 <span data-ttu-id="3467b-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3467b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3467b-113">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3467b-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3467b-114">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3467b-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3467b-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3467b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3467b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="3467b-116">See also</span></span>

- [<span data-ttu-id="3467b-117">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="3467b-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
