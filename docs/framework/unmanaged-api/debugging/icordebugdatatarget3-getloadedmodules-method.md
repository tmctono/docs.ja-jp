---
title: ICorDebugDataTarget3::GetLoadedModules メソッド
ms.date: 03/30/2017
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
ms.openlocfilehash: d4c22146422085daa4dc9d90ae5b3735a12500c2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793553"
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a><span data-ttu-id="2770f-102">ICorDebugDataTarget3::GetLoadedModules メソッド</span><span class="sxs-lookup"><span data-stu-id="2770f-102">ICorDebugDataTarget3::GetLoadedModules Method</span></span>
<span data-ttu-id="2770f-103">これまでに読み込まれたモジュールの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="2770f-103">Gets a list of the modules that have been loaded so far.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2770f-104">構文</span><span class="sxs-lookup"><span data-stu-id="2770f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2770f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2770f-105">Parameters</span></span>  
 `cRequestedModules`  
 <span data-ttu-id="2770f-106">[in] 情報を要求する対象のモジュールの数。</span><span class="sxs-lookup"><span data-stu-id="2770f-106">[in] The number of modules for which information is requested.</span></span>  
  
 `pcFetchedModules`  
 <span data-ttu-id="2770f-107">[out] 情報が返された対象モジュールの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="2770f-107">[out] A pointer to the number of modules about which information was returned.</span></span>  
  
 `pLoadedModules`  
 <span data-ttu-id="2770f-108">入出力読み込まれたモジュールに関する情報を提供する[ICorDebugLoadedModule](icordebugloadedmodule-interface.md)オブジェクトの配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="2770f-108">[out] A pointer to an array of [ICorDebugLoadedModule](icordebugloadedmodule-interface.md) objects that provide information about loaded modules.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2770f-109">コメント</span><span class="sxs-lookup"><span data-stu-id="2770f-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2770f-110">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2770f-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2770f-111">要件</span><span class="sxs-lookup"><span data-stu-id="2770f-111">Requirements</span></span>  
 <span data-ttu-id="2770f-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2770f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2770f-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2770f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2770f-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2770f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2770f-115">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2770f-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2770f-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="2770f-116">See also</span></span>

- [<span data-ttu-id="2770f-117">ICorDebugDataTarget3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2770f-117">ICorDebugDataTarget3 Interface</span></span>](icordebugdatatarget3-interface.md)
- [<span data-ttu-id="2770f-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2770f-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
