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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59198492"
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="055d3-102">LogSwitchCallReason 列挙型</span><span class="sxs-lookup"><span data-stu-id="055d3-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="055d3-103">デバッグとトレースの切り替えで実行された操作を示します。</span><span class="sxs-lookup"><span data-stu-id="055d3-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="055d3-104">構文</span><span class="sxs-lookup"><span data-stu-id="055d3-104">Syntax</span></span>  
  
```  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="055d3-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="055d3-105">Members</span></span>  
  
|<span data-ttu-id="055d3-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="055d3-106">Member</span></span>|<span data-ttu-id="055d3-107">説明</span><span class="sxs-lookup"><span data-stu-id="055d3-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="055d3-108">デバッグとトレース スイッチが作成されました。</span><span class="sxs-lookup"><span data-stu-id="055d3-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="055d3-109">デバッグとトレース スイッチが変更されました。</span><span class="sxs-lookup"><span data-stu-id="055d3-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="055d3-110">デバッグとトレース スイッチが削除されました。</span><span class="sxs-lookup"><span data-stu-id="055d3-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="055d3-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="055d3-111">Requirements</span></span>  
 <span data-ttu-id="055d3-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="055d3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="055d3-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="055d3-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="055d3-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="055d3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="055d3-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="055d3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="055d3-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="055d3-116">See also</span></span>

- [<span data-ttu-id="055d3-117">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="055d3-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
