---
title: FLockClrVersionCallback 関数ポインター
ms.date: 03/30/2017
api_name:
- FLockClrVersionCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FLockClrVersionCallback
helpviewer_keywords:
- FLockClrVersionCallback function pointer [.NET Framework hosting]
ms.assetid: 98a4762d-9ad2-45bd-9d03-39064a028b44
topic_type:
- apiref
ms.openlocfilehash: f1ad414c30788801e14a33e98a0893e2a0f58d0c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136514"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="a7a8d-102">FLockClrVersionCallback 関数ポインター</span><span class="sxs-lookup"><span data-stu-id="a7a8d-102">FLockClrVersionCallback Function Pointer</span></span>
<span data-ttu-id="a7a8d-103">は、初期化が開始されたか完了したことを示すために、共通言語ランタイム (CLR) が呼び出す関数を指します。</span><span class="sxs-lookup"><span data-stu-id="a7a8d-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="a7a8d-104">この関数ポインターは .NET Framework 4 で非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="a7a8d-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7a8d-105">構文</span><span class="sxs-lookup"><span data-stu-id="a7a8d-105">Syntax</span></span>  
  
```cpp  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="a7a8d-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="a7a8d-106">Remarks</span></span>  
 <span data-ttu-id="a7a8d-107">この関数は、ホストによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="a7a8d-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7a8d-108">［要件］</span><span class="sxs-lookup"><span data-stu-id="a7a8d-108">Requirements</span></span>  
 <span data-ttu-id="a7a8d-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7a8d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7a8d-110">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a7a8d-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a7a8d-111">**ライブラリ:** Mscorwks.dll</span><span class="sxs-lookup"><span data-stu-id="a7a8d-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="a7a8d-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7a8d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7a8d-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="a7a8d-113">See also</span></span>

- [<span data-ttu-id="a7a8d-114">LockClrVersion 関数</span><span class="sxs-lookup"><span data-stu-id="a7a8d-114">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)
- [<span data-ttu-id="a7a8d-115">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="a7a8d-115">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
