---
title: ICorDebugLoadedModule::GetBaseAddress メソッド
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
ms.openlocfilehash: 190c9114cffa537ba162b19abdf30d5a6aee87f8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788448"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="647fe-102">ICorDebugLoadedModule::GetBaseAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="647fe-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="647fe-103">読み込まれたモジュールのベース アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="647fe-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="647fe-104">構文</span><span class="sxs-lookup"><span data-stu-id="647fe-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="647fe-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="647fe-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="647fe-106">[out] 読み込まれたモジュールのベース アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="647fe-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="647fe-107">コメント</span><span class="sxs-lookup"><span data-stu-id="647fe-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="647fe-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="647fe-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="647fe-109">要件</span><span class="sxs-lookup"><span data-stu-id="647fe-109">Requirements</span></span>  
 <span data-ttu-id="647fe-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="647fe-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="647fe-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="647fe-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="647fe-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="647fe-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="647fe-113">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="647fe-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="647fe-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="647fe-114">See also</span></span>

- [<span data-ttu-id="647fe-115">ICorDebugLoadedModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="647fe-115">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="647fe-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="647fe-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
