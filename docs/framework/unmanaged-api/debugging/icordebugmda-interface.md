---
title: ICorDebugMDA インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugMDA
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA
helpviewer_keywords:
- ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 8ecbb854-295c-4dd4-b9fc-01ebeac46e06
topic_type:
- apiref
ms.openlocfilehash: d711f36b4e2071dac9458a023e1d3cf4743e77b3
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212634"
---
# <a name="icordebugmda-interface"></a><span data-ttu-id="d76c7-102">ICorDebugMDA インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d76c7-102">ICorDebugMDA Interface</span></span>
<span data-ttu-id="d76c7-103">マネージド デバッグ アシスタント (MDA) メッセージを表します。</span><span class="sxs-lookup"><span data-stu-id="d76c7-103">Represents a managed debugging assistant (MDA) message.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d76c7-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="d76c7-104">Methods</span></span>  
  
|<span data-ttu-id="d76c7-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="d76c7-105">Method</span></span>|<span data-ttu-id="d76c7-106">説明</span><span class="sxs-lookup"><span data-stu-id="d76c7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d76c7-107">GetDescription メソッド</span><span class="sxs-lookup"><span data-stu-id="d76c7-107">GetDescription Method</span></span>](icordebugmda-getdescription-method.md)|<span data-ttu-id="d76c7-108">この MDA の説明を格納している文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="d76c7-108">Gets a string containing a description of this MDA.</span></span>|  
|[<span data-ttu-id="d76c7-109">GetFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="d76c7-109">GetFlags Method</span></span>](icordebugmda-getflags-method.md)|<span data-ttu-id="d76c7-110">この MDA に関連付けられているフラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="d76c7-110">Gets the flags associated with this MDA.</span></span>|  
|[<span data-ttu-id="d76c7-111">GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="d76c7-111">GetName Method</span></span>](icordebugmda-getname-method.md)|<span data-ttu-id="d76c7-112">この MDA の名前を格納している文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="d76c7-112">Gets a string containing the name of this MDA.</span></span>|  
|[<span data-ttu-id="d76c7-113">GetOSThreadId メソッド</span><span class="sxs-lookup"><span data-stu-id="d76c7-113">GetOSThreadId Method</span></span>](icordebugmda-getosthreadid-method.md)|<span data-ttu-id="d76c7-114">この MDA が実行されているオペレーティングシステムのスレッド id を取得します。</span><span class="sxs-lookup"><span data-stu-id="d76c7-114">Gets the operating system thread identifier upon which this MDA is executing.</span></span>|  
|[<span data-ttu-id="d76c7-115">GetXML メソッド</span><span class="sxs-lookup"><span data-stu-id="d76c7-115">GetXML Method</span></span>](icordebugmda-getxml-method.md)|<span data-ttu-id="d76c7-116">この MDA に関連付けられている XML の完全ストリームを取得します。</span><span class="sxs-lookup"><span data-stu-id="d76c7-116">Gets the full XML stream associated with this MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d76c7-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="d76c7-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d76c7-118">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d76c7-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d76c7-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="d76c7-119">Requirements</span></span>  
 <span data-ttu-id="d76c7-120">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d76c7-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d76c7-121">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d76c7-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d76c7-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d76c7-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d76c7-123">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d76c7-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d76c7-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="d76c7-124">See also</span></span>

- [<span data-ttu-id="d76c7-125">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="d76c7-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="d76c7-126">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="d76c7-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
