---
title: ICorDebugManagedCallback::ExitThread メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitThread
helpviewer_keywords:
- ExitThread method [.NET Framework debugging]
- ICorDebugManagedCallback::ExitThread method [.NET Framework debugging]
ms.assetid: 62db708b-6cf0-45c5-b897-4b5c75bd2505
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37815d8aead1ec89826c13db6f012f2cd17bc792
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132445"
---
# <a name="icordebugmanagedcallbackexitthread-method"></a><span data-ttu-id="54aae-102">ICorDebugManagedCallback::ExitThread メソッド</span><span class="sxs-lookup"><span data-stu-id="54aae-102">ICorDebugManagedCallback::ExitThread Method</span></span>
<span data-ttu-id="54aae-103">マネージ コードが実行しているスレッドが終了していることをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="54aae-103">Notifies the debugger that a thread that was executing managed code has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54aae-104">構文</span><span class="sxs-lookup"><span data-stu-id="54aae-104">Syntax</span></span>  
  
```  
HRESULT ExitThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54aae-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="54aae-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="54aae-106">[in]マネージ スレッドを格納しているアプリケーション ドメインを表す ICorDebugAppDomain オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="54aae-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="54aae-107">[in]マネージ スレッドを表す ICorDebugThread オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="54aae-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54aae-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="54aae-108">Remarks</span></span>  
 <span data-ttu-id="54aae-109">1 回、`ExitThread`コールバックが発生した、スレッドはスレッドの列挙型では削除されます。</span><span class="sxs-lookup"><span data-stu-id="54aae-109">Once the `ExitThread` callback is fired, the thread will no longer appear in thread enumerations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54aae-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="54aae-110">Requirements</span></span>  
 <span data-ttu-id="54aae-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="54aae-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54aae-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54aae-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54aae-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54aae-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="54aae-114">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="54aae-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="54aae-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="54aae-115">See also</span></span>

- [<span data-ttu-id="54aae-116">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="54aae-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
