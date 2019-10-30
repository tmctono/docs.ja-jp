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
ms.openlocfilehash: e2550320494b9ba43947c3176788042f5c2e6ad5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130629"
---
# <a name="icordebugmanagedcallbackunloadclass-method"></a><span data-ttu-id="ea80a-102">ICorDebugManagedCallback::UnloadClass メソッド</span><span class="sxs-lookup"><span data-stu-id="ea80a-102">ICorDebugManagedCallback::UnloadClass Method</span></span>
<span data-ttu-id="ea80a-103">クラスがアンロードされていることをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="ea80a-103">Notifies the debugger that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea80a-104">構文</span><span class="sxs-lookup"><span data-stu-id="ea80a-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadClass (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugClass      *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea80a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ea80a-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="ea80a-106">からクラスを含むアプリケーションドメインを表す、のオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ea80a-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the class.</span></span>  
  
 `c`  
 <span data-ttu-id="ea80a-107">からクラスを表す、のオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ea80a-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea80a-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="ea80a-108">Remarks</span></span>  
 <span data-ttu-id="ea80a-109">この呼び出しの後にクラスを参照することはできません。</span><span class="sxs-lookup"><span data-stu-id="ea80a-109">The class should not be referenced after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea80a-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="ea80a-110">Requirements</span></span>  
 <span data-ttu-id="ea80a-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea80a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea80a-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ea80a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ea80a-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea80a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea80a-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea80a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea80a-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea80a-115">See also</span></span>

- [<span data-ttu-id="ea80a-116">LoadClass メソッド</span><span class="sxs-lookup"><span data-stu-id="ea80a-116">LoadClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)
- [<span data-ttu-id="ea80a-117">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ea80a-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
