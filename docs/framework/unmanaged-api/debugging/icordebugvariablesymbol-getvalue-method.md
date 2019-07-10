---
title: ICorDebugVariableSymbol::GetValue メソッド
ms.date: 03/30/2017
ms.assetid: 90abece1-392e-4ade-94a1-30c75b0f7074
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed88c8ff78006c14bdee51ba6f95aaaedd66cf41
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774832"
---
# <a name="icordebugvariablesymbolgetvalue-method"></a><span data-ttu-id="8eca0-102">ICorDebugVariableSymbol::GetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="8eca0-102">ICorDebugVariableSymbol::GetValue Method</span></span>
<span data-ttu-id="8eca0-103">変数の値をバイト配列として取得します。</span><span class="sxs-lookup"><span data-stu-id="8eca0-103">Gets the value of a variable as a byte array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8eca0-104">構文</span><span class="sxs-lookup"><span data-stu-id="8eca0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue(  
   [in] ULONG32 offset,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [out] ULONG32 *pcbValue,  
   [out, size_is(cbValue), length_is(*pcbValue)] BYTE pValue[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8eca0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8eca0-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="8eca0-106">[in] 値を読み取る変数内の開始オフセットです。</span><span class="sxs-lookup"><span data-stu-id="8eca0-106">[in] The starting offset in the variable from which to read the value.</span></span> <span data-ttu-id="8eca0-107">このパラメーターは、オブジェクトのメンバー フィールドを読み取る際に使用されます。</span><span class="sxs-lookup"><span data-stu-id="8eca0-107">This parameter is used when reading member fields in an object.</span></span>  
  
 `cbContext`  
 <span data-ttu-id="8eca0-108">[in] `context` 引数のバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="8eca0-108">[in] The size in bytes of the `context` argument.</span></span>  
  
 `context`  
 <span data-ttu-id="8eca0-109">[in] 値の読み取りに使用されるスレッド コンテキスト。</span><span class="sxs-lookup"><span data-stu-id="8eca0-109">[in] The thread context used to read the value.</span></span>  
  
 `cbValue`  
 <span data-ttu-id="8eca0-110">[in] `pValue` バッファーのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="8eca0-110">[in] The size in bytes of the `pValue` buffer.</span></span>  
  
 `pcbValue`  
 <span data-ttu-id="8eca0-111">[out] `pValue` バッファーに実際に書き込まれたバイト数。</span><span class="sxs-lookup"><span data-stu-id="8eca0-111">[out] The number of bytes actually written to the `pValue` buffer.</span></span>  
  
 `pValue`  
 <span data-ttu-id="8eca0-112">[out] 変数の値が格納されているバイト配列。</span><span class="sxs-lookup"><span data-stu-id="8eca0-112">[out] A byte array that contains the value of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8eca0-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="8eca0-113">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8eca0-114">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="8eca0-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8eca0-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="8eca0-115">Requirements</span></span>  
 <span data-ttu-id="8eca0-116">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8eca0-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8eca0-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8eca0-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8eca0-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8eca0-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8eca0-119">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8eca0-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eca0-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="8eca0-120">See also</span></span>

- [<span data-ttu-id="8eca0-121">ICorDebugVariableSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8eca0-121">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="8eca0-122">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8eca0-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
