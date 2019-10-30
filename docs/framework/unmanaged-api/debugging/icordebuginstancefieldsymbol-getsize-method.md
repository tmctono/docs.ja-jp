---
title: 'GetSize Instancefieldsymbol:: メソッド'
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
ms.openlocfilehash: 71828cd8486e2ff09190d23473dbab303b92f933
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139028"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="d3660-102">GetSize Instancefieldsymbol:: メソッド</span><span class="sxs-lookup"><span data-stu-id="d3660-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="d3660-103">インスタンス フィールドのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="d3660-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3660-104">構文</span><span class="sxs-lookup"><span data-stu-id="d3660-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3660-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d3660-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="d3660-106">[out] フィールドの長さへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d3660-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3660-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="d3660-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d3660-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d3660-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3660-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="d3660-109">Requirements</span></span>  
 <span data-ttu-id="d3660-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3660-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3660-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d3660-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d3660-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3660-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3660-113">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3660-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3660-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3660-114">See also</span></span>

- [<span data-ttu-id="d3660-115">ICorDebugInstanceFieldSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d3660-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="d3660-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d3660-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
