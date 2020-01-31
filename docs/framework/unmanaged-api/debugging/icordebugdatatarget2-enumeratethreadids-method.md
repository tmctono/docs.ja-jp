---
title: ICorDebugDataTarget2::EnumerateThreadIDs メソッド
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
ms.openlocfilehash: 74d4905f2b386f8e0345e4300dd2c8c6d0c882ea
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783650"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="f2f0b-102">ICorDebugDataTarget2::EnumerateThreadIDs メソッド</span><span class="sxs-lookup"><span data-stu-id="f2f0b-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>
<span data-ttu-id="f2f0b-103">アクティブなスレッド ID の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="f2f0b-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2f0b-104">構文</span><span class="sxs-lookup"><span data-stu-id="f2f0b-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,   
    [out] ULONG32 *pcThreadIds,   
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2f0b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f2f0b-105">Parameters</span></span>  
 <span data-ttu-id="f2f0b-106">cThreadIDs</span><span class="sxs-lookup"><span data-stu-id="f2f0b-106">cThreadIDs</span></span>  
 <span data-ttu-id="f2f0b-107">[入力] ID を返すことのできるスレッドの最大数。</span><span class="sxs-lookup"><span data-stu-id="f2f0b-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="f2f0b-108">pcThreadIds</span><span class="sxs-lookup"><span data-stu-id="f2f0b-108">pcThreadIds</span></span>  
 <span data-ttu-id="f2f0b-109">[出力] `ULONG32` 配列に書き込まれたスレッド ID の実際の数を示す `pThreadIds` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f2f0b-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="f2f0b-110">pThreadIDs</span><span class="sxs-lookup"><span data-stu-id="f2f0b-110">pThreadIDs</span></span>  
 <span data-ttu-id="f2f0b-111">スレッド識別子の配列。</span><span class="sxs-lookup"><span data-stu-id="f2f0b-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2f0b-112">コメント</span><span class="sxs-lookup"><span data-stu-id="f2f0b-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f2f0b-113">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f2f0b-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2f0b-114">要件</span><span class="sxs-lookup"><span data-stu-id="f2f0b-114">Requirements</span></span>  
 <span data-ttu-id="f2f0b-115">**プラットフォーム:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="f2f0b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2f0b-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2f0b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2f0b-117">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2f0b-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2f0b-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2f0b-118">See also</span></span>

- [<span data-ttu-id="f2f0b-119">ICorDebugDataTarget2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f2f0b-119">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="f2f0b-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f2f0b-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
