---
title: ICorDebugManagedCallback::UnloadAssembly メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadAssembly
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadAssembly method [.NET Framework debugging]
- UnloadAssembly method [.NET Framework debugging]
ms.assetid: 6734321c-c8a9-401f-a558-cad715ec4a77
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e770602858761dbcf15c233dceebfd35be106aa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59214132"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="51d7d-102">ICorDebugManagedCallback::UnloadAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="51d7d-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="51d7d-103">共通言語ランタイム アセンブリがアンロードされたことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="51d7d-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51d7d-104">構文</span><span class="sxs-lookup"><span data-stu-id="51d7d-104">Syntax</span></span>  
  
```  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51d7d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="51d7d-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="51d7d-106">[in]アセンブリに含まれるアプリケーション ドメインを表す ICorDebugAppDomain オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="51d7d-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="51d7d-107">[in]アセンブリを表す ICorDebugAssembly オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="51d7d-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51d7d-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="51d7d-108">Remarks</span></span>  
 <span data-ttu-id="51d7d-109">このコールバックの後、アセンブリを使用しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="51d7d-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51d7d-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="51d7d-110">Requirements</span></span>  
 <span data-ttu-id="51d7d-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="51d7d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51d7d-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51d7d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51d7d-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51d7d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51d7d-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51d7d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51d7d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="51d7d-115">See also</span></span>

- [<span data-ttu-id="51d7d-116">LoadAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="51d7d-116">LoadAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)
- [<span data-ttu-id="51d7d-117">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="51d7d-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
