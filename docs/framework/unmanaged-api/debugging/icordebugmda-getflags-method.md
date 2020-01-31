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
ms.openlocfilehash: 0c7b8dae756fbb9ab27ff187eeb83a931b016b7f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793288"
---
# <a name="icordebugmdagetflags-method"></a><span data-ttu-id="0c7cc-102">ICorDebugMDA::GetFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="0c7cc-102">ICorDebugMDA::GetFlags Method</span></span>
<span data-ttu-id="0c7cc-103">によって表されるマネージデバッグアシスタント (MDA) に関連付けら[れている](icordebugmda-interface.md)フラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="0c7cc-103">Gets the flags associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c7cc-104">構文</span><span class="sxs-lookup"><span data-stu-id="0c7cc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags (  
    [in] CorDebugMDAFlags *pFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c7cc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0c7cc-105">Parameters</span></span>  
 `pFlags`  
 <span data-ttu-id="0c7cc-106">からこの MDA のフラグの設定を指定する[Cordebugmdaflags](cordebugmdaflags-enumeration.md)列挙値のビットごとの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="0c7cc-106">[in] A bitwise combination of the [CorDebugMDAFlags](cordebugmdaflags-enumeration.md) enumeration values that specify the settings of the flags for this MDA.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c7cc-107">要件</span><span class="sxs-lookup"><span data-stu-id="0c7cc-107">Requirements</span></span>  
 <span data-ttu-id="0c7cc-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c7cc-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c7cc-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c7cc-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c7cc-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c7cc-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c7cc-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c7cc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c7cc-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c7cc-112">See also</span></span>

- [<span data-ttu-id="0c7cc-113">ICorDebugMDA インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0c7cc-113">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="0c7cc-114">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="0c7cc-114">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
