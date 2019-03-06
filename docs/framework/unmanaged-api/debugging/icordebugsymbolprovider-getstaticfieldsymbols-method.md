---
title: ICorDebugSymbolProvider::GetStaticFieldSymbols メソッド
ms.date: 03/30/2017
ms.assetid: b178367f-a6e4-413c-b06f-daf3804b456b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 69ad0878daf57c379a5958dbeacddac8510c6eba
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476153"
---
# <a name="icordebugsymbolprovidergetstaticfieldsymbols-method"></a><span data-ttu-id="508ce-102">ICorDebugSymbolProvider::GetStaticFieldSymbols メソッド</span><span class="sxs-lookup"><span data-stu-id="508ce-102">ICorDebugSymbolProvider::GetStaticFieldSymbols Method</span></span>
<span data-ttu-id="508ce-103">typespec シグネチャに対応する静的フィールド シンボルを取得します。</span><span class="sxs-lookup"><span data-stu-id="508ce-103">Gets the static field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="508ce-104">構文</span><span class="sxs-lookup"><span data-stu-id="508ce-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugStaticFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="508ce-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="508ce-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="508ce-106">[in] `typeSig` 配列のバイト数。</span><span class="sxs-lookup"><span data-stu-id="508ce-106">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="508ce-107">[in] `typespec` シグネチャを格納するバイト配列。</span><span class="sxs-lookup"><span data-stu-id="508ce-107">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="508ce-108">[in] 要求されるシンボルの数。</span><span class="sxs-lookup"><span data-stu-id="508ce-108">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="508ce-109">[out] メソッドによって取得されたシンボル数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="508ce-109">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="508ce-110">[out]ポインター、 [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)要求された静的フィールド シンボルを格納する配列。</span><span class="sxs-lookup"><span data-stu-id="508ce-110">[out] A pointer to an [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) array that contains the requested static field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="508ce-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="508ce-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="508ce-112">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="508ce-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="508ce-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="508ce-113">Requirements</span></span>  
 <span data-ttu-id="508ce-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="508ce-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="508ce-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="508ce-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="508ce-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="508ce-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="508ce-117">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="508ce-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="508ce-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="508ce-118">See also</span></span>
- [<span data-ttu-id="508ce-119">GetInstanceFieldSymbols メソッド</span><span class="sxs-lookup"><span data-stu-id="508ce-119">GetInstanceFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getinstancefieldsymbols-method.md)
- [<span data-ttu-id="508ce-120">ICorDebugSymbolProvider インターフェイス</span><span class="sxs-lookup"><span data-stu-id="508ce-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="508ce-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="508ce-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
