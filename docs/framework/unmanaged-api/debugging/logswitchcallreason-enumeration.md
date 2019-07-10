---
title: LogSwitchCallReason 列挙型
ms.date: 03/30/2017
api_name:
- LogSwitchCallReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- LogSwitchCallReason
helpviewer_keywords:
- LogSwitchCallReason enumeration [.NET Framework debugging]
ms.assetid: 5bbb8d1b-bbc4-47b0-b1b1-2d54cc0be291
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 894f74f12de7ed0754dcca34eacb815efc33c766
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752571"
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="21ef6-102">LogSwitchCallReason 列挙型</span><span class="sxs-lookup"><span data-stu-id="21ef6-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="21ef6-103">デバッグとトレースの切り替えで実行された操作を示します。</span><span class="sxs-lookup"><span data-stu-id="21ef6-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21ef6-104">構文</span><span class="sxs-lookup"><span data-stu-id="21ef6-104">Syntax</span></span>  
  
```cpp  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="21ef6-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="21ef6-105">Members</span></span>  
  
|<span data-ttu-id="21ef6-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="21ef6-106">Member</span></span>|<span data-ttu-id="21ef6-107">説明</span><span class="sxs-lookup"><span data-stu-id="21ef6-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="21ef6-108">デバッグとトレース スイッチが作成されました。</span><span class="sxs-lookup"><span data-stu-id="21ef6-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="21ef6-109">デバッグとトレース スイッチが変更されました。</span><span class="sxs-lookup"><span data-stu-id="21ef6-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="21ef6-110">デバッグとトレース スイッチが削除されました。</span><span class="sxs-lookup"><span data-stu-id="21ef6-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="21ef6-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="21ef6-111">Requirements</span></span>  
 <span data-ttu-id="21ef6-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="21ef6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21ef6-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="21ef6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="21ef6-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21ef6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21ef6-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21ef6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21ef6-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="21ef6-116">See also</span></span>

- [<span data-ttu-id="21ef6-117">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="21ef6-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
