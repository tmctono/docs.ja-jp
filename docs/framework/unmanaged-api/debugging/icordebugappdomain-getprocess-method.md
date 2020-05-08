---
title: ICorDebugAppDomain::GetProcess メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebugAppDomain interface [.NET Framework debugging]
- ICorDebugAppDomain::GetProcess method [.NET Framework debugging]
ms.assetid: 9d0b9628-a91c-40d0-b9bc-00b34a396b8f
topic_type:
- apiref
ms.openlocfilehash: 90ac981f9b5ee71ca59f76823e7b796471571e4e
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895200"
---
# <a name="icordebugappdomaingetprocess-method"></a><span data-ttu-id="da423-102">ICorDebugAppDomain::GetProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="da423-102">ICorDebugAppDomain::GetProcess Method</span></span>
<span data-ttu-id="da423-103">アプリケーションドメインを格納しているプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="da423-103">Gets the process containing the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da423-104">構文</span><span class="sxs-lookup"><span data-stu-id="da423-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da423-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="da423-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="da423-106">入出力プロセスを表す、オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="da423-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da423-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="da423-107">Requirements</span></span>  
 <span data-ttu-id="da423-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da423-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da423-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da423-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da423-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da423-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da423-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da423-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
