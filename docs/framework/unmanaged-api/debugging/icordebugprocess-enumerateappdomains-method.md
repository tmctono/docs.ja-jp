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
ms.openlocfilehash: 748a44075f7f73e54bab689bcb8865dee2b14946
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207837"
---
# <a name="icordebugprocessenumerateappdomains-method"></a><span data-ttu-id="2ac42-102">ICorDebugProcess::EnumerateAppDomains メソッド</span><span class="sxs-lookup"><span data-stu-id="2ac42-102">ICorDebugProcess::EnumerateAppDomains Method</span></span>
<span data-ttu-id="2ac42-103">このプロセス内のすべてのアプリケーションドメインを列挙します。</span><span class="sxs-lookup"><span data-stu-id="2ac42-103">Enumerates all the application domains in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ac42-104">構文</span><span class="sxs-lookup"><span data-stu-id="2ac42-104">Syntax</span></span>  
  
``` cpp
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ac42-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2ac42-105">Parameters</span></span>  
 `ppAppDomains`  
 <span data-ttu-id="2ac42-106">入出力このプロセス内のアプリケーションドメインの列挙子である[ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md)のアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2ac42-106">[out] A pointer to the address of an [ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md) that is an enumerator for the application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ac42-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="2ac42-107">Remarks</span></span>  
 <span data-ttu-id="2ac42-108">このメソッド[は、によって](icordebugmanagedcallback-createprocess-method.md)使用できます。</span><span class="sxs-lookup"><span data-stu-id="2ac42-108">This method can be used before the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ac42-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="2ac42-109">Requirements</span></span>  
 <span data-ttu-id="2ac42-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ac42-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ac42-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ac42-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ac42-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ac42-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ac42-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ac42-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
