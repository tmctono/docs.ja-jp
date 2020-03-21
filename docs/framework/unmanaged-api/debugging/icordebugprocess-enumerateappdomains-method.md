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
ms.openlocfilehash: 4489238df05edef384b4073ee738a184ff8809ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178672"
---
# <a name="icordebugprocessenumerateappdomains-method"></a><span data-ttu-id="5e185-102">ICorDebugProcess::EnumerateAppDomains メソッド</span><span class="sxs-lookup"><span data-stu-id="5e185-102">ICorDebugProcess::EnumerateAppDomains Method</span></span>
<span data-ttu-id="5e185-103">このプロセス内のすべてのアプリケーション ドメインを列挙します。</span><span class="sxs-lookup"><span data-stu-id="5e185-103">Enumerates all the application domains in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e185-104">構文</span><span class="sxs-lookup"><span data-stu-id="5e185-104">Syntax</span></span>  
  
``` cpp
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e185-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5e185-105">Parameters</span></span>  
 `ppAppDomains`  
 <span data-ttu-id="5e185-106">[アウト]このプロセスのアプリケーション ドメインの列挙子である[ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md)のアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5e185-106">[out] A pointer to the address of an [ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md) that is an enumerator for the application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e185-107">解説</span><span class="sxs-lookup"><span data-stu-id="5e185-107">Remarks</span></span>  
 <span data-ttu-id="5e185-108">このメソッドは、[コールバック](icordebugmanagedcallback-createprocess-method.md)の前に使用できます。</span><span class="sxs-lookup"><span data-stu-id="5e185-108">This method can be used before the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e185-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="5e185-109">Requirements</span></span>  
 <span data-ttu-id="5e185-110">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e185-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e185-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e185-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e185-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e185-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e185-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e185-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
