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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d4e006a03db5b16de93dfd07ec7b964db4bfc1d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609218"
---
# <a name="cordebugdecodeeventflagswindows-enumeration"></a><span data-ttu-id="60735-102">CorDebugDecodeEventFlagsWindows 列挙体</span><span class="sxs-lookup"><span data-stu-id="60735-102">CorDebugDecodeEventFlagsWindows Enumeration</span></span>
<span data-ttu-id="60735-103">Windows プラットフォームのデバッグ イベントに関する追加情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="60735-103">Provides additional information about debug events on the Windows platform.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60735-104">構文</span><span class="sxs-lookup"><span data-stu-id="60735-104">Syntax</span></span>  
  
```  
typedef enum CorDebugDecodeEventFlagsWindows {  
    IS_FIRST_CHANCE = 1,  
} CorDebugDecodeEventFlagsWindows;  
```  
  
## <a name="members"></a><span data-ttu-id="60735-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="60735-105">Members</span></span>  
  
|<span data-ttu-id="60735-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="60735-106">Member</span></span>|<span data-ttu-id="60735-107">説明</span><span class="sxs-lookup"><span data-stu-id="60735-107">Description</span></span>|  
|------------|-----------------|  
|`IS_FIRST_CHANCE`|<span data-ttu-id="60735-108">デバッグ イベントが初回例外であることを示します。</span><span class="sxs-lookup"><span data-stu-id="60735-108">Indicates that the debug event is a first-chance exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60735-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="60735-109">Remarks</span></span>  
 <span data-ttu-id="60735-110">[Icordebugprocess 6::decodeevent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md)メソッドが含まれています、`dwFlags`パラメーター デバッグ イベントに関する追加情報を提供し、値がターゲット アーキテクチャに依存します。</span><span class="sxs-lookup"><span data-stu-id="60735-110">The [ICorDebugProcess6::DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method includes a `dwFlags` parameter that provides additional information about a debug event and whose value is dependent on the target architecture.</span></span> <span data-ttu-id="60735-111">`CorDebugDecodeEventFlagsWindows` 列挙体は、Windows プラットフォームでデバッグ イベントと共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="60735-111">The `CorDebugDecodeEventFlagsWindows` enumeration can be used with debug events on the Windows platform.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60735-112">この列挙型は .NET ネイティブのデバッグ シナリオのみで使用することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="60735-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60735-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="60735-113">Requirements</span></span>  
 <span data-ttu-id="60735-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="60735-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60735-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="60735-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="60735-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60735-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60735-117">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60735-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60735-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="60735-118">See also</span></span>

- [<span data-ttu-id="60735-119">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="60735-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
