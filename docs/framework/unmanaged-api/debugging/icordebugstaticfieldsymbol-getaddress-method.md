---
title: の場合は、":" GetAddress メソッド
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
ms.openlocfilehash: 65761e48491b2a4c81ccd05b17d8723f71f52e5c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131792"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="bf9d3-102">の場合は、":" GetAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="bf9d3-102">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>
<span data-ttu-id="bf9d3-103">静的フィールドのアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="bf9d3-103">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf9d3-104">構文</span><span class="sxs-lookup"><span data-stu-id="bf9d3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf9d3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bf9d3-105">Parameters</span></span>  
 <span data-ttu-id="bf9d3-106">pRVA</span><span class="sxs-lookup"><span data-stu-id="bf9d3-106">pRVA</span></span>  
 <span data-ttu-id="bf9d3-107">[out] 静的フィールドの相対仮想アドレス (RVA) へのポインター。</span><span class="sxs-lookup"><span data-stu-id="bf9d3-107">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf9d3-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="bf9d3-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bf9d3-109">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="bf9d3-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf9d3-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="bf9d3-110">Requirements</span></span>  
 <span data-ttu-id="bf9d3-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf9d3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf9d3-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bf9d3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bf9d3-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf9d3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf9d3-114">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf9d3-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf9d3-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf9d3-115">See also</span></span>

- [<span data-ttu-id="bf9d3-116">ICorDebugStaticFieldSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bf9d3-116">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="bf9d3-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bf9d3-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
