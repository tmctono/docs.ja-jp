---
title: CorDebugChainReason 列挙型
ms.date: 03/30/2017
api_name:
- CorDebugChainReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugChainReason
helpviewer_keywords:
- CorDebugChainReason enumeration [.NET Framework debugging]
ms.assetid: c915da51-50b2-41df-841a-2b971f4d0975
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cac790ebbf25ee3095db293ba90612be37fff9b9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609231"
---
# <a name="cordebugchainreason-enumeration"></a><span data-ttu-id="c75f0-102">CorDebugChainReason 列挙型</span><span class="sxs-lookup"><span data-stu-id="c75f0-102">CorDebugChainReason Enumeration</span></span>
<span data-ttu-id="c75f0-103">呼び出しチェーンが開始する理由を示します。</span><span class="sxs-lookup"><span data-stu-id="c75f0-103">Indicates the reason or reasons for the initiation of a call chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c75f0-104">構文</span><span class="sxs-lookup"><span data-stu-id="c75f0-104">Syntax</span></span>  
  
```  
typedef enum CorDebugChainReason {  
    CHAIN_NONE              = 0x000,  
    CHAIN_CLASS_INIT        = 0x001,  
    CHAIN_EXCEPTION_FILTER  = 0x002,  
    CHAIN_SECURITY          = 0x004,  
    CHAIN_CONTEXT_POLICY    = 0x008,  
    CHAIN_INTERCEPTION      = 0x010,  
    CHAIN_PROCESS_START     = 0x020,  
    CHAIN_THREAD_START      = 0x040,  
    CHAIN_ENTER_MANAGED     = 0x080,  
    CHAIN_ENTER_UNMANAGED   = 0x100,  
    CHAIN_DEBUGGER_EVAL     = 0x200,  
    CHAIN_CONTEXT_SWITCH    = 0x400,  
    CHAIN_FUNC_EVAL         = 0x800  
} CorDebugChainReason;  
```  
  
## <a name="members"></a><span data-ttu-id="c75f0-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="c75f0-105">Members</span></span>  
  
|<span data-ttu-id="c75f0-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="c75f0-106">Member</span></span>|<span data-ttu-id="c75f0-107">説明</span><span class="sxs-lookup"><span data-stu-id="c75f0-107">Description</span></span>|  
|------------|-----------------|  
|`CHAIN_NONE`|<span data-ttu-id="c75f0-108">呼び出しチェーンが開始されていません。</span><span class="sxs-lookup"><span data-stu-id="c75f0-108">No call chain has been initiated.</span></span>|  
|`CHAIN_CLASS_INIT`|<span data-ttu-id="c75f0-109">コンストラクターによって、チェーンが開始されました。</span><span class="sxs-lookup"><span data-stu-id="c75f0-109">The chain was initiated by a constructor.</span></span>|  
|`CHAIN_EXCEPTION_FILTER`|<span data-ttu-id="c75f0-110">例外フィルターによって、チェーンが開始されました。</span><span class="sxs-lookup"><span data-stu-id="c75f0-110">The chain was initiated by an exception filter.</span></span>|  
|`CHAIN_SECURITY`|<span data-ttu-id="c75f0-111">セキュリティを適用するコードによって、チェーンが開始されました。</span><span class="sxs-lookup"><span data-stu-id="c75f0-111">The chain was initiated by code that enforces security.</span></span>|  
|`CHAIN_CONTEXT_POLICY`|<span data-ttu-id="c75f0-112">コンテキスト ポリシーによって、チェーンが開始されました。</span><span class="sxs-lookup"><span data-stu-id="c75f0-112">The chain was initiated by a context policy.</span></span>|  
|`CHAIN_INTERCEPTION`|<span data-ttu-id="c75f0-113">使用しません。</span><span class="sxs-lookup"><span data-stu-id="c75f0-113">Not used.</span></span>|  
|`CHAIN_PROCESS_START`|<span data-ttu-id="c75f0-114">使用しません。</span><span class="sxs-lookup"><span data-stu-id="c75f0-114">Not used.</span></span>|  
|`CHAIN_THREAD_START`|<span data-ttu-id="c75f0-115">スレッド実行の開始によって、チェーンが開始されました。</span><span class="sxs-lookup"><span data-stu-id="c75f0-115">The chain was initiated by the start of a thread execution.</span></span>|  
|`CHAIN_ENTER_MANAGED`|<span data-ttu-id="c75f0-116">マネージド コードへのエントリによって、チェーンが開始されました。</span><span class="sxs-lookup"><span data-stu-id="c75f0-116">The chain was initiated by entry into managed code.</span></span>|  
|`CHAIN_ENTER_UNMANAGED`|<span data-ttu-id="c75f0-117">アンマネージ コードへのエントリによって、チェーンが開始されました。</span><span class="sxs-lookup"><span data-stu-id="c75f0-117">The chain was initiated by entry into unmanaged code.</span></span>|  
|`CHAIN_DEBUGGER_EVAL`|<span data-ttu-id="c75f0-118">使用しません。</span><span class="sxs-lookup"><span data-stu-id="c75f0-118">Not used.</span></span>|  
|`CHAIN_CONTEXT_SWITCH`|<span data-ttu-id="c75f0-119">使用しません。</span><span class="sxs-lookup"><span data-stu-id="c75f0-119">Not used.</span></span>|  
|`CHAIN_FUNC_EVAL`|<span data-ttu-id="c75f0-120">関数の評価によって、チェーンが開始されました。</span><span class="sxs-lookup"><span data-stu-id="c75f0-120">The chain was initiated by a function evaluation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c75f0-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="c75f0-121">Remarks</span></span>  
 <span data-ttu-id="c75f0-122">使用して、 [icordebugchain::getreason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md)メソッドを呼び出しチェーンが開始する理由を確認します。</span><span class="sxs-lookup"><span data-stu-id="c75f0-122">Use the [ICorDebugChain::GetReason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md) method to ascertain the reasons for the initiation of a call chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c75f0-123">必要条件</span><span class="sxs-lookup"><span data-stu-id="c75f0-123">Requirements</span></span>  
 <span data-ttu-id="c75f0-124">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c75f0-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c75f0-125">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c75f0-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c75f0-126">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c75f0-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c75f0-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c75f0-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c75f0-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="c75f0-128">See also</span></span>

- [<span data-ttu-id="c75f0-129">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="c75f0-129">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
