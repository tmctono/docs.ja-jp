---
title: Icordebugsymbolprovider::getinstancefieldsymbols メソッド
ms.date: 03/30/2017
ms.assetid: a29b9233-ee67-4b53-b8bc-c00b281e7edb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02ffabfc43861d3d295a0bd2ea09213b06b6868a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771408"
---
# <a name="icordebugsymbolprovidergetinstancefieldsymbols-method"></a><span data-ttu-id="4b443-102">Icordebugsymbolprovider::getinstancefieldsymbols メソッド</span><span class="sxs-lookup"><span data-stu-id="4b443-102">ICorDebugSymbolProvider::GetInstanceFieldSymbols Method</span></span>
<span data-ttu-id="4b443-103">typespec シグネチャに対応するインスタンス フィールド シンボルを取得します。</span><span class="sxs-lookup"><span data-stu-id="4b443-103">Gets the instance field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b443-104">構文</span><span class="sxs-lookup"><span data-stu-id="4b443-104">Syntax</span></span>  
  
```cpp  
HRESULT GetInstanceFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugInstanceFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b443-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4b443-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="4b443-106">[in] `typeSig` 配列のバイト数。</span><span class="sxs-lookup"><span data-stu-id="4b443-106">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="4b443-107">[in] `typespec` シグネチャを格納するバイト配列。</span><span class="sxs-lookup"><span data-stu-id="4b443-107">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="4b443-108">[in] 要求されるシンボルの数。</span><span class="sxs-lookup"><span data-stu-id="4b443-108">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="4b443-109">[out] メソッドによって取得されたシンボル数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="4b443-109">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="4b443-110">[out]ポインター、 [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)要求されたインスタンス フィールド シンボルを含む配列。</span><span class="sxs-lookup"><span data-stu-id="4b443-110">[out] A pointer to an [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) array that contains the requested instance field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b443-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="4b443-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b443-112">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="4b443-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b443-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="4b443-113">Requirements</span></span>  
 <span data-ttu-id="4b443-114">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b443-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b443-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b443-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b443-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b443-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b443-117">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b443-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b443-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b443-118">See also</span></span>

- [<span data-ttu-id="4b443-119">GetStaticFieldSymbols メソッド</span><span class="sxs-lookup"><span data-stu-id="4b443-119">GetStaticFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getstaticfieldsymbols-method.md)
- [<span data-ttu-id="4b443-120">ICorDebugSymbolProvider インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4b443-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="4b443-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4b443-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
