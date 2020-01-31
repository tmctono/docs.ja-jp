---
title: ICorDebugMergedAssemblyRecord::GetCulture メソッド
ms.date: 03/30/2017
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
ms.openlocfilehash: c8fb5ace27fbf7fbebdaca5822af99cd6673e8cf
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793129"
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="a7f95-102">ICorDebugMergedAssemblyRecord::GetCulture メソッド</span><span class="sxs-lookup"><span data-stu-id="a7f95-102">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>
<span data-ttu-id="a7f95-103">アセンブリのプレフィックス インデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="a7f95-103">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7f95-104">構文</span><span class="sxs-lookup"><span data-stu-id="a7f95-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7f95-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a7f95-105">Parameters</span></span>  
 `pIndex`  
 <span data-ttu-id="a7f95-106">[out] プレフィックス インデックスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a7f95-106">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7f95-107">コメント</span><span class="sxs-lookup"><span data-stu-id="a7f95-107">Remarks</span></span>  
 <span data-ttu-id="a7f95-108">プレフィックス インデックスは、マージされたメタデータの型名での名前の競合を回避する目的で使用されます。</span><span class="sxs-lookup"><span data-stu-id="a7f95-108">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a7f95-109">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7f95-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7f95-110">要件</span><span class="sxs-lookup"><span data-stu-id="a7f95-110">Requirements</span></span>  
 <span data-ttu-id="a7f95-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7f95-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7f95-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a7f95-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7f95-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7f95-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7f95-114">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7f95-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7f95-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="a7f95-115">See also</span></span>

- [<span data-ttu-id="a7f95-116">ICorDebugMergedAssemblyRecord インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a7f95-116">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="a7f95-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a7f95-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
