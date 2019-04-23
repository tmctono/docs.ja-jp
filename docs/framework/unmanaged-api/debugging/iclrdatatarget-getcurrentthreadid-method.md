---
title: ICLRDataTarget::GetCurrentThreadID メソッド
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetCurrentThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::GetCurrentThreadID method [.NET Framework debugging]
ms.assetid: dc9a0a6c-d592-4fb7-86ed-62684da3b0e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9687f6139d67a2387091367c2c72167e03be4eee
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080658"
---
# <a name="iclrdatatargetgetcurrentthreadid-method"></a><span data-ttu-id="8179b-102">ICLRDataTarget::GetCurrentThreadID メソッド</span><span class="sxs-lookup"><span data-stu-id="8179b-102">ICLRDataTarget::GetCurrentThreadID Method</span></span>
<span data-ttu-id="8179b-103">現在のスレッドのオペレーティング システムの識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="8179b-103">Gets the operating system identifier for the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8179b-104">構文</span><span class="sxs-lookup"><span data-stu-id="8179b-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentThreadID (  
    [out] ULONG32    *threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8179b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8179b-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="8179b-106">[out]ターゲット プロセスの現在のスレッドのオペレーティング システムの識別子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="8179b-106">[out] A pointer to the operating system identifier of the current thread for the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8179b-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="8179b-107">Remarks</span></span>  
 <span data-ttu-id="8179b-108">ターゲット プロセスでは、現在のスレッドが存在しない場合、`GetCurrentThreadID`メソッドが失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8179b-108">If there is no current thread for the target process, the `GetCurrentThreadID` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8179b-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="8179b-109">Requirements</span></span>  
 <span data-ttu-id="8179b-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8179b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8179b-111">**ヘッダー:** ClrData.idl、ClrData.h</span><span class="sxs-lookup"><span data-stu-id="8179b-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="8179b-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8179b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8179b-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8179b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8179b-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="8179b-114">See also</span></span>

- [<span data-ttu-id="8179b-115">ICLRDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8179b-115">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
