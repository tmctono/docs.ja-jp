---
title: ICorDebugSymbolProvider::GetMergedAssemblyRecords メソッド
ms.date: 03/30/2017
ms.assetid: cc4c510d-550d-4941-af34-81987caf3425
ms.openlocfilehash: 6a537a88bd4ab666eff8b5dda994da96bfcc5e52
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791619"
---
# <a name="icordebugsymbolprovidergetmergedassemblyrecords-method"></a><span data-ttu-id="ff47f-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords メソッド</span><span class="sxs-lookup"><span data-stu-id="ff47f-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords Method</span></span>
<span data-ttu-id="ff47f-103">すべてのマージされたアセンブリのシンボル レコードを取得します。</span><span class="sxs-lookup"><span data-stu-id="ff47f-103">Gets the symbol records for all the merged assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff47f-104">構文</span><span class="sxs-lookup"><span data-stu-id="ff47f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMergedAssemblyRecords(  
   [in] ULONG32 cRequestedRecords,  
   [out] ULONG32 *pcFetchedRecords,  
   [out, size_is(cRequestedRecords), length_is(*pcFetchedRecords)] ICorDebugMergedAssemblyRecord *pRecords[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff47f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ff47f-105">Parameters</span></span>  
 `cRequestedRecords`  
 <span data-ttu-id="ff47f-106">[in] 要求されるシンボル レコードの数。</span><span class="sxs-lookup"><span data-stu-id="ff47f-106">[in] The number of symbol records requested.</span></span>  
  
 `pcFetchedRecords`  
 <span data-ttu-id="ff47f-107">[out] メソッドによって取得されたシンボル レコード数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="ff47f-107">[out] A pointer to the number of symbol records retrieved by the method.</span></span>  
  
 `pRecords`  
 <span data-ttu-id="ff47f-108">[ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md)オブジェクトの配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="ff47f-108">A pointer to an array of [ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md) objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff47f-109">コメント</span><span class="sxs-lookup"><span data-stu-id="ff47f-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ff47f-110">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ff47f-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff47f-111">要件</span><span class="sxs-lookup"><span data-stu-id="ff47f-111">Requirements</span></span>  
 <span data-ttu-id="ff47f-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff47f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff47f-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ff47f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ff47f-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff47f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff47f-115">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff47f-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff47f-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="ff47f-116">See also</span></span>

- [<span data-ttu-id="ff47f-117">ICorDebugSymbolProvider インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ff47f-117">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="ff47f-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ff47f-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
