---
title: ICorDebugModuleDebugEvent::GetModule メソッド
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
ms.openlocfilehash: 4d9eea8fb5c42002763a0ae52a186bf2c1e6d2ee
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792904"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="2f0f2-102">ICorDebugModuleDebugEvent::GetModule メソッド</span><span class="sxs-lookup"><span data-stu-id="2f0f2-102">ICorDebugModuleDebugEvent::GetModule Method</span></span>
<span data-ttu-id="2f0f2-103">ロードまたはアンロードされたばかりのマージ モジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="2f0f2-103">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f0f2-104">構文</span><span class="sxs-lookup"><span data-stu-id="2f0f2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f0f2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2f0f2-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="2f0f2-106">[out] ロードまたはアンロードされたばかりのマージ モジュールを表す ICorDebugModule オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2f0f2-106">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f0f2-107">コメント</span><span class="sxs-lookup"><span data-stu-id="2f0f2-107">Remarks</span></span>  
 <span data-ttu-id="2f0f2-108">[Geteventkind](icordebugdebugevent-geteventkind-method.md)メソッドを呼び出して、モジュールが読み込まれたかアンロードされたかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="2f0f2-108">You can call the [GetEventKind](icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2f0f2-109">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2f0f2-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f0f2-110">要件</span><span class="sxs-lookup"><span data-stu-id="2f0f2-110">Requirements</span></span>  
 <span data-ttu-id="2f0f2-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f0f2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f0f2-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f0f2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f0f2-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f0f2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f0f2-114">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f0f2-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f0f2-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f0f2-115">See also</span></span>

- [<span data-ttu-id="2f0f2-116">ICorDebugModuleDebugEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2f0f2-116">ICorDebugModuleDebugEvent Interface</span></span>](icordebugmoduledebugevent-interface.md)
- [<span data-ttu-id="2f0f2-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2f0f2-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
