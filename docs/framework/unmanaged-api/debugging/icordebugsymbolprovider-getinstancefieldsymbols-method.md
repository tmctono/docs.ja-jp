---
title: 'のコードプロバイダー:: GetInstanceFieldSymbols メソッド'
ms.date: 03/30/2017
ms.assetid: a29b9233-ee67-4b53-b8bc-c00b281e7edb
ms.openlocfilehash: 0ad8ddd78d963681c0b2f69bf0f211ad464dc7b7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138869"
---
# <a name="icordebugsymbolprovidergetinstancefieldsymbols-method"></a><span data-ttu-id="a38f7-102">のコードプロバイダー:: GetInstanceFieldSymbols メソッド</span><span class="sxs-lookup"><span data-stu-id="a38f7-102">ICorDebugSymbolProvider::GetInstanceFieldSymbols Method</span></span>
<span data-ttu-id="a38f7-103">typespec シグネチャに対応するインスタンス フィールド シンボルを取得します。</span><span class="sxs-lookup"><span data-stu-id="a38f7-103">Gets the instance field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a38f7-104">構文</span><span class="sxs-lookup"><span data-stu-id="a38f7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetInstanceFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugInstanceFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a38f7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a38f7-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="a38f7-106">[in] `typeSig` 配列のバイト数。</span><span class="sxs-lookup"><span data-stu-id="a38f7-106">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="a38f7-107">[in] `typespec` シグネチャを格納するバイト配列。</span><span class="sxs-lookup"><span data-stu-id="a38f7-107">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="a38f7-108">[in] 要求されるシンボルの数。</span><span class="sxs-lookup"><span data-stu-id="a38f7-108">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="a38f7-109">[out] メソッドによって取得されたシンボル数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="a38f7-109">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="a38f7-110">入出力要求されたインスタンスフィールドシンボルが格納されている、コード例の[シンボル](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="a38f7-110">[out] A pointer to an [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) array that contains the requested instance field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a38f7-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="a38f7-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a38f7-112">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a38f7-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a38f7-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="a38f7-113">Requirements</span></span>  
 <span data-ttu-id="a38f7-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a38f7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a38f7-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a38f7-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a38f7-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a38f7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a38f7-117">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a38f7-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a38f7-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="a38f7-118">See also</span></span>

- [<span data-ttu-id="a38f7-119">GetStaticFieldSymbols メソッド</span><span class="sxs-lookup"><span data-stu-id="a38f7-119">GetStaticFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getstaticfieldsymbols-method.md)
- [<span data-ttu-id="a38f7-120">ICorDebugSymbolProvider インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a38f7-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="a38f7-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a38f7-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
