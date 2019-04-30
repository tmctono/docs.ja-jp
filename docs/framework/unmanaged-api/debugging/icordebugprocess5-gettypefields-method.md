---
title: ICorDebugProcess5::GetTypeFields メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeFields
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeFields
helpviewer_keywords:
- GetTypeFields method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeFields method [.NET Framework debugging]
ms.assetid: 6a0ad3ee-dacb-47e9-abae-4536bcc4804b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c2725c62105e92996bb2d8e79e8ff504904e9c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948721"
---
# <a name="icordebugprocess5gettypefields-method"></a><span data-ttu-id="4984d-102">ICorDebugProcess5::GetTypeFields メソッド</span><span class="sxs-lookup"><span data-stu-id="4984d-102">ICorDebugProcess5::GetTypeFields Method</span></span>
<span data-ttu-id="4984d-103">型に属するフィールドについてを説明します。</span><span class="sxs-lookup"><span data-stu-id="4984d-103">Provides information about the fields that belong to a type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4984d-104">構文</span><span class="sxs-lookup"><span data-stu-id="4984d-104">Syntax</span></span>  
  
```  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],   
    [out] ULONG32 *pceltNeeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4984d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4984d-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="4984d-106">[in]フィールド情報を取得する型の識別子です。</span><span class="sxs-lookup"><span data-stu-id="4984d-106">[in] The identifier of the type whose field information is retrieved.</span></span>  
  
 `celt`  
 <span data-ttu-id="4984d-107">[in]数[COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md)フィールド情報を取得するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4984d-107">[in] The number of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects whose field information is to be retrieved.</span></span>  
  
 `fields`  
 <span data-ttu-id="4984d-108">[out]配列の[COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md)型に属するフィールドに関する情報を提供するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4984d-108">[out] An array of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects that provide information about the fields that belong to the type.</span></span>  
  
 `pceltNeeded`  
 <span data-ttu-id="4984d-109">[out]数へのポインター [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md)に含まれるオブジェクト`fields`します。</span><span class="sxs-lookup"><span data-stu-id="4984d-109">[out] A pointer to the number of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects included in `fields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4984d-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="4984d-110">Remarks</span></span>  
 <span data-ttu-id="4984d-111">`celt`フィールドがフィールドの情報を設定するメソッドを使用して数を指定するパラメーター`fields`の値に対応する必要があります、`COR_TYPE_LAYOUT::numFields`フィールド。</span><span class="sxs-lookup"><span data-stu-id="4984d-111">The `celt` parameter, which specifies the number of fields whose field information the method uses to populate `fields`, should correspond to the value of the `COR_TYPE_LAYOUT::numFields` field.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4984d-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="4984d-112">Requirements</span></span>  
 <span data-ttu-id="4984d-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4984d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4984d-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4984d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4984d-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4984d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4984d-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4984d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4984d-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="4984d-117">See also</span></span>

- [<span data-ttu-id="4984d-118">ICorDebugProcess5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4984d-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="4984d-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4984d-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
