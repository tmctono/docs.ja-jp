---
title: 'いい変数 Home:: GetSlotIndex メソッド'
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
ms.openlocfilehash: 542bfa05c55ef224d1b9111f9af6c069e9e23542
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790968"
---
# <a name="icordebugvariablehomegetslotindex-method"></a><span data-ttu-id="ce7ea-102">いい変数 Home:: GetSlotIndex メソッド</span><span class="sxs-lookup"><span data-stu-id="ce7ea-102">ICorDebugVariableHome::GetSlotIndex Method</span></span>
<span data-ttu-id="ce7ea-103">ローカル変数のマネージドスロットインデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="ce7ea-103">Gets the managed slot-index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce7ea-104">構文</span><span class="sxs-lookup"><span data-stu-id="ce7ea-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce7ea-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ce7ea-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="ce7ea-106">入出力ローカル変数のスロットインデックスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ce7ea-106">[out] A pointer to the slot-index of a local variable.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ce7ea-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="ce7ea-107">Return Value</span></span>  
 <span data-ttu-id="ce7ea-108">メソッドは、次の値を返します。</span><span class="sxs-lookup"><span data-stu-id="ce7ea-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="ce7ea-109">Value</span><span class="sxs-lookup"><span data-stu-id="ce7ea-109">Value</span></span>|<span data-ttu-id="ce7ea-110">説明</span><span class="sxs-lookup"><span data-stu-id="ce7ea-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="ce7ea-111">メソッド呼び出しによって `pSlotIndex`でスロットインデックス値が返されました。</span><span class="sxs-lookup"><span data-stu-id="ce7ea-111">The method call returned a slot-index value in `pSlotIndex`.</span></span>|  
|`E_FAIL`|<span data-ttu-id="ce7ea-112">現在のは、[関数の引数](icordebugvariablehome-interface.md)を表します。</span><span class="sxs-lookup"><span data-stu-id="ce7ea-112">The current [ICorDebugVariableHome](icordebugvariablehome-interface.md) instance represents a function argument.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce7ea-113">コメント</span><span class="sxs-lookup"><span data-stu-id="ce7ea-113">Remarks</span></span>  
 <span data-ttu-id="ce7ea-114">このローカル変数のメタデータを取得するために、スロットインデックスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ce7ea-114">The slot-index can be used to retrieve the metadata for this local variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce7ea-115">要件</span><span class="sxs-lookup"><span data-stu-id="ce7ea-115">Requirements</span></span>  
 <span data-ttu-id="ce7ea-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce7ea-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce7ea-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ce7ea-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce7ea-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce7ea-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce7ea-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce7ea-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce7ea-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="ce7ea-120">See also</span></span>

- [<span data-ttu-id="ce7ea-121">ICorDebugVariableHome インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ce7ea-121">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
