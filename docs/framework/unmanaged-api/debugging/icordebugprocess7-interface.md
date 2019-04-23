---
title: ICorDebugProcess7 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugProcess7
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 71aee5f3-5e10-44fa-be69-6d8a475f2c14
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f0d73da04242bfe5a4958a62d2a48b609b474309
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59195411"
---
# <a name="icordebugprocess7-interface"></a><span data-ttu-id="15770-102">ICorDebugProcess7 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="15770-102">ICorDebugProcess7 Interface</span></span>
<span data-ttu-id="15770-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="15770-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="15770-104">ターゲット プロセスでメモリ内のメタデータ更新を処理するようにデバッガーを構成するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="15770-104">Provides a method that configures the debugger to handle in-memory metadata updates in the target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="15770-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="15770-105">Methods</span></span>  
  
|<span data-ttu-id="15770-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="15770-106">Method</span></span>|<span data-ttu-id="15770-107">説明</span><span class="sxs-lookup"><span data-stu-id="15770-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="15770-108">SetWriteableMetadataUpdateMode メソッド</span><span class="sxs-lookup"><span data-stu-id="15770-108">SetWriteableMetadataUpdateMode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md)|<span data-ttu-id="15770-109">デバッガーがメモリ内のメタデータ更新をターゲット プロセスでどのように処理するかを決定する値を設定します。</span><span class="sxs-lookup"><span data-stu-id="15770-109">Sets a value that determines how the debugger handles in-memory updates to metadata within the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15770-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="15770-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15770-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="15770-111">Requirements</span></span>  
 <span data-ttu-id="15770-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="15770-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15770-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15770-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="15770-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15770-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15770-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15770-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15770-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="15770-116">See also</span></span>

- [<span data-ttu-id="15770-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="15770-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="15770-118">デバッグ</span><span class="sxs-lookup"><span data-stu-id="15770-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
