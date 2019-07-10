---
title: ICorPublish::GetProcess メソッド
ms.date: 03/30/2017
api_name:
- ICorPublish.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::GetProcess
helpviewer_keywords:
- ICorPublish::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorPublish interface [.NET Framework debugging]
ms.assetid: c5143805-2eb7-45b8-85ed-c8fb34df1084
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b2dcdaed34044122dd2a61c9e0b5bb02f8cc0d9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774275"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="950e2-102">ICorPublish::GetProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="950e2-102">ICorPublish::GetProcess Method</span></span>
<span data-ttu-id="950e2-103">取得、 [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)指定の識別子を持つプロセスを表すインスタンス。</span><span class="sxs-lookup"><span data-stu-id="950e2-103">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="950e2-104">構文</span><span class="sxs-lookup"><span data-stu-id="950e2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess(  
    [in] unsigned              pid,   
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="950e2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="950e2-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="950e2-106">[in]プロセスの識別子です。</span><span class="sxs-lookup"><span data-stu-id="950e2-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="950e2-107">[out]アドレスへのポインター、`ICorPublishProcess`プロセスを表すインスタンス。</span><span class="sxs-lookup"><span data-stu-id="950e2-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="950e2-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="950e2-108">Remarks</span></span>  
 <span data-ttu-id="950e2-109">`GetProcess` プロセスが存在しないか、現在のユーザーがデバッグ可能なマネージ プロセスがない場合は失敗します。</span><span class="sxs-lookup"><span data-stu-id="950e2-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="950e2-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="950e2-110">Requirements</span></span>  
 <span data-ttu-id="950e2-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="950e2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="950e2-112">**ヘッダー:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="950e2-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="950e2-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="950e2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="950e2-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="950e2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="950e2-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="950e2-115">See also</span></span>

- [<span data-ttu-id="950e2-116">ICorPublish インターフェイス</span><span class="sxs-lookup"><span data-stu-id="950e2-116">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
