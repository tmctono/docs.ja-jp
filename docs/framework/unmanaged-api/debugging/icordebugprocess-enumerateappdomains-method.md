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
ms.openlocfilehash: 35e3e37b1487b5dda9945402c6a3338384147f9a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792639"
---
# <a name="icordebugprocessenumerateappdomains-method"></a><span data-ttu-id="5230f-102">ICorDebugProcess::EnumerateAppDomains メソッド</span><span class="sxs-lookup"><span data-stu-id="5230f-102">ICorDebugProcess::EnumerateAppDomains Method</span></span>
<span data-ttu-id="5230f-103">このプロセス内のすべてのアプリケーションドメインを列挙します。</span><span class="sxs-lookup"><span data-stu-id="5230f-103">Enumerates all the application domains in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5230f-104">構文</span><span class="sxs-lookup"><span data-stu-id="5230f-104">Syntax</span></span>  
  
``` cpp 
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5230f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5230f-105">Parameters</span></span>  
 `ppAppDomains`  
 <span data-ttu-id="5230f-106">入出力このプロセス内のアプリケーションドメインの列挙子である[ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md)のアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5230f-106">[out] A pointer to the address of an [ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md) that is an enumerator for the application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5230f-107">コメント</span><span class="sxs-lookup"><span data-stu-id="5230f-107">Remarks</span></span>  
 <span data-ttu-id="5230f-108">このメソッド[は、によって](icordebugmanagedcallback-createprocess-method.md)使用できます。</span><span class="sxs-lookup"><span data-stu-id="5230f-108">This method can be used before the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5230f-109">要件</span><span class="sxs-lookup"><span data-stu-id="5230f-109">Requirements</span></span>  
 <span data-ttu-id="5230f-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5230f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5230f-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5230f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5230f-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5230f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5230f-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5230f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
