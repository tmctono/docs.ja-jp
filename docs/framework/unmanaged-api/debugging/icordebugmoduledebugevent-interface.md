---
title: ICorDebugModuleDebugEvent インターフェイス
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
ms.openlocfilehash: ec6bad730d807b9a36ce5bba1c6f5d80da375f6d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213334"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="908e2-102">ICorDebugModuleDebugEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="908e2-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="908e2-103">モジュールレベルのイベントをサポートするように、のモジュールレベル[のイベントを](icordebugdebugevent-interface.md)拡張します。</span><span class="sxs-lookup"><span data-stu-id="908e2-103">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="908e2-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="908e2-104">Methods</span></span>  
  
|<span data-ttu-id="908e2-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="908e2-105">Method</span></span>|<span data-ttu-id="908e2-106">説明</span><span class="sxs-lookup"><span data-stu-id="908e2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="908e2-107">GetModule メソッド</span><span class="sxs-lookup"><span data-stu-id="908e2-107">GetModule Method</span></span>](icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="908e2-108">ロードまたはアンロードされたばかりのマージ モジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="908e2-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="908e2-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="908e2-109">Remarks</span></span>  
 <span data-ttu-id="908e2-110">[MODULE_LOADED](cordebugdebugeventkind-enumeration.md)イベントと[MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md)イベントの種類は、このインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="908e2-110">The [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="908e2-111">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="908e2-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="908e2-112">インターフェイス ポインターを取得するために `QueryInterface` を呼び出そうとすると、.NET ネイティブ外の ICorDebug シナリオに対して `E_NOINTERFACE` が返されます。</span><span class="sxs-lookup"><span data-stu-id="908e2-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="908e2-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="908e2-113">Requirements</span></span>  
 <span data-ttu-id="908e2-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="908e2-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="908e2-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="908e2-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="908e2-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="908e2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="908e2-117">**.NET Framework のバージョン:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="908e2-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="908e2-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="908e2-118">See also</span></span>

- [<span data-ttu-id="908e2-119">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="908e2-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="908e2-120">デバッグ</span><span class="sxs-lookup"><span data-stu-id="908e2-120">Debugging</span></span>](index.md)
