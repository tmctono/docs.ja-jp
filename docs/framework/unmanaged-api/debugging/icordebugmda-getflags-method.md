---
title: ICorDebugMDA::GetFlags メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetFlags
helpviewer_keywords:
- ICorDebugMDA::GetFlags method [.NET Framework debugging]
- GetFlags method [.NET Framework debugging]
ms.assetid: 87ce7c5b-fd82-453e-bf55-c8a32150b183
topic_type:
- apiref
ms.openlocfilehash: 7c3b0331cc4d987070b2d04beb621c4966a27cb9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129838"
---
# <a name="icordebugmdagetflags-method"></a><span data-ttu-id="34b17-102">ICorDebugMDA::GetFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="34b17-102">ICorDebugMDA::GetFlags Method</span></span>
<span data-ttu-id="34b17-103">によって表されるマネージデバッグアシスタント (MDA) に関連付けら[れている](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)フラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="34b17-103">Gets the flags associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34b17-104">構文</span><span class="sxs-lookup"><span data-stu-id="34b17-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags (  
    [in] CorDebugMDAFlags *pFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34b17-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="34b17-105">Parameters</span></span>  
 `pFlags`  
 <span data-ttu-id="34b17-106">からこの MDA のフラグの設定を指定する[Cordebugmdaflags](../../../../docs/framework/unmanaged-api/debugging/cordebugmdaflags-enumeration.md)列挙値のビットごとの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="34b17-106">[in] A bitwise combination of the [CorDebugMDAFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugmdaflags-enumeration.md) enumeration values that specify the settings of the flags for this MDA.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34b17-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="34b17-107">Requirements</span></span>  
 <span data-ttu-id="34b17-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34b17-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34b17-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34b17-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34b17-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34b17-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34b17-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34b17-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34b17-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="34b17-112">See also</span></span>

- [<span data-ttu-id="34b17-113">ICorDebugMDA インターフェイス</span><span class="sxs-lookup"><span data-stu-id="34b17-113">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="34b17-114">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="34b17-114">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
