---
title: ICorDebugModuleDebugEvent::GetModule メソッド
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
ms.openlocfilehash: 1df71ddbf1ee76cc8202d8f9e263b9d95b4aaa09
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213362"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="4d3bf-102">ICorDebugModuleDebugEvent::GetModule メソッド</span><span class="sxs-lookup"><span data-stu-id="4d3bf-102">ICorDebugModuleDebugEvent::GetModule Method</span></span>
<span data-ttu-id="4d3bf-103">ロードまたはアンロードされたばかりのマージ モジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="4d3bf-103">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d3bf-104">構文</span><span class="sxs-lookup"><span data-stu-id="4d3bf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d3bf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4d3bf-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="4d3bf-106">[out] ロードまたはアンロードされたばかりのマージ モジュールを表す ICorDebugModule オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="4d3bf-106">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d3bf-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="4d3bf-107">Remarks</span></span>  
 <span data-ttu-id="4d3bf-108">[Geteventkind](icordebugdebugevent-geteventkind-method.md)メソッドを呼び出して、モジュールが読み込まれたかアンロードされたかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="4d3bf-108">You can call the [GetEventKind](icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4d3bf-109">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d3bf-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d3bf-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="4d3bf-110">Requirements</span></span>  
 <span data-ttu-id="4d3bf-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d3bf-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d3bf-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4d3bf-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d3bf-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d3bf-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d3bf-114">**.NET Framework のバージョン:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d3bf-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d3bf-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d3bf-115">See also</span></span>

- [<span data-ttu-id="4d3bf-116">ICorDebugModuleDebugEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4d3bf-116">ICorDebugModuleDebugEvent Interface</span></span>](icordebugmoduledebugevent-interface.md)
- [<span data-ttu-id="4d3bf-117">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="4d3bf-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
