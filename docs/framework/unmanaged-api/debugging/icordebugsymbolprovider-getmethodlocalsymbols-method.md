---
title: ICorDebugSymbolProvider::GetMethodLocalSymbols メソッド
ms.date: 03/30/2017
ms.assetid: 8b989e38-e779-49d1-9e90-f1f920484b08
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 721de9957e67412c32e90853215cd4f5e2cf29ae
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498277"
---
# <a name="icordebugsymbolprovidergetmethodlocalsymbols-method"></a><span data-ttu-id="c3361-102">ICorDebugSymbolProvider::GetMethodLocalSymbols メソッド</span><span class="sxs-lookup"><span data-stu-id="c3361-102">ICorDebugSymbolProvider::GetMethodLocalSymbols Method</span></span>
<span data-ttu-id="c3361-103">メソッドの指定の相対仮想アドレス (RVA) で、そのメソッドのローカル シンボルを取得します。</span><span class="sxs-lookup"><span data-stu-id="c3361-103">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3361-104">構文</span><span class="sxs-lookup"><span data-stu-id="c3361-104">Syntax</span></span>  
  
```  
HRESULT GetMethodLocalSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3361-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c3361-105">Parameters</span></span>  
 `nativeRVA`  
 <span data-ttu-id="c3361-106">[in] メソッドのネイティブ相対仮想アドレス。</span><span class="sxs-lookup"><span data-stu-id="c3361-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="c3361-107">[in] ローカル シンボルの要求数。</span><span class="sxs-lookup"><span data-stu-id="c3361-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="c3361-108">[out] メソッドによって取得されたシンボル数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c3361-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="c3361-109">[out]ポインター、 [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)メソッドのローカル シンボルを含む配列。</span><span class="sxs-lookup"><span data-stu-id="c3361-109">[out] A pointer to an [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3361-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="c3361-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c3361-111">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c3361-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3361-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="c3361-112">Requirements</span></span>  
 <span data-ttu-id="c3361-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3361-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3361-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c3361-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c3361-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3361-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3361-116">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3361-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3361-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="c3361-117">See also</span></span>
- [<span data-ttu-id="c3361-118">GetMethodParameterSymbols メソッド</span><span class="sxs-lookup"><span data-stu-id="c3361-118">GetMethodParameterSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodparametersymbols-method.md)
- [<span data-ttu-id="c3361-119">ICorDebugSymbolProvider インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c3361-119">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="c3361-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c3361-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
