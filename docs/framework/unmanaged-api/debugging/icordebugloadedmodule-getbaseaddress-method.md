---
title: ICorDebugLoadedModule::GetBaseAddress メソッド
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85748106edb34b98f975a40bcc2617401536e271
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910099"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="db6e9-102">ICorDebugLoadedModule::GetBaseAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="db6e9-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="db6e9-103">読み込まれたモジュールのベース アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="db6e9-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db6e9-104">構文</span><span class="sxs-lookup"><span data-stu-id="db6e9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db6e9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="db6e9-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="db6e9-106">[out] 読み込まれたモジュールのベース アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="db6e9-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db6e9-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="db6e9-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="db6e9-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="db6e9-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db6e9-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="db6e9-109">Requirements</span></span>  
 <span data-ttu-id="db6e9-110">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="db6e9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db6e9-111">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="db6e9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db6e9-112">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="db6e9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db6e9-113">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db6e9-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db6e9-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="db6e9-114">See also</span></span>

- [<span data-ttu-id="db6e9-115">ICorDebugLoadedModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="db6e9-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="db6e9-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="db6e9-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
