---
title: ICorDebugDataTarget2::EnumerateThreadIDs メソッド
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 70b3b57b51faed51aa7d5a70a3b785e0f719321b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59215847"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="5804d-102">ICorDebugDataTarget2::EnumerateThreadIDs メソッド</span><span class="sxs-lookup"><span data-stu-id="5804d-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>
<span data-ttu-id="5804d-103">アクティブなスレッド ID の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="5804d-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5804d-104">構文</span><span class="sxs-lookup"><span data-stu-id="5804d-104">Syntax</span></span>  
  
```  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,   
    [out] ULONG32 *pcThreadIds,   
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5804d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5804d-105">Parameters</span></span>  
 <span data-ttu-id="5804d-106">cThreadIDs</span><span class="sxs-lookup"><span data-stu-id="5804d-106">cThreadIDs</span></span>  
 <span data-ttu-id="5804d-107">[入力] ID を返すことのできるスレッドの最大数。</span><span class="sxs-lookup"><span data-stu-id="5804d-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="5804d-108">pcThreadIds</span><span class="sxs-lookup"><span data-stu-id="5804d-108">pcThreadIds</span></span>  
 <span data-ttu-id="5804d-109">[出力] `ULONG32` 配列に書き込まれたスレッド ID の実際の数を示す `pThreadIds` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="5804d-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="5804d-110">pThreadIDs</span><span class="sxs-lookup"><span data-stu-id="5804d-110">pThreadIDs</span></span>  
 <span data-ttu-id="5804d-111">スレッド識別子の配列。</span><span class="sxs-lookup"><span data-stu-id="5804d-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5804d-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="5804d-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5804d-113">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="5804d-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5804d-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="5804d-114">Requirements</span></span>  
 <span data-ttu-id="5804d-115">**プラットフォーム:** 参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md).**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5804d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5804d-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5804d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5804d-117">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5804d-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5804d-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="5804d-118">See also</span></span>

- [<span data-ttu-id="5804d-119">ICorDebugDataTarget2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5804d-119">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="5804d-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5804d-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
