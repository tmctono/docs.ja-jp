---
title: ICorDebugVariableSymbol::GetSlotIndex メソッド
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 58bb2cc63f2336ca9cfbed8ebeac0d607c18b2c4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968159"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="afb00-102">ICorDebugVariableSymbol::GetSlotIndex メソッド</span><span class="sxs-lookup"><span data-stu-id="afb00-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="afb00-103">ローカル変数のマネージド スロット インデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="afb00-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afb00-104">構文</span><span class="sxs-lookup"><span data-stu-id="afb00-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="afb00-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="afb00-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="afb00-106">[out] ローカル変数のスロット インデックスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="afb00-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="afb00-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="afb00-107">Return Value</span></span>  
 <span data-ttu-id="afb00-108">正常終了した場合は、`S_OK`。</span><span class="sxs-lookup"><span data-stu-id="afb00-108">`S_OK` if successful.</span></span> <span data-ttu-id="afb00-109">変数が関数引数の場合は `E_FAIL`。</span><span class="sxs-lookup"><span data-stu-id="afb00-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="afb00-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="afb00-110">Remarks</span></span>  
 <span data-ttu-id="afb00-111">ローカル変数のマネージド スロット インデックスを使用すると、変数のメタデータ情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="afb00-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
> <span data-ttu-id="afb00-112">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="afb00-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afb00-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="afb00-113">Requirements</span></span>  
 <span data-ttu-id="afb00-114">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="afb00-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afb00-115">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="afb00-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="afb00-116">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="afb00-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="afb00-117">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afb00-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afb00-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="afb00-118">See also</span></span>

- [<span data-ttu-id="afb00-119">ICorDebugVariableSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="afb00-119">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="afb00-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="afb00-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
