---
title: ICorDebugDataTarget2::EnumerateThreadIDs メソッド
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 848929901e91164bdccda5c1e77069364452a782
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750247"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="74ce3-102">ICorDebugDataTarget2::EnumerateThreadIDs メソッド</span><span class="sxs-lookup"><span data-stu-id="74ce3-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>
<span data-ttu-id="74ce3-103">アクティブなスレッド ID の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="74ce3-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74ce3-104">構文</span><span class="sxs-lookup"><span data-stu-id="74ce3-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,   
    [out] ULONG32 *pcThreadIds,   
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74ce3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="74ce3-105">Parameters</span></span>  
 <span data-ttu-id="74ce3-106">cThreadIDs</span><span class="sxs-lookup"><span data-stu-id="74ce3-106">cThreadIDs</span></span>  
 <span data-ttu-id="74ce3-107">[入力] ID を返すことのできるスレッドの最大数。</span><span class="sxs-lookup"><span data-stu-id="74ce3-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="74ce3-108">pcThreadIds</span><span class="sxs-lookup"><span data-stu-id="74ce3-108">pcThreadIds</span></span>  
 <span data-ttu-id="74ce3-109">[出力] `ULONG32` 配列に書き込まれたスレッド ID の実際の数を示す `pThreadIds` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="74ce3-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="74ce3-110">pThreadIDs</span><span class="sxs-lookup"><span data-stu-id="74ce3-110">pThreadIDs</span></span>  
 <span data-ttu-id="74ce3-111">スレッド識別子の配列。</span><span class="sxs-lookup"><span data-stu-id="74ce3-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74ce3-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="74ce3-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="74ce3-113">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="74ce3-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74ce3-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="74ce3-114">Requirements</span></span>  
 <span data-ttu-id="74ce3-115">**プラットフォーム:** 参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md).**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="74ce3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74ce3-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74ce3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74ce3-117">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74ce3-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74ce3-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="74ce3-118">See also</span></span>

- [<span data-ttu-id="74ce3-119">ICorDebugDataTarget2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="74ce3-119">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="74ce3-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="74ce3-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
