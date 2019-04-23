---
title: ICorDebugVariableSymbol::SetValue メソッド
ms.date: 03/30/2017
ms.assetid: 4609418d-71fa-44bc-9618-4d529d25cabb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5bfbadc5553e86b2db10d66298c8d24d2a0f8bde
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59211577"
---
# <a name="icordebugvariablesymbolsetvalue-method"></a><span data-ttu-id="beed5-102">ICorDebugVariableSymbol::SetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="beed5-102">ICorDebugVariableSymbol::SetValue Method</span></span>
<span data-ttu-id="beed5-103">バイト配列の値を変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="beed5-103">Assigns the value of a byte array to a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="beed5-104">構文</span><span class="sxs-lookup"><span data-stu-id="beed5-104">Syntax</span></span>  
  
```  
HRESULT SetValue(  
   [in] ULONG32 offset,  
   [in] DWORD threadID,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [in, size_is(cbValue)] BYTE pValue[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="beed5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="beed5-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="beed5-106">[in] 値を設定する変数内の開始オフセットです。</span><span class="sxs-lookup"><span data-stu-id="beed5-106">[in] The starting offset in the variable at which to set the value.</span></span> <span data-ttu-id="beed5-107">このパラメーターは、オブジェクトのメンバー フィールドに書き込む際に使用されます。</span><span class="sxs-lookup"><span data-stu-id="beed5-107">This parameter is used when writing to member fields in an object.</span></span>  
  
 `threadID`  
 <span data-ttu-id="beed5-108">[in] 新しい値を反映させるためにコンテキストを更新する必要があるスレッドのスレッド ID。</span><span class="sxs-lookup"><span data-stu-id="beed5-108">[in] The thread identifier of the thread whose context must be updated to reflect the new value.</span></span>  
  
 `cbContext`  
 <span data-ttu-id="beed5-109">[in] スレッド コンテキストのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="beed5-109">[in] The size in bytes of the thread context.</span></span>  
  
 `context`  
 <span data-ttu-id="beed5-110">[in] 値の書き込みに使用されるスレッド コンテキスト。</span><span class="sxs-lookup"><span data-stu-id="beed5-110">[in] The thread context used to write the value.</span></span>  
  
 `cbValue`  
 <span data-ttu-id="beed5-111">[in] `pValue` バッファーのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="beed5-111">[in] The size in bytes of the `pValue` buffer.</span></span>  
  
 `pValue`  
 <span data-ttu-id="beed5-112">[in] 設定する値が含まれるバッファー。</span><span class="sxs-lookup"><span data-stu-id="beed5-112">[in] The buffer that contains the value to set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="beed5-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="beed5-113">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="beed5-114">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="beed5-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="beed5-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="beed5-115">Requirements</span></span>  
 <span data-ttu-id="beed5-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="beed5-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="beed5-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="beed5-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="beed5-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="beed5-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="beed5-119">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="beed5-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beed5-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="beed5-120">See also</span></span>

- [<span data-ttu-id="beed5-121">ICorDebugVariableSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="beed5-121">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="beed5-122">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="beed5-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
