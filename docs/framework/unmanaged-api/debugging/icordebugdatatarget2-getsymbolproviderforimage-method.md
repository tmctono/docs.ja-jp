---
title: ICorDebugDataTarget2::GetSymbolProviderForImage メソッド
ms.date: 03/30/2017
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
ms.openlocfilehash: 7800630be0ed9afb321d607046be308088781388
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976448"
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a><span data-ttu-id="0aeba-102">ICorDebugDataTarget2::GetSymbolProviderForImage メソッド</span><span class="sxs-lookup"><span data-stu-id="0aeba-102">ICorDebugDataTarget2::GetSymbolProviderForImage Method</span></span>
<span data-ttu-id="0aeba-103">モジュールのベース アドレスからそのモジュールのシンボル プロバイダーを返します。</span><span class="sxs-lookup"><span data-stu-id="0aeba-103">Returns the symbol-provider for a module from the base address of that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0aeba-104">構文</span><span class="sxs-lookup"><span data-stu-id="0aeba-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0aeba-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0aeba-105">Parameters</span></span>  
 `imageBaseAddress`  
 <span data-ttu-id="0aeba-106">からモジュールのベースアドレスを表す[CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md)値。</span><span class="sxs-lookup"><span data-stu-id="0aeba-106">[in] A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents the base address of a module.</span></span>  
  
 `ppSymProvider`  
 <span data-ttu-id="0aeba-107">入出力ツール[プロバイダー](icordebugsymbolprovider-interface.md)オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="0aeba-107">[out] A pointer to the address of an [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0aeba-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="0aeba-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0aeba-109">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="0aeba-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0aeba-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="0aeba-110">Requirements</span></span>  
 <span data-ttu-id="0aeba-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0aeba-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0aeba-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0aeba-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0aeba-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0aeba-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0aeba-114">**.NET Framework のバージョン:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0aeba-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0aeba-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="0aeba-115">See also</span></span>

- [<span data-ttu-id="0aeba-116">ICorDebugDataTarget2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0aeba-116">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="0aeba-117">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="0aeba-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
