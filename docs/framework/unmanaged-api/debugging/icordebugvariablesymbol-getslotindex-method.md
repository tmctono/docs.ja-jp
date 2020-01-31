---
title: ICorDebugVariableSymbol::GetSlotIndex メソッド
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
ms.openlocfilehash: 3510daffb55bdb22aa5f835bf27157e7c8428509
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790890"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="ea848-102">ICorDebugVariableSymbol::GetSlotIndex メソッド</span><span class="sxs-lookup"><span data-stu-id="ea848-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="ea848-103">ローカル変数のマネージド スロット インデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="ea848-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea848-104">構文</span><span class="sxs-lookup"><span data-stu-id="ea848-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea848-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ea848-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="ea848-106">[out] ローカル変数のスロット インデックスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ea848-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ea848-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="ea848-107">Return Value</span></span>  
 <span data-ttu-id="ea848-108">正常終了した場合は、`S_OK`。</span><span class="sxs-lookup"><span data-stu-id="ea848-108">`S_OK` if successful.</span></span> <span data-ttu-id="ea848-109">変数が関数引数の場合は `E_FAIL`。</span><span class="sxs-lookup"><span data-stu-id="ea848-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea848-110">コメント</span><span class="sxs-lookup"><span data-stu-id="ea848-110">Remarks</span></span>  
 <span data-ttu-id="ea848-111">ローカル変数のマネージド スロット インデックスを使用すると、変数のメタデータ情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="ea848-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ea848-112">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ea848-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea848-113">要件</span><span class="sxs-lookup"><span data-stu-id="ea848-113">Requirements</span></span>  
 <span data-ttu-id="ea848-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea848-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea848-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ea848-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ea848-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea848-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea848-117">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea848-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea848-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea848-118">See also</span></span>

- [<span data-ttu-id="ea848-119">ICorDebugVariableSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ea848-119">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="ea848-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ea848-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
