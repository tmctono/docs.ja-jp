---
title: CorDebugDecodeEventFlagsWindows 列挙体
ms.date: 03/30/2017
api_name:
- CorDebugDecodeEventFlagsWindows
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aa6cf962-30ae-4cfd-8895-826deeb46a54
topic_type:
- apiref
ms.openlocfilehash: da3a100bd552eaa3233642b006e0265adbcac1ca
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132214"
---
# <a name="cordebugdecodeeventflagswindows-enumeration"></a><span data-ttu-id="c8473-102">CorDebugDecodeEventFlagsWindows 列挙体</span><span class="sxs-lookup"><span data-stu-id="c8473-102">CorDebugDecodeEventFlagsWindows Enumeration</span></span>
<span data-ttu-id="c8473-103">Windows プラットフォームのデバッグ イベントに関する追加情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c8473-103">Provides additional information about debug events on the Windows platform.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8473-104">構文</span><span class="sxs-lookup"><span data-stu-id="c8473-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugDecodeEventFlagsWindows {  
    IS_FIRST_CHANCE = 1,  
} CorDebugDecodeEventFlagsWindows;  
```  
  
## <a name="members"></a><span data-ttu-id="c8473-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="c8473-105">Members</span></span>  
  
|<span data-ttu-id="c8473-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="c8473-106">Member</span></span>|<span data-ttu-id="c8473-107">説明</span><span class="sxs-lookup"><span data-stu-id="c8473-107">Description</span></span>|  
|------------|-----------------|  
|`IS_FIRST_CHANCE`|<span data-ttu-id="c8473-108">デバッグ イベントが初回例外であることを示します。</span><span class="sxs-lookup"><span data-stu-id="c8473-108">Indicates that the debug event is a first-chance exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8473-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="c8473-109">Remarks</span></span>  
 <span data-ttu-id="c8473-110">[ICorDebugProcess6::D ecodeevent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md)メソッドには、デバッグイベントに関する追加情報を提供し、ターゲットアーキテクチャに依存する値を持つ `dwFlags` パラメーターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c8473-110">The [ICorDebugProcess6::DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method includes a `dwFlags` parameter that provides additional information about a debug event and whose value is dependent on the target architecture.</span></span> <span data-ttu-id="c8473-111">`CorDebugDecodeEventFlagsWindows` 列挙体は、Windows プラットフォームでデバッグ イベントと共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="c8473-111">The `CorDebugDecodeEventFlagsWindows` enumeration can be used with debug events on the Windows platform.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c8473-112">この列挙型は .NET ネイティブのデバッグ シナリオのみで使用することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="c8473-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8473-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="c8473-113">Requirements</span></span>  
 <span data-ttu-id="c8473-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8473-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8473-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8473-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8473-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8473-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8473-117">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8473-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8473-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8473-118">See also</span></span>

- [<span data-ttu-id="c8473-119">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="c8473-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
