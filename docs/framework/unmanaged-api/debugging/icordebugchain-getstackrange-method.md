---
title: ICorDebugChain::GetStackRange メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetStackRange
helpviewer_keywords:
- ICorDebugChain::GetStackRange method [.NET Framework debugging]
- GetStackRange method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 554284e7-3f6c-4d40-8da5-1c9317fbd484
topic_type:
- apiref
ms.openlocfilehash: 64e697323377d664b7b1e36bbf5931a44465cc51
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178956"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="6777d-102">ICorDebugChain::GetStackRange メソッド</span><span class="sxs-lookup"><span data-stu-id="6777d-102">ICorDebugChain::GetStackRange Method</span></span>
<span data-ttu-id="6777d-103">このチェーンのスタック セグメントのアドレス範囲を取得します。</span><span class="sxs-lookup"><span data-stu-id="6777d-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6777d-104">構文</span><span class="sxs-lookup"><span data-stu-id="6777d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6777d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6777d-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="6777d-106">[アウト]スタック セグメントの`CORDB_ADDRESS`開始アドレスである値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="6777d-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="6777d-107">[アウト]スタック セグメントの`CORDB_ADDRESS`終了アドレスである値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="6777d-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6777d-108">解説</span><span class="sxs-lookup"><span data-stu-id="6777d-108">Remarks</span></span>  
 <span data-ttu-id="6777d-109">数値の範囲は、スタック フレームの位置を比較する場合にのみ意味があります。</span><span class="sxs-lookup"><span data-stu-id="6777d-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="6777d-110">実際にスタックに格納されている内容について、何も仮定できません。</span><span class="sxs-lookup"><span data-stu-id="6777d-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6777d-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="6777d-111">Requirements</span></span>  
 <span data-ttu-id="6777d-112">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6777d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6777d-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6777d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6777d-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6777d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6777d-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6777d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
