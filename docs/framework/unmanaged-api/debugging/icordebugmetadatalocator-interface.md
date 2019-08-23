---
title: ICorDebugMetaDataLocator インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugMetaDataLocator
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMetaDataLocator
helpviewer_keywords:
- ICorDebugMetaDataLocator interface [.NET Framework debugging]
ms.assetid: 287f5ecd-863f-4090-a615-077859f0257b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64cf11ec294486fdc14d424e731eac8e4745d892
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939866"
---
# <a name="icordebugmetadatalocator-interface"></a><span data-ttu-id="16206-102">ICorDebugMetaDataLocator インターフェイス</span><span class="sxs-lookup"><span data-stu-id="16206-102">ICorDebugMetaDataLocator Interface</span></span>
<span data-ttu-id="16206-103">デバッガーにメタデータ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="16206-103">Provides metadata information to the debugger.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="16206-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="16206-104">Methods</span></span>  
  
|<span data-ttu-id="16206-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="16206-105">Method</span></span>|<span data-ttu-id="16206-106">説明</span><span class="sxs-lookup"><span data-stu-id="16206-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="16206-107">GetMetadata メソッド</span><span class="sxs-lookup"><span data-stu-id="16206-107">GetMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmetadatalocator-getmetadata-method.md)|<span data-ttu-id="16206-108">デバッガーが要求した操作を完了するために必要となるメタデータが含まれているモジュールの完全パスを返すように、デバッガーに求めます。</span><span class="sxs-lookup"><span data-stu-id="16206-108">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16206-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="16206-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="16206-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="16206-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16206-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="16206-111">Requirements</span></span>  
 <span data-ttu-id="16206-112">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="16206-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16206-113">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="16206-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="16206-114">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="16206-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16206-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16206-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16206-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="16206-116">See also</span></span>

- [<span data-ttu-id="16206-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="16206-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="16206-118">デバッグ</span><span class="sxs-lookup"><span data-stu-id="16206-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
