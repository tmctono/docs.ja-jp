---
title: ICorDebugThread::GetActiveChain メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveChain
helpviewer_keywords:
- ICorDebugThread::GetActiveChain method [.NET Framework debugging]
- GetActiveChain method [.NET Framework debugging]
ms.assetid: f50de1f7-40ef-4949-b542-1d9a61f7bfef
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 59328c8b7e86694610de20ade72a98a4280b439d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762622"
---
# <a name="icordebugthreadgetactivechain-method"></a><span data-ttu-id="ad54b-102">ICorDebugThread::GetActiveChain メソッド</span><span class="sxs-lookup"><span data-stu-id="ad54b-102">ICorDebugThread::GetActiveChain Method</span></span>
<span data-ttu-id="ad54b-103">ICorDebugThread オブジェクトでアクティブな (最新) スタック チェーンへのインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="ad54b-103">Gets an interface pointer to the active (most recent) stack chain on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad54b-104">構文</span><span class="sxs-lookup"><span data-stu-id="ad54b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveChain (  
    [out] ICorDebugChain **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad54b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ad54b-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="ad54b-106">[out]スタック チェーンを表す ICorDebugChain オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ad54b-106">[out] A pointer to the address of an ICorDebugChain object that represents the stack chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad54b-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="ad54b-107">Remarks</span></span>  
 <span data-ttu-id="ad54b-108">`ppChain`パラメーターが現在アクティブなスタック チェーンがない場合は null です。</span><span class="sxs-lookup"><span data-stu-id="ad54b-108">The `ppChain` parameter is null if no stack chain is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad54b-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="ad54b-109">Requirements</span></span>  
 <span data-ttu-id="ad54b-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad54b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad54b-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ad54b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad54b-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad54b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad54b-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad54b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
