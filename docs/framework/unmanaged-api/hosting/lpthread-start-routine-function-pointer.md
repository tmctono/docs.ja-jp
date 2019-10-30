---
title: LPTHREAD_START_ROUTINE 関数ポインター
ms.date: 03/30/2017
api_name:
- LPTHREAD_START_ROUTINE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- LPTHREAD_START_ROUTINE
helpviewer_keywords:
- LPTHREAD_START_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 7b9b93b0-fe92-42ba-8693-701168a29dde
topic_type:
- apiref
ms.openlocfilehash: c6e0c02af93b9df726202f397bbb2afc306f3b3a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73090875"
---
# <a name="lpthread_start_routine-function-pointer"></a><span data-ttu-id="1ab24-102">LPTHREAD_START_ROUTINE 関数ポインター</span><span class="sxs-lookup"><span data-stu-id="1ab24-102">LPTHREAD_START_ROUTINE Function Pointer</span></span>
<span data-ttu-id="1ab24-103">スレッドの実行を開始したことをホストに通知する関数を指します。</span><span class="sxs-lookup"><span data-stu-id="1ab24-103">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 <span data-ttu-id="1ab24-104">この関数ポインターは .NET Framework 4 で非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="1ab24-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ab24-105">構文</span><span class="sxs-lookup"><span data-stu-id="1ab24-105">Syntax</span></span>  
  
```cpp  
typedef DWORD (__stdcall *LPTHREAD_START_ROUTINE) (  
    [in] LPVOID lpThreadParameter  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ab24-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1ab24-106">Parameters</span></span>  
 `lpThreadParameter`  
 <span data-ttu-id="1ab24-107">から実行を開始したコードへのポインター。</span><span class="sxs-lookup"><span data-stu-id="1ab24-107">[in] A pointer to the code that has started executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ab24-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="1ab24-108">Remarks</span></span>  
 <span data-ttu-id="1ab24-109">`LPTHREAD_START_ROUTINE` ポイントする関数はコールバック関数であり、ホストアプリケーションのライターによって実装される必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ab24-109">The function to which `LPTHREAD_START_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ab24-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="1ab24-110">Requirements</span></span>  
 <span data-ttu-id="1ab24-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ab24-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ab24-112">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1ab24-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1ab24-113">**ライブラリ:** Mscorwks.dll</span><span class="sxs-lookup"><span data-stu-id="1ab24-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="1ab24-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ab24-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ab24-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ab24-115">See also</span></span>

- [<span data-ttu-id="1ab24-116">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="1ab24-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
