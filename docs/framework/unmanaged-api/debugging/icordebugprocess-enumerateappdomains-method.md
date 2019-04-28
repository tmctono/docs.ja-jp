---
title: ICorDebugProcess::EnumerateAppDomains メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.EnumerateAppDomains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::EnumerateAppDomains
helpviewer_keywords:
- ICorDebugProcess::EnumerateAppDomains method [.NET Framework debugging]
- EnumerateAppDomains method [.NET Framework debugging]
ms.assetid: d508981f-e2b2-445b-a649-69951c22702d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02e051d311e447475bea724b0bd7420ee8b590f6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61749099"
---
# <a name="icordebugprocessenumerateappdomains-method"></a><span data-ttu-id="24c68-102">ICorDebugProcess::EnumerateAppDomains メソッド</span><span class="sxs-lookup"><span data-stu-id="24c68-102">ICorDebugProcess::EnumerateAppDomains Method</span></span>
<span data-ttu-id="24c68-103">このプロセスですべてのアプリケーション ドメインを列挙します。</span><span class="sxs-lookup"><span data-stu-id="24c68-103">Enumerates all the application domains in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24c68-104">構文</span><span class="sxs-lookup"><span data-stu-id="24c68-104">Syntax</span></span>  
  
```  
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24c68-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="24c68-105">Parameters</span></span>  
 `ppAppDomains`  
 <span data-ttu-id="24c68-106">[out]アドレスへのポインター、 [ICorDebugAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md)はこのプロセスのアプリケーション ドメインの列挙子。</span><span class="sxs-lookup"><span data-stu-id="24c68-106">[out] A pointer to the address of an [ICorDebugAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md) that is an enumerator for the application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24c68-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="24c68-107">Remarks</span></span>  
 <span data-ttu-id="24c68-108">このメソッドは、前に使用することができます、 [icordebugmanagedcallback::createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="24c68-108">This method can be used before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24c68-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="24c68-109">Requirements</span></span>  
 <span data-ttu-id="24c68-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="24c68-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24c68-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="24c68-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="24c68-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24c68-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24c68-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24c68-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
