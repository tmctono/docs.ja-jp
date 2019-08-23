---
title: ICorDebugDataTarget2::EnumerateThreadIDs メソッド
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1dc5f8b7fa308bdb0fb270c11e044244839a7b47
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910288"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="5fb96-102">ICorDebugDataTarget2::EnumerateThreadIDs メソッド</span><span class="sxs-lookup"><span data-stu-id="5fb96-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>
<span data-ttu-id="5fb96-103">アクティブなスレッド ID の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="5fb96-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fb96-104">構文</span><span class="sxs-lookup"><span data-stu-id="5fb96-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,   
    [out] ULONG32 *pcThreadIds,   
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fb96-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5fb96-105">Parameters</span></span>  
 <span data-ttu-id="5fb96-106">cThreadIDs</span><span class="sxs-lookup"><span data-stu-id="5fb96-106">cThreadIDs</span></span>  
 <span data-ttu-id="5fb96-107">[入力] ID を返すことのできるスレッドの最大数。</span><span class="sxs-lookup"><span data-stu-id="5fb96-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="5fb96-108">pcThreadIds</span><span class="sxs-lookup"><span data-stu-id="5fb96-108">pcThreadIds</span></span>  
 <span data-ttu-id="5fb96-109">[出力] `ULONG32` 配列に書き込まれたスレッド ID の実際の数を示す `pThreadIds` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="5fb96-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="5fb96-110">pThreadIDs</span><span class="sxs-lookup"><span data-stu-id="5fb96-110">pThreadIDs</span></span>  
 <span data-ttu-id="5fb96-111">スレッド識別子の配列。</span><span class="sxs-lookup"><span data-stu-id="5fb96-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fb96-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="5fb96-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5fb96-113">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="5fb96-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fb96-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="5fb96-114">Requirements</span></span>  
 <span data-ttu-id="5fb96-115">**・** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="5fb96-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5fb96-116">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="5fb96-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5fb96-117">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fb96-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fb96-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="5fb96-118">See also</span></span>

- [<span data-ttu-id="5fb96-119">ICorDebugDataTarget2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5fb96-119">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="5fb96-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5fb96-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
