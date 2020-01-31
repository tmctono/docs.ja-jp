---
title: ICorDebugManagedCallback::LoadAssembly メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadAssembly
helpviewer_keywords:
- LoadAssembly method [.NET Framework debugging]
- ICorDebugManagedCallback::LoadAssembly method [.NET Framework debugging]
ms.assetid: 55cb673a-e240-43a6-a406-6912e7c0fe66
topic_type:
- apiref
ms.openlocfilehash: 80836cbbf82a97ccd6dc7251e5cbe934e0cbe66f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777279"
---
# <a name="icordebugmanagedcallbackloadassembly-method"></a><span data-ttu-id="3388b-102">ICorDebugManagedCallback::LoadAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="3388b-102">ICorDebugManagedCallback::LoadAssembly Method</span></span>
<span data-ttu-id="3388b-103">共通言語ランタイム (CLR) アセンブリが正常に読み込まれたことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="3388b-103">Notifies the debugger that a common language runtime (CLR) assembly has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3388b-104">構文</span><span class="sxs-lookup"><span data-stu-id="3388b-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadAssembly (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugAssembly  *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3388b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3388b-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="3388b-106">からアセンブリが読み込まれたアプリケーションドメインを表す、のオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3388b-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the assembly has been loaded.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="3388b-107">からアセンブリを表す、オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3388b-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3388b-108">要件</span><span class="sxs-lookup"><span data-stu-id="3388b-108">Requirements</span></span>  
 <span data-ttu-id="3388b-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3388b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3388b-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3388b-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3388b-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3388b-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3388b-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3388b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3388b-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="3388b-113">See also</span></span>

- [<span data-ttu-id="3388b-114">UnloadAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="3388b-114">UnloadAssembly Method</span></span>](icordebugmanagedcallback-unloadassembly-method.md)
- [<span data-ttu-id="3388b-115">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3388b-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
