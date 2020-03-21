---
title: ICorDebugDataTarget2::EnumerateThreadIDs メソッド
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
ms.openlocfilehash: 120a970aac33b1ab06ae47335a959d2791f893ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178988"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="e6139-102">ICorDebugDataTarget2::EnumerateThreadIDs メソッド</span><span class="sxs-lookup"><span data-stu-id="e6139-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>
<span data-ttu-id="e6139-103">アクティブなスレッド ID の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="e6139-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6139-104">構文</span><span class="sxs-lookup"><span data-stu-id="e6139-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,
    [out] ULONG32 *pcThreadIds,
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6139-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e6139-105">Parameters</span></span>  
 <span data-ttu-id="e6139-106">cThreadIDs</span><span class="sxs-lookup"><span data-stu-id="e6139-106">cThreadIDs</span></span>  
 <span data-ttu-id="e6139-107">[入力] ID を返すことのできるスレッドの最大数。</span><span class="sxs-lookup"><span data-stu-id="e6139-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="e6139-108">pcThreadIds</span><span class="sxs-lookup"><span data-stu-id="e6139-108">pcThreadIds</span></span>  
 <span data-ttu-id="e6139-109">[出力] `ULONG32` 配列に書き込まれたスレッド ID の実際の数を示す `pThreadIds` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="e6139-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="e6139-110">pThreadIDs</span><span class="sxs-lookup"><span data-stu-id="e6139-110">pThreadIDs</span></span>  
 <span data-ttu-id="e6139-111">スレッド識別子の配列。</span><span class="sxs-lookup"><span data-stu-id="e6139-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6139-112">解説</span><span class="sxs-lookup"><span data-stu-id="e6139-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e6139-113">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e6139-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6139-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="e6139-114">Requirements</span></span>  
 <span data-ttu-id="e6139-115">**プラットフォーム:**[「システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。**ヘッダー:** コルデバッグ.idl、コルデバッグ.h</span><span class="sxs-lookup"><span data-stu-id="e6139-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e6139-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6139-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6139-117">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6139-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6139-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6139-118">See also</span></span>

- [<span data-ttu-id="e6139-119">ICorDebugDataTarget2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e6139-119">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="e6139-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e6139-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
