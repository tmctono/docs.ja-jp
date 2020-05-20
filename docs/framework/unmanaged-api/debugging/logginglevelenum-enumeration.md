---
title: LoggingLevelEnum 列挙型
ms.date: 03/30/2017
api_name:
- LoggingLevelEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- LoggingLevelEnum
helpviewer_keywords:
- LoggingLevelEnum enumeration [.NET Framework debugging]
ms.assetid: 09daac08-005a-46b2-beab-408d0820c5e5
topic_type:
- apiref
ms.openlocfilehash: 62ea982f30a6a73648d9bf36722c0b5a49a68896
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420748"
---
# <a name="logginglevelenum-enumeration"></a><span data-ttu-id="5f222-102">LoggingLevelEnum 列挙型</span><span class="sxs-lookup"><span data-stu-id="5f222-102">LoggingLevelEnum Enumeration</span></span>
<span data-ttu-id="5f222-103">マネージド スレッドがイベントを記録する際にイベント ログに書き込まれる説明メッセージの重大度レベルを示します。</span><span class="sxs-lookup"><span data-stu-id="5f222-103">Indicates the severity level of a descriptive message that is written to the event log when a managed thread logs an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f222-104">構文</span><span class="sxs-lookup"><span data-stu-id="5f222-104">Syntax</span></span>  
  
```cpp  
typedef enum LoggingLevelEnum {  
    LTraceLevel0 = 0,  
    LTraceLevel1,  
    LTraceLevel2,  
    LTraceLevel3,  
    LTraceLevel4,  
    LStatusLevel0 = 20,  
    LStatusLevel1,  
    LStatusLevel2,  
    LStatusLevel3,  
    LStatusLevel4,  
    LWarningLevel = 40,  
    LErrorLevel = 50,  
    LPanicLevel = 100  
} LoggingLevelEnum;  
```  
  
## <a name="members"></a><span data-ttu-id="5f222-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="5f222-105">Members</span></span>  
  
|<span data-ttu-id="5f222-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="5f222-106">Member</span></span>|<span data-ttu-id="5f222-107">説明</span><span class="sxs-lookup"><span data-stu-id="5f222-107">Description</span></span>|  
|------------|-----------------|  
|`LTraceLevel0`|<span data-ttu-id="5f222-108">メッセージはトレースレベル0です。</span><span class="sxs-lookup"><span data-stu-id="5f222-108">The message is a trace level 0.</span></span>|  
|`LTraceLevel1`|<span data-ttu-id="5f222-109">メッセージはトレースレベル1です。</span><span class="sxs-lookup"><span data-stu-id="5f222-109">The message is a trace level 1.</span></span>|  
|`LTraceLevel2`|<span data-ttu-id="5f222-110">メッセージはトレースレベル2です。</span><span class="sxs-lookup"><span data-stu-id="5f222-110">The message is a trace level 2.</span></span>|  
|`LTraceLevel3`|<span data-ttu-id="5f222-111">メッセージはトレースレベル3です。</span><span class="sxs-lookup"><span data-stu-id="5f222-111">The message is a trace level 3.</span></span>|  
|`LTraceLevel4`|<span data-ttu-id="5f222-112">メッセージはトレースレベル4です。</span><span class="sxs-lookup"><span data-stu-id="5f222-112">The message is a trace level 4.</span></span>|  
|`LStatusLevel0`|<span data-ttu-id="5f222-113">メッセージはステータスレベル0です。</span><span class="sxs-lookup"><span data-stu-id="5f222-113">The message is a status level 0.</span></span>|  
|`LStatusLevel1`|<span data-ttu-id="5f222-114">メッセージはステータスレベル1です。</span><span class="sxs-lookup"><span data-stu-id="5f222-114">The message is a status level 1.</span></span>|  
|`LStatusLevel2`|<span data-ttu-id="5f222-115">メッセージはステータスレベル2です。</span><span class="sxs-lookup"><span data-stu-id="5f222-115">The message is a status level 2.</span></span>|  
|`LStatusLevel3`|<span data-ttu-id="5f222-116">メッセージはステータスレベル3です。</span><span class="sxs-lookup"><span data-stu-id="5f222-116">The message is a status level 3.</span></span>|  
|`LStatusLevel4`|<span data-ttu-id="5f222-117">メッセージはステータスレベル4です。</span><span class="sxs-lookup"><span data-stu-id="5f222-117">The message is a status level 4.</span></span>|  
|`LWarningLevel`|<span data-ttu-id="5f222-118">メッセージは警告レベルです。</span><span class="sxs-lookup"><span data-stu-id="5f222-118">The message is a warning level.</span></span>|  
|`LErrorLevel`|<span data-ttu-id="5f222-119">メッセージはエラーレベルです。</span><span class="sxs-lookup"><span data-stu-id="5f222-119">The message is an error level.</span></span>|  
|`LPanicLevel`|<span data-ttu-id="5f222-120">メッセージはパニックレベルです。</span><span class="sxs-lookup"><span data-stu-id="5f222-120">The message is a panic level.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f222-121">解説</span><span class="sxs-lookup"><span data-stu-id="5f222-121">Remarks</span></span>  
 <span data-ttu-id="5f222-122">共通言語ランタイム (CLR: common language runtime) は、コンポーネントのマネージ[コールバック:: LogMessage](icordebugmanagedcallback-logmessage-method.md)メソッドを呼び出して、マネージスレッドがイベントを記録したことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="5f222-122">The common language runtime (CLR) calls the [ICorDebugManagedCallback::LogMessage](icordebugmanagedcallback-logmessage-method.md) method to notify the debugger that a managed thread has logged an event.</span></span> <span data-ttu-id="5f222-123">CLR は、マネージスレッドによって `LoggingLevelEnum` イベントログに書き込まれたメッセージの重大度レベルを示すために、列挙体の値を渡します。</span><span class="sxs-lookup"><span data-stu-id="5f222-123">The CLR passes a value of the `LoggingLevelEnum` enumeration to indicate the severity level of the message that the managed thread wrote to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f222-124">要件</span><span class="sxs-lookup"><span data-stu-id="5f222-124">Requirements</span></span>  
 <span data-ttu-id="5f222-125">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f222-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f222-126">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f222-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f222-127">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f222-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f222-128">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f222-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f222-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="5f222-129">See also</span></span>

- <xref:System.Diagnostics.EventLog>
- [<span data-ttu-id="5f222-130">列挙体のデバッグ</span><span class="sxs-lookup"><span data-stu-id="5f222-130">Debugging Enumerations</span></span>](debugging-enumerations.md)
