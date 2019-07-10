---
title: ICorDebugLoadedModule::GetBaseAddress メソッド
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: adb01b8aa57bf3ed928578d15e0859b9ac73bc7d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759939"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="e7954-102">ICorDebugLoadedModule::GetBaseAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="e7954-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="e7954-103">読み込まれたモジュールのベース アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="e7954-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7954-104">構文</span><span class="sxs-lookup"><span data-stu-id="e7954-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7954-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e7954-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="e7954-106">[out] 読み込まれたモジュールのベース アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e7954-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7954-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="e7954-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e7954-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e7954-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7954-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="e7954-109">Requirements</span></span>  
 <span data-ttu-id="e7954-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7954-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7954-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e7954-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e7954-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7954-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7954-113">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7954-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7954-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7954-114">See also</span></span>

- [<span data-ttu-id="e7954-115">ICorDebugLoadedModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e7954-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="e7954-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e7954-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
