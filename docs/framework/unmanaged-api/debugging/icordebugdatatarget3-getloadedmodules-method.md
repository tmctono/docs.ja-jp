---
title: ICorDebugDataTarget3::GetLoadedModules メソッド
ms.date: 03/30/2017
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fc62618c5872a2c3e3740be4c60ae02e386c1868
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750031"
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a><span data-ttu-id="d3610-102">ICorDebugDataTarget3::GetLoadedModules メソッド</span><span class="sxs-lookup"><span data-stu-id="d3610-102">ICorDebugDataTarget3::GetLoadedModules Method</span></span>
<span data-ttu-id="d3610-103">これまでに読み込まれたモジュールの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="d3610-103">Gets a list of the modules that have been loaded so far.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3610-104">構文</span><span class="sxs-lookup"><span data-stu-id="d3610-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3610-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d3610-105">Parameters</span></span>  
 `cRequestedModules`  
 <span data-ttu-id="d3610-106">[in] 情報を要求する対象のモジュールの数。</span><span class="sxs-lookup"><span data-stu-id="d3610-106">[in] The number of modules for which information is requested.</span></span>  
  
 `pcFetchedModules`  
 <span data-ttu-id="d3610-107">[out] 情報が返された対象モジュールの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="d3610-107">[out] A pointer to the number of modules about which information was returned.</span></span>  
  
 `pLoadedModules`  
 <span data-ttu-id="d3610-108">[out]配列へのポインター [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)に関する情報を提供するオブジェクトにモジュールが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="d3610-108">[out] A pointer to an array of [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) objects that provide information about loaded modules.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3610-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="d3610-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d3610-110">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d3610-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3610-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="d3610-111">Requirements</span></span>  
 <span data-ttu-id="d3610-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3610-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3610-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d3610-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d3610-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3610-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3610-115">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3610-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3610-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3610-116">See also</span></span>

- [<span data-ttu-id="d3610-117">ICorDebugDataTarget3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d3610-117">ICorDebugDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)
- [<span data-ttu-id="d3610-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d3610-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
