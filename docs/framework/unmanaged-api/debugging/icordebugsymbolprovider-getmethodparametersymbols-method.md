---
title: ICorDebugSymbolProvider::GetMethodParameterSymbols メソッド
ms.date: 03/30/2017
ms.assetid: 58b7c0b9-f6ad-4b49-b92d-0e421cfd0ec6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 98efd1446c88c3a6c004b5a3254c9db835a43804
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197374"
---
# <a name="icordebugsymbolprovidergetmethodparametersymbols-method"></a><span data-ttu-id="3cf88-102">ICorDebugSymbolProvider::GetMethodParameterSymbols メソッド</span><span class="sxs-lookup"><span data-stu-id="3cf88-102">ICorDebugSymbolProvider::GetMethodParameterSymbols Method</span></span>
<span data-ttu-id="3cf88-103">メソッドの指定の相対仮想アドレス (RVA: relative virtual address ) で、そのメソッドのパラメーター シンボルを取得します。</span><span class="sxs-lookup"><span data-stu-id="3cf88-103">Gets a method's parameter symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cf88-104">構文</span><span class="sxs-lookup"><span data-stu-id="3cf88-104">Syntax</span></span>  
  
```  
HRESULT GetMethodParameterSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3cf88-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3cf88-105">Parameters</span></span>  
 `nativeRVA`  
 <span data-ttu-id="3cf88-106">[in] メソッドのネイティブ相対仮想アドレス。</span><span class="sxs-lookup"><span data-stu-id="3cf88-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="3cf88-107">[in] ローカル シンボルの要求数。</span><span class="sxs-lookup"><span data-stu-id="3cf88-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="3cf88-108">[out] メソッドによって取得されたシンボル数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="3cf88-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="3cf88-109">[out]ポインター、 [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)メソッドのローカル シンボルを含む配列。</span><span class="sxs-lookup"><span data-stu-id="3cf88-109">[out] A pointer to an [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3cf88-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="3cf88-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3cf88-111">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="3cf88-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cf88-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="3cf88-112">Requirements</span></span>  
 <span data-ttu-id="3cf88-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cf88-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cf88-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3cf88-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3cf88-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3cf88-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3cf88-116">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="3cf88-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3cf88-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="3cf88-117">See also</span></span>

- [<span data-ttu-id="3cf88-118">GetMethodLocalSymbols メソッド</span><span class="sxs-lookup"><span data-stu-id="3cf88-118">GetMethodLocalSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodlocalsymbols-method.md)
- [<span data-ttu-id="3cf88-119">ICorDebugSymbolProvider インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3cf88-119">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="3cf88-120">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="3cf88-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
