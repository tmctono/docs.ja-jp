---
title: CorDebugDebugEventKind 列挙体
ms.date: 03/30/2017
api_name:
- CorDebugDebugEventKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6075a6cd-97e6-4472-a090-0dd14860d1f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e5479fad3f19c219a0ca1d5d01934ce92a7162e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127174"
---
# <a name="cordebugdebugeventkind-enumeration"></a><span data-ttu-id="ceeab-102">CorDebugDebugEventKind 列挙体</span><span class="sxs-lookup"><span data-stu-id="ceeab-102">CorDebugDebugEventKind Enumeration</span></span>
<span data-ttu-id="ceeab-103">情報がデコードされるによってイベントの種類を示す、 [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="ceeab-103">Indicates the type of event whose information is decoded by the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ceeab-104">構文</span><span class="sxs-lookup"><span data-stu-id="ceeab-104">Syntax</span></span>  
  
```  
typedef enum CorDebugDebugEventKind {  
    DEBUG_EVENT_KIND_MODULE_LOADED                          = 1,  
    DEBUG_EVENT_KIND_MODULE_UNLOADED                        = 2,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE         = 3,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE    = 4,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND  = 5,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED            = 6  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="ceeab-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="ceeab-105">Members</span></span>  
  
|<span data-ttu-id="ceeab-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="ceeab-106">Member</span></span>|<span data-ttu-id="ceeab-107">説明</span><span class="sxs-lookup"><span data-stu-id="ceeab-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EVENT_KIND_MODULE_LOADED`|<span data-ttu-id="ceeab-108">モジュールの読み込みイベント。</span><span class="sxs-lookup"><span data-stu-id="ceeab-108">A module load event.</span></span>|  
|`DEBUG_EVENT_KIND_MODULE_UNLOADED`|<span data-ttu-id="ceeab-109">モジュールのアンロード イベント。</span><span class="sxs-lookup"><span data-stu-id="ceeab-109">A module unload event.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="ceeab-110">初回例外。</span><span class="sxs-lookup"><span data-stu-id="ceeab-110">A first-chance exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="ceeab-111">ユーザーの初回例外。</span><span class="sxs-lookup"><span data-stu-id="ceeab-111">A first-chance user exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="ceeab-112">`catch` ハンドラーが存在する例外。</span><span class="sxs-lookup"><span data-stu-id="ceeab-112">An exception for which a `catch` handler exists.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED`|<span data-ttu-id="ceeab-113">未処理の例外。</span><span class="sxs-lookup"><span data-stu-id="ceeab-113">An unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ceeab-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="ceeab-114">Remarks</span></span>  
 <span data-ttu-id="ceeab-115">メンバー、`CorDebugDebugEventKind`列挙体が呼び出しによって返される、 [icordebugdebugevent::geteventkind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="ceeab-115">A member of the `CorDebugDebugEventKind` enumeration is returned by calling the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ceeab-116">この列挙型は .NET ネイティブのデバッグ シナリオのみで使用することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="ceeab-116">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ceeab-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="ceeab-117">Requirements</span></span>  
 <span data-ttu-id="ceeab-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ceeab-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ceeab-119">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ceeab-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ceeab-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ceeab-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ceeab-121">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="ceeab-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ceeab-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="ceeab-122">See also</span></span>

- [<span data-ttu-id="ceeab-123">列挙体のデバッグ</span><span class="sxs-lookup"><span data-stu-id="ceeab-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
