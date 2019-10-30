---
title: WAITORTIMERCALLBACK 関数ポインター
ms.date: 03/30/2017
api_name:
- WAITORTIMERCALLBACK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAITORTIMERCALLBACK
helpviewer_keywords:
- WAITORTIMERCALLBACK function pointer [.NET Framework hosting]
ms.assetid: 1fec4aef-0a06-4df0-bae7-d31a9ef9603d
topic_type:
- apiref
ms.openlocfilehash: db6a20dee21b6c8bbd55fa9b52a159a00fe310d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092030"
---
# <a name="waitortimercallback-function-pointer"></a><span data-ttu-id="13b1f-102">WAITORTIMERCALLBACK 関数ポインター</span><span class="sxs-lookup"><span data-stu-id="13b1f-102">WAITORTIMERCALLBACK Function Pointer</span></span>
<span data-ttu-id="13b1f-103">待機ハンドル (<xref:System.Threading.WaitHandle>) が通知されたか、タイムアウトしたことをホストに通知する関数を指します。</span><span class="sxs-lookup"><span data-stu-id="13b1f-103">Points to a function that notifies the host that a wait handle (<xref:System.Threading.WaitHandle>) has either been signaled or timed out.</span></span>  
  
 <span data-ttu-id="13b1f-104">この関数ポインターは .NET Framework 4 で非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="13b1f-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13b1f-105">構文</span><span class="sxs-lookup"><span data-stu-id="13b1f-105">Syntax</span></span>  
  
```cpp  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13b1f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="13b1f-106">Parameters</span></span>  
 `lpParameter`  
 <span data-ttu-id="13b1f-107">からホストによって定義された情報を格納しているオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="13b1f-107">[in] A pointer to an object that contains information defined by the host.</span></span>  
  
 `TimerOrWaitFired`  
 <span data-ttu-id="13b1f-108">[in] 待機ハンドルがタイムアウトした場合は `true`、シグナルを送信した場合は `false` します。</span><span class="sxs-lookup"><span data-stu-id="13b1f-108">[in] `true` if the wait handle timed out, or `false` if it was signaled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13b1f-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="13b1f-109">Remarks</span></span>  
 <span data-ttu-id="13b1f-110">`WAITORTIMERCALLBACK` ポイントする関数はコールバック関数であり、ホストアプリケーションのライターによって実装される必要があります。</span><span class="sxs-lookup"><span data-stu-id="13b1f-110">The function to which `WAITORTIMERCALLBACK` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13b1f-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="13b1f-111">Requirements</span></span>  
 <span data-ttu-id="13b1f-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13b1f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13b1f-113">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="13b1f-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="13b1f-114">**ライブラリ:** Mscorwks.dll</span><span class="sxs-lookup"><span data-stu-id="13b1f-114">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="13b1f-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13b1f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13b1f-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="13b1f-116">See also</span></span>

- [<span data-ttu-id="13b1f-117">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="13b1f-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
