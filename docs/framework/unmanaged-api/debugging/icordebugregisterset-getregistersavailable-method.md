---
title: ICorDebugRegisterSet::GetRegistersAvailable メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable
helpviewer_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable method [.NET Framework debugging]
- GetRegistersAvailable method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 4ba08ffa-55a2-4662-9d6d-4738f1db60c9
topic_type:
- apiref
ms.openlocfilehash: 9d8bd6ab13fa408fd7390aaeb76baee274742f48
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137699"
---
# <a name="icordebugregistersetgetregistersavailable-method"></a><span data-ttu-id="e61a5-102">ICorDebugRegisterSet::GetRegistersAvailable メソッド</span><span class="sxs-lookup"><span data-stu-id="e61a5-102">ICorDebugRegisterSet::GetRegistersAvailable Method</span></span>
<span data-ttu-id="e61a5-103">[このは、この](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)"この" のどのレジスタが現在使用可能であるかを示すビットマスクを取得します。</span><span class="sxs-lookup"><span data-stu-id="e61a5-103">Gets a bit mask indicating which registers in this [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) are currently available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e61a5-104">構文</span><span class="sxs-lookup"><span data-stu-id="e61a5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e61a5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e61a5-105">Parameters</span></span>  
 `pAvailable`  
 <span data-ttu-id="e61a5-106">入出力現在使用できるレジスタを示すビットマスク。</span><span class="sxs-lookup"><span data-stu-id="e61a5-106">[out] A bit mask that indicates which registers are currently available.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e61a5-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="e61a5-107">Remarks</span></span>  
 <span data-ttu-id="e61a5-108">特定の状況でその値を特定できない場合は、レジスタを使用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e61a5-108">A register may be unavailable if its value cannot be determined for the given situation.</span></span>  
  
 <span data-ttu-id="e61a5-109">返されたマスクには、レジスタごとにビットが含まれています (1 < レジスタインデックス <)。</span><span class="sxs-lookup"><span data-stu-id="e61a5-109">The returned mask contains a bit for each register (1 << the register index).</span></span> <span data-ttu-id="e61a5-110">レジスタが使用可能な場合、ビット値は1です。使用できない場合は0です。</span><span class="sxs-lookup"><span data-stu-id="e61a5-110">The bit value is 1 if the register is available, or 0 if it is not available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e61a5-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="e61a5-111">Requirements</span></span>  
 <span data-ttu-id="e61a5-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e61a5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e61a5-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e61a5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e61a5-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e61a5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e61a5-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e61a5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e61a5-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="e61a5-116">See also</span></span>

- [<span data-ttu-id="e61a5-117">ICorDebugRegisterSet インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e61a5-117">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="e61a5-118">ICorDebugRegisterSet2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e61a5-118">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
