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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 701d578a1d3af941923d68ddc0cb7c97dd0ca8ab
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761939"
---
# <a name="icordebugmdagetflags-method"></a><span data-ttu-id="2d2d6-102">ICorDebugMDA::GetFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="2d2d6-102">ICorDebugMDA::GetFlags Method</span></span>
<span data-ttu-id="2d2d6-103">によって表されるマネージ デバッグ アシスタント (MDA) に関連付けられているフラグを取得[ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="2d2d6-103">Gets the flags associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d2d6-104">構文</span><span class="sxs-lookup"><span data-stu-id="2d2d6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags (  
    [in] CorDebugMDAFlags *pFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d2d6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2d2d6-105">Parameters</span></span>  
 `pFlags`  
 <span data-ttu-id="2d2d6-106">[in]ビットごとの組み合わせ、 [CorDebugMDAFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugmdaflags-enumeration.md)この MDA のフラグの設定を指定する列挙値。</span><span class="sxs-lookup"><span data-stu-id="2d2d6-106">[in] A bitwise combination of the [CorDebugMDAFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugmdaflags-enumeration.md) enumeration values that specify the settings of the flags for this MDA.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d2d6-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="2d2d6-107">Requirements</span></span>  
 <span data-ttu-id="2d2d6-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d2d6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d2d6-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2d2d6-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d2d6-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d2d6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d2d6-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d2d6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d2d6-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d2d6-112">See also</span></span>

- [<span data-ttu-id="2d2d6-113">ICorDebugMDA インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2d2d6-113">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="2d2d6-114">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="2d2d6-114">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
