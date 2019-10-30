---
title: 'GetCodeRange Method Provider:: メソッド'
ms.date: 03/30/2017
ms.assetid: 49a2451f-d250-4e73-aa96-9ff49d9f11c6
ms.openlocfilehash: 84bf545fedf3a6c7915d94fd0c2630268585b6eb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138917"
---
# <a name="icordebugsymbolprovidergetcoderange-method"></a><span data-ttu-id="44061-102">GetCodeRange Method Provider:: メソッド</span><span class="sxs-lookup"><span data-stu-id="44061-102">ICorDebugSymbolProvider::GetCodeRange Method</span></span>
<span data-ttu-id="44061-103">メソッド内の指定の相対仮想アドレス (RVA: relative virtual address) で、メソッド開始アドレスとサイズを取得します。</span><span class="sxs-lookup"><span data-stu-id="44061-103">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44061-104">構文</span><span class="sxs-lookup"><span data-stu-id="44061-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeRange(  
   [in] ULONG32 codeRva,   
   [out] ULONG32* pCodeStartAddress,   
   [out] ULONG32* pCodeSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44061-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="44061-105">Parameters</span></span>  
 `codeRva`  
 <span data-ttu-id="44061-106">[in] メソッド内の相対仮想アドレス (RVA)。</span><span class="sxs-lookup"><span data-stu-id="44061-106">[in] The relative virtual address (RVA) in a method.</span></span>  
  
 `pCodeStartAddress`  
 <span data-ttu-id="44061-107">[out] メソッドの開始アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="44061-107">[out] A pointer to the starting address of the method.</span></span>  
  
 `pCodeSize`  
 <span data-ttu-id="44061-108">メソッドのコードのサイズ (メソッドのコードのバイト数) へのポインター。</span><span class="sxs-lookup"><span data-stu-id="44061-108">A pointer to the method code size (the number of bytes of the method's code).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44061-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="44061-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="44061-110">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="44061-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44061-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="44061-111">Requirements</span></span>  
 <span data-ttu-id="44061-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44061-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44061-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44061-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44061-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44061-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44061-115">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44061-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44061-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="44061-116">See also</span></span>

- [<span data-ttu-id="44061-117">ICorDebugSymbolProvider インターフェイス</span><span class="sxs-lookup"><span data-stu-id="44061-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="44061-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="44061-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
