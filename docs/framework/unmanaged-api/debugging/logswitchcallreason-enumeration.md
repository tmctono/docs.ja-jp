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
ms.openlocfilehash: 7eadb595eb62b4f1a9dcc888225cbb7454119c7c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198492"
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="d27cc-102">LogSwitchCallReason 列挙型</span><span class="sxs-lookup"><span data-stu-id="d27cc-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="d27cc-103">デバッグとトレースの切り替えで実行された操作を示します。</span><span class="sxs-lookup"><span data-stu-id="d27cc-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d27cc-104">構文</span><span class="sxs-lookup"><span data-stu-id="d27cc-104">Syntax</span></span>  
  
```  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="d27cc-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="d27cc-105">Members</span></span>  
  
|<span data-ttu-id="d27cc-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="d27cc-106">Member</span></span>|<span data-ttu-id="d27cc-107">説明</span><span class="sxs-lookup"><span data-stu-id="d27cc-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="d27cc-108">デバッグとトレース スイッチが作成されました。</span><span class="sxs-lookup"><span data-stu-id="d27cc-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="d27cc-109">デバッグとトレース スイッチが変更されました。</span><span class="sxs-lookup"><span data-stu-id="d27cc-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="d27cc-110">デバッグとトレース スイッチが削除されました。</span><span class="sxs-lookup"><span data-stu-id="d27cc-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d27cc-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="d27cc-111">Requirements</span></span>  
 <span data-ttu-id="d27cc-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d27cc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d27cc-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d27cc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d27cc-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d27cc-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d27cc-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="d27cc-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d27cc-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="d27cc-116">See also</span></span>

- [<span data-ttu-id="d27cc-117">列挙体のデバッグ</span><span class="sxs-lookup"><span data-stu-id="d27cc-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
