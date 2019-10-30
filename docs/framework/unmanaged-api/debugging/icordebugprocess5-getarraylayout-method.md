---
title: ICorDebugProcess5::GetArrayLayout メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetArrayLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetArrayLayout
helpviewer_keywords:
- ICorDebugProcess5::GetArrayLayout method [.NET Framework debugging]
- GetArrayLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 9a7393b9-9735-43c6-8616-afb103c432fd
topic_type:
- apiref
ms.openlocfilehash: 5a415c8f3124c08984f8101e1f4dbcae6bf96fbf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129607"
---
# <a name="icordebugprocess5getarraylayout-method"></a><span data-ttu-id="0ca65-102">ICorDebugProcess5::GetArrayLayout メソッド</span><span class="sxs-lookup"><span data-stu-id="0ca65-102">ICorDebugProcess5::GetArrayLayout Method</span></span>
<span data-ttu-id="0ca65-103">配列型のレイアウトに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="0ca65-103">Provides information about the layout of array types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ca65-104">構文</span><span class="sxs-lookup"><span data-stu-id="0ca65-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArrayLayout(    [in] COR_TYPEID id,     [out] COR_ARRAY_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ca65-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0ca65-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="0ca65-106">からレイアウトが必要な配列を指定する[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)トークン。</span><span class="sxs-lookup"><span data-stu-id="0ca65-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that specifies the array whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="0ca65-107">入出力メモリ内の配列のレイアウトに関する情報を格納している[COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md)構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="0ca65-107">[out] A pointer to a [COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) structure that contains information about the layout of the array in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ca65-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="0ca65-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ca65-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="0ca65-109">Requirements</span></span>  
 <span data-ttu-id="0ca65-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ca65-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ca65-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ca65-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ca65-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ca65-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ca65-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ca65-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ca65-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ca65-114">See also</span></span>

- [<span data-ttu-id="0ca65-115">ICorDebugProcess5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0ca65-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="0ca65-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0ca65-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
