---
title: ICorDebugModuleDebugEvent::GetModule メソッド
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c0cc1305f47f03c8c9b35bab5c980cb23d1b157
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942494"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="01f72-102">ICorDebugModuleDebugEvent::GetModule メソッド</span><span class="sxs-lookup"><span data-stu-id="01f72-102">ICorDebugModuleDebugEvent::GetModule Method</span></span>
<span data-ttu-id="01f72-103">ロードまたはアンロードされたばかりのマージ モジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="01f72-103">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01f72-104">構文</span><span class="sxs-lookup"><span data-stu-id="01f72-104">Syntax</span></span>  
  
```  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01f72-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="01f72-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="01f72-106">[out]ICorDebugModule だけロードまたはアンロードされたマージ モジュールを表すオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="01f72-106">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01f72-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="01f72-107">Remarks</span></span>  
 <span data-ttu-id="01f72-108">呼び出すことができます、 [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md)モジュールの読み込みまたはアンロードされたかどうかを判断するメソッド。</span><span class="sxs-lookup"><span data-stu-id="01f72-108">You can call the [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="01f72-109">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="01f72-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01f72-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="01f72-110">Requirements</span></span>  
 <span data-ttu-id="01f72-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="01f72-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01f72-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="01f72-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="01f72-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01f72-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01f72-114">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01f72-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01f72-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="01f72-115">See also</span></span>

- [<span data-ttu-id="01f72-116">ICorDebugModuleDebugEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="01f72-116">ICorDebugModuleDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)
- [<span data-ttu-id="01f72-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="01f72-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
