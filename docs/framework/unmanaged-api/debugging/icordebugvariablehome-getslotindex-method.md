---
title: ICorDebugVariableHome::GetSlotIndex メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetSlotIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetSlotIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetSlotIndex method [.NET Framework debugging]
- GetSlotIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 966da50d-5665-4fff-bf7b-1c72bbadd9a4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 186f4a939cb3e01a527cf6ef06029232e7f5c22a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489364"
---
# <a name="icordebugvariablehomegetslotindex-method"></a><span data-ttu-id="38ebe-102">ICorDebugVariableHome::GetSlotIndex メソッド</span><span class="sxs-lookup"><span data-stu-id="38ebe-102">ICorDebugVariableHome::GetSlotIndex Method</span></span>
<span data-ttu-id="38ebe-103">ローカル変数のマネージ スロット インデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="38ebe-103">Gets the managed slot-index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38ebe-104">構文</span><span class="sxs-lookup"><span data-stu-id="38ebe-104">Syntax</span></span>  
  
```  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38ebe-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="38ebe-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="38ebe-106">[out]ローカル変数のスロット インデックスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="38ebe-106">[out] A pointer to the slot-index of a local variable.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="38ebe-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="38ebe-107">Return Value</span></span>  
 <span data-ttu-id="38ebe-108">メソッドは、次の値を返します。</span><span class="sxs-lookup"><span data-stu-id="38ebe-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="38ebe-109">[値]</span><span class="sxs-lookup"><span data-stu-id="38ebe-109">Value</span></span>|<span data-ttu-id="38ebe-110">説明</span><span class="sxs-lookup"><span data-stu-id="38ebe-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="38ebe-111">メソッドの呼び出しでのスロット インデックス値が返されました`pSlotIndex`します。</span><span class="sxs-lookup"><span data-stu-id="38ebe-111">The method call returned a slot-index value in `pSlotIndex`.</span></span>|  
|`E_FAIL`|<span data-ttu-id="38ebe-112">現在[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)インスタンスは、関数の引数を表します。</span><span class="sxs-lookup"><span data-stu-id="38ebe-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a function argument.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38ebe-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="38ebe-113">Remarks</span></span>  
 <span data-ttu-id="38ebe-114">スロット インデックスは、このローカル変数のメタデータの取得に使用できます。</span><span class="sxs-lookup"><span data-stu-id="38ebe-114">The slot-index can be used to retrieve the metadata for this local variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38ebe-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="38ebe-115">Requirements</span></span>  
 <span data-ttu-id="38ebe-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="38ebe-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38ebe-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="38ebe-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38ebe-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38ebe-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38ebe-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38ebe-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38ebe-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="38ebe-120">See also</span></span>
- [<span data-ttu-id="38ebe-121">ICorDebugVariableHome インターフェイス</span><span class="sxs-lookup"><span data-stu-id="38ebe-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
