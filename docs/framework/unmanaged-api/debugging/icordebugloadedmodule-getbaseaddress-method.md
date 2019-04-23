---
title: ICorDebugLoadedModule::GetBaseAddress メソッド
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e84d6deca0cd09cc547636007208c70ab91c1ab1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59223538"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="2a182-102">ICorDebugLoadedModule::GetBaseAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="2a182-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="2a182-103">読み込まれたモジュールのベース アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="2a182-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a182-104">構文</span><span class="sxs-lookup"><span data-stu-id="2a182-104">Syntax</span></span>  
  
```  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a182-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2a182-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="2a182-106">[out] 読み込まれたモジュールのベース アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2a182-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a182-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="2a182-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a182-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2a182-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a182-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="2a182-109">Requirements</span></span>  
 <span data-ttu-id="2a182-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a182-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a182-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2a182-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2a182-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a182-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a182-113">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a182-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a182-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a182-114">See also</span></span>

- [<span data-ttu-id="2a182-115">ICorDebugLoadedModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2a182-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="2a182-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2a182-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
