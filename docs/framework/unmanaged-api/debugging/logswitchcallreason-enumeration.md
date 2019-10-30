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
ms.openlocfilehash: 2a6ca9f4d74c508ac0a2af68c2a5b0a3e6d6b217
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139181"
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="4b754-102">LogSwitchCallReason 列挙型</span><span class="sxs-lookup"><span data-stu-id="4b754-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="4b754-103">デバッグとトレースの切り替えで実行された操作を示します。</span><span class="sxs-lookup"><span data-stu-id="4b754-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b754-104">構文</span><span class="sxs-lookup"><span data-stu-id="4b754-104">Syntax</span></span>  
  
```cpp  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="4b754-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="4b754-105">Members</span></span>  
  
|<span data-ttu-id="4b754-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="4b754-106">Member</span></span>|<span data-ttu-id="4b754-107">説明</span><span class="sxs-lookup"><span data-stu-id="4b754-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="4b754-108">デバッグ/トレーススイッチが作成されました。</span><span class="sxs-lookup"><span data-stu-id="4b754-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="4b754-109">デバッグ/トレーススイッチが変更されました。</span><span class="sxs-lookup"><span data-stu-id="4b754-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="4b754-110">デバッグ/トレーススイッチが削除されました。</span><span class="sxs-lookup"><span data-stu-id="4b754-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4b754-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="4b754-111">Requirements</span></span>  
 <span data-ttu-id="4b754-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b754-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b754-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b754-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b754-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b754-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b754-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b754-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b754-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b754-116">See also</span></span>

- [<span data-ttu-id="4b754-117">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="4b754-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
