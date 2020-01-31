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
ms.openlocfilehash: 06c08499298656c8314d72667d9dac88c8d11e6a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788339"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="b0887-102">ICorDebugManagedCallback::UnloadAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="b0887-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="b0887-103">共通言語ランタイムアセンブリがアンロードされたことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="b0887-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0887-104">構文</span><span class="sxs-lookup"><span data-stu-id="b0887-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0887-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b0887-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="b0887-106">からアセンブリが格納されているアプリケーションドメインを表す、のオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b0887-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="b0887-107">からアセンブリを表す、オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b0887-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0887-108">コメント</span><span class="sxs-lookup"><span data-stu-id="b0887-108">Remarks</span></span>  
 <span data-ttu-id="b0887-109">このコールバックの後にアセンブリを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="b0887-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0887-110">要件</span><span class="sxs-lookup"><span data-stu-id="b0887-110">Requirements</span></span>  
 <span data-ttu-id="b0887-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0887-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0887-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0887-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0887-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0887-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0887-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0887-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0887-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0887-115">See also</span></span>

- [<span data-ttu-id="b0887-116">LoadAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="b0887-116">LoadAssembly Method</span></span>](icordebugmanagedcallback-loadassembly-method.md)
- [<span data-ttu-id="b0887-117">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b0887-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
