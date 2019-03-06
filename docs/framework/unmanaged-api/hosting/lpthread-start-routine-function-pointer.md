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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8f111736f1a8115614cbeb13402f0ef75cf6038f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479325"
---
# <a name="lpthreadstartroutine-function-pointer"></a><span data-ttu-id="c8b50-102">LPTHREAD_START_ROUTINE 関数ポインター</span><span class="sxs-lookup"><span data-stu-id="c8b50-102">LPTHREAD_START_ROUTINE Function Pointer</span></span>
<span data-ttu-id="c8b50-103">スレッドの実行を開始したことをホストに通知する関数を指します。</span><span class="sxs-lookup"><span data-stu-id="c8b50-103">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 <span data-ttu-id="c8b50-104">この関数のポインターが非推奨とされた、[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c8b50-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8b50-105">構文</span><span class="sxs-lookup"><span data-stu-id="c8b50-105">Syntax</span></span>  
  
```  
typedef DWORD (__stdcall *LPTHREAD_START_ROUTINE) (  
    [in] LPVOID lpThreadParameter  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8b50-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c8b50-106">Parameters</span></span>  
 `lpThreadParameter`  
 <span data-ttu-id="c8b50-107">[in]実行を開始するコードへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c8b50-107">[in] A pointer to the code that has started executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8b50-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="c8b50-108">Remarks</span></span>  
 <span data-ttu-id="c8b50-109">関数`LPTHREAD_START_ROUTINE`ポイントはコールバック関数であり、ホスト アプリケーションの作成者によって実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8b50-109">The function to which `LPTHREAD_START_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8b50-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="c8b50-110">Requirements</span></span>  
 <span data-ttu-id="c8b50-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8b50-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8b50-112">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c8b50-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c8b50-113">**ライブラリ:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="c8b50-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="c8b50-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8b50-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8b50-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8b50-115">See also</span></span>
- [<span data-ttu-id="c8b50-116">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="c8b50-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
