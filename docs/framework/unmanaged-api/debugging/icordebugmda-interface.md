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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cea8f6827d3e361b3f6498e6612d8b11a2357285
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59098670"
---
# <a name="icordebugmda-interface"></a><span data-ttu-id="c8893-102">ICorDebugMDA インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c8893-102">ICorDebugMDA Interface</span></span>
<span data-ttu-id="c8893-103">マネージド デバッグ アシスタント (MDA) メッセージを表します。</span><span class="sxs-lookup"><span data-stu-id="c8893-103">Represents a managed debugging assistant (MDA) message.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c8893-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="c8893-104">Methods</span></span>  
  
|<span data-ttu-id="c8893-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="c8893-105">Method</span></span>|<span data-ttu-id="c8893-106">説明</span><span class="sxs-lookup"><span data-stu-id="c8893-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c8893-107">GetDescription メソッド</span><span class="sxs-lookup"><span data-stu-id="c8893-107">GetDescription Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getdescription-method.md)|<span data-ttu-id="c8893-108">この MDA の説明を含む文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="c8893-108">Gets a string containing a description of this MDA.</span></span>|  
|[<span data-ttu-id="c8893-109">GetFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="c8893-109">GetFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getflags-method.md)|<span data-ttu-id="c8893-110">この MDA に関連付けられているフラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="c8893-110">Gets the flags associated with this MDA.</span></span>|  
|[<span data-ttu-id="c8893-111">GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="c8893-111">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getname-method.md)|<span data-ttu-id="c8893-112">この MDA の名前を含む文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="c8893-112">Gets a string containing the name of this MDA.</span></span>|  
|[<span data-ttu-id="c8893-113">GetOSThreadId メソッド</span><span class="sxs-lookup"><span data-stu-id="c8893-113">GetOSThreadId Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getosthreadid-method.md)|<span data-ttu-id="c8893-114">この MDA を実行するオペレーティング システムのスレッド識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="c8893-114">Gets the operating system thread identifier upon which this MDA is executing.</span></span>|  
|[<span data-ttu-id="c8893-115">GetXML メソッド</span><span class="sxs-lookup"><span data-stu-id="c8893-115">GetXML Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getxml-method.md)|<span data-ttu-id="c8893-116">この MDA に関連付けられている完全な XML ストリームを取得します。</span><span class="sxs-lookup"><span data-stu-id="c8893-116">Gets the full XML stream associated with this MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8893-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="c8893-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8893-118">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c8893-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8893-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="c8893-119">Requirements</span></span>  
 <span data-ttu-id="c8893-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8893-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8893-121">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8893-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8893-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8893-122">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c8893-123">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="c8893-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c8893-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8893-124">See also</span></span>

- [<span data-ttu-id="c8893-125">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="c8893-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="c8893-126">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="c8893-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
