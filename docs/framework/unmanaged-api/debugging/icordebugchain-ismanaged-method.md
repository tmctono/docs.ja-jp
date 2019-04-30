---
title: ICorDebugChain::IsManaged メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugChain.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::IsManaged
helpviewer_keywords:
- ICorDebugChain::IsManaged method [.NET Framework debugging]
- IsManaged method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 17b389a0-1a4d-4e8a-8613-9bc1769930f9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a27ea95ca78f7db8f67ec2a13f02767e67619e97
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989340"
---
# <a name="icordebugchainismanaged-method"></a><span data-ttu-id="ae362-102">ICorDebugChain::IsManaged メソッド</span><span class="sxs-lookup"><span data-stu-id="ae362-102">ICorDebugChain::IsManaged Method</span></span>
<span data-ttu-id="ae362-103">このチェーンがマネージ コードを実行しているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="ae362-103">Gets a value that indicates whether this chain is running managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae362-104">構文</span><span class="sxs-lookup"><span data-stu-id="ae362-104">Syntax</span></span>  
  
```  
HRESULT IsManaged (  
    [out] BOOL               *pManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae362-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ae362-105">Parameters</span></span>  
 `pManaged`  
 <span data-ttu-id="ae362-106">[out]`true`このチェーンには、マネージ コードが実行されている場合は、それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="ae362-106">[out] `true` if this chain is running managed code; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae362-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="ae362-107">Requirements</span></span>  
 <span data-ttu-id="ae362-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae362-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae362-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae362-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae362-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae362-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae362-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae362-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
