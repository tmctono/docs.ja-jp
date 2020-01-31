---
title: ICorDebugSymbolProvider::GetInstanceFieldSymbols メソッド
ms.date: 03/30/2017
ms.assetid: a29b9233-ee67-4b53-b8bc-c00b281e7edb
ms.openlocfilehash: 9c55ce4d36681e173047cfb51515a74899c5a9fe
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791634"
---
# <a name="icordebugsymbolprovidergetinstancefieldsymbols-method"></a><span data-ttu-id="f5848-102">ICorDebugSymbolProvider::GetInstanceFieldSymbols メソッド</span><span class="sxs-lookup"><span data-stu-id="f5848-102">ICorDebugSymbolProvider::GetInstanceFieldSymbols Method</span></span>
<span data-ttu-id="f5848-103">typespec シグネチャに対応するインスタンス フィールド シンボルを取得します。</span><span class="sxs-lookup"><span data-stu-id="f5848-103">Gets the instance field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5848-104">構文</span><span class="sxs-lookup"><span data-stu-id="f5848-104">Syntax</span></span>  
  
```cpp  
HRESULT GetInstanceFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugInstanceFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5848-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f5848-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="f5848-106">[in] `typeSig` 配列のバイト数。</span><span class="sxs-lookup"><span data-stu-id="f5848-106">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="f5848-107">[in] `typespec` シグネチャを格納するバイト配列。</span><span class="sxs-lookup"><span data-stu-id="f5848-107">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="f5848-108">[in] 要求されるシンボルの数。</span><span class="sxs-lookup"><span data-stu-id="f5848-108">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="f5848-109">[out] メソッドによって取得されたシンボル数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f5848-109">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="f5848-110">入出力要求されたインスタンスフィールドシンボルが格納されている、コード例の[シンボル](icordebugstaticfieldsymbol-interface.md)配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f5848-110">[out] A pointer to an [ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md) array that contains the requested instance field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5848-111">コメント</span><span class="sxs-lookup"><span data-stu-id="f5848-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f5848-112">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f5848-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5848-113">要件</span><span class="sxs-lookup"><span data-stu-id="f5848-113">Requirements</span></span>  
 <span data-ttu-id="f5848-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5848-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5848-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f5848-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5848-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5848-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5848-117">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5848-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5848-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5848-118">See also</span></span>

- [<span data-ttu-id="f5848-119">GetStaticFieldSymbols メソッド</span><span class="sxs-lookup"><span data-stu-id="f5848-119">GetStaticFieldSymbols Method</span></span>](icordebugsymbolprovider-getstaticfieldsymbols-method.md)
- [<span data-ttu-id="f5848-120">ICorDebugSymbolProvider インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f5848-120">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="f5848-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f5848-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
