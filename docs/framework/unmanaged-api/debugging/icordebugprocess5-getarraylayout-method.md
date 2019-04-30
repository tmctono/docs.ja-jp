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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 332de11790e78b712a429365bd89cc9e41539edc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948760"
---
# <a name="icordebugprocess5getarraylayout-method"></a><span data-ttu-id="b4aa3-102">ICorDebugProcess5::GetArrayLayout メソッド</span><span class="sxs-lookup"><span data-stu-id="b4aa3-102">ICorDebugProcess5::GetArrayLayout Method</span></span>
<span data-ttu-id="b4aa3-103">配列型のレイアウトに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="b4aa3-103">Provides information about the layout of array types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4aa3-104">構文</span><span class="sxs-lookup"><span data-stu-id="b4aa3-104">Syntax</span></span>  
  
```  
HRESULT GetArrayLayout(    [in] COR_TYPEID id,     [out] COR_ARRAY_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4aa3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b4aa3-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="b4aa3-106">[in]A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)トークンを持つレイアウトが必要な配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="b4aa3-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that specifies the array whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="b4aa3-107">[out]ポインターを[COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md)メモリ内の配列のレイアウトに関する情報を含む構造体。</span><span class="sxs-lookup"><span data-stu-id="b4aa3-107">[out] A pointer to a [COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) structure that contains information about the layout of the array in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4aa3-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="b4aa3-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4aa3-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="b4aa3-109">Requirements</span></span>  
 <span data-ttu-id="b4aa3-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4aa3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4aa3-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4aa3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4aa3-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4aa3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4aa3-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4aa3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4aa3-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4aa3-114">See also</span></span>

- [<span data-ttu-id="b4aa3-115">ICorDebugProcess5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b4aa3-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="b4aa3-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b4aa3-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
