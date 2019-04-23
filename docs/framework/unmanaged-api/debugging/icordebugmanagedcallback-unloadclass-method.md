---
title: ICorDebugManagedCallback::UnloadClass メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadClass
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadClass method [.NET Framework debugging]
- UnloadClass method [.NET Framework debugging]
ms.assetid: 66a59b18-ce9a-41f4-b23b-4dd6753d6d36
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b3eb8bf59ee2a91c62a6ff74b1903d92607a9ffe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197874"
---
# <a name="icordebugmanagedcallbackunloadclass-method"></a><span data-ttu-id="f32b9-102">ICorDebugManagedCallback::UnloadClass メソッド</span><span class="sxs-lookup"><span data-stu-id="f32b9-102">ICorDebugManagedCallback::UnloadClass Method</span></span>
<span data-ttu-id="f32b9-103">クラスがアンロードされることをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="f32b9-103">Notifies the debugger that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f32b9-104">構文</span><span class="sxs-lookup"><span data-stu-id="f32b9-104">Syntax</span></span>  
  
```  
HRESULT UnloadClass (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugClass      *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f32b9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f32b9-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="f32b9-106">[in]クラスを含むアプリケーション ドメインを表す ICorDebugAppDomain オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f32b9-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the class.</span></span>  
  
 `c`  
 <span data-ttu-id="f32b9-107">[in]クラスを表す ICorDebugClass オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f32b9-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f32b9-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="f32b9-108">Remarks</span></span>  
 <span data-ttu-id="f32b9-109">クラスは、この呼び出しの後は参照できません。</span><span class="sxs-lookup"><span data-stu-id="f32b9-109">The class should not be referenced after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f32b9-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="f32b9-110">Requirements</span></span>  
 <span data-ttu-id="f32b9-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f32b9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f32b9-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f32b9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f32b9-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f32b9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f32b9-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f32b9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f32b9-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="f32b9-115">See also</span></span>

- [<span data-ttu-id="f32b9-116">LoadClass メソッド</span><span class="sxs-lookup"><span data-stu-id="f32b9-116">LoadClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)
- [<span data-ttu-id="f32b9-117">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f32b9-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
