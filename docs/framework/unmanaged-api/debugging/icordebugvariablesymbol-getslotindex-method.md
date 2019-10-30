---
title: 'ICorDebugVariableSymbol:: GetSlotIndex メソッド'
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
ms.openlocfilehash: a7a7ecf7d3e3d0d2125b03d3604c44138a2be0cc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120974"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="04c69-102">ICorDebugVariableSymbol:: GetSlotIndex メソッド</span><span class="sxs-lookup"><span data-stu-id="04c69-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="04c69-103">ローカル変数のマネージド スロット インデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="04c69-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04c69-104">構文</span><span class="sxs-lookup"><span data-stu-id="04c69-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04c69-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="04c69-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="04c69-106">[out] ローカル変数のスロット インデックスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="04c69-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="04c69-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="04c69-107">Return Value</span></span>  
 <span data-ttu-id="04c69-108">正常終了した場合は、`S_OK`。</span><span class="sxs-lookup"><span data-stu-id="04c69-108">`S_OK` if successful.</span></span> <span data-ttu-id="04c69-109">変数が関数引数の場合は `E_FAIL`。</span><span class="sxs-lookup"><span data-stu-id="04c69-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04c69-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="04c69-110">Remarks</span></span>  
 <span data-ttu-id="04c69-111">ローカル変数のマネージド スロット インデックスを使用すると、変数のメタデータ情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="04c69-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
> <span data-ttu-id="04c69-112">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="04c69-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04c69-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="04c69-113">Requirements</span></span>  
 <span data-ttu-id="04c69-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04c69-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04c69-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="04c69-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="04c69-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04c69-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04c69-117">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04c69-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04c69-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="04c69-118">See also</span></span>

- [<span data-ttu-id="04c69-119">ICorDebugVariableSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="04c69-119">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="04c69-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="04c69-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
