---
title: 'いい Moduledebugevent:: GetModule メソッド'
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
ms.openlocfilehash: 5dc26d0367d01bc8da957c3ce648c3e529dddb08
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096935"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="6c015-102">いい Moduledebugevent:: GetModule メソッド</span><span class="sxs-lookup"><span data-stu-id="6c015-102">ICorDebugModuleDebugEvent::GetModule Method</span></span>
<span data-ttu-id="6c015-103">ロードまたはアンロードされたばかりのマージ モジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="6c015-103">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c015-104">構文</span><span class="sxs-lookup"><span data-stu-id="6c015-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c015-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6c015-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="6c015-106">入出力先ほど読み込まれた、またはアンロードされたマージモジュールを表す、モジュールオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6c015-106">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c015-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="6c015-107">Remarks</span></span>  
 <span data-ttu-id="6c015-108">[Geteventkind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md)メソッドを呼び出して、モジュールが読み込まれたかアンロードされたかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="6c015-108">You can call the [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6c015-109">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6c015-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c015-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="6c015-110">Requirements</span></span>  
 <span data-ttu-id="6c015-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c015-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c015-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6c015-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6c015-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c015-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c015-114">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c015-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c015-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c015-115">See also</span></span>

- [<span data-ttu-id="6c015-116">ICorDebugModuleDebugEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6c015-116">ICorDebugModuleDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)
- [<span data-ttu-id="6c015-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6c015-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
