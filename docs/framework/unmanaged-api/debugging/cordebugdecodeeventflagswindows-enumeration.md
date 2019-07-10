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
ms.openlocfilehash: bab7da5855eaf562e55738b489ebf6f62dc45d04
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740232"
---
# <a name="cordebugdecodeeventflagswindows-enumeration"></a><span data-ttu-id="23ddb-102">CorDebugDecodeEventFlagsWindows 列挙体</span><span class="sxs-lookup"><span data-stu-id="23ddb-102">CorDebugDecodeEventFlagsWindows Enumeration</span></span>
<span data-ttu-id="23ddb-103">Windows プラットフォームのデバッグ イベントに関する追加情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="23ddb-103">Provides additional information about debug events on the Windows platform.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23ddb-104">構文</span><span class="sxs-lookup"><span data-stu-id="23ddb-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugDecodeEventFlagsWindows {  
    IS_FIRST_CHANCE = 1,  
} CorDebugDecodeEventFlagsWindows;  
```  
  
## <a name="members"></a><span data-ttu-id="23ddb-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="23ddb-105">Members</span></span>  
  
|<span data-ttu-id="23ddb-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="23ddb-106">Member</span></span>|<span data-ttu-id="23ddb-107">説明</span><span class="sxs-lookup"><span data-stu-id="23ddb-107">Description</span></span>|  
|------------|-----------------|  
|`IS_FIRST_CHANCE`|<span data-ttu-id="23ddb-108">デバッグ イベントが初回例外であることを示します。</span><span class="sxs-lookup"><span data-stu-id="23ddb-108">Indicates that the debug event is a first-chance exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23ddb-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="23ddb-109">Remarks</span></span>  
 <span data-ttu-id="23ddb-110">[Icordebugprocess 6::decodeevent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md)メソッドが含まれています、`dwFlags`パラメーター デバッグ イベントに関する追加情報を提供し、値がターゲット アーキテクチャに依存します。</span><span class="sxs-lookup"><span data-stu-id="23ddb-110">The [ICorDebugProcess6::DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method includes a `dwFlags` parameter that provides additional information about a debug event and whose value is dependent on the target architecture.</span></span> <span data-ttu-id="23ddb-111">`CorDebugDecodeEventFlagsWindows` 列挙体は、Windows プラットフォームでデバッグ イベントと共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="23ddb-111">The `CorDebugDecodeEventFlagsWindows` enumeration can be used with debug events on the Windows platform.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="23ddb-112">この列挙型は .NET ネイティブのデバッグ シナリオのみで使用することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="23ddb-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23ddb-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="23ddb-113">Requirements</span></span>  
 <span data-ttu-id="23ddb-114">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="23ddb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23ddb-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23ddb-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23ddb-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23ddb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23ddb-117">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23ddb-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23ddb-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="23ddb-118">See also</span></span>

- [<span data-ttu-id="23ddb-119">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="23ddb-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
