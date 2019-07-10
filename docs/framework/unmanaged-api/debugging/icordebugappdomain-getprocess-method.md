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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eebb0c39cb8ae69dfce1e865f2784bbe9a408786
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737838"
---
# <a name="icordebugappdomaingetprocess-method"></a><span data-ttu-id="b9362-102">ICorDebugAppDomain::GetProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="b9362-102">ICorDebugAppDomain::GetProcess Method</span></span>
<span data-ttu-id="b9362-103">アプリケーション ドメインを格納しているプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="b9362-103">Gets the process containing the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9362-104">構文</span><span class="sxs-lookup"><span data-stu-id="b9362-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9362-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b9362-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="b9362-106">[out]プロセスを表す ICorDebugProcess オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b9362-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9362-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="b9362-107">Requirements</span></span>  
 <span data-ttu-id="b9362-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9362-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9362-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9362-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9362-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9362-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9362-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9362-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
