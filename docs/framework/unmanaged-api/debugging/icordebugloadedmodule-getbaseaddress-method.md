---
title: ICorDebugLoadedModule::GetBaseAddress メソッド
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
ms.openlocfilehash: d8c91c10577efd6a76af778cd01002de006df43a
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209878"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="76461-102">ICorDebugLoadedModule::GetBaseAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="76461-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="76461-103">読み込まれたモジュールのベース アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="76461-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76461-104">構文</span><span class="sxs-lookup"><span data-stu-id="76461-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76461-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="76461-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="76461-106">[out] 読み込まれたモジュールのベース アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="76461-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76461-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="76461-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="76461-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="76461-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76461-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="76461-109">Requirements</span></span>  
 <span data-ttu-id="76461-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76461-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76461-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="76461-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="76461-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76461-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76461-113">**.NET Framework のバージョン:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76461-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76461-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="76461-114">See also</span></span>

- [<span data-ttu-id="76461-115">ICorDebugLoadedModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="76461-115">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="76461-116">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="76461-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
