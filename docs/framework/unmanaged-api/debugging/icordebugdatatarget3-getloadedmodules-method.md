---
title: ICorDebugDataTarget3::GetLoadedModules メソッド
ms.date: 03/30/2017
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 464fd9ac44d6ba5717dbc4ecfbe03b6e6ad52276
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789722"
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a><span data-ttu-id="4a2e4-102">ICorDebugDataTarget3::GetLoadedModules メソッド</span><span class="sxs-lookup"><span data-stu-id="4a2e4-102">ICorDebugDataTarget3::GetLoadedModules Method</span></span>
<span data-ttu-id="4a2e4-103">これまでに読み込まれたモジュールの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="4a2e4-103">Gets a list of the modules that have been loaded so far.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a2e4-104">構文</span><span class="sxs-lookup"><span data-stu-id="4a2e4-104">Syntax</span></span>  
  
```  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a2e4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4a2e4-105">Parameters</span></span>  
 `cRequestedModules`  
 <span data-ttu-id="4a2e4-106">[in] 情報を要求する対象のモジュールの数。</span><span class="sxs-lookup"><span data-stu-id="4a2e4-106">[in] The number of modules for which information is requested.</span></span>  
  
 `pcFetchedModules`  
 <span data-ttu-id="4a2e4-107">[out] 情報が返された対象モジュールの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="4a2e4-107">[out] A pointer to the number of modules about which information was returned.</span></span>  
  
 `pLoadedModules`  
 <span data-ttu-id="4a2e4-108">[out]配列へのポインター [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)に関する情報を提供するオブジェクトにモジュールが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="4a2e4-108">[out] A pointer to an array of [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) objects that provide information about loaded modules.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a2e4-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="4a2e4-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a2e4-110">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="4a2e4-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a2e4-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="4a2e4-111">Requirements</span></span>  
 <span data-ttu-id="4a2e4-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a2e4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a2e4-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4a2e4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a2e4-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a2e4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a2e4-115">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a2e4-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a2e4-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a2e4-116">See also</span></span>

- [<span data-ttu-id="4a2e4-117">ICorDebugDataTarget3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4a2e4-117">ICorDebugDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)
- [<span data-ttu-id="4a2e4-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4a2e4-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
