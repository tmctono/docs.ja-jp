---
title: ICorDebugSymbolProvider::GetStaticFieldSymbols メソッド
ms.date: 03/30/2017
ms.assetid: b178367f-a6e4-413c-b06f-daf3804b456b
ms.openlocfilehash: 2428521b9b08060fd147a7c9b9054239bf957f69
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379372"
---
# <a name="icordebugsymbolprovidergetstaticfieldsymbols-method"></a><span data-ttu-id="18c90-102">ICorDebugSymbolProvider::GetStaticFieldSymbols メソッド</span><span class="sxs-lookup"><span data-stu-id="18c90-102">ICorDebugSymbolProvider::GetStaticFieldSymbols Method</span></span>
<span data-ttu-id="18c90-103">typespec シグネチャに対応する静的フィールド シンボルを取得します。</span><span class="sxs-lookup"><span data-stu-id="18c90-103">Gets the static field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18c90-104">構文</span><span class="sxs-lookup"><span data-stu-id="18c90-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugStaticFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18c90-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="18c90-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="18c90-106">[in] `typeSig` 配列のバイト数。</span><span class="sxs-lookup"><span data-stu-id="18c90-106">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="18c90-107">[in] `typespec` シグネチャを格納するバイト配列。</span><span class="sxs-lookup"><span data-stu-id="18c90-107">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="18c90-108">[in] 要求されるシンボルの数。</span><span class="sxs-lookup"><span data-stu-id="18c90-108">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="18c90-109">[out] メソッドによって取得されたシンボル数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="18c90-109">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="18c90-110">入出力要求された静的なフィールドシンボルが格納されている、表示名のある[シンボル](icordebugstaticfieldsymbol-interface.md)配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="18c90-110">[out] A pointer to an [ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md) array that contains the requested static field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18c90-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="18c90-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="18c90-112">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c90-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18c90-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="18c90-113">Requirements</span></span>  
 <span data-ttu-id="18c90-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18c90-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18c90-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18c90-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="18c90-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18c90-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18c90-117">**.NET Framework のバージョン:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18c90-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18c90-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="18c90-118">See also</span></span>

- [<span data-ttu-id="18c90-119">GetInstanceFieldSymbols メソッド</span><span class="sxs-lookup"><span data-stu-id="18c90-119">GetInstanceFieldSymbols Method</span></span>](icordebugsymbolprovider-getinstancefieldsymbols-method.md)
- [<span data-ttu-id="18c90-120">ICorDebugSymbolProvider インターフェイス</span><span class="sxs-lookup"><span data-stu-id="18c90-120">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="18c90-121">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="18c90-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
