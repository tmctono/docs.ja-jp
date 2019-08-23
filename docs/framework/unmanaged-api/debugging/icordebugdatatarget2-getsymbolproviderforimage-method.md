---
title: ICorDebugDataTarget2::GetSymbolProviderForImage メソッド
ms.date: 03/30/2017
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e5a6e70d5148756a5ed8d17c56577da920d1b69
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911450"
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a><span data-ttu-id="a81e7-102">ICorDebugDataTarget2::GetSymbolProviderForImage メソッド</span><span class="sxs-lookup"><span data-stu-id="a81e7-102">ICorDebugDataTarget2::GetSymbolProviderForImage Method</span></span>
<span data-ttu-id="a81e7-103">モジュールのベース アドレスからそのモジュールのシンボル プロバイダーを返します。</span><span class="sxs-lookup"><span data-stu-id="a81e7-103">Returns the symbol-provider for a module from the base address of that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a81e7-104">構文</span><span class="sxs-lookup"><span data-stu-id="a81e7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,   
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a81e7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a81e7-105">Parameters</span></span>  
 `imageBaseAddress`  
 <span data-ttu-id="a81e7-106">からモジュールのベースアドレスを表す[CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)値です。</span><span class="sxs-lookup"><span data-stu-id="a81e7-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the base address of a module.</span></span>  
  
 `ppSymProvider`  
 <span data-ttu-id="a81e7-107">入出力ツール[プロバイダー](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a81e7-107">[out] A pointer to the address of an [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a81e7-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="a81e7-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a81e7-109">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a81e7-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a81e7-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="a81e7-110">Requirements</span></span>  
 <span data-ttu-id="a81e7-111">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a81e7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a81e7-112">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="a81e7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a81e7-113">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="a81e7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a81e7-114">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a81e7-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a81e7-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="a81e7-115">See also</span></span>

- [<span data-ttu-id="a81e7-116">ICorDebugDataTarget2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a81e7-116">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="a81e7-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a81e7-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
