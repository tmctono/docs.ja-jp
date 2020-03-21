---
title: ICorDebugDataTarget2::GetSymbolProviderForImage メソッド
ms.date: 03/30/2017
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
ms.openlocfilehash: 500d36b414be686071990a6e1b40dd8759d02ae9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178929"
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a><span data-ttu-id="4a801-102">ICorDebugDataTarget2::GetSymbolProviderForImage メソッド</span><span class="sxs-lookup"><span data-stu-id="4a801-102">ICorDebugDataTarget2::GetSymbolProviderForImage Method</span></span>
<span data-ttu-id="4a801-103">モジュールのベース アドレスからそのモジュールのシンボル プロバイダーを返します。</span><span class="sxs-lookup"><span data-stu-id="4a801-103">Returns the symbol-provider for a module from the base address of that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a801-104">構文</span><span class="sxs-lookup"><span data-stu-id="4a801-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a801-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4a801-105">Parameters</span></span>  
 `imageBaseAddress`  
 <span data-ttu-id="4a801-106">[in]モジュールのベース アドレスを表す[CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)値。</span><span class="sxs-lookup"><span data-stu-id="4a801-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the base address of a module.</span></span>  
  
 `ppSymProvider`  
 <span data-ttu-id="4a801-107">[アウト][オブジェクトの](icordebugsymbolprovider-interface.md)アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="4a801-107">[out] A pointer to the address of an [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a801-108">解説</span><span class="sxs-lookup"><span data-stu-id="4a801-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4a801-109">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="4a801-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a801-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="4a801-110">Requirements</span></span>  
 <span data-ttu-id="4a801-111">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a801-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a801-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4a801-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a801-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a801-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a801-114">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a801-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a801-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a801-115">See also</span></span>

- [<span data-ttu-id="4a801-116">ICorDebugDataTarget2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4a801-116">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="4a801-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4a801-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
