---
title: ICorDebugMergedAssemblyRecord::GetCulture メソッド
ms.date: 03/30/2017
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 77947da5bbda39700b687ecf91eb367eee28ca6b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494585"
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="377e0-102">ICorDebugMergedAssemblyRecord::GetCulture メソッド</span><span class="sxs-lookup"><span data-stu-id="377e0-102">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>
<span data-ttu-id="377e0-103">アセンブリのプレフィックス インデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="377e0-103">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="377e0-104">構文</span><span class="sxs-lookup"><span data-stu-id="377e0-104">Syntax</span></span>  
  
```  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="377e0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="377e0-105">Parameters</span></span>  
 `pIndex`  
 <span data-ttu-id="377e0-106">[out] プレフィックス インデックスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="377e0-106">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="377e0-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="377e0-107">Remarks</span></span>  
 <span data-ttu-id="377e0-108">プレフィックス インデックスは、マージされたメタデータの型名での名前の競合を回避する目的で使用されます。</span><span class="sxs-lookup"><span data-stu-id="377e0-108">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="377e0-109">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="377e0-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="377e0-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="377e0-110">Requirements</span></span>  
 <span data-ttu-id="377e0-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="377e0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="377e0-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="377e0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="377e0-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="377e0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="377e0-114">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="377e0-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="377e0-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="377e0-115">See also</span></span>
- [<span data-ttu-id="377e0-116">ICorDebugMergedAssemblyRecord インターフェイス</span><span class="sxs-lookup"><span data-stu-id="377e0-116">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="377e0-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="377e0-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
