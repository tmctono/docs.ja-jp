---
title: ICorDebugVariableSymbol::SetValue メソッド
ms.date: 03/30/2017
ms.assetid: 4609418d-71fa-44bc-9618-4d529d25cabb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5436f56d3dcad7de3df2296485b0a36e5b3cfd79
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967964"
---
# <a name="icordebugvariablesymbolsetvalue-method"></a><span data-ttu-id="2bf89-102">ICorDebugVariableSymbol::SetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="2bf89-102">ICorDebugVariableSymbol::SetValue Method</span></span>
<span data-ttu-id="2bf89-103">バイト配列の値を変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="2bf89-103">Assigns the value of a byte array to a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bf89-104">構文</span><span class="sxs-lookup"><span data-stu-id="2bf89-104">Syntax</span></span>  
  
```cpp  
HRESULT SetValue(  
   [in] ULONG32 offset,  
   [in] DWORD threadID,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [in, size_is(cbValue)] BYTE pValue[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bf89-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2bf89-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="2bf89-106">[in] 値を設定する変数内の開始オフセットです。</span><span class="sxs-lookup"><span data-stu-id="2bf89-106">[in] The starting offset in the variable at which to set the value.</span></span> <span data-ttu-id="2bf89-107">このパラメーターは、オブジェクトのメンバー フィールドに書き込む際に使用されます。</span><span class="sxs-lookup"><span data-stu-id="2bf89-107">This parameter is used when writing to member fields in an object.</span></span>  
  
 `threadID`  
 <span data-ttu-id="2bf89-108">[in] 新しい値を反映させるためにコンテキストを更新する必要があるスレッドのスレッド ID。</span><span class="sxs-lookup"><span data-stu-id="2bf89-108">[in] The thread identifier of the thread whose context must be updated to reflect the new value.</span></span>  
  
 `cbContext`  
 <span data-ttu-id="2bf89-109">[in] スレッド コンテキストのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="2bf89-109">[in] The size in bytes of the thread context.</span></span>  
  
 `context`  
 <span data-ttu-id="2bf89-110">[in] 値の書き込みに使用されるスレッド コンテキスト。</span><span class="sxs-lookup"><span data-stu-id="2bf89-110">[in] The thread context used to write the value.</span></span>  
  
 `cbValue`  
 <span data-ttu-id="2bf89-111">[in] `pValue` バッファーのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="2bf89-111">[in] The size in bytes of the `pValue` buffer.</span></span>  
  
 `pValue`  
 <span data-ttu-id="2bf89-112">[in] 設定する値が含まれるバッファー。</span><span class="sxs-lookup"><span data-stu-id="2bf89-112">[in] The buffer that contains the value to set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2bf89-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="2bf89-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2bf89-114">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2bf89-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bf89-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="2bf89-115">Requirements</span></span>  
 <span data-ttu-id="2bf89-116">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2bf89-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bf89-117">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="2bf89-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2bf89-118">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="2bf89-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2bf89-119">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bf89-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bf89-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="2bf89-120">See also</span></span>

- [<span data-ttu-id="2bf89-121">ICorDebugVariableSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2bf89-121">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="2bf89-122">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2bf89-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
